---
title: "Remote git commands fail with \"protocol error: bad line length character: Acti\""
date: "2020-04-21"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
  - "tipstricks"
  - "windows"
---

If you encounter an error "protocol error: bad line length character: Acti" (the last 4 characters might be different) when executing a remote Git command in SmartGit on Windows, please launch `cmd.exe` and look for some default output (in our case, e.g. `Active code page: 65001`). This might be caused by a so-called _autorun_ script which can be configured at the registry key **AUTORUN** at **HKLM\\SOFTWARE\\Microsoft\\Command Processor**.

Solution: Ensure that the script does **not** output anything.
