---
title: "SmartGit 24.1 preview 7"
date: "2024-06-21"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- Clone:
	- asks for Credential Helper configuration when cloning for the first time
	- preselects the repository's *active* branch
	- "URL or Path" should be tolerant if the user pastes "git clone <url>"
- Preferences: added option to configure the Credential Helper during a clone
- Standard window:
	- Merge/Rebase: are rejected now if there are local changes
	- Open in Browser for GitHub repositories
- Syntax:
	- C#: support for verbatim, interpolated strings, string escapes, etc.
- HTTP authentication: ensure that SmartGit's own credential helper is called first
- Setup/Register: should handle URLs which are entered into the License File field and vice versa
- Working Tree, Log window:
	- Repositories view: added Copy Path context menu item

## Fixed Bugs
- Branch, Rename: must not overwrite other branches differing in case only
- Clone:
	- fixed possible internal error when configuring Hosting Provider in on-top dialog
	- if the master password was canceled, "Searching..." was still shown
	- might have failed to ask for passwords of submodule repositories (Standard window only)
- GitHub:
	- Hosting Provider configuration might have failed for specific org setups
	- should not warn for multiple accounts anymore (they are supported now)
- HTTP authentication (credential helper):
	- fixed multiple, recurring prompts when working with multiple GitHub profiles
	- fixed various credential-related problems (regressions since 23.1)
	- might have failed if SmartGit needs to be started up
- Log window:
	- Copy Name/Path: did nothing on Commit selection
	- Reveal: revealing a commit might have hung
- Refresh:
	- gitattributes: attributes for the same file might have been processed in the wrong order
	- should be tolerant in case of "access denied" for (global) config file
- Standard/Log: staged file which has been untracked-renamed in the working tree did not show up

## Other Noteworthy Changes
- Bundled Git rolled back to version 2.43.0 due to [LFS-related regressions in version 2.45.1](https://raw.githubusercontent.com/git/git/master/Documentation/RelNotes/2.45.2.txt):
- gitattributes:
	- support for macro attributes (CGit compatibility)
	- support for "global" and "system" files (CGit compatibility)
- JRE upgraded to Java 21
- Rollback: added low-level property `rollback.message` to configure/prevent setting the commit message
