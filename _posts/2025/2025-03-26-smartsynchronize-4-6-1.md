---
title: "SmartSynchronize 4.6.1"
date: "2025-03-26"
categories:
  - "smartsynchronize"
tags:
  - "smartsynchronize"
---

This **SmartSynchronize 4.6.1** release comes with a couple of bug fixes and improvements, mostly related to syntax coloring.
We recommend to update.

- [download](https://www.syntevo.com/smartsynchronize/download/)

## New Features and Improvements
- Syntax:
	- support for Nix (package manager) files
	- Dart: add string escape sequences and templates
	- Pascal: support more keywords from Delphi

## Fixed Bugs
- Syntax:
	- C#: can have multiple number of `"` in `$"` strings
	- Pascal/Delphi:
		- non-US-ASCII letter break lexing
		- identifiers can start with `&`
	- PHP: failed on `@`
	- Powershell: possible internal error
- MacOS: some table columns were not wide enough initially

## Other Noteworthy Changes
- "More Options" checkbox in multiple dialogs needed mnemonic
- File Manager:
	- Sort by Extension: by default ignore the case (low-level property *fileManager.directoryPane.sortByExt.ignoreCase*)
