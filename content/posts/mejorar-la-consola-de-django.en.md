---
title: "Better Django shell"
slug: "better-django-shell"
date: 2015-09-22T22:58:50-04:00
draft: false
---

![Better Django shell](https://i.imgur.com/gQke7hF.gif)

Using [django-extensions](http://django-extensions.readthedocs.io/en/latest/) and
[bpython](https://bpython-interpreter.org/) we'll add autocompletion, syntax highlighting and automatic import of our models to the Django shell.

Install these packages:

```
pip install django-extensions
pip install bpython
```

Now we add `django-extensions` to our Django project applications.
Edit the `app/app/settings.py` file:

```
INSTALLED_APPS = (
    ...
    'django_extensions'
)
```

Now we can launch the improved shell:

```
python manage.py shell_plus
```