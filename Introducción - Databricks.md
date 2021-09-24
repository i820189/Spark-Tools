
## Pequeña Comparación

Azure:
- Databricks (no es el mismo que se utiliza en AWS o GCP o como el Comunnity es mas robusto)
- Utiliza repositorios como BlobStorage o FileStorage
- Ofrece servicio de Encriptación para temas de seguridad de datos en los envíos.
- Se suele trabajar tdos en un mismo entorno, sin descargar nada de manera local (DE y DS y DA)
- Se integra con facilidad a diferentes STORAGES ya que no es su fuerte de Databricks almacenar.

Amazon
- EMR (Elastic Map Reduce)
- Utilizamiento como S3 o Redshift

GCP
- Dataprop
- Utiliza almacenamiento como Cloud Storage



--------------

## Terminología dentro de Databricks:
- Notebook : es como un jupyter del mismo databricks
- Cluster : recursos computacionales, cada notebook debe estar conectado a un cluster.
- Jobs : Es la forma de ejecutar un notebook de forma  programada, utilizado para automatizar procesos de DE, DS o DA
- Libraries : Son paquetes o modulos que permiten extender las funcionalidades de spark o python etc..
- Data :    Se usa tablas SQl para la data estructurada, las tbalas pueden ser usadas en S3 o BlobStorage   
- Experiments : Son experimentos de Machine Learning que pueden ser ejecutados en el Workspace


--------
## Recursos Spark:
- Spark The Definitive Guide
- Learning Spark Edition 2
- Databricks pagina

--------

## Databricks
- Crear un Notebook
- Crear un Cluster
  - Runtime 7.5 (Scala 2.12, Spark 3.01)
  - 1 Driver: 15 GB Memory, 2 cores, 1DBU
  - 0 Workers: 0.0 GB memory, 0 Core, 0 DBU
  - Servidores mas barato son de EEUU, europa o asia es mas caro.
  - Libraries : podemos instalar librerías de manera rápida y cargarlo.
  - Event Log : puede haber un seguimiento de Log amigable
  - Spark UI : es algo que se hereda, es de Spache Spark nativo, se monitorea aquí SPARK ya no el cluster.
  - Driver Logs : Log del Driver ya no del cluster, cuando se ejecuta spark o python en spark, se debe traducir , eso lo realiza los:
    - Del Executor
    - Del Worker
  - Apps, puedo instalar rstudioserver en caso mi equipo trabaje con ello
  - Spark Cluster UI - Master

## Spark Jobs Databricks
- economico para ejecutar procesos cortos
- ejecuta y el cluster se destruye
- hay manera de gestionar los recursos de cluster para ejecución, como FIFO o FEIR , esta configuración se realiza ya en el cluster
- Se puede programar mediante el API Scheduler, se puede atar jobs en secuencia. (https://docs.databricks.com/dev-tools/api/latest/jobs.html) no necesariamente es el modo visual del databricks.