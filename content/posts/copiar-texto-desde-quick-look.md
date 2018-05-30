---
title: "Copiar texto desde Quick Look"
date: 2014-12-02T22:14:55-04:00
draft: false
---

**Quick Look** es la aplicación que despliega las previsualizaciones de archivos cuando
presionas la barra espaciadora en Finder, una función disponible desde Mac OS X Leopard.

Sin embargo la previsualización de archivos de texto no permite seleccionar ni copiar
texto, teniendo que abrir TextEdit u otro editor.

Ejecutando los siguientes comandos en Terminal podremos activar esa función.

```
defaults write com.apple.finder QLEnableTextSelection -bool TRUE
killall Finder
```

Para revertir el cambio ejecutar:

```
defaults delete com.apple.finder QLEnableTextSelection
killall Finder
```

Fuente: [Macworld](https://www.macworld.com/article/1164668/software-utilities/select-and-copy-text-within-quick-look-previews.html).
