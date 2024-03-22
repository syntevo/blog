---
title: "SmartGit 24.1 preview 3"
date: "2024-03-22"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- Clone:
	- easier cloning from hosting providers
	- the hosting provider repositories are shown in a tree structure instead of a table

## Fixed Bugs
- Changes view, Compare, ...: several problems resolved for display of non-US-ASCII characters that are not supported by the selected font
- Hosting providers: for some configurations the Domain input field was missing
- Refresh (config): possible internal error if config file ends after subsection name [CgConfigState.parse Buffer.nextGetIndex BUE (2)]
- MacOS: on some systems the row height of tree and table controls was increased

## Other Noteworthy Changes
- Split Commit:
	- Continue: if all changes of the original commit were committed, allow to skip the confirmation dialog
- updated SWT
- Standard window:
	- Branches: improved anchor branch selection (source vs. target branch) for pull requests
