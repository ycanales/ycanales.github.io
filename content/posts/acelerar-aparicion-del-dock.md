---
title: "Acelerar aparición del Dock"
date: 2014-11-30T22:09:25-04:00
draft: false
---

En macOS si configuramos el Dock para que se oculte y muestre automáticamente
notaremos un pequeño retraso entre que llegamos con el cursor al borde inferior
de la pantalla y la aparición del Dock.

Para mostrarlo inmediatamente abrimos una terminal y ejecutamos estas tres líneas:

```
defaults write com.apple.dock autohide-delay -int 0
defaults write com.apple.dock autohide-time-modifier -float 0.4
killall Dock
```

Si queremos revertir los cambios ejecutamos:

```
defaults delete com.apple.dock autohide-delay
defaults delete com.apple.dock autohide-time-modifier
killall Dock
```

Fuente: [Ask Different](https://apple.stackexchange.com/questions/33600/how-can-i-make-auto-hide-show-for-the-dock-faster/46222#46222).