---
title: "Use Flatpak-based File Compare"
date: "2025-06-11"
categories:
  - "smartgit"
  - "smartsvn"
tags:
  - "smartgit"
  - "smartsvn"
---

To invoke a GUI file compare tool that you have installed as flatpak bundle, please follow these steps:

- find out the full path of *flatpak*: `which flatpak`
- find out the name of your file compare tool: `flatpak list`
- in the SmartGit/SmartSVN preferences:
	- add a new *Diff tool* with the
		- Command: full path *flatpak*, e.g. `/usr/sbin/flatpak`
		- Arguments: `run <name-of-tool> ${leftFile} ${rightFile}`, e.g. `run io.github.mightycreak.Diffuse ${leftFile} ${rightFile}`
