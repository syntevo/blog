---
title: "SmartSynchronize 4.6.3"
date: "2025-09-29"
categories:
  - "smartsynchronize"
tags:
  - "smartsynchronize"
---

This **SmartSynchronize 4.6.3** release comes with a couple of bug fixes, and MacOS 26 support.
We recommend to update.

- [download](https://www.syntevo.com/smartsynchronize/download/)

## Fixed Bugs
- Directory compare: possible internal error in Changes view
- Editor controls: possible internal error changing font
- File Manager: internal error unpacking from inside 7z archive with multiple entries for same path
- Syntax:
	- C#: several fixes
	- Properties: values with `\` at end of line were incorrectly detected
	- XML: several fixes
- Linux:
	- first dialog shows up with weird size
	- browser might not be found
- MacOS:
	- alternativing row colors for tables were broken (enable by setting `table.allowAlternatingRowColorsOnMacOS`)

## Other Noteworthy Changes
- update bundled 7z to version 25.01
- officially support MacOS 26 Tahoe
