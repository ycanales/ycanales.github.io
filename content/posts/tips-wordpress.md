---
title: "Tips Wordpress"
date: 2013-07-12T22:02:23-04:00
draft: false
---

## Cambiar contraseña a usuario por línea de comandos

Nos conectamos por SSH a la máquina que contiene la base de datos, ésta aparece en el
archivo `wp-config.php`, donde dice `define('DB_HOST', 'localhost');` (en este caso,
está en el mismo servidor que hospeda el sitio.)

Aprovechamos de anotar desde el archivo otros datos que vamos a necesitar:

```
define('DB_NAME', 'la_bd');
define('DB_USER', 'el_usuario');
define('DB_PASSWORD', '12345');
```

Una vez conectados por SSH a la máquina, nos metemos a MySQL:

```
$ mysql -p
mysql> use la_bd;
mysql> UPDATE wp_users
     > SET user_pass = MD5('nueva password') WHERE user_login = "admin";
```

Donde **admin** es el usuario al que queremos cambiar la contraseña.

## Actualizar la URL del sitio

Antes de cambiar la dirección o dominio del sitio web debemos configurarlo en el panel
de Wordpress:

Si se te olvidó hacer el cambio se verá mal la página al cargarla en su nueva dirección y,
si mal no recuerdo, tampoco te permitirá ingresar con tu usuario. Siguiendo los pasos
anteriores para ingresar a la consola de MySQL podemos corregir esto:

```
$ mysql -p
mysql> use la_bd;
mysql> UPDATE wp_options
     > SET option_value = "http://nueva-direccion.cl"
     > WHERE option_name = "home";
```

Aunque cambiamos sólo uno de los dos valores mostrados en el pantallazo anterior ahora
podemos ingresar al panel y corregir el otro valor también.

## Cambiar idioma a un Wordpress ya instalado

Si tienes Wordpress en inglés y quieres colocarlo en español la solución es bastante rápida.
Primero editamos el archivo `wp-config.php` y donde dice `define('WPLANG', '');` colocamos
`define('WPLANG', 'es_ES')`, cuando entremos al panel de configuración nos ofrecerá actualizar
la instalación de Wordpress a la versión en español.
