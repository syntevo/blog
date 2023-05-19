---
title: "SmartGit 18.2 does not start on (some) Linux systems"
date: "2018-12-21"
categories: 
  - "smartgit"
tags: 
  - "linux"
  - "smartgit"
---

If SmartGit 18.2 does not start on your Linux while SmartGit 18.1 worked fine, the reason might be that 18.1 used GTK2 and 18.2 uses GTK3. Use following instructions to let SmartGit 18.2 use GTK2, too:

1. if the directory ~/.local/share/smartgit exists, please delete it
2. copy lib/org.eclipse.swt.gtk.linux.x86\_64.jar from the SmartGit 18.1 installation to 18.2
3. in bin/smartgit.sh remove the leading # from the line #export SWT\_GTK3=0
4. configure SmartGit to update the installation for new builds (Preferences, page _SmartGit Updates_, option _Update SmartGit application in-place_)
5. ensure, that the installation is up-to-date (About dialog, page _Information_, click the button right beside the _Version_ input field if enabled)

The tasks 2 and 3 you will need to do after each SmartGit update.
