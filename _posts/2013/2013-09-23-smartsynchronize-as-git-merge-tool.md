---
title: "SmartSynchronize as Git merge tool"
date: "2013-09-23"
categories: 
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

If you want to use [SmartSynchronize](http://www.syntevo.com/smartsynchronize) as merge tool for Git, you need to configure the ~/.gitconfig (or .git/config) similarly:

\[merge\]
        tool = smartsynchronize
\[mergetool "smartsynchronize"\]
        cmd = '/C/Program Files/tom/SmartSynchronize/bin/smartsynchronize.exe' "$LOCAL" "$REMOTE" "$MERGED"
        trustExitCode = false
