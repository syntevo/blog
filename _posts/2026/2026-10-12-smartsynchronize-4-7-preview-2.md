---
title: "SmartSynchronize 4.7 preview 2"
date: "2026-10-12"
categories:
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

A new public build of **SmartSynchronize 4.7** is available for download.

- [download](https://www.syntevo.com/smartsynchronize/preview)

## New Features and Improvements
- official support for MacOS 27
- Directory compare, Changes view:
  - Word-wrap support

## Fixed Bugs
- all editors, Find/Replace dialog:
  - possible internal error if, e.g. `$1` was used though no group defined in search string
- Directory compare, Changes view:
  - line numbers and expand buttons text appeared bolder than normal text
  - line number not aligned with text
  - in Unified view, background color for added/removed block was too intensive
- Directory compare:
  - connector could become out-of-sync with editors
- File Merge:
  - possible internal error invoking Take Left/Right from left/right editor
- Syntax:
  - C/C++: better handling of invalid code
  - Java: lacked support for newer keywords
  - JavaScript: fixed several bugs and possible internal errors
  - Markdown: link highlighting was broken
  - ShellScript: fixed a possible internal error
- Linux
  - Preferences: table columns were too narrow

## Other Noteworthy Changes
- all editors, Find/Replace dialog:
  - set initial focus to replace text if a text was selected and used as search text
  - more compact
- preferences dialog: opens faster
- improved forced-light theme (less dull-gray)
- File Merge: use darker color in change stripes
- updated SWT fixing a couple of bugs
- switch to JRE 25.0.4
- update 7zip to version 26.04
- more graphics became theme-dependent colors
