---
title: "Edit \"Open Git-Shell\" default external tool for SmartGit 7"
date: "2015-09-09"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

The default external tool "Open Git-Shell" from SmartGit 6.5 does not work any more with the Git shipped with SmartGit 7 because the Git directory structure has changed. You can fix this yourself by editing this external tool in SmartGit's preferences:

Command: `${gitDir}\git-bash.exe` Arguments: `--cd=${filePath}`
