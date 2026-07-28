---
title: "SmartSynchronize 4.7 preview 1"
date: "2026-07-28"
categories:
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

The first public build of **SmartSynchronize 4.7** is available for download.

- [download](https://www.syntevo.com/smartsynchronize/preview)

## New Features and Improvements
- File Manager:
  - Create Dir: optionally also open directory
  - Create File: optionally also open the editor
  - Delete Directory: 1s delay after determined files to delete to easier cancel the operation
    (low level property `fileManager.deletePhysical.delayForDir`)
  - Directory sorting is applies recursively now
  - File Viewer: allow to open editor
  - Multi-Rename-Dialog:
    - make remembering pattern explicit
    - show reg-ex input fields
  - Preferences: add color/theme configuration
  - Sort directories always by name (option)
- Syntax:
  - Dart: string improvements
  - Go: escape sequences, word-select in strings
  - Git config
  - ERB: improve frontmatter
  - Markdown: use much better parser
  - Rust: escape sequences, word-select in strings, support for lifetimes
  - Vlang: improve strings, string interpolation, escape sequences
- Compare, Merge, Editor:
  - support language-specific word-definitions for caret movements/double-click
  - improve added/removed/changed coloring
- Preferences: for search, also highlight "Low-level Properties"
- rework icons; different variants for light and dark theme
- theme improvements (e.g. darker dark theme)

## Fixed Bugs
- Compare, Syntax-based: shift blocks similar to other options
- Directory compare, Changes view:
  - colors differ for line number gutter and block borders
  - inner line change for multi-line-inner-line change not shown
  - hidden-change markers are not drawn when making window smaller
  - go to next/prev change shortcuts did not work
- File compare:
  - internal error when using Grammarly
  - dark theme: gets light background when focused
  - background might be drawn over text
  - Double-click (word-wise navigation), Shell-Script: variables with underscores are not treated as word
  - Connector: fix outline y coordinates
- File Editor: with autosave enabled, one can't close the window if directory is gone
- File Manager:
  - Unpack from inside archive: assertion if archive contains multiple entries for the same path
  - Multi-Rename-dialog, replace pattern editor: don't trim spaces
  - Copy from Archive: did not preselect the name (while it did for copying from file system)
  - Pasting a file path in double-quotes ignored the last character inside the quotes
  - Line number might not be aligned correctly with text
- File Viewer: pressing `End` might not go to the end of the file (if lines are excessively long)
- Preferences:
  - Editor-colors:
    - possible internal error by importing file containing not all required colors
    - don't create backup directory
- Themes:
  - Toolbar (forced light theme): hover-border not visible
  - Forced dark theme on light system theme: separators in status line are too bright
- Theme-properties files: "depends" properties not correctly loaded
- Toolbar (Windows): shows tooltip only after a second move
- Syntax:
  - Basic: possible internal error with unicode
  - C: incorrectly parsed `#XXX` lines
  - C#: verbatim string fixes
  - JavaScript, TSX file: interpolated string treated as identifier
  - Markdown:
    - Html block not detected
    - internal error for line "# a #"
  - Powershell: possible internal error with non-closed string
  - Properties: values with `\` at EOL are not correctly detected
  - Shell-Script: parse bug for escaped character
  - Verilog: `x` is erroneously treated as bin number instead of identifier
  - XML: several fixes
- Linux:
  - can't launch if a monitor has > 200% zoom
  - windows may occur on "wrong" monitor
  - "jumpy" selection when double-clicking `..` entry in File manager
  - first dialog shows with weird size
  - MX Linux: no browser can be found though installed
  - WSL:
    - Browser can't be opened
    - tooltip background is wrong
- MacOS:
  - alternating row colors for tables were broken
  - filtered file table keeps yellow state
  - tooltip is unreadable (MacOS 14 with dark system theme)
  - dark system theme: selection-color lines (selected toolbar button, tab bar) hardly noticable
  - Compare: with Japanese IME unwanted `\n` are inserted
  - text editors, compare: do not allow to go to text start/end

## Other Noteworthy Changes
- added low-level property `ui.speedSearch` to allow character accelerators in tables/trees (= prevent speed-search catching these characters)
- added low-level property `beep.enable` to disable a beep
- confirmation dialogs: some buttons may be shown in red indicating dangerous choices (not on MacOS)
- "Execute in Terminal": support for `konsole`
- File Manager:
  - favorites: create default "Home" and "Downloads" entries for Windows, too
  - Multi-Rename-dialog, find pattern editor: don't trim spaces
  - for corrupt archives with duplicate entries, take the first ones
- File Editor:
  - shorter (adaptive) delay of syntax refresh after typing
- File Merge:
  - use darker colors in change stripes
- Font: if Japanese locale is detected, the font "BIZ UDゴシック" or "ＭＳ ゴシック" are used
- notifications:
  - ability to copy text, either selected or all
  - larger, but less prominent close button
- Preferences:
  - add basic accessibility information for tables
  - low-level properties: remove confirmation button and show all by default
  - improve speed when opening (only loading controls of currently visible card)
- Syntax:
  - Pascal/Delphi: add default extension .pp (used by Free Pascal)
- Text "editors": allow to configure (additional) line spacing
- Themes:
  - (forced) Light theme: less dull-gray
- Toolbar: show highlight bar for selected toolbar button
- updated 7z to version 26.02
- updated SSHJ
- Linux:
  - Tree: cursor-left on a collapsed node should select the parent node
  - File systems: report also `/media/<user>/` paths
- Windows:
  - on high-DPI monitors use SWT's default scaling
