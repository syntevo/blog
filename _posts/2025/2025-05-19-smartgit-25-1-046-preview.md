---
title: "SmartGit 25.1.046 preview"
date: "2025-05-19"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build of **SmartGit 25.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview/)

## New Features, Improvements
- Changes view, Compare, ...:
	- support language-specific word-definitions for caret movement (e.g. `foo_bar` as a identifier will be treated as one word, but not inside strings or comments)
	- allow to configure additional line spacing using the low-level property `styledText.lineSpacing`
- Commit: AI commit message generation improved
- Edit Git-Config:
	- syntax coloring
	- check validity before saving, reject to save invalid files
- Log Graph: for stashes show the comment message instead of the commit message
- Preferences:
	- Authentication:
		- rewritten management for API tokens (GitHub, JIRA, ...)
- Submodules: honor Git config `submodule.recurse = false`
- Standard window:
	- Add Branch: allow to create a branch for which a similar named remote branch exists (if low-level property `standard.addBranch.allowOverwrite` is set)
	- All Branches + Tags: remember the reg-ex option
	- My History: warn only those cases of `<name> != <remote>/<name>` if renaming the local branch could fix it
	- Rename Stashes

## Fixed Bugs
- Changes view, Compare, ...: Syntax-selection dialog did not scroll selection into view
- Clone: fails if repository is already open
- Kill Process dialog: possible internal error
- Log Graph: filtering with inversion (using leading `!`) did only work correct if "message" was selected
- Rebase Interactive: Edit Message missed "JIRA" option if bugtraq was configured
- Show Changes: possibly incorrect HEAD vs. Index vs. Working Tree file content selection for renamed files
- Linux:
	- Changes view: zoomed images occurred blurred
	- dragging a ref might select a different commit (workaround for https://github.com/eclipse-platform/eclipse.platform.swt/issues/2119)
	- windows may occur on "wrong" monitor
- Standard window:
	- Graph: may show incomplete ref context menu

## Other Noteworthy Changes
- various commands: enable remote support, so, e.g., LFS authentication also works
- Refresh: added low-level property `refresh.ignoreSymlinkModificationsIfUnsupported`
- Standard window:
	- My History, All Branches + Tags: reduced (minimum) image height
