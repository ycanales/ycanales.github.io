---
title: "Mejorar la consola de Django"
date: 2015-09-22T22:58:50-04:00
draft: false
---

![Consola de Django mejorada](https://i.imgur.com/gQke7hF.gif)

Con [django-extensions](http://django-extensions.readthedocs.io/en/latest/) y
[bpython](https://bpython-interpreter.org/) le agregaremos a la consola de Django import
automático de nuestros modelos, syntax highlight y autocompletado del código.

Instalamos los paquetes:

```
pip install django-extensions
pip install bpython
```

Ahora en nuestro proyecto Django agregamos `django-extensions` a las aplicaciones.
Editamos el archivo `app/app/settings.py`:

```
INSTALLED_APPS = (
    ...
    'django_extensions'
)
```

Ahora podemos lanzar la consola mejorada:

```
python manage.py shell_plus
```

