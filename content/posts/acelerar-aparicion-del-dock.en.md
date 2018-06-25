---
title: "Faster dock appearing"
slug: "faster-dock-appearing"
date: 2014-11-30T22:09:25-04:00
draft: false
---

In macOS if we set the Dock to automatically hide and show we'll
notice a slight delay between reaching the bottom of the screen and
the Dock appearing.

For it to show immediately open a terminal and run these three lines:

```
defaults write com.apple.dock autohide-delay -int 0
defaults write com.apple.dock autohide-time-modifier -float 0.4
killall Dock
```

To revert the changes:

```
defaults delete com.apple.dock autohide-delay
defaults delete com.apple.dock autohide-time-modifier
killall Dock
```

Source: [Ask Different](https://apple.stackexchange.com/questions/33600/how-can-i-make-auto-hide-show-for-the-dock-faster/46222#46222).