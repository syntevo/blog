---
title: Running SmartGit 25.1 on ARM64 Linux
date: 2025-12-19
categories:
  - smartgit
tags:
  - smartgit
---

SmartGit can easily be configured to run on ARM64/AArch64 based Linux systems:

## Prerequisites

### Git
Ensure Git and Git LFS are installed on your system (`sudo apt install git git-lfs`).
`git version` should show `2.50.1`.

## Steps

1. Download and extract the SmartGit `.tar.gz` archive from [smartgit.dev](https://www.smartgit.dev/download/) to your preferred installation directory.

2. Remove the `jre/` and `git/` directories from the SmartGit installation directory

3. Unpack the AArch64 OpenJDK:
  - download the **AArch64 / ARM64** tar.gz-bundle of, e.g., [Microsoft OpenJDK](https://docs.microsoft.com/en-us/java/openjdk/download)
  - unpack it as `jre/` directory inside the SmartGit installation directory

4. launch `bin/smartgit.sh`

5. Create a startmenu item (optionally): execute `bin/add-menuitem.sh`

### Summary

The installation has been tested and verified on:
- Raspberry Pi 5 with Ubuntu 25.10
- Ubuntu 24.04 running in Parallels on Apple M2 Pro Mac

While the procedure should work on other Linux/Debian/Ubuntu versions, compatibility has only been verified with the configurations listed above.
