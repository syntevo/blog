---
title: "SmartGit 24.1 preview 6"
date: "2024-05-23"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- Update Git to 2.45.1 fixing some [vulnerabilities]({% post_url 2024-05-22-git-vulnerabilities %})

## Fixed Bugs
- Changes view:
	- Unified view: selection-related operations should only be available if reasonable for the selected "side" type
	- internal error when trying to stage "left" block at line 0
	- internal error for Unstage Selection for last block in unified diff view
- Log Graph (and Commits view):
	- for .mailmap lines containing <>, mapping is not applied
	- for email-only .mailmap lines, the original Author name is lost
- Refresh: possible internal error if mailmap.file contains an invalid path
- Standard window:
	- adding, e.g., *Reset Advanced* to toolbar fails for "Basic" configuration
- Linux, several text input fields:
	- internal error undoing changes after having typed Chinese characters with Pinyin

## Other Noteworthy Changes
- Syntax:
	- Verilog: add support for more literal formats
- Text editors:
	- Find and Replace: should replace the initial selection, too (if matching)
	- Move/Select word: added low-level property `styledtext.wordCaretMovementType` to customize the behavior; the `_` will be treated as word-character, e.g. also for double-click
- Standard window:
	- Commit view:
		- for empty repository, show default branch name (to which the first commit will go)
		- file completion: the currently selected file will be preselected (if possible)
