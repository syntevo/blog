---
title: "SmartGit upgrade on MacOS fails with \"Directory '.../AppTranslocation/.../SmartGit.new.app' could not be created\""
date: "2020-06-18"
categories: 
  - "smartgit"
---

Depending on how you run/install SmartGit, on upgrade you may run into read-only file system problems which are caused by App Translocation. This happens:

1. if started directly from the DMG file by double-clicking the SmartGit.app; or
2. if copied from the DMG file to a different location (like Applications) **without using Finder**, e.g. from terminal by cp -R /Volumes/SmartGit\\ 20.1.2/SmartGit.app /Applications

In both cases, in SmartGit's **About** dialog, page **Information**, we can see for **Java Version** a translocated path containing AppTranslocation.

To resolve case (1), we can simply copy SmartGit.app from the DMG file to the preferred location (e.g. "Applications") **using Finder**.

In case of (2), from terminal, we can see that the extended attribute "com.apple.quarantine" is set:

`$ xattr -l SmartGit.app com.apple.quarantine: ...;...;Safari;...`

We can get rid of this attribute using:

`$ xattr -d com.apple.quarantine SmartGit.app`

Now, when restarting SmartGit, the **About** dialog will show the actual installation path.

Credits to: [https://lapcatsoftware.com/articles/app-translocation.html](https://lapcatsoftware.com/articles/app-translocation.html) [https://apple.stackexchange.com/questions/87313](https://apple.stackexchange.com/questions/87313)
