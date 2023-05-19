---
title: "Launching Terminal (cmd.exe) from Java"
date: "2014-07-31"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

Until now SmartGit used following command for its default _Open in Terminal_ external tool:

cmd.exe /k start /d <path>

This did not work for paths like _C:\\foo, bar+=hello & world_ though SmartGit had logic to escape the path in this case when launching cmd.exe. Also, the Task Manager showed two running cmd.exe processes, one remaining after the window has been closed. Changing the command to

cmd.exe /c start pushd <path>

resolves both problems and the path-escaping logic also is not necessary anymore.
