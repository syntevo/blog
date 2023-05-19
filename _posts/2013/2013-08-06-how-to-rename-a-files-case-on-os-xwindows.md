---
title: "How to rename a file's case on OS X/Windows"
date: "2013-08-06"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

Imagine, you need to rename a file makefile to Makefile on OS X or Windows using SmartGit. Simply renaming is not sufficient, because the file is treated as the same (the file systems are case-preserving, but not case-sensitive). So we need a trick:

- rename the file to a temporary name, e.g. makefile to makefile.tmp
- commit the missing makefile and the untracked makefile.tmp
- rename the temporary file to the final name, e.g. makefile.tmp to Makefile
- commit the missing makefile.tmp and the untracked Makefile with the _Amend_\-option selected
