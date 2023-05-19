---
title: "Twitter Poll: should the Log by default always show the working tree node (it will still be easy to switch off)?"
date: "2021-03-12"
categories: 
  - "smartgit"
---

We are frequently contacted by users which are wondering why certain Git operations in the Files view are not available or why certain toolbar buttons are grayed out. Usually, it turns out that this is caused by having the HEAD commit selected instead of the invisible working tree node: if the working tree is unmodified, it will be hidden by default and thus to have all operations available it must first be revealed using the Graph's Home button (house symbol).

There is already the **Show Working Tree Permanently** option in the Graph's options menu, but it's not the default and thus the vast majority of users don't recognize it.

[![](/assets/images/poll-permanent-wt.png)](/assets/images/poll-permanent-wt.png)Our **proposed solution** to this problem is to make **Show Working Tree Permanently** the default. This will make the working tree functionality in the Log more obvious and easier to invoke. Users which prefer to not see the unmodified working tree can simply toggle the option off.

Poll: [https://twitter.com/smartgithg/status/1370385647719084040](https://twitter.com/smartgithg/status/1370385647719084040)
