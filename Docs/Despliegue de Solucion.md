Despliegue de la Solución
Consideraciones:

Para identificar los diferentes artefactos de utilizarán los prefijos

brz_ : Objetos relativos a la capa “Bronze” (Bronce)
slv_ : Objetos relativos a la capa “Silver” (Plata)
gld_ : Objetos relativos a la capa “Gold” (Oro)
Desarrollo de la Propuesta
Se habilitarán dos(2) áreas de trabajo principales: una para la gestión de datos y otra para la reportería. Debido al volumen de datos no será necesario la habilitación de un nuevo Environment.

1. WSP_MartinicaRealState (Área de Datos)
Este espacio concentrará la información bajo la arquitectura medallón, organizada en tres capas

Data_brz (Bronze): contendrá los datos en crudo, sin transformaciones.
Data_slv (Silver): almacenará los datos semitransformados. En esta capa se mantendrá el historial de las entidades.
Data_gld (Gold): incluirá los datos depurados y con nomenclatura amigable, listos para ser utilizados por los analistas.
2. WSP_MartinicaRealState_Reports (Área de Reportería)
En este espacio se organizarán carpetas por cada unidad de negocio, donde se publicarán y gestionarán los reportes correspondientes.

Dentro del área de datos (WSP_MartinicaRealState) cada nivel tendrá organizado los diferentes artefactos necesarios para el procesamiento de datos de la siguiente manera:

data: Aqui estará el repositorio de datos. LAKEHOUSE/WAREHOUSE/EVENTHOUSE
notebooks: Aquí estarán los scripts (ETL, código pyspark, sparksql) con la lógica de proceso.
pipelines: Aquí estarán los orquestadores de las diferentes actividades. Su finalidad es sincronizar el procesamiento de los datos para llevarlos al área de data respectiva.
