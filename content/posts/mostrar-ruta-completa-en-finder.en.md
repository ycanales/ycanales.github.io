---
title: "Showing full path in Finder window"
slug: "showing-full-path-in-finder-window"
date: 2014-12-03T22:54:40-04:00
draft: false
---

When we need to locate a file from Finder into Terminal or another
application it can be useful to know the full path of it.

With these commands we'll be able to show it in the window title:

```
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES
killall Finder
```

Source: [TUAW (now at Engadget)](https://www.engadget.com/2008/12/05/terminal-tips-enable-path-view-in-finder/).