---
title: "SmartGit 24.1 preview 9"
date: "2024-07-12"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A new preview build for **SmartGit 24.1** is available for download.

- [Download](https://www.syntevo.com/smartgit/preview)

## New Features, Improvements
- Azure DevOps: include link to profile for Cloud settings dialog
- Changes view, Compare: improved inner-line diff based on syntax of selected language
- Checkout: warn if switching will change `.gitmodules` (it might be harder to switch back; sometimes happens trying to check out the wrong branch by accident)
- Clone, GitHub:
	- added options which kind of repositories to query
	- more efficient repository query which gives almost all repositories of the old, expensive query
- Log: honor `diff.renames=copies` when following renames/copies 

## Fixed Bugs
- Cherry-Pick/Squash Commits: possible internal error related to invalid Git commits
- Hosting Providers: configuration of 23.1 is not properly upgraded (UUIDs are missing)
- Investigate: merged changes are not detected as origin
- Refresh: packed refs/replace were not processed
- Window | Reset Perspective: keeps previous layout
- Syntax:
	- Pascal: missed keyword `const`
	- Perl: incorrect lexing after slash
	- PHP: incorrect lexing
	- XML: might be confused by conflict markers
- Standard window:
	- Push: `remote.pushDefault` was not honored

## Other Noteworthy Changes
- JIRA: improve authentication dialog for JIRA cloud
- Refresh: check and warn in case of external `credential.helper`
- Log window:
	- Branches view: delete multiple stashes using Delete-key
- Working Tree and Log window:
	- Push: honor `remote.pushDefault` for new branches
- Standard window:
	- Log, Files: commit diff logic should honor the commit times for selection of what's left and right
