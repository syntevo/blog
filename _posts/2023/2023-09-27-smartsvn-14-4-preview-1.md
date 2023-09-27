---
title: "SmartSVN 14.4 preview 1"
date: "2023-09-27"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

The first public preview build for SmartSVN 14.4 is available.

- [Download](https://www.smartsvn.com/preview/)

## New Features or Improvements
- Preferences:
	- unified Font and Color settings, added colors preview with (editable) language specific snippets
	- set low-level property `preferences.font.showFixedWidthOption` to show a combobox limiting the shown fonts to those with fixed widths
- Syntax coloring:
	- ANTLR: support for code blocks, escape sequences
	- Forth support
	- Markdown support
	- Java: support for Java 21 string templates, escape sequences
	- TOML: support for escape sequences
	- Verilog support
	- X86 ASM

## Fixed Bugs
- possible internal error with invalid proxy configurations
- possible internal error when opening a new window and quickly dragging another one
- Changes view:
	- deselecting a file kept vertical scrollbar as-is instead of resetting it
	- did not set editable/non-editable background colors
	- scrolling might stop after certain changes
- Syntax colorings:
	- Cmd: incorrect detection of FOR variables
	- Groovy: incorrect coloring for initial `"` of string
	- PHP: incorrect coloring for `?>` closing `<?php`
	- Python: incorrect detection of number literals with _ and binary literals
- Tree and Table controls: speed-search box appeared at wrong location if it was horizontally scrolled
- Linux: on some systems, e.g. Manjaro with dark default system theme, the focused selection color was hardly to distinguish from the background color

## Other Noteworthy Changes
- text editors:
	- changed whitespace option "Trailing and changed" to "Trailing, in selection and changed blocks"
	- added low-level property `styledtext.useOwnWordBoundaryDetection` to use system word detection
- updated SSHJ to v0.35.0
- Windows: does not create executable temp files
- Linux:
	- detect date format from `LC_TIME` environment variable
	- shows notification if system is configured to not use UTF-8 encoding which might cause problems with non-US-ASCII characters in file names
- MacOS: support for MacOS 14 (Sonoma)
