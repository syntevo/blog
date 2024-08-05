---
title: "SmartGit 24.1 preview 10"
date: "2024-08-05"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- File Log: provide Open link for appropriate hosting provider
- Git-Flow:
	- Finish Release: support fast-forward master
- Rebase: when invoking on a commit from the HEAD history, offer to rebase this single commit
- Rebase Continue: warn before applying unstaged working tree changes

## Fixed Bugs
- Azure DevOps: Create Pull Request opened wrong URL
- Git: possible inconsistent processing of gitconfig file
- GitFlow:
	- Finish Release with squash did not work for custom base branch
- GitHub (and others):
	- refreshing failed for multiple configurations for the same hosting provider
- GitLab: token expires too frequently
- Log graph:
	- possible internal error related to invalid commit data, e.g. no author
	- dragging a single commit onto its history should offer to Rebase, too
	- internal error when clicking bugtraq link
- Preferences, Tools: Add/Edit dialog may grow too large
- Refresh (file monitoring): fix for Windows directory mounts
- Syntax coloring:
	- ANTLR: did not support `\u{12345}` escape
	- C#: failed to parse double-quote character literal `'"'`
	- HTML: did not report whitespace correctly
	- JavaScript/TypeScript: incorrect lexing of recursive template mode
	- JavaScript/TypeScript: failed on `@`
	- Ruby: failed on `@`
	- Shellscript: failed on `$`
	- Swift: failed on `@`
	- Swift: identifiers can contain unicode characters, e.g. emojis
- Log window:
	- GitHub (and others):
		- fetching pull request did not properly reveal anymore (regression from 23.1)
- Log and Working tree windows:
	- show "current" branch for empty repository
- Standard window:
	- Commit: for empty repository, show the correct branch which will be used when committing

## Other Noteworthy Changes
- history-related commands: improved message if commit reorganization is not possible/supported
- Preferences:
	- Git executable page: show also LFS version
- Setup: ask user (again) which Git executable to use; don't ask if only the bundled git was found
- Syntax coloring:
	- Ruby: support heredoc
- Syntax diff: instead of crashing for buggy lexer, highlight remaining part of the file as invalid
