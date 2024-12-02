---
title: "SmartSynchronize 4.6 preview 2"
date: "2024-09-20"
categories:
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

The second public build of **SmartSynchronize 4.6** is available for download.

- [download](https://www.syntevo.com/smartsynchronize/preview)

## New Features and Improvements
- File manager:
	- built-in Text editor: support for block selection

## Fixed Bugs
- File Compare:
	- Export to HTML: produces hard-to-read colors for dark theme
- File Manager:
	- after closing a File Compare which saved changes, no refresh happened
- Syntax:
	- ERB: produced bad compare results for syntax-based diff
	- Innosetup: `{ }` and `(* *)` block comments were not supported in `[code]` section
	- HTML, XML: possible internal error with invalid content (e.g. while editing the file)
	- Shellscript: incorrect parsing if conditional expressions, command substitution or double quoted strings were nested
- possible internal error for weird proxy setups

## Other Noteworthy Changes
- License server: proxy support
- MacOS 15 (Sequoia) support
- File Manager:
	- Pack: improved dialog and extension handling when switching the type
- update SWT fixing
	- very slow rendering of characters before 0x20
	- possible internal error immediately after waking up from sleep (Windows)
