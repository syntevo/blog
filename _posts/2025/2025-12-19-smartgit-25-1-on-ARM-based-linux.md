---
title: Running SmartGit 25.1 on Ubuntu ARM Devices
date: 2025-12-19
categories:
  - smartgit
tags:
  - smartgit
---

If you’re trying to run **SmartGit on an Ubuntu system powered by ARM (e.g., Raspberry Pi, Ubuntu on ARM laptops)** you’ve probably noticed that there’s no official ARM build available from Syntevo yet. The standard SmartGit binaries are distributed for x86_64 Linux only, which means they won’t run natively on an ARM-based machine out of the box.

SmartGit can run on ARM64 or AArch64 based Linux systems as it is a Java application. The installation requires providing ARM64-compatible dependencies.

### Prerequisites

#### Git
Ensure Git and Git LFS are installed on your system.
`git version` should  at least return 2.50.1
#### Java
OpenJDK 21 is recommended for running SmartGit on AArch64 architecture.

Either install OpenJDK 21 using, e.g., `apt install openjdk-21-jdk`, or download its tar.gz-bundle from, e.g. [https://docs.microsoft.com/en-us/java/openjdk/download](https://docs.microsoft.com/en-us/java/openjdk/download "https://docs.microsoft.com/en-us/java/openjdk/download") and unpack it, replacing the `jre/` directory inside the SmartGit installation directory.

### Installation Steps

1. **Download SmartGit**  
   Download and extract the SmartGit `.tar` archive from [www.smartgit.dev](https://www.smartgit.dev) to your preferred installation directory.

2. **Strip Bundled Components (Optional)**  
   Remove the `/jre` and `/git` directories from your installation directory to use the system-provided versions.

3. **Create Desktop Shortcut**  
   Execute `add-menuitem.sh` from the `bin` directory within your installation path to create a desktop shortcut.

### Summary

The installation has been tested and verified on:
- Raspberry Pi 5 with Ubuntu 25.10
- Ubuntu 24.04 running in Parallels on Apple M2 Pro Mac

While the procedure should work on other Linux/Debian/Ubuntu versions, compatibility has only been verified with the configurations listed above.



