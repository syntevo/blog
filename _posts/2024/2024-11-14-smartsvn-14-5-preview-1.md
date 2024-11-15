---
title: "SmartSVN 14.5 preview 1"
date: "2024-11-14"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

The first public preview build for SmartSVN 14.5 is available.

- [Download](https://www.smartsvn.com/preview/)

## New Features or Improvements
- support for MacOS 15 (Sequoia)
- upgrade to SVN 1.14.4 binaries (containing security fixes)
- Changes view:
	- Ignore WS (whitespace) button
- Changes view, File Compare:
	- experimental support for syntax-based tokenizing
	- inner-line diff improvements for small equal areas at beginning/end, or with many identical characters
- Externals dialog:
	- support multi-selection
	- Set to:
		- Latest revision
		- HEAD
- File Compare:
	- Find and Replace: if the initial selection matches, use that for the first replace
- Merge, Revision Chooser dialog: show unmergable revisions in gray
- Preferences:
	- Authentication:
		- replace *Show Password**s*** with *Show Password*
		- add *Show Password* for SSHl and SSH credentials
	- Text Editors:
		- Font Family: show checkbox *Show only fixed-width fonts*
- Syntax:
	- support for Gettext (`*.po`) files

## Fixed Bugs
- Annotate:
	- "Changes since" used too light background hardly noticable
	- "by-Author" coloring was dark even with light theme
- Changes view, File Compare:
	- non-US-ASCII characters might increase line height causing weird effects when scrolling
- completion popup: default selection was not always visible
- File Compare: Export to HTML used hard-to-read colors with dark theme
- Preferences:
	- Tools: Add/Edit dialog may grow too large
- Syntax:
	- multiple languages: `\` before line ending
	- ANTLR: did not support `\{12345}` escape
	- C++: support 0x0C as whitespace; problems with some number literals
	- C#: failed to parse `"` in character literal; support verbatim, interpolated strings, string escapes
	- HTML: incorrect parsing
	- InnoSetup: problems with strings; support for `{}` comments in `[code]` section
	- Java: buggy parsing of text blocks containing `"`
	- JavaScript/TypeScript: problems with `@`; recursive template mode
	- Groovy: problems with `@`
	- Markdown: characters >= 0x80 caused problems; allow `_` in text, `<`link`>` support
	- Pascal: `const` should be keyword
	- Perl: incorrect parsing
	- PHP: `<?` can occur inside tag arguments
	- Ruby: problems with `@`; heredoc support
	- Shell: emojis support; conditional expression support; `$`-problems
	- Swift: identifiers can contain unicode characters, e.g. emojis; problems with `@`
	- Verilog: more literal formats, more keywords
	- XML: problem with `&`; internal error for files containing conflict markers
- Window | Reset Perspective: kept previous layout
- Linux:
	- maximizing a window remembered location (0, 0) for unmaximized bounds
	- Ubuntu 24.04: did not restore maximized state
	- text controls: internal error undoing changes after having typed Chinese characters with Pinyin
	- tables: default column width too narrow
	- Exit: temp directory could not be cleared
	- Branch browser: double-clicking to check out a different branch selects the next ref after the previous HEAD ref, too
	- multiple issues with forced light-theme on dark system theme
	- WSL: if appending Windows path was disabled, browsers could not be opened
- MacOS:
	- tooltip might cause dialog to be shown behind of parent
	- fixed alignment of controls, especially in preferences
- Windows:
	- File monitoring: fix for Windows directory mounts

## Other Noteworthy Changes
- Text controls: added low-level property `styledtext.wordCaretMovementType` to support word-wise caret movement configuration and double-click behavior
- Changes view:
	- Goto Prev/Next change: don't move caret into the opposite direction
	- Linux: don't support SVG images by default (the support was incomplete and not supported for other systems)
- Changes view, File Compare: use unfocused selection color only if other text control became focused
- JIRA:
	- better default query for Select from JIRA
	- improved authentication dialog
	- Resolve dialog: improve wording
- upgrade to Java 21
- upgrade to SSHJ 0.38.0
- upgraded SWT
- support for `no_proxy` and `NO_PROXY` environment variables
