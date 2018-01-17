
## Introducción al Big Data
**Diego Sepúlveda**
Note:
https://gitpitch.com/dsepulve/big-data-presentation/style


---

## Motivación

El término de Big Data en general, se usa para las estrategias y tecnologías no tradicionales necesarias para recopilar, organizar, procesar y recopilar información de grandes volúmenes de datos. Si bien el problema de trabajar con datos que exceden la capacidad de computación o el almacenamiento de una sola máquina no es nuevo, la penetración, la escala y el valor de este tipo de informática se han expandido enormemente en los últimos años.

---

## ¿Qué es el Big Data?
Formalmente no hay una definición de Big Data que pueda describir con exactitud todo lo que engloba, pero si podemos mencionar ciertas característias que son comunes en un sistema de Big Data que podrían ayudar a definirlo:

_"El Big Data significa que un conjunto de datos es muy grande para procesarse o almacenarse razonablemente con herramientas tradicionales o en una sola máquina."_

---

## ¿Cómo podemos identificar un sistema de Big Data?

En 2001, Doug Laney de Gartner presentó lo que se conoce como las _"tres V de Big Data"_ para describir algunas características que hacen que los sistemas de big data sean diferentes de otros procesos de datos.
 - **Volumen**
 - **Velocidad**
 - **Variedad**

---

## Volumen
Estos conjuntos de datos pueden estar en órdenes de magnitud mayores que los conjuntos de datos tradicionales, lo que exige más reflexión en cada etapa del ciclo de vida de procesamiento y almacenamiento.
A menudo, debido a que los requisitos de trabajo superan las capacidades de una sola máquina, esto se convierte en un desafío para agrupar, asignar y coordinar recursos de grupos de máquinas. La gestión de clusters y los algoritmos capaces de dividir las tareas en piezas más pequeñas cobran cada vez más importancia.

---

## Velocidad
A menudo, se espera que los datos sean procesados ​​en tiempo real para obtener información del sistema. En este enfoque la retroalimentación es casi instantánea. Los datos se analizan constantemente para mantenerse al día con la afluencia de nueva información y dar resultados valiosos desde el principio. Estas estrategias requieren sistemas robustos con componentes altamente disponibles para protegerse contra fallas a lo largo de la cadena de datos.

---

## Variedad
Los datos pueden ser subministrados desde diversas fuentes, tanto internos o externos. El Big Data busca manejar datos **potencialmente útiles** independiente de dónde provengan al consolidar. Mientras los sistemas más tradicionales suelen esperar que los datos ingresen formateados y organizados, el Big Data **usualmente** almacena datos más cercanos a su estado original. Idealmente, cualquier transformación o cambio en los datos brutos ocurrirá en la memoria en el momento del procesamiento.

---
## Otras características

Además de las tres _V originales_, se han descrito algunas cualidades adiciones:

- **Veracidad**: la variedad de fuentes y la complejidad del procesamiento pueden generar desafíos para evaluar la validéz de los datos.
- **Variabilidad**: es posible que se necesiten recursos adicionales para identificar, procesar o filtrar datos de baja calidad.
- **Valor**: los sistemas establecidos son pueden ser complejos como para que el uso de los datos y la extracción del valor real se vuelvan difíciles.

---

## ¿Cómo se vería un ciclo de vida en Big Data?
Las categorías generales para el procesamiento de Big Data son:
 1. Ingesta de datos en el sistema
 2. Persistencia de datos
 3. Análisis
 4. Visualización de resultados 

---
## Clustered Computing (1/2)

Para poder cumplir con los requerimientos y exigencias, es posible que una sola máquina no sea capáz de cumplir con la demanda, es por ello que las herramientas usadas para el tratamiento de datos estan pensadas para el uso distribuido de los recursos.

---

## Clustered Computing (2/2)
Algunos conceptos que debemos tener presentes son:

- **Distrubución de recursos**: la combinación de almacenamiento, CPU y memoria es extremadamente importante. Procesar grandes conjuntos de datos requiere grandes cantidades de recursos.
- **Alta disponibilidad**: los clusters proporcionan niveles de tolerancia a errores y garantías de disponibilidad para evitar que las fallas de hardware o software.
- **Escalabilidad**: los clusters facilitan la escalabilidad horizontal al agregar máquinas adicionales al grupo.

---
## Ingesta de datos

La ingesta es tomar datos sin procesar y agregarlos al sistema. La complejidad depende del formato y la calidad de las fuentes de datos.
Tecnologías como **Apache Sqoop** pueden tomar RDB y agregarlos a un sistema de big data. Del mismo modo, **Apache Flume** y **Apache Chukwa** son para agregar e importar Logs de aplicaciones y servidores. Los sistemas MQ como **Apache Kafka** también se pueden usar como una interfaz entre varios generadores de datos y un sistema de big data.

---

## Persistencia de datos

La ingestión entrega los datos a los componentes de almacenamiento. Luce simple pero el volumen entrante, la disponibilidad y la capa de computación distribuida hacen que sea necesario contar con sistemas de almacenamiento más complejos.
Esto implica un sistema de archivos distribuidos. Soluciones como el sistema de archivos HDFS de **Apache Hadoop** permiten que se guarden grandes cantidades de datos en el cluster. 

---

## Análisis de Datos (1/2)
La capa de cálculo es quizás la parte más diversa del sistema, ya que los requisitos y el enfoque pueden variar significativamente según el tipo de conocimiento que se desee. Es comun procesar los datos de manera repetida, ya sea iterativamente con una sola herramienta o con varias para mostrar diferentes tipos de información. El **procesamiento por lotes** (batch) implica realizar procesos conocidos como división, mapeo, mezcla, reducción y ensamblaje.

---

## Análisis de Datos (2/2)

El procesamiento en tiempo real (online) exige que la información se procese y prepare inmediatamente. Además requiere que el sistema reaccione a medida que se disponga de nueva información. Una forma de lograr esto es el procesamiento continuo es con un flujo constante de datos. Otra característica común de los procesos online es la **In-Memory Computing**, que funciona con representaciones de los datos en la memoria del cluster para evitar tener que volver a escribir en el disco.
**Apache Storm, Apache Flink y Apache Spark** proporcionan diferentes formas de lograr un procesamiento en tiempo real o casi en tiempo real.

---

## Visualizando los Resultados

Reconocer las tendencias de los datos es más importante que los valores mismos. La visualización de datos es una de las formas más útiles de detectar tendencias y dar sentido a una gran cantidad de puntos de datos.
El procesamiento en tiempo real se utiliza para visualizar las métricas de aplicaciones y servidores. Los datos cambian con frecuencia y los grandes deltas en las métricas indican impactos significativos en la salud de las organizaciones. Proyectos como Prometheus son útiles para procesar las secuencias de datos y visualizar esa información. Otra alternativa es con Elastic Stack. Compuesto por **Logstash** para la recopilación de datos, **Elasticsearch** para indexar los datos y **Kibana** para la visualización. 

---

# Anexo, Glosario

---
## Batch Processing
El procesamiento por lotes es una estrategia digital que implica procesar datos en conjuntos grandes. Esto es ideal para trabajos que no requieren mucho tiempo y que operan en grandes conjuntos de datos. El proceso se inicia y en un momento posterior, el sistema devuelve los resultados.

---
## Data lake
Data lake es un término para un gran repositorio de datos recopilados en un estado relativamente crudo. Esto se usa con frecuencia para referirse a los datos recopilados en un sistema de big data que podría no estar estructurado y cambiar con frecuencia. Esto difiere en espíritu de los almacenes de datos (Data Warehouse).

---
## Data Mining*
La minería de datos es un término amplio para la práctica de tratar de encontrar patrones en grandes conjuntos de datos. Es el proceso de tratar de refinar una gran cantidad de datos en un conjunto de información más comprensible y coherente.

---
## Data Warehouse
 Los almacenes de datos son depósitos de Big Data que ordenados se pueden usar para análisis e informes. A diferencia de un Data lake, un almacén de datos se compone de datos que se han limpiado, integrado con otras fuentes y, en general, está bien ordenado. A menudo se habla de almacenes de datos en relación con big data, pero normalmente son componentes de sistemas más convencionales.

---
## ETL
 ETL significa extraer, transformar y cargar. Se refiere al proceso de tomar datos en bruto y prepararlos para el uso del sistema. Tradicionalmente, este es un proceso asociado a los almacenes de datos, pero las características de este proceso también se encuentran en las tuberías de ingestión de los sistemas de big data.

---
## Hadoop
 Hadoop es un proyecto de Apache que fue el éxito inicial de código abierto en big data. Consiste en un sistema de archivos distribuido llamado HDFS, con una administración de cluster y un administrador de recursos en la parte superior llamado YARN. Las capacidades de procesamiento por lotes son proporcionadas por el motor MapReduce. Se pueden ejecutar otros sistemas de análisis junto con MapReduce en las implementaciones actuales de Hadoop.

---
## In-memory Computing
La computación en memoria es una estrategia que implica mover los conjuntos de datos en funcionamiento por completo dentro de la memoria colectiva de un cluster. Los cálculos intermedios no se escriben en el disco y se guardan en la memoria. Esto le da a los sistemas de cómputo en memoria como Apache Spark una gran ventaja en la velocidad sobre los sistemas de E/S vinculados como MapReduce de Hadoop.

---
## Machine Learning
El aprendizaje automático es el estudio y la práctica de diseñar sistemas que pueden aprender, ajustar y mejorar en función de los datos que se les proporcionan. Esto generalmente implica la implementación de algoritmos predictivos y estadísticos que pueden concentrarse continuamente en el comportamiento y las percepciones "correctas" a medida que fluyen más datos a través del sistema.

---
## MapReduce
 MapReduce (no la implementación) es un algoritmo para programar el trabajo en un cluster de computación. El proceso implica dividir la configuración del problema (asignarla a diferentes nodos) y calcular sobre ellos para producir resultados intermedios, mezclando los resultados para alinear conjuntos similares, y luego reduciendo los resultados al generar un único valor para cada conjunto.

---
## NoSQL
NoSQL es un término amplio que se refiere a bases de datos diseñadas fuera del modelo relacional tradicional. Las bases de datos NoSQL tienen diferentes ventajas y desventajas en comparación con las bases de datos relacionales, pero a menudo son muy adecuadas para los sistemas de big data debido a su flexibilidad y su arquitectura de distribución frecuente.

---
## Stream Processing
 El procesamiento de flujo es la práctica de computar sobre elementos de datos individuales a medida que se mueven a través de un sistema. Esto permite el análisis en tiempo real de los datos que se están alimentando al sistema y es útil para operaciones sensibles al tiempo que usan métricas de alta velocidad