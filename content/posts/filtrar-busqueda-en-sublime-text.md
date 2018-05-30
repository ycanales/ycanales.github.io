---
title: "Filtrar búsqueda en Sublime Text"
date: 2016-07-20T23:06:49-04:00
draft: false
---

Cuando utilizamos en Sublime Text la búsqueda avanzada (`⌘+⇧+F` en macOS / `Ctrl + ⇧ + F`
en Windows) podemos excluir archivos y directorios de los resultados de búsqueda en el
campo *Where*, por ejemplo:

```
-*proyecto/dist*
```

Para más de una exclusión:

```
-*proyecto/dist*, -*proyecto/bower_components*
```

