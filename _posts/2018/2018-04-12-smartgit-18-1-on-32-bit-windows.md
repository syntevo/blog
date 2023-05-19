---
title: "SmartGit 18.1 on 32-bit Windows"
date: "2018-04-12"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

SmartGit 18.1 by default requires a 64-bit Windows (and ships with a 64-bit Java and Git), but it can be run on 32-bit Windows, too:

- - download and unpack the [Portable Bundle](https://www.syntevo.com/smartgit/download/)
    - if you don't already have a Java Runtime Environment (JRE) 1.8 installed, download it from it from [Oracle](http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) and install it
    - if you don't already have a latest Git installed, download it from [git-scm.com](https://git-scm.com/download/win) and either install the setup or unpack the portable bundle
    - then launch <smartgit-install-dir>\\bin\\smartgit32.exe (smartgit.exe is now 64-bit!)
    - if the wrong JRE is used, you can set the environment variable SMARTGIT\_JAVA\_HOME to point to the one SmartGit should use
    - select the Git you have installed or unpacked

Note: in the long run, SmartGit will stop supporting 32-bit Windows, because Java and SWT will stop supporting it.

###### Update from 2019-05-23:

Oracle has changed the license agreement for Java recently and hence Java 1.8 binaries are not available any more without registration. But there are OpenJDK builds available on [GitHub](https://github.com/ojdkbuild/ojdkbuild) or [Amazon](https://aws.amazon.com/corretto/).
