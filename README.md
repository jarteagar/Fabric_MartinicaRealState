-- Canales | Grano: CODMES + FECDIA + CODCLAVEPARTYCLI + CANAL + PASO | Diaria | UC13
-- Eventos reutilizables del recorrido digital de credito: 1 Arribos, 3 Inicio de flujo, 4 Simulacion, 6 Venta.
-- El armado del funnel (paso 2, rangos, digitalidad, pilotos, liquidez) se hace en la solucion (_SOLUCION).
-- Validar redundancia con DP "Gestion de canales alternativos" / "Modelo Transaccion-Canal".
/*
CREATE OR REPLACE TABLE catalog_lhcl_prod_bcp_expl.bcp_edv_tmedpag_001.fct_credito_evento_digital
CLUSTER BY (codmes, paso)
COMMENT 'DP Credito Personas - Eventos digitales del recorrido de credito'
AS*/
WITH param AS (  
-- [DE] parametros vigentes: CODMES maximo <= mes actual
  SELECT codgrupoparametro, codparametro, desvalorparametro1, desvalorparametro2,
         COALESCE(CAST(numvalorparametro1 AS DECIMAL(18,4)), TRY_CAST(desvalorparametro1 AS DECIMAL(18,4))) AS num1
  FROM 
-- catalog_lhcl_prod_bcp.bcp_rdv_de_lkde_v.de_parametrocreditopersonas
catalog_lhcl_prod_bcp.BCP_DDV_PMI_DPACTIVOSPERSONAS.DE_PARAMETROGENERALACTIVOPERSONAPMI
  WHERE codmes = (SELECT MAX(codmes) FROM 
-- catalog_lhcl_prod_bcp.bcp_rdv_de_lkde_v.de_parametrocreditopersonas
catalog_lhcl_prod_bcp.BCP_DDV_PMI_DPACTIVOSPERSONAS.DE_PARAMETROGENERALACTIVOPERSONAPMI
 WHERE codmes <= DATE_FORMAT(CURRENT_DATE(), 'yyyyMM'))
),
plist AS (  
-- [DE] listas de DESVALORPARAMETRO1 separadas por coma
  SELECT codparametro, TRIM(v) AS valor
  FROM param LATERAL VIEW EXPLODE(SPLIT(desvalorparametro1, ',')) t AS v
),
cat AS (  
-- [DE] catalogo: CODCATALOGO + CODCONCEPTONEG -> DESCONCEPTONEG
  SELECT TRIM(codcatalogo) AS codcatalogo, TRIM(codconceptoneg) AS cod, TRIM(desconceptoneg) AS des
  FROM 
 -- catalog_lhcl_prod_bcp.bcp_rdv_de_lkde_v.de_catalogocreditopersonas
catalog_lhcl_prod_bcp.BCP_DDV_PMI_DPACTIVOSPERSONAS.DE_CATALOGODESCRIPTIVAACTIVOPERSONAPMI
),
params AS (
  SELECT CAST(ADD_MONTHS(TRUNC(CURRENT_DATE(), 'MM'),
         -CAST((SELECT num1 FROM param WHERE codparametro = 'VENTANA_EVDIG') AS INT)) AS DATE) AS fecha_inicio   -- [DE] VENTANA_EVDIG
),
prod_funnel AS (  -- [DE] PROD_FUNNEL (reemplaza dim_producto_credito.flg_funnel_digital)
  SELECT TRIM(c) AS codproducto
  FROM param LATERAL VIEW EXPLODE(SPLIT(desvalorparametro1, ',')) t AS c
  WHERE codparametro = 'PROD_FUNNEL'
),
arribos AS (
  SELECT DATE_FORMAT(fecinteraccion, 'yyyyMM') AS codmes,                             MIN(CAST(fecinteraccion AS DATE)) AS fecdia,
         'bmo' AS canal, '1. Arribos' AS paso, codclavepartycli
  FROM catalog_lhcl_prod_bcp.bcp_udv_int_v.h_interaccionbancamovil
  WHERE fecinteraccion >= (SELECT fecha_inicio FROM params)
    AND CAST(tipinteraccion AS STRING) = (SELECT CAST(CAST(num1 AS INT) AS STRING) FROM param WHERE codparametro = 'EVD_TIPINTER')   -- [DE] EVD_TIPINTER
  GROUP BY DATE_FORMAT(fecinteraccion, 'yyyyMM'), codclavepartycli
  UNION ALL
  SELECT DATE_FORMAT(fecvisitanavegaciondigital, 'yyyyMM') AS codmes, MIN(CAST(fecvisitanavegaciondigital AS DATE)) AS fecdia,
         'web' AS canal, '1. Arribos' AS paso, codclavepartycli
  FROM catalog_lhcl_prod_bcp.bcp_udv_int_v.h_hitnavegaciondigital
  WHERE fecdia >= (SELECT fecha_inicio FROM params)
    AND desrutaurl IN (SELECT valor FROM plist WHERE codparametro = 'EVD_RUTAARRIBO')   -- [DE] EVD_RUTAARRIBO
    AND codinternocomputacional IS NOT NULL
  GROUP BY DATE_FORMAT(fecvisitanavegaciondigital, 'yyyyMM'), codclavepartycli
),
pasos AS (
  SELECT DATE_FORMAT(fecdia, 'yyyyMM') AS codmes, CAST(fecdia AS DATE) AS fecdia, canal, paso, codclavepartycli
  FROM (
    SELECT n.fecdia, n.codclavepartycli,
           COALESCE(cn.des, n.descanal) AS canal,   -- [DE] CANNAVEG
           pf.des AS paso                            -- [DE] PASOFUNNEL
    FROM catalog_lhcl_prod_bcp.bcp_ddv_crm_navegaciondigital_v.hd_visitapaginahitnavegaciondigital n
    INNER JOIN cat pf   -- [DE] PASOFUNNEL: solo rutas del catalogo
      ON pf.codcatalogo = 'PASOFUNNEL' AND pf.cod = n.desrutaurl
    LEFT JOIN cat cn    -- [DE] CANNAVEG
      ON cn.codcatalogo = 'CANNAVEG' AND cn.cod = n.descanal
    WHERE n.fecdia >= (SELECT fecha_inicio FROM params)
      AND n.codinternocomputacional IS NOT NULL
  ) x
  GROUP BY DATE_FORMAT(fecdia, 'yyyyMM'), CAST(fecdia AS DATE), canal, paso, codclavepartycli
),
ventas AS (
  SELECT o.codmes_desembolso AS codmes, o.fecha_desembolso AS fecdia, d.canal_funnel AS canal, '6. Venta' AS paso, o.codclavepartycli
  FROM catalog_lhcl_prod_bcp.bcp_edv_tmedpag_001.fct_credito_desembolso o
  INNER JOIN catalog_lhcl_prod_bcp.bcp_edv_tmedpag_001.dim_credito d
    ON o.codclavecta = d.codclavecta
  INNER JOIN prod_funnel p   -- [DE] reemplaza dim_producto_credito
    ON o.codproducto = p.codproducto
  WHERE o.fecha_desembolso >= (SELECT fecha_inicio FROM params)
    AND d.canal_funnel IN (SELECT valor FROM plist WHERE codparametro = 'EVD_CANALES')   -- [DE] EVD_CANALES
  GROUP BY o.codmes_desembolso, o.fecha_desembolso, d.canal_funnel, o.codclavepartycli
),
eventos AS (
  SELECT * FROM arribos
  UNION ALL SELECT * FROM pasos
  UNION ALL SELECT * FROM ventas
),
con_lead AS (
  SELECT DISTINCT codmescampania AS codmes, codclavepartycli
  FROM catalog_lhcl_prod_bcp.bcp_edv_tmedpag_001.fct_credito_lead
  WHERE flg_lead_priorizado = 1
)
SELECT e.codmes, e.fecdia, e.canal, e.paso, e.codclavepartycli,
       CASE WHEN l.codclavepartycli IS NOT NULL THEN 1 ELSE 0 END AS flg_con_lead,
       CASE WHEN ar.codclavepartycli IS NOT NULL AND l.codclavepartycli IS NOT NULL
            THEN '1. Reactivo' ELSE '2. Proactivo' END AS tipo_arribo_fisico,
       CURRENT_TIMESTAMP() AS fecactualizacionregistro
FROM eventos e
LEFT JOIN con_lead l
  ON e.codmes = l.codmes AND e.codclavepartycli = l.codclavepartycli
LEFT JOIN (SELECT DISTINCT codmes, fecdia, codclavepartycli FROM arribos) ar
  ON e.codmes = ar.codmes AND e.codclavepartycli = ar.codclavepartycli AND e.fecdia = ar.fecdia;
