---
title: "Crash on KDE"
date: "2015-06-08"
categories: 
  - "smartgit"
  - "smartsvn"
  - "smartsynchronize"
tags: 
  - "linux"
  - "smartgit"
  - "smartsvn"
  - "smartsynchronize"
---

If SmartGit, SmartSVN or SmartSynchronize crashes for you on dialogs where (on other platforms) comboboxes are visible, please check whether the **oxygen-gtk** style is selected. It is reported to be [extremely buggy](http://javaclipse.blogspot.de/2015/06/mars-on-linux.html) and better should be replaced with either Adwaita or Clearlooks-Phenix:

1. Open the System Settings [![KDE: System Settings](/assets/images/kde1-248x300.png)](/assets/images/kde1.png)
2. Select the Application Appearance [![kde2](/assets/images/kde2-300x252.png)](/assets/images/kde2.png)
3. On the GTK+ Appearance page select, e.g. Adwaita [![kde3](/assets/images/kde3-300x208.png)](/assets/images/kde3.png)

[SWT bug report](https://bugs.eclipse.org/bugs/show_bug.cgi?id=473152)

Please also check out [javaclipse.blogspot.de/2015/06/mars-on-linux.html](http://javaclipse.blogspot.de/2015/06/mars-on-linux.html) for alternative hints.
