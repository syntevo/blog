---
title: "SmartGit 25.1.054 preview"
date: "2025-07-09"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build of **SmartGit 25.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview/)

## New Features, Improvements
- Edit Author: easy way to paste author strings `name <email>`
- Edit Message: add GitHub issue selector
- Licenses: academic, open-source and charity licenses become full licenses (see https://blog.syntevo.com/smartgit/2025/06/26/non-commercial-full-version.html)
- Log, Details: copy `name <email>`
- Squash: optionally add **co-authored-by** lines
- Standard window:
	- Edit Message: allow during Rebase for HEAD commit
	- File Log: for conflicting files limit the log by default to HEAD only
	- GitHub: query all remotes for displaying pull requests

## Fixed Bugs
- Changes view: colors of separator lines differ in gutter and text field
- Commit, AI: internal error when switching model while having a commit node selected in the Graph
- GitHub/others, comments: possible problems with orphan (e.g. the initial) commit
- GitLab: isssues with handling pull requests from disjoint history
- Push: possibly unclear text for forced push confirmation dialog
- Refresh (refs): possible internal error related to invalid packed-refs file
- Syntax, Properties: values with `\` at EOL were not correctly detected
- Standard window:
	- Integrate: possibly fails to find main ref for repositories with multiple remotes

## Other Noteworthy Changes
- AI integration, config: support for optional urlQueryParams
- Git: upgrade to version 2.50
- Git Config Editor: no lonely save toolbar button
- Log: remembers different window locations for repository log and file/subdirectory log
- Rename Stash: more robust implementation
- Repository Settings (and Preferences, Git Config): editing should be partially possible if (simple) includes are used
- Several commands: disable for non-normal states, e.g. rebasing, merging, cherry-picking, ...
- Standard window:
	- Checkout remote branch: try "branch-remote" before "branch-\<number\>"
	- Start Feature: warn for duplicate feature-prefix
	- when opening a repository the Graph view should get the focus
	- My History: "All branches" renamed to "All my branches"
