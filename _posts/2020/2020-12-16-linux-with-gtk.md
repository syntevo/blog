---
title: "Linux with GTK &lt;3.20"
date: "2020-12-16"
categories: 
  - "smartgit"
---

SmartGit 20.2.1 will allow to switch to an alternative SWT implementation which supports GTK <3.20. If you are running such a system, SmartGit will tell you on startup. Following steps will be necessary:

1. 1. 1. If you have installed SmartGit < 20.2.1, install the latest bundle from the [SmartGit download page](https://www.syntevo.com/smartgit/download/).
        2. Locate smartgit.vmoptions: usually it's located at ~/.config/smartgit/smartgit.vmoptions (if not present there, check the parent of SmartGit's settings directory, as displayed in the **About** dialog). Add following line to this file: `swtver=4932`
        3. Restart SmartGit: if everything is configured correctly, SmartGit will print an information about a custom SWT version to terminal and should start up properly.
