Propuesta de Solución para la Organización y Aprovechamiento de la Información
Actualmente, la empresa maneja datos de distintas fuentes y en diferentes formatos, lo que dificulta tener una visión unificada y confiable para la toma de decisiones. Para resolver este reto, proponemos implementar una arquitectura de datos organizada en etapas (modelo medallón) dentro de Microsoft Fabric, la cual permitirá ordenar, limpiar y transformar la información de manera progresiva hasta llegar a un nivel óptimo para el análisis.

El proceso funcionará de la siguiente manera:

Almacenamiento inicial (Bronce): Aquí se guardarán los datos tal como llegan de las fuentes, sin modificaciones. Esto asegura que la empresa siempre tenga disponible una copia íntegra y segura de la información original.
Transformación y depuración (Plata): En esta etapa los datos se limpian, corrigen y estandarizan. El objetivo es eliminar inconsistencias y dejar la información lista para que sea entendida y utilizada de forma confiable por la organización.
Información lista para análisis (Oro): Finalmente, los datos ya organizados se trasladan a un almacén de datos (Warehouse), un espacio diseñado especialmente para que los equipos de negocio puedan acceder fácilmente a la información, generar reportes claros y confiables, y aplicar distintos niveles de seguridad y control de acceso según los roles de los usuarios.
Para acompañar este proceso, se establecerán dos áreas de trabajo:

Una dedicada a la gestión y procesamiento de los datos.
Otra enfocada en la publicación de informes y tableros para las distintas áreas del negocio.
Beneficios para la empresa:
Contar con información confiable y actualizada para la toma de decisiones.
Reducir el tiempo de preparación de reportes, permitiendo a los equipos enfocarse en el análisis y no en la recopilación de datos.
Garantizar seguridad y control de accesos, de modo que cada persona vea solo lo que le corresponde.
Escalabilidad: la solución crecerá junto con el negocio, soportando nuevos volúmenes de datos y fuentes de información en el futuro.
