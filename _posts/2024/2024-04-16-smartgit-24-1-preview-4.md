---
title: "SmartGit 24.1 preview 4"
date: "2024-04-16"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- Hosting Provider improvements:
	- separate configurations for "cloud" and "enterprise"
	- GitHub:
		- support OAuth-authentication for Git executable with multiple remotes
		- show warnings which GitHub reports about OAuth-inaccessible organizations
- Standard window:
	- Submodule toolbar button with popup for faster switching to submodule; removed previous Submodule category

## Fixed Bugs
- Clone: URL input field was not preselected if clipboard contained URL
- Directories view (Standard window, Log window): sorting was not case-insensitive as in other parts
- Preferences, Hosting Providers: double-click did not invoke Edit
- Push: internal error when trying to push multiple repositories at once
- Linux, MacOS: cloning from URL did not work (URL was treated as file)

## Other Noteworthy Changes
- Clone, Repository selection:
	- allow filtering by group
	- ability to repository copy URL
- File editor (git config files): optional auto-save
- Hosting providers:
	- hid simple providers by default; can be enabled with low-level property
	- hid "Use oauth-token for repository authentication (instead of password)" - use low-level properties `*.useTokenForRepositoryAuthentication` for not recommended password access
- Refresh:
	- performance improvements for index-only changes, e.g. after Stage
	- do not display index path for case-changed directories
- Standard window:
	- Commit view: during rebase show the rebased branch instead of "HEAD"
	- removed inline help controls
	- reduced space between toolbar buttons
- MacOS:
	- environment variable detection: invoke shell with interactive option (-i)
