---
title: "SmartGit SVN integration: end-of-life announcement"
date: "2021-02-28"
categories: 
  - "smartgit"
---

SmartGit's SVN integration will be discontinued on Dec 31, 2022. We have decided to take this step because the amount of users of the SVN integration is steadily decreasing and is already less than 1% of overall Git users. On the other hand, the SVN integration affects many code parts, making them harder to maintain/change. Also, the support effort for non-default SVN server layouts is quite high. When putting increased maintenance effort into relation to the low number of users, we believe that dropping the SVN integration will be beneficial for our overall user base.

### What does that mean for you?

If you are **not** accessing SVN repositories, this will not affect you at all. Note that former SVN repositories which have been converted to Git once and since then are only used as Git repositories (i.e. no more pulling/pushing back to SVN) are actually pure Git repositories and thus will not be affected.

If you are actually still accessing SVN repositories, you can continue using the latest major version released before Dec 31, 2022 even after this date (of course, only on the operating systems supported by these versions) to clone/push/pull to your SVN repositories. There will be no more bug-fixes to the SVN integration for these versions after Dec 31, 2022, though.

For major versions released after Dec 31, 2022 the pure Git functionality will continue working with already cloned SVN repositories, but pulling/pushing (or cloning new repositories) to/from SVN servers will not be possible anymore.

We recommend to convert your SVN repositories to Git or use [SmartSVN](https://www.smartsvn.com) to access them.
