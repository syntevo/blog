---
title: "SmartSVN 14.5 preview 2"
date: "2024-12-18"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

The second public preview build for SmartSVN 14.5 is available.

- [Download](https://www.smartsvn.com/preview/)

## New Features or Improvements
- upgrade to SVN 1.14.5 binaries (containing security fixes)
- Syntax:
	- Powershell
	- TCL

## Fixed Bugs
- Compare:
	- Markdown: changes in ```...``` section are treated as one block
	- Apply Innerline-Change not available
- Properties | Edit Properties: internal error
- possible dead-lock related to updating transactions tree
- tooltips might be shown on wrong monitor
- Syntax:
	- Kotlin: fixing several limitations and bugs
- MacOS:
	- app menu item prefix "SWT_" on non-English systems

## Other Noteworthy Changes
- Check for Updates: switch from HTTP to HTTPS
- in preview builds don't show expire information in title (confuses users)
- Linux:
	- launcher unset `java.library.path` to prevent possible conflicts with system libraries
