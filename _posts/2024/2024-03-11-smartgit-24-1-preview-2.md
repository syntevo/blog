---
title: "SmartGit 24.1 preview 2"
date: "2024-03-11"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## Fixed Bugs
- Standard window:
	- Graph view: for multi-selection the commit popup was shown when clicking at ref
- MacOS:
	- Commit, Line Length Guides: if the message contained tab characters, the max-length-bars were drawn at wrong position
	- environment variable detection failed if `pwsh` was selected
- Windows:
	- Commit, Rewrap: wrapped incorrectly
- WSL: if appending Windows path was disabled, browser window could not be opened

## Other Noteworthy Changes
- Clone:
	- the local path is now split into parent directory and directory name making it easier to place repositories into one or more parent directories
	- even for the first repository a path is suggested
- i18n: updated Chinese translation
- Preferences, Hosting Providers, Add: use popup button to select the type of repository
- Repository Search:
	- if all repositories and groups were deleted before opening the Repository Search, it will group them by path like the repositories found during the Setup wizard
- Setup wizard: stream-lined
	- main window selector became first page
	- Git executable and SSH client are configured by default and can be changed in the preferences
- updated SWT
	- fixing drawing of non-US-ASCII characters in the Changes view and Compare
- Log and Working Tree windows:
	- Files: "Renamed Path" shows new (target) path for rename sources
- Standard window:
	- improved keyboard navigation, e.g.
		Window | Branches cycles through Ref selector of My History and All Branches + Tag;
		Window | Files cycles through Local Files and History Files
