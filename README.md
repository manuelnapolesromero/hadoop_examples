# hadoop_examples
Hadoop examples for Herramientas Avanzadas para Grandes Volumenes de Datos

**Resumen del Tutorial: Conteo de Palabras con MapReduce en Docker Hadoop**

Este tutorial describe los pasos para ejecutar un ejemplo básico de MapReduce (conteo de palabras) utilizando un entorno Docker de Hadoop. 

El proceso incluye:
Descargar los recursos necesarios: Se descarga un archivo .jar precompilado con las clases de ejemplo de MapReduce y un archivo de texto (.txt) para procesar.
Mover los archivos al contenedor: Los archivos .jar y .txt descargados se copian al contenedor Docker llamado namenode utilizando el comando docker cp.
Crear directorio de entrada en HDFS: Dentro del contenedor namenode, se crea un directorio llamado /user/root/input_contador en el Sistema de Archivos Distribuido de Hadoop (HDFS).
Copiar el archivo de texto a HDFS: El archivo el_quijote.txt se copia desde el directorio temporal del contenedor (/tmp) al directorio de entrada creado en HDFS (/user/root/input_contador) utilizando el comando hdfs dfs -put.
Ejecutar el trabajo MapReduce: Se ejecuta el programa de conteo de palabras (WordCount) incluido en el archivo .jar de ejemplo, especificando el directorio de entrada (input_contador) y el directorio de salida (output_contador) en HDFS.
Ver los resultados en HDFS: Se utiliza el comando hdfs dfs -cat para visualizar el contenido del archivo de resultados (part-r-00000) dentro del directorio de salida en HDFS. También se menciona el comando hdfs dfs -ls para listar el contenido del directorio de salida.
Exportar los resultados al host: El archivo de resultados se copia desde HDFS a un archivo local (/tmp/quijote_wc.txt) dentro del contenedor y luego se copia del contenedor al directorio actual del host (.) utilizando docker cp.
Ver los resultados localmente: Finalmente, se indica que el archivo quijote_wc.txt contendrá el recuento de palabras del archivo original.
En resumen, el tutorial guía al usuario a través de la configuración de un entorno básico de MapReduce en Docker para realizar un conteo de palabras, desde la descarga de los recursos hasta la visualización de los resultados tanto en HDFS como localmente.
