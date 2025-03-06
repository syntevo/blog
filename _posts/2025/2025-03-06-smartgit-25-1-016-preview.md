---
title: "SmartGit 25.1.016 preview"
date: "2025-03-06"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build of **SmartGit 25.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview/)

## New Features, Improvements
- Branches view: Hamburger option "Except for single refs" is now unselected by default
- Commit: opt-in AI commit message generation ([documentation](https://docs.syntevo.com/SmartGit/Latest/Manual/Integrations/AI))
- Files table: show moved+modified with a different icon than moved+unchanged
- Graph:
	- Refresh: include node about how to increase the performance limit
	- denote worktrees
	- Checkout will now open the other worktree (instead of fail)
- Pull Requests:
	- Fetch/Merge should only retrieve the corresponding ref, without including tags
- Run Garbage Collector command: added LFS prune
- Syntax coloring:
	- Dart: added escape sequences, string interpolation
	- Nix
- Log window:
	- Checkout should follow the same "default branch" name logic as Add Branch
	- Files: Save As for a commit diff shows the commit IDs on the buttons
- Log and Working Tree window:
	- Files view: show details in the tooltip of renamed files
- Standard window:
	- added tracking commands (Set Tracking, Stop tracking)
	- added worktree commands (Add, Remove, Prune)
	- added Push-to command
	- All Branches + Tags: the filter should be case insensitive
	- Discard: optionally also deletes untracked files
	- Integrate Feature: do not merge (for certain scenarios), but always rebase
	- Graph:
		- long-running filters should report results on-the-fly
		- denote refreshing state for background operations (e.g. filtering)
	- Refresh: improved performance of local refresh
	- Start Feature:
		- for multi-base-branch setups, preselect the closes base branch
		- can also be triggered from a selected commit

## Fixed Bugs
- Checkout: problem when switching a submodule to a plain directory (or visa versa)
- Graph:
	- Alt+Down did not reload on an "arrow"
	- do not try to extend in filtered mode
- GUI: "More Options" checkbox in multiple dialogs was lacking the mnemonic
- Repositories view: dragging an entry beyond the last one seemed to accept it
- Syntax:
	- Powershell: possible internal error
- Worktrees: branch of rebasing/bisecting worktrees was not properly detected
- Standard window:
	- could not invoke terminal tools in opened submodule
	- Graph:
		- right-clicking a ref did not use that refs in external tool for `${commit}`
		- possible endless refreshing for repositories with very short history
	- Undo Last Commit: should check for untracked files, too
