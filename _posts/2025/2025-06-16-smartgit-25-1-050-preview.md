---
title: "SmartGit 25.1.050 preview"
date: "2025-06-16"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build of **SmartGit 25.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview/)

## New Features, Improvements
- Standard window:
	- Checkout remote branch: uses different name now (instead of aborting) for multi-remote repositories with equally named already existing local branch

## Fixed Bugs
- Changes view, File Compare, ...: internal error double-clicking word immediately preceding EOF
- Refresh (WT, Windows): possible internal error if repository is located on symlink
- Refresh (WT/Changes View, ...): possible hang when trying to access Git-LFS objects
- Syntax coloring:
	- C#: failed for `@`
- Standard window:
	- Rename Branch: now only tries to rename the remote branch if it was equally named with the local branch
	- closing with submodule selected, automatically opened repository in first tab; now opens the parent repository tab
	- Conflict Solver: internal error when staging file on close, and the corresponding repository tab has already been closed
- MacOS:
	- alternatving row colors for tables were broken
- Linux:
	- Toolbar: click-and-hold to show popup did not work

## Other Noteworthy Changes
- Git-Flow, Finish Release: clarify dialog when master merge isn't supported due to a custom base branch
- updated Git to version 2.49.0
	- on Windows with `core.longPaths` set to `true` by default
- I18n:
	- translation fixes and slight improvements
	- potentially incorrect texts for multiple dialog GUI items (due to duplicates)
