---
title: "Copying text from Quick Look"
slug: "copying"
date: 2014-12-02T22:14:55-04:00
draft: false
---

**Quick Look** is the application that shows file previews when pressing
space in Finder, a feature available since Mac OS X Leopard.

The text files preview won't allow you to select or copy text, however,
forcing you to open TextEdit or another editor.

Running these two commands at Terminal will enable that function:

```
defaults write com.apple.finder QLEnableTextSelection -bool TRUE
killall Finder
```

To revert the changes:

```
defaults delete com.apple.finder QLEnableTextSelection
killall Finder
```

Source: [Macworld](https://www.macworld.com/article/1164668/software-utilities/select-and-copy-text-within-quick-look-previews.html).