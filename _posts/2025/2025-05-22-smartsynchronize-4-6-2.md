---
title: "SmartSynchronize 4.6.2"
date: "2025-05-22"
categories:
  - "smartsynchronize"
tags:
  - "smartsynchronize"
---

This **SmartSynchronize 4.6.2** release comes with a couple of bug fixes and improvements, mostly related to Linux.
We recommend to update.

- [download](https://www.syntevo.com/smartsynchronize/download/)

## Fixed Bugs
- Syntax:
	- Java: illegal characters could break lexing
	- Scala: `@` breaks lexing
- Linux:
	- switching directories using Ctrl+P popup did not work
	- Directory Compare, preview: images were zoomed blurry

## Other Noteworthy Changes
- Linux:
	- Launcher: don't set `GDK_BACKEND=x11` any more by default as it might causes freezes
	- *Execute in Terminal*: support *Konsole*
