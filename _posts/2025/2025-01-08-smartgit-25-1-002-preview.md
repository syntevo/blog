---
title: "SmartGit 25.1.002 preview"
date: "2025-01-08"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

The first public build of **SmartGit 25.1** is available for download.
The most obvious change is a different version numbering.

- [Download](https://www.syntevo.com/smartgit/preview/)

## New Features, Improvements
- Files view: denote unexpanded LFS files
- Preferences:
	- Syntax coloring configuration:
		- clicking a token in the preview selects the corresponding color
- Push To: preselect the matching remote for the selected ref
- Syntax coloring:
	- Kotlin: valid/invalid escapes, string templates
	- Powershell
	- TCL
- Standard window:
	- Commit: allow to create empty merge commit
	- Files: introduce "Open in GitHub"
	- Finish Feature: if branch was not deleted, don't suggest to delete it the next time

## Fixed Bugs
- Edit Commit Message: silently failed for empty commits
- Graph: dragging a remote ref must not be allowed
- Revert: commit messages containing patterns `${sha}` or `\n` might be expanded
- Standard window:
	- switching from Local Files to History did not focus any control
- Windows 11 24H2: menu and scrollbar background was bright in dark theme

## Other Noteworthy Changes
- Revert and Rollback: use low-level property to configure message templates
- new version numbering
- JIRA Resolve dialog: scroll selection into view
- Log window:
	- right-clicking a commit should show "Reveal Commit" instead of "Select Commit"
- Standard window:
	- Local Files toolbar button: in case of conflict show only the number of conflicting files, not all changed files
