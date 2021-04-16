# Parte 1: Primeros pasos en Cloudera

Descargar el archivo [**Titanic.txt**](https://github.com/Pelu-k/clase-big-data/tree/main/Parte%201/Recursos)

En la terminal ejecutar el comando para crear una carpeta donde se guardara el archivo

> mkdir big-data
>
> cd big-data

Ahora ejecutamos, para poder ver lo que hay a nivel de Hadoop

> hadoop fs -ls /

Creamos una carpeta en Hadoop

> hadoop fs -mkdir /big-destino

Le damos todos los permisos a la carpeta

> hadoop fs -chmod +rwx /big-destino

Ahora copiamos el archivo Titanic desde linux a hadoop

> hadoop fs -put /home/cloudera/big-data/Titanic.txt /big-destino

Le damos todos los permisos al archivo Titanic *(solo por si a caso)*

> hadoop fs -chmod +rwx /big-destino/Titanic.txt

Abrimos Hue, seleccionamos la lupa con el signo +, ahora que estamos en las *Collection* precionamos el signo + para cargar nuestro archivo.

Indicamos la dirección de nuestro archivo, para eso debemos retroseder en el directorio para ir a la raiz de hadoop, para eso seleccionamos la carpeta .. hasta encontrar nuestra carpeta *big-destino*, la seleccionamos y cargamos nuestro archivo.

Ahora le damos al boton *next* y comprobamos que se ven los datos y finalmente presionamos *submit* para guardar el archivo en Hue.

Ahora presionamos la opción **HDFS**, comenzamos a retroceder hasta el directorio raiz (/) y seleccionamos la carpeta *big-destino* y seleccionamos el archivo *Titanic.txt*, el archivo no tiene cabeceras por lo que hay que agregarlos, para eso debemos seleccionar la opción de editar y agregar en la primera linea *clase,edad,sexo,sobrevivio* y guardamos.

Ahora seleccionamos la opción de **SQL** y seleccionamos *default*, presionamos el signo + y buscamos el archivo *Titanic.txt* de la carpeta *big-destino*.

Una vez cargado, y no dio ningun error al cargar el archivo, seleccionamos la opción *Query*, *Impala* y escribimos:

> **SELECT** * **FROM** default.titanic

Se nos deberia mostrar toda la información de la tabla titanic.