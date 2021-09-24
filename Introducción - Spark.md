## Objetivos:
- Entender qué es Apache Spark y el funcionamiento
- Comprender la arquitectura de Spark
- ¿Cómo funciona Spark en AWS, Google Cloud y Azure?
- Conocer Databricks

## ¿Qué es Apache Spark?
Es un motor computacional unificado y un conjunto de librerías para el **procesamiento de data en paralelo**. Spark es uno de los proyectos de open source más activos en el mundo. Spark soporta múltiples lenguajes de programación como Python, Java, Scala o R. Posee librerías para diversas tareas como SQL, Streaming y Machine Learning. Puedes ejecutarlo desde en una laptop a miles de servidores. Esto hace que el escalamiento sea simple. [Spark The Definitive Guide, Ch 1]

![Menu](https://image.slidesharecdn.com/24hopazuredatabricksiseasierthanyouthinkv2-190911002741/95/azure-databricks-is-easier-than-you-think-6-638.jpg)

## Disgreguemos el concepto de Apache Spark
#### **UNIFICADO**
Spark está diseñado para **soportar un gran rango de tareas** de data analytics como por ejemplo una carga de información, ejecución de querys en SQL, algoritmos de Machine Learning y flujos en Streaming. Por jemplo si cargamos data usando una query SQL y luego evaluamos un modelo de Machine Learning sobre ese dataset usando las librerías de Spark, **el engine puede combinar esos pasos para que no se tenga escanear dos veces la data**. 
No es necesario estar generando un output y volviendo a leer en otro lado, etc ...

#### **MOTOR COMPUTACIONAL**
**Spark se centra en el procesamiento**, tomando data de cloud storage systems como Google Cloud Storage, Azure Storage o Amazon S3, además de otros tipos de storage como Apache Hadoop, MySQL o Apache Kafka. Esto significa que **Spark no almacena data**. Es decir existe una separación entre el procesamiento y almacenamiento caso contrario a lo que suscedía con Apache Hadoop (ofrecía Haddop + HDFS obligatoriamente).

#### **LIBRERIAS**
Busca proveer una API unificada para tareas comunes de análisis. Las librerías permiten agregar a Spark nuevas funcionalidades. Por ejemplo librerías para SQL y data estructurada SparkSQL, Machine Learning (MLlib y SparkML), stream processing (Structured Streaming) y análisis de gráfos con GraphX. Además existen muchas más librerías que puedes ver en https://spark-packages.org/ ¿Cuántos paquetes tiene disponible hoy Spark? ¿Cuál es la categoría más popular?

![Menu](./assets/Screenshot_3.png)


## Brieft Apache Spark History
Apache Spark empezo en el 2009 en UC Berkeley con un paper(ttps://www.usenix.org/legacy/event/hotcloud10/tech/full_papers/Zaharia.pdf) publicado como parte del Spark research project. En esa epoca Hadoop como MapReduce era el motor dominante. En el 2011 desarrollaron Shark que permitio a Spark ejecutar SQL. En el 2013 paso a ser un proyecto parte de la Apache Software Foundation. Parte del equipo de AMPlab fundo Databricks para darle mayor soporte al proyecto.

Apache Spark 1.0 salio en el 2014, Apache Spark 2.0 en 2016 y Apache 3.0 en 2020.

## Spark's Architecture
Un cluster o grupo de computadoras, agrupa los recursos como RAM y CPUs permitiendonos una mayor capacidad. Para que podamos sacarle el mayor provecho las maquinas agrupadas no son sufiente, necesitan un framework para coordinar el trabajo. Spark hace eso, administra y coordina la ejecucion de las tareas sobre la data para todo el cluster

Las maquinas que Spark usa para ejecutar las tareas son administradas por un cluster manager como: Spark's standalone cluster manager, YARN, Mesos o Kubernetes. Nosotros luego enviamos un Spark Application a cualquiera de esos cluster managers, los cuales nos asignaran recursos para nuestra aplicacion y asi puedan hacer su trabajo.

## Spark Applications
Un Spark Application consiste de un driver process y un conjunto de executor processes

El proceso driver es responsable de tres actividades:
- Mantener la infomacion de acerca del Spark Application
- Responder al programa del usuario o input
- Analizar y distribuir, y programar el trabajo a los executors

El Driver Process es el corazon de un Apache Spark Application y mantiene la informacion relevante durante la vida de la aplicacion.

Los Executor Process son responsables de ejecutar el codigo asignado por el Driver y reportar el estado de su ejecucion al driver.

Considerar que pueden haber varios Spark Application ejecutandose en un cluster y siendo administrados por un Cluster Manager.

Las APIs de Spark hacen posible correr Spark usando varios lenguajes de programación. Este código es traducido en 'código' Spark que se ejecuta en el cluster.

Spark soporta varios lenguajes de programación como: Scala (lenguaje por dejecto), Java, Python, SQL y R.

## ¿Por qué Scala?
