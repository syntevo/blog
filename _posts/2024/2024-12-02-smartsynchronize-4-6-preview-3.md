---
title: "SmartSynchronize 4.6 preview 3"
date: "2024-12-02"
categories:
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

A new preview release for **SmartSynchronize 4.6** is available for download.

- [download](https://www.syntevo.com/smartsynchronize/preview)

## New Features and Improvements
- File manager:
	- Multi-rename dialog: show diff-like file names
- new syntax coloring for:
	- Powershell
	- TCL

## Fixed Bugs
- File Manager:
	- SFTP dialog: input was not verified correctly, e.g. not existence of private key file
	- Text Viewer, Search: did not scroll to match before current view
- Syntax:
	- C++: allow 0x0C (form feed) as whitespace character
	- Groovy: error typing `@`
	- HTML: incorrect parsing
	- InnoSetup: fixes for strings
	- Markdown: incorrect handling of characters >= 0x80
	- PHP: `<?` can occur inside tag arguments
	- Shell: emojis could break syntax coloring
	- XML: error typing `&`
	- multiple languages: problematic parsing with \ at line end and Windows line endings
- Linux:
	- maximizing a window forgot previous location
	- Ubuntu 24.04: did not restore maximized state
- MacOS:
	- on non-English systems the app-menu shows "SWT_XXX (no resource bundle)"
	- clicking link in unsupported OS version dialog does nothing

## Other Noteworthy Changes
- File manager:
	- Multi-rename: did not allow to skip if a target file already existed
	- after successful drop the dragged items are unmarked
	- Open Directory Compare: only optionally use selected directory (low-level property `fileManager.compareDirs.useSelectedDirEntry`)
	- tiny changes to `light-taube.theme`
- update 7z to version 24.08
