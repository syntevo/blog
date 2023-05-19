---
title: "New Russian time-zones"
date: "2014-11-11"
categories: 
  - "smartcvs"
  - "smartgit"
  - "smartsynchronize"
tags: 
  - "smartcvs"
  - "smartgit"
  - "smartsynchronize"
---

If you are living in Russia and are affected by incorrectly displayed times in, e.g., SmartGit, here comes the solution.

The reason for the incorrect time-zone display is that the Java version shipped with SmartGit does not know about such new time-zone changes (see the [chart](http://www.oracle.com/technetwork/java/javase/tzdata-versions-138805.html "chart") for time-zone changes and Java versions).

To work-around, please edit `smartgit.vmoptions`, add following line (and tweak if necessary)

`-Duser.timezone=Etc/GMT-3`

and restart SmartGit.
