---
title: "SmartGit 25.1.063 preview"
date: "2025-08-01"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build of **SmartGit 25.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview/)

## New Features, Improvements
- AI setup wizard
- AI commit message generation improved:
  - improve detection of reusable commit message for reworder
  - support for "@ai<"
  - config: diffContextLines configuration
  - config: support for ${generic} and ${reasoning} model names
  - config: support default API URLs
  - config: fix possible duplication of commit message prompts
  - improve API secret id
- Git Notes: displayed as markdown in the Commit details
- Merge: support octopus merges by selecting multiple branches
- Syntax, Markdown: different implementation
- Standard window:
  - My History view: added options which pull requests to show
    - ability to show unassigned pull requests
    - show background refresh in toolbar
    - denote problematic states with warning icon

## Fixed Bugs
- Bisect: focusing old branches did not work reliably
- Changes view:
  - possible internal error trying to Stage inner-line change
  - possible internal error related to caret
  - potential OOME reading text file with certain characters at the beginning
- Checkout:
  - switching to worktree did not work if worktree was not yet known as repository
  - switching to worktree should display error in case of an invalid worktree
- Cherry-Pick File: submodules were not properly initialized/updates
- GitHub:
  - possible internal error adding comment
  - possible internal error querying CI state
- Graph:
  - potential internal error for certain branching structures when filtering
  - old (root) branches may be layouted too far top in the Graph
- Creating a tag or pushing an existing tag used different pushability conditions
- Distributed Review: adding or removing comment did not redraw
- MacOS: potential issues with PATHs, e.g., when using Homebrew LFS
- Log window:
  - Branches view: confusing availability of commands for multi-selection of different entry types
- Standard window:
  - could not rename incorrectly named branch to correct name
  - Commit: should not switch to History if there are local changes remaining (for initial commit)
  - GitHub/CI: possible confusion with multiple remotes
  - History, Files: Open in GitHub should be available for All Refs and Tags, too (not only My History)

## Other Noteworthy Changes
- Git: upgrade to version 2.50.1
= Graph: improved rebasing state layout
- GUI:
  - buttons for dangerous choices have a red background
  - Preferences: the search now also finds low-level properties
  - support for character-based accelerators by disabling the speed-search in tables/trees by setting the low-level property `ui.speedSearch`
- various dialogs: natural sorting of branches
- Register: allow to select existing on-premise license file
- Standard window:
  - Graph: improved filter performance
  - My History: improved tooltip for pull requests
