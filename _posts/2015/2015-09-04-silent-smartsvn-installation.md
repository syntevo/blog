---
title: "Silent SmartSVN Installation"
date: "2015-09-04"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

The SmartSVN Windows installer uses InnoSetup. The command line options that can be passed to `setup.exe` are listed in the [InnoSetup documentation](http://www.jrsoftware.org/ishelp/index.php?topic=setupcmdline).

So a `setup.exe /VERYSILENT /SUPPRESSMSGBOXES` should work for most users.
