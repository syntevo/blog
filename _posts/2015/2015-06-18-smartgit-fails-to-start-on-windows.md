---
title: "SmartGit fails to start on Windows"
date: "2015-06-18"
categories: 
  - "smartgit"
  - "smartsvn"
  - "smartsynchronize"
tags: 
  - "smartgit"
  - "smartsvn"
  - "smartsynchronize"
---

If you try to launch SmartGit and see a "Couldn't load main class." error, be sure to check the TEMP and TMP environment variables. They should point to a directory where the current user has write access ([references](http://stackoverflow.com/questions/30587352)).
