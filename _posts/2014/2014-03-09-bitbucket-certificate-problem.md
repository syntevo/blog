---
title: "Bitbucket Certificate Problem"
date: "2014-03-09"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

Since Bitbucket certificates have changed, SmartGit refuses to connect ("SHA fingerprint of certificate does not match"). We will update fingerprints for version 5.0.8. In the meanwhile you may use the latest build (**Help|Check for Latest Build**) or your may fix it manually by adding following line to `smartgit.properties` (in the SmartGit settings directory, see About dialog):

smartgit.hostingProvider.bitbucket.sslFingerprint=37:A8:0E:13:87:DA:13:C3:B8:35:6F:84:EF:74:D2:38:B1:AC:59:9B

After restarting SmartGit, connection will work again.

**Edit:** As of February 25th, 2015, the official fingerprint as it shows up in the web browswer is `E9:5D:6B:1D:28:51:AC:FF:39:93:85:87:F6:30:BE:2E:7B:D0:DA:EA`.
