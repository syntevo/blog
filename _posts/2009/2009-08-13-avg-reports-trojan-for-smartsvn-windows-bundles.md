---
title: "AVG reports trojan for SmartSVN Windows bundles"
date: "2009-08-13"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

Starting today at about 2:00 pm (GMT), we are receiving now frequently reports that trojan _Downloader.Banload.ANUF_ is found in the SmartSVN Windows bundles (_installer_, as well as _portable_ bundle). People reporting this trojan are using the [AVG free](http://free.avg.com/) anti-virus scanner. **\[Update\]** [AVG has just confirmed the false positives](http://blog.syntevo.com/2009/08/13/1250187863166.html) and gives instructions how to handle them.**\[/Update\]** The supposedly infected files are:

- smartsvn.exe (MD5: 6f039e0164c72fe92195fca29eab67f5)
- smartsvnc.exe (MD5: 5bfb7e22662c3b49bbbf9b1d1d4ac1aa)
- iconSmartSvnExe (MD5: 6f039e0164c72fe92195fca29eab67f5)

We have checked these files with [virusscan.jotti.org](http://virusscan.jotti.org/) which tests with different virus scanners and all except AVG [can't find something suspicious](./wp-content/uploads/imported/jotti.png). Locally, we have run [Avira Antivir](http://www.avira.com/en/download/index.html) and [NOD32](http://www.eset.com/) which also found the files being clean.

If you are uncertain, please use a different antivirus software to verify, too, and leave us a comment. Thanks!
