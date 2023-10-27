---
title: "SmartSynchronize 4.5 preview 3"
date: "2023-10-27"
categories:
  - "smartsynchronize"
tags: 
  - "smartsynchronize"
---

The new preview build of **SmartSynchronize 4.5** is available for download.

- [download](https://www.syntevo.com/smartsynchronize/preview)

## New Features and Improvements
- Preferences
    - Colors and Font configuration:
        - completely reworked, including snippets for all supported languages
        - added low-level property `preferences.font.showFixedWidthOption` to show checkbox *Show only fixed-width fonts*
        - ability to reset individual colors to their defaults
        - show whitespaces in selection

## Fixed Bugs
- File Manager:
    - Delete: a junction is deleted recursively like a directory
- Directory Compare, Preview:
    - Images viewer: zooming is incorrectly handled by mouse position
    - Go to next change goes to next file
    - did not set configured readonly background color
- Syntax
    - Groovy: initial " of string incorrectly highlighted
    - PHP: incorrect highlighted ?> after <?php
    - Markdown: stop styling at begin of new list item, header, ...
- GUI: some checkboxes/radiobuttons were incorrectly layed out (only noticable on some systems)
- MacOS:
    - Preferences, left tree control: selection shows white text on light-blue background

## Other Noteworthy Changes
- support for **MacOS 14.x**
- Syntax
    - ANTLR: support for code blocks
    - C(++): show valid and invalid escape sequences
    - Cmd: support "string"
    - Java: support for Java 21 String templates and more invalid char literal (escape) sequences
    - Markdown: support for front matter (blog)
