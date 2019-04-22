---
title: "Utilizar dependencia local con NPM o Yarn"
date: 2019-04-22T15:49:17-04:00
draft: false
---

Si bien la mayoría de las veces instalamos las dependencias para nuestro proyecto Javascript con `npm install [NOMBRE_DEPENDENCIA]` podríamos querer usar una versión local, por ejemplo si estamos desarrollando una nueva librería o modificando una ya existente.

En estos casos **npm** (y también **yarn**) nos permite vincular esta dependencia local a una aplicación que la consuma de la siguiente manera:

- Primero vamos al directorio de la dependencia local y corremos:
    - Si usamos **npm**: `npm link`
    - Si usamos **yarn**: `yarn link`
- Luego vamos al directorio del proyecto que utiliza esta librería y corremos:
    - Si usamos **npm**: `npm link [NOMBRE_DEPENDENCIA]`
    - Si usamos **yarn**: `yarn link [NOMBRE_DEPENDENCIA]`

¡Y listo!

Para deshacer la vinculación:

- Con **npm** debemos correr:
    - `npm rm --global [NOMBRE_DEPENDENCIA]`
- Con **yarn**:
    - Vamos al directorio del proyecto que utiliza esta librería y corremos:
        - `yarn unlink [NOMBRE_DEPENDENCIA]`
    - Vamos al directorio de la dependencia local y corremos:
        - `yarn unlink`