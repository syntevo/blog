---
title: "SmartGit 25.1.038 preview"
date: "2025-04-18"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build of **SmartGit 25.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview/)

## New Features, Improvements
- Blame, Investigate: honors configured text file encoding
- Standard window:
	- All Branches + Tags:
		- add remotes
			- including context commands for fetching, renaming, deleting, ...
		- branches and tags are grouped by prefix, except for *Sort by Date* (for which it makes no sense)
- Log and Standard window:
	- Checkout (Enter): by default will check out local branch(es) on the selected commit

## Fixed Bugs
- Standard window:
	- preferences option "Allow modifying pushed commits:
		- "Only for feature branches" did not work for empty feature prefix
		- low-level property "push.forcedPushConfirmationForSafeBranches" should also be honored if force-pushing is allowed "For all branches"

## Other Noteworthy Changes
- Branches/Graph: added low-level property "core.refs.additionalTopLevelRefs" to parse additional top-level refs
- Master password dialog: make hint visible
- Preferences:
	- Low-level Properties: removed confirmation button and show all by default
- updated SWT
- Standard window:
	- Repositories tab:
		- add link to select obsolete repositories
		- Filter:
			- entered (valid) path is taken as default for *Add or Create Repository*
			- use Ctrl/Cmd+Enter to invoke the *Add* or *Initialize* command for existing repositories/directories
	- Stashes view: auto-select newest stash
