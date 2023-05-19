---
title: "Unattended installation of SmartSVN"
date: "2010-01-08"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

**Note** These instructions do NOT apply any more for SmartSVN version >= 9.

When deploying SmartSVN to many users, having everyone of them to go through the Setup wizard can be cumbersome. This article gives a short receipt on how to perform an unattended respectively quiet installation of SmartSVN.

First of all, [download](http://www.syntevo.com/smartsvn/download.html?all=true) the Windows installer bundle **with** JRE. Unzip this file and start the setup\*.exe. The executable will unpack the contained _MSI_ installer to a sub-directory within the TEMP directory. You should find there smartsvn.msi and jre.cab. Take both files to an intermediate directory, say c:\\temp\\install and cd to that directory.

The installation itself is performed using the msiexec utility program which comes with every Windows installation. Following command will perform a full installation of SmartSVN to _C:\\Program Files\\SmartSVN_:

msiexec /q /log log.txt /i smartsvn.msi DIR\_INSTALL="C:\\Program Files\\SmartSVN" JRECABFILE=jre.cab

Having the installation logged to the log.txt is not necessary, but will be helpful to trace possible problems.

The installation can be customized by skipping certain features from the installation using the _REMOVE_ property. For instance:

msiexec /q /log log.txt /i smartsvn.msi DIR\_INSTALL="C:\\Program Files\\SmartSVN" JRECABFILE=jre.cab ADDLOCAL=All REMOVE=featureShellExtFull,featureStatusCache

will skip the full shell integration and the _Status Cache_ service. In the same way following features can be selected/deselected from the installation:

- featureShellExt (Explorer Integration)
    - featureShellExtFull (Full Integration)
    - featureStatusCache (Status Cache)
- featureAutostart (Automatic Start)
- featureJre (Installation of the JRE)

**Note:** If you don't want to install SmartSVN with its own JRE, you may download the installer bundle without JRE and perform the same procedure, just with having JRECABFILE=jre.cab skipped for the _msiexec_\-call.
