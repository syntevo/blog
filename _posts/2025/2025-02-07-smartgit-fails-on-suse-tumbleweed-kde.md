---
title: "SmartGit on KDE systems"
date: "2025-02-07"
categories:
  - "smartgit"
tags:
  - "smartgit"
  - "SuSE Tumbleweed"
  - "kde"
author: "Thomas Singer"
---

## SmartGit might fail to start on KDE systems

I've tested SuSE Tumbleweed with a KDE desktop.
SmartGit did not start and showed a message about not being able to load `libswt-pi4-4966r1.so` (note the `pi4`) when launched from a terminal.
That surprised me because the file `libswt-pi3-gtk-4966r1.so` (note the `pi3`) was properly expanded to `~/.config/smartgit/24.1/swt.tmp`.

So it looks like the `libswt-pi3-gtk-4966r1.so` could not be loaded and gave a misleading error message.
To investigate the missing dependency, I used `ldd`:
```
$ cd ~/.config/smartgit/24.1/swt.tmp
$ ldd libswt-pi3-gtk-4966r1.so | grep found
       libgthread-2.0.so.0 => not found
```

After installing the missing **libgthread** bundle
```
$ sudo zypper install libgthread-2_0-0
```
SmartGit started fine.
