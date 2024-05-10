---
title: "SmartGit 24.1 preview 5"
date: "2024-05-10"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- Preferences:
	- Git Executable: added option to easier selecting bundled Git
- Standard window:
	- Copy URL on current repository tab
	- Windows:
		- Show case-changed files
		- Ability to fix case-changed files

## Fixed Bugs
- Files context menu: Submodule | Add should only be applicable on nested roots
- Files: fixed display of case-changed files in Index
- GitHub: notification "could be configured" should only show up for GitHub repositories
- Preferences:
	- Updates: options for in-place/light-weight updates was not remembered
- Log window:
	- Edit Message: "Select from Log" was only shown for non-HEAD commit
- Standard window:
	- possible display of non-existing renamed in Working Tree list, related to case-changes files
- Linux: internal error undoing typed Chinese (and maybe others) characters

## Other Noteworthy Changes
- Compare:
	- inner-line diff improvements for small equal areas at beginning/end
	- inner-line diff improvements for lines with many identical characters
- Files, context menu: group submodule commands, so it is obvious that they are related
- JIRA: improve authentication dialog for JIRA cloud
- Refresh: improved refresh performance for large repositories (UI related)
- Submodules:
	- allow to deinit modified submodules
- Standard window:
	- double clicking a working tree file defaults to Compare instead of Stage, because it is more defensive
	- Files: improve commands in context menu
