# Proy_SDGr18_JulianDuque
Proyecto que toma datos de órdenes de trabajo de suspensión y de reconexiones  de servicios públicos, y genera datos para evaluar el comportamiento de estos.

Se requiere contar con información consolidada y analítica sobre el comportamiento de las suspensiones y reconexiones del servicio, que permita realizar seguimiento a la cantidad de actividades ejecutadas y a los tiempos transcurridos en su atención, identificando variaciones por período, ciclo y estrato. Esta información busca facilitar el monitoreo de la operación, detectar comportamientos atípicos o posibles demoras en los procesos de suspensión y reconexión, y disponer de elementos objetivos para apoyar la toma de decisiones y el mejoramiento de la gestión operativa.

Para este propósito se desarrolla un proceso de ETL que toma los datos de 2 archivos CSV con las órdenes de trabajo de Suspensiones y Reconexiones de lo que va corrido del año, apoyandonos para el proceso en la estructura bajo el modelo Medallion:

cat_ejec_dbricks: con 3 esquemas: "bronze", "silver" y "golden"

En el esquema "bronza" se carga el contenido de los archicos cada uno en su tabla: "suspensiones" y "reinstalaciones"

Se realiza la transformación y unión de los datos, que son cardados en el esquema "silver", en la tabla "suspen_reinsta" y finalmente se generando los totales que se espera entreguen la información requerida en "golden", en la tabla "suspen_Reinsta_resultados"