---
title: "SmartGit 25.1 on Older Linux Systems"
date: "2025-12-18"
categories:
  - "smartgit"
tags:
  - "smartgit"
---

If you have an older Linux system, e.g. Ubuntu 20.04, Linux Mint 20, Redhat or RockyLinux 8.10, you may see an error `SWT OS.java Error: Failed to load swt-pi3, loading swt-pi4 as fallback` or `GLIBC_2.34 not found` when trying to launch SmartGit 25.1.
Then do the following steps to get it started as a workaround:
- download the Tar archive of [SmartGit 25.1](https://www.smartgit.dev/download/),
- download the Tar archive of [SmartGit 24.1](https://www.smartgit.dev/download/archive/),
- unpack both archives
- replace `<smartgit-25.1>/lib/org.eclipse.swt.gtk.linux.x86_64.jar` with the one from SmartGit 24.1

Now you should be able to start SmartGit 25.1.
- open the SmartGit preferences (Edit \| Preferences), page *SmartGit Updates* and select the option *Do not check for new updates* (or, if disabled, *Check and report new updates*)
