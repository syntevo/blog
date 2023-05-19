---
title: "SmartGit 19.1 and non-default theme on macOS 10.14"
date: "2019-09-05"
categories: 
  - "smartgit"
---

By default, SmartGit 19.1 should follow the system light/dark theme (the _Theme_\-option "_Automatic select light/dark (recommended)_" is selected). If, for whatever reason, you want to see a dark SmartGit on a light system (or visa versa) like you did in SmartGit 18.2, select the light or dark system independent theme option. Without any further changes, this will cause a couple of visual glitches because of following issues between SWT and the new used macOS API: [bugs.eclipse.org/bugs/show\_bug.cgi?id=549046](https://bugs.eclipse.org/bugs/show_bug.cgi?id=549046) [bugs.eclipse.org/bugs/show\_bug.cgi?id=549174](https://bugs.eclipse.org/bugs/show_bug.cgi?id=549174)

You can mostly work around these problems by adding following line to `~/Library/Preferences/SmartGit/19.1/smartgit.properties`:

`org.eclipse.swt.display.useSystemTheme=false`
