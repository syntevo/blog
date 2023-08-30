---
title: "SmartSynchronize 4.5 preview 1"
date: "2023-08-30"
categories:
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

The first public build of **SmartSynchronize 4.5** is available for download.

- [download](https://www.syntevo.com/smartsynchronize/preview)

## New Features and Improvements
- Syntax coloring:
	- added Forth
	- added Verilog
	- added X86 Assembler
- File Compare/Merge:
	- ability to apply lines at start/end of changed block with different line count
- File Manager:
	- Windows: new default external tool *Open Powershell*

## Fixed Bugs
- Directory Compare:
	- File table: speed-search input field is shown at wrong position if table is scrolled horizontally
	- Preview: the vertical scroll bar was not reset after unselecting a file
- autoupdate: the `control-<build-number>` files were not cleaned up
- possible internal error with invalid proxy configuration
- Syntax coloring:
	- Batch files: incorrect detection of FOR variables
	- Python: lacked support for `_` in number literals
- Linux: the created `.desktop` file was considered as buggy by the *desktop-file-validate* command

## Other Noteworthy Changes
- ability to use the system select-word behavior by setting low-level property `styledtext.useOwnWordBoundaryDetection` to `false`
- use flat images
- updated SSHJ to v0.35.0
- update SWT:
	- GC.init(Win32): catch early possible error (BugID 6327)
	- Issue #603: [win32] Windows TaskBar shows wrong overlay after closing related Shell
- Linux:
	- detect date format according to `LC_TIME` environment variable
	- shows notification if a non-utf-8 configuration has been detected
