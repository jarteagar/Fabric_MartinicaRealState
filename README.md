# Fabric_MartinicaRealState
Proyecto de Solución con SAAS MS Fabric

# Proyecto: Real Estate Analytics en Microsoft Fabric

## Objetivo
Construir una plataforma data-driven en Microsoft Fabric para integrar datos de ventas, marketing, valorizaciones, leads y portales inmobiliarios, con el fin de habilitar analítica de:
- Precios
- Rotación de inventario
- Performance de campañas

## Arquitectura
- Ingesta: Pipelines (Data Factory) desde ADLS
- Almacenamiento: Lakehouse en OneLake (Bronze-Silver-Gold)
- Transformación: Notebooks PySpark
- Modelo semántico: Warehouse + Semantic Model
- Visualización: Power BI App ("Real Estate Command Center")
- Observabilidad: Alerts en Fabric Capacity Metrics App

## Contenido del repositorio
- `/docs`: Documentación del proyecto (requerimientos, diagramas de arquitectura)
- `/notebooks`: Notebooks PySpark de transformación
- `/sql`: Scripts SQL para el Warehouse
- `/pipelines`: Definiciones de pipelines de Fabric
- `/powerbi`: Reportes y dashboards (opcional)

## Procesamiento
- Batch diario: 00:30 a.m.

## 👥 Contacto
Autor: [Tu nombre]  
