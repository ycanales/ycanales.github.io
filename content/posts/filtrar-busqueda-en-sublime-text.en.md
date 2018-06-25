---
title: "Excluding paths in Sublime Text search"
slug: "excluding-paths-in-sublime-text-search"
date: 2016-07-20T23:06:49-04:00
draft: false
---

When using the advanced search in Sublime Text—`⌘+⇧+F` in macOS or `Ctrl+⇧+F`
in Windows—we can exclude files and directories from using the *Where* field, for instance:

```
-*project/dist*
```

For several exclusions:

```
-*project/dist*, -*project/node_modules*
```