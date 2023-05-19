---
title: "Compatibility with OS X 10.7 (Lion)"
date: "2011-07-22"
categories: 
  - "smartgit"
  - "smartsvn"
tags: 
  - "smartgit"
  - "smartsvn"
---

We've done a quick test of our applications with Mac OS X 10.7 ("Lion"). In contrast with previous versions, Mac OS X 10.7 ships without Java preinstalled. But when starting a Java application (like SmartGit or SmartSVN), Java will be automatically downloaded and installed from Apple.

Summary: except of the file watcher, everything seems to work fine. We'll keep you updated.

**Update:** If the SmartSVN's services (minimal Finder integration) seems to be broken, invoke /System/Library/CoreServices/pbs in a Terminal.

**Update 2:** [SmartGit 2.0.6](http://www.syntevo.com/smartgit/download.html) and [SmartSVN 6.6.9](http://www.syntevo.com/smartsvn/download.html) should work fine on OS X 10.7.
