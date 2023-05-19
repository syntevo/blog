---
title: "Linux: don't like autohiding scrollbars?"
date: "2019-09-11"
categories: 
  - "smartgit"
tags: 
  - "linux"
---

If you are a Linux user which has problems with autohiding scrollbars that make it hard to select the last item in a table, tree or text control, you should try to set the environment variable GTK\_OVERLAY\_SCROLLING to 0 before launching the application. For SmartGit, open **bin/smartgit.sh** in a text editor and add the line

export GTK\_OVERLAY\_SCROLLING=0

before the last line.
