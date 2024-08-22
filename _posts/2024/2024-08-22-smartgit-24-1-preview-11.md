---
title: "SmartGit 24.1 preview 11"
date: "2024-08-22"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- Blame/Investigate: honor "diff.renames=copies" when following renames/copies
- Blame: for "View Commit", denotes if the file path has been changed
- Changes View, File Compare: rework "Ignore Whitespace" option(s):
	- "Ignore Whitespace" option instead of "Ignore Leading" and "Ignore All"
	- Changes view: added toggle button in view header
	- the option is automatically reset for local files if a different one is selected (to avoid unintentionally commit unseen whitespace changes); in committed files it is preserved
- Log, Working tree window:
	- optionally stage/unstage on double-clicking a local file (Preferences, page "User Interface")
- Preferences:
	- Git Executable: added option for using own credential helper (ignoring any system one)
- Linux and macOS:
	- bundled Git now comes with ready-to-use LFS configuration like the Windows bundled Git

## Fixed Bugs
- Changes view:
	- possible internal error when applying lines for syntax-dependent tokenizing
	- Apply Selection: should only be applicable for full line of an added block, not for arbitrary subsets
- GitHub/others:
	- Edit dialog continued to reject configuration after having created a token for an overlapping account once
	- possible internal error when opening a github.com repository, but having configured an on-premise GitHub Enterprise instance only
- Refresh:
	- `.gitattributes` "working-tree-encoding" was not honored
	- possibly confusing missing-untracked detection
	- is now tolerant for FileSystemLoopException
	- External credential helper notification showed wrong config path
- Syntax:
	- Java: buggy parsing of text block containing double-quotes
	- Shellscript: internal error for herefodc in file with Windows line endings
- Standard window:
	- Configure Features: did not save empty feature prefix
	- Integrate:
		- did not update submodules
		- did not work for empyt feature prefix
- Linux:
	- bundle still used old Java version

## Other Noteworthy Changes
- update bundled Git to version 2.46.0
- Add Repository: change default of low-level property `repository.suggestMostAppropriateGroup` because the behavior often was unexpected for users
- Changes view:
	- Apply Selection: is now tolerant if full line content but line endings has been selected
- Completion: introduce low-level property `completion.useAltAsModifier` to be able to get Alt+Space (instead of Ctrl+Space) working on MacOS if Ctrl+Space is already used by switching keyboard layouts
- JIRA: better default query for "Select from JIRA"
- GitHub: uses new libary Apollo GraphQL
- Log graph:
	- Hamburger menu, Author Avatar > Only If Changed: changed default to unselected (raised too many questions by users)
- Proxy: support NO_PROXY and no_proxy environment variables
- Refresh:
	- added low-level property `refresh.evaluateContentChangesForModifiedFileMode`
- SSH: removed outdated and unused SSH libraries
- Standard window:
	- Pull: optionally allow local modifications by setting low-level property `standard.pull.allowDirtyWt`
- Log window:
	- Files: improve table columns for working tree state
- Linux:
	- disable SVG support (can be re-enabled with `changesView.showSvgAsText`) because it was not supported on other platforms and was not very good
	- WSL: warn for host-mounted repositories
- macOS:
	- trying to use the home directory as repository did not work because of file permission issues
