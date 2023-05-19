---
title: "msysgit: access denied error for files with leading period in the name"
date: "2010-05-25"
---

In the last time my IDE ([IntelliJ IDEA](http://www.jetbrains.com)) from time to time reported an "access denied" error when writing .classpath files. The reason was that msysgit made these files hidden by default.

In the [Noise And Heat blog](http://www.noiseandheat.com/blog/2010/02/17/the-case-of-eclipse-msysgit-and-the-obstinate-dot-files/) I found the solution: one has to set the core.hidedotfiles property to false:

git config --global core.hidedotfiles false
