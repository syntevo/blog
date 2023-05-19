---
title: "Playing with themes"
date: "2017-02-21"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

SmartGit 17 allows to use theme files that can define alternative colors for foreground or background of certain controls.

To start, the easiest way to start is to invoke SmartGit 17.1 preview 2 (or newer) with the command line parameter

\--write-default-theme-file

This way a file **own.theme** is created in the SmartGit settings directory (the exact path of the file is printed; you can rename or move it). You now can start tweaking this file. It contains of _key=value_ lines. The most keys should be self-explaining. The value usually is a color defined as #rrggbb using hexadecimal values, but it also can be name of another key which makes it easier to create a couple of named colors instead of having to write the same #rrggbb value for different controls. _inherit_ means to inherit the color from the parent control, _default_ forces to use the control uses its default color from the operating system.

Now you only need to tell SmartGit about the **own.theme** file in the SmartGit preferences:

[![](/assets/images/theme-custom-1024x650.png)](/assets/images/theme-custom.png)

###### Example:

To create a theme that uses a dark background color for the main toolbar, uncomment the line

#toolBar.background#shell=default

and change the value to _inherit_ (to inherit the background from the parent _shell_ control):

toolBar.background#shell=inherit

Similarly change the line

#toolBar.foreground#shell=default

to

toolBar.foreground#shell=inherit

though the last change won't have any effect on all platforms because of a [limitation of SWT](https://bugs.eclipse.org/bugs/show_bug.cgi?id=508033).
