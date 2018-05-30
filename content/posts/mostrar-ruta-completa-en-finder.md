---
title: "Mostrar ruta completa en Finder"
date: 2014-12-03T22:54:40-04:00
draft: false
---

Cuando necesitamos ubicar un archivo del Finder en Terminal u otro programa nos puede
ser útil saber la ruta completa de este.

Ejecutamos en una consola:

```
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES
killall Finder
```

Fuente: [TUAW (ahora Engadget)](https://www.engadget.com/2008/12/05/terminal-tips-enable-path-view-in-finder/).