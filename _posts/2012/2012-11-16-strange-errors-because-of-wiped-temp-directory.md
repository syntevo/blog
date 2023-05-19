---
title: "Strange errors because of wiped temp directory"
date: "2012-11-16"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A couple of users reported strange bugs of SmartGit. Their sent log files revealed that some other application seemed to have cleared SmartGit's temp directory while it was running. We've got following mail from Jon Phipps who seem to have found a possible reason. We thank him for letting us know and want to share his experience:

I just wanted to let you know of a problem with the temp folder and MenuEverywhere. It seems that when **MenuEverywhere** starts up at login, some applications that use the system temp folder have a problem: the temp folder is cleared a few minutes after they start. If MenuEverywhere is started _after_ these programs the problem doesn't occur, so the fix is to not launch it at startup or not run it at all (I would miss it).

I've noticed this with both Microsoft Word 11 and Syntevo SmartGit 3 -- it took me forever to track down MenuEverywhere as the problem, but it's definite.

I'm running version 1.9.9 (1806) on OS X Lion 10.7.5.

On my mac the cleared folder is: /private/var/folders/gm/kkh0yd4d4\_z6s90s9szzj69c0000gn/T/ which is the tmpdir... TMPDIR=/var/folders/gm/kkh0yd4d4\_z6s90s9szzj69c0000gn/T/ ...and seems to be deleted and immediately reopened about 2 minutes after Smartgit or Word startup.

See [this thread](http://answers.microsoft.com/en-us/mac/forum/macoffice2011-macword/word-error-message-word-cannot-save-or-create-this/fa4162a0-ddc4-425d-b9b1-68c0d1f26887) too: _"I found the problem. I was using the program MenuEverywhere because I have multiple monitors. I disabled MenuEverywhere, deleted it from my computer, restarted my Mac and the problem was gone. Word works again. "_

I copied this message to Syntevo support, since this is a problem that seems to have come up more than once for them and I've been fighting it for months.
