---
title: Importar datos a MySQL desde un archivo CSV con TIMESTAMP
date: 2014-11-20
tags: Tutorial, MySQL
---

En este post veremos como importar datos en formato CSV a una base de datos MySQL.

Partimos por ingresar al administrador de MySQL por línea de comandos:

```
mysql -u user_mysql -p
```

Listamos y seleccionamos la base de datos a utilizar:

```
show databases;
use nombre_de_la_bd;
```

Procedemos a importar el archivo CSV fijándonos bien en colocar bien la ruta absoluta del archivo, y por seguridad dejar expresados primero el caracter delimitador y segundo el caracter que rodea el valor. Para nuestro ejemplo una línea del CSV luciría así:

```
"1";"Perico";"Palotes";"1285435139"
```

Escribimos en la consola de MySQL la siguiente consulta:

```
load data local infile '/ruta/absoluta/al/archivo.csv' into table datos fields terminated by ';' enclosed by '"' lines terminated by '\n' (id, nombre, apellido, @datetime) SET datetime=FROM_UNIXTIME(@datetime);
```

En la cuarta columna que corresponde al tipo de dato TIMESTAMP utilizamos una variable, la cual establecemos con la función `FROM_UNIXTIME`que la transformará al formato correcto para su uso en la base de datos.

Hasta la próxima.

