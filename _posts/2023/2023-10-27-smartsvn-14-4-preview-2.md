---
title: "SmartSVN 14.4 preview 2"
date: "2023-10-27"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

The new public preview build for SmartSVN 14.4 is available.

- [Download](https://www.smartsvn.com/preview/)

Fixed Bugs
----------
- Changes view
    - Images viewer: zooming was incorrectly handled by mouse position
    - Go to next change goes to next file
- GUI: some radiobuttons/checkboxes were not correctly vertically layed out
- Syntax:
    - Markdown: styling did not stop at begin of new list item, header, ...
- MacOS:
    - Preferences, left tree: selection shows white text on light-blue background
- Windows:
    - smartsvnc.exe showed warning

Other Noteworthy Changes
------------------------
- support for MacOS 14.x
- Preferences:
    - Font and Color settings:
        - ability to reset individual colors to their defaults
        - show whitespaces in selection
- Syntax:
    - C(++): show valid and invalid escape sequences
    - Cmd: support "string"
    - Java: support more invalid char literal (escape) sequences
