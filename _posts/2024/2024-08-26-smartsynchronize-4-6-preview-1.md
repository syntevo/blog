---
title: "SmartSynchronize 4.6 preview 1"
date: "2024-08-26"
categories:
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

The first public build of **SmartSynchronize 4.6** is available for download.

- [download](https://www.syntevo.com/smartsynchronize/preview)

## New Features and Improvements
- File Manager:
	- Multi-File-Rename:
		- remembers last renames
- File Compare:
	- optional syntax-based tokenizing
	- Ignore Whitespace option reworked (single on/off option instead of three)

## Fixed Bugs
- File Manager:
	- SFTP: if deleting a remote file failed, no error was shown
	- Viewer: possible OOME
	- Windows:
		- Edit Link: did not work for C:\Foo because C:\ does not allow to create temp files
	- Linux:
		- File Finder, Reveal: failed to bring window to front
		- Ubuntu 22.04: some operations like Pack did not start until the user clicked the progress dialog
- Compare:
	- non-US-ASCII characters may change line height
- Syntax:
	- ANTLR: did not support \u{12345} escapes
	- C#: failed to parse character literal, verbatim, interpolated strings, string escapes, ...
	- Java: incorrect parsing of text blocks containing double-quotes
	- JavaScript:
		- incorrect parsing of @
		- incorrect parsing of recursive template mode
	- Pascal: did not know 'const' keyword
	- Perl: several parsing problems
	- Ruby:
		- incorrect parsing of @
		- support for heredoc
	- Shell script: incorrect parsing of $
	- Swift:
		- incorrect parsing of @
		- identifiers could contain unicode characters, e.g. emojis
	- XML: internal error for file with Git conflict markers
	- several: possible internal error for files with Windows line endings
	- parsing failed if token ended with 32-bit char, e.g. emoji
- Text editors:
	- Linux: internal error undoing changes after having typed Chinese characters with Pinyin
	  workaround for this SWT bug: https://github.com/eclipse-platform/eclipse.platform.swt/issues/1213
- Linux:
	- table columns by default too narrow
	- tree control: cursor-right did not send expand event
	- WSL: if appending Windows path is disabled, browser windows can't be opened
- MacOS:
	- fix v-alignment of controls, especially in preferences dialog, page User Interface


## Other Noteworthy Changes
- File Manager:
	- Copy Name/Path: ability to copy multiple entries (one line per entry)
	- Directory table, Sorting: fix sorting by name (this will ensure, that "foo.txt" is sorted before "foo-2.txt")
	- Goto Opposite Directory: becomes main menu item
	- Text viewer, search: only select Case-Sensitive, if the user enters a letter with shift pressed
	- external applications are launched with settings directory as default instead of installation directory (to prevent upgrade failures of locked directory)
	- Linux:
		- list also mounted file systems from gvfs under /run/user/<uid>/gvfs/
- Compare:
	- Compare: inner-line diff improvements for small equal areas at beginning/end
	- Compare: inner-line diff improvements for lines with many identical characters
- Proxy: support for NO_PROXY and no_proxy environment variables
- Text editors:
	- Find and Replace: if the selection matches, use that for the first replace
	- Move/select word: make customizable using low-level property `styledtext.wordCaretMovementType`
	- optionally save on deactivate
- Syntax coloring:
	- support for Gettext (.po) files
	- Markdown:
		- allow `_` inside text, e.g. URLs
		- quote fix and <links> support
	- Verilog: more literal formats
- JRE 21
- Linux:
	Directory compare: preview does not show SVG files as graphic (because it was not supported on other systems; and the supported SVG features were very limited)
