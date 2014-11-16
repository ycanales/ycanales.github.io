---
title: Acelerar autohide del Dock
date: 2014-11-16
tags: Tips, OS X
---

![Dock más rápido](/images/2014-11-16-velocidad_intro.gif "Dock más rápido")

Si exprimes cada pixel de la pantalla activando la opción para que el *dock* se oculte automáticamente te habrás dado cuenta que la apertura tiene un retraso que llega a ser desagradable con el uso prolongado.

Para mostrar inmediatamente el *dock* y acelerar un poco la animación nos valemos de esta respuesta en [Ask Different](http://apple.stackexchange.com/a/46222/38435 "Ask Different") de *StackExchange*.

Basta con abrir *Terminal* y pegar las siguientes líneas:

```
defaults write com.apple.dock autohide-delay -int 0
defaults write com.apple.dock autohide-time-modifier -float 0.4
killall Dock
```

Para revertir los cambios:

```
defaults delete com.apple.dock autohide-delay
defaults delete com.apple.dock autohide-time-modifier
killall Dock
```

