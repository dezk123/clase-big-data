# Clase Big Data

## Indice

* [Software](#Software)
* [Comandos básicos](#Comandos-basicos)
* [Comandos Hadoop](#Comandos-Hadoop)
* [Permisos en linux](#Permisos-en-linux)
* Contenidos de clase
    * [Parte 1 : Primeros pasos en Cloudera](https://github.com/Pelu-k/clase-big-data/tree/main/Parte%201)

## Software

Los softwares necesarios para la realizacion de esta asignatura son:

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Cloudera](https://drive.google.com/drive/u/1/folders/12MVmy7d8DTFxiJ_tgtHshFEuZmq8SPbe) - Maquina virtual entregada por la institución

## Comandos básicos

Moverse entre carpetas

> **cd** "nombre carpeta" 
>
> **cd** ..

Crear carpetas

> **mkdir** "nombre de la carpeta"

Listar directorios y archivos

> **ls**
>
> dir

Modificar permisos

> **chmod** +rwx
>
> **chmod** -rwx

## Comandos Hadoop

Hay que tener en cuenta que para interactuar con hadoop desde la terminal todos los comandos deben comenzar con:

> **hadoop fs**

Listar directorios

> hadoop fs **-ls /**

Crear carpetas

> hadoop fs **-mkdir "/nombre-carpeta"**

Copiar archivos desde linux a hadoop

> hadoop fs **-put /directorio/de/origen /directorio/destino**

Agregar permisos *(con este comando se estan agregando todos los permisos)*

> hadoop fs **-chmod +rwx "nombre carpeta o archivo"**

Eliminar permisos *(con este comando se estan eliminando todos los permisos)*

> hadoop fs **-chmod -rwx "nombre carpeta o archivo"**

## Permisos en linux

<table>
    <thead>
        <tr>
            <th>Permiso</th>
            <th>Valor Octal</th>
            <th>Descripción</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>---</td>
            <td>0</td>
            <td>No tiene ningun permiso</td>
        </tr>
        <tr>
            <td>--x</td>
            <td>1</td>
            <td>Solo permiso de ejecución</td>
        </tr>
        <tr>
            <td>-w-</td>
            <td>2</td>
            <td>Solo permiso de escritura</td>
        </tr>
        <tr>
            <td>-wx</td>
            <td>3</td>
            <td>Permisos de escritura y ejecución</td>
        </tr>
        <tr>
            <td>r--</td>
            <td>4</td>
            <td>Solo permiso de lectura</td>
        </tr>
        <tr>
            <td>r-x</td>
            <td>5</td>
            <td>Permisos de lectura y ejecución</td>
        </tr>
        <tr>
            <td>rw-</td>
            <td>6</td>
            <td>Permisos de lectura y escritura</td>
        </tr>
        <tr>
            <td>rwx</td>
            <td>7</td>
            <td>Todos los permisos establecidos, lectura, escritura y ejecución</td>
        </tr>
    </tbody>
</table>

Hay que tener en cuenta que los permisos en linux estan divididos en 3: **propietario**, **grupo** y **otros**

<table>
    <thead>
        <tr>
            <th>Permiso</th>
            <th>Valor</th>
            <th>Descripción</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>rw- --- ---</td>
            <td>600</td>
            <td>El propietario tiene permisos de lectura y escritura</td>
        </tr>
        <tr>
            <td>rwx --x --x</td>
            <td>711</td>
            <td>El propietario lectura, escritura y ejecución, el grupo y otros solo ejecución</td>
        </tr>
        <tr>
            <td>rwx r-x r-x</td>
            <td>755</td>
            <td>El propietario lectura, escritura y ejecución, el grupo y otros pueden leer y ejecutar el archivo</td>
        </tr>
        <tr>
            <td>rwx rwx rwx</td>
            <td>777</td>
            <td>El archivo puede ser leído, escrito y ejecutado por quien sea</td>
        </tr>
        <tr>
            <td>r-- --- ---</td>
            <td>400</td>
            <td>Solo el propietario puede leer el archivo, pero ni el mismo puede modificarlo o ejecutarlo y por supuesto ni el grupo ni otros pueden hacer nada en el</td>
        </tr>
        <tr>
            <td>rw- r-- ---</td>
            <td>640</td>
            <td>El usuario propietario puede leer y escribir, el grupo puede leer el archivo y otros no pueden hacer nada</td>
        </tr>
    </tbody>
</table>

[Fuente de la información sobre los permisos](https://blog.desdelinux.net/permisos-y-derechos-en-linux/)