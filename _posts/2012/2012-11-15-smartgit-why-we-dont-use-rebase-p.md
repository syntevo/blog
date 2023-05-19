---
title: "SmartGit: why we don't use \"rebase -p\""
date: "2012-11-15"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

From time to time we are asked why SmartGit does not support the _git rebase -p_ option. I've now tried to rebase my _master_ which contains a merge commit onto a tiny fork '_test_' from an older version of _master_. This is the resulting log graph:

![](images/rebase-p-merge-log.png)

There have been a couple of modified files in my merge commit, probably due to conflicts which we had at the time or merging:

![](images/rebase-p-merge-log-files.png)

Now, a '_git rebase -p test master_' fails at the merge commit and results in following unexpected conflicts (at least from my perspective, as an advanced Git user):

![](images/rebase-p-merge-wt-files.png)

For this reason, we decided to not support _\-p_ for _rebase_ until now. For SmartGit 4 we will detect whether merge commits will be affected by the _rebase_ on Pull and will suggest to _merge_ instead, but still offer to _rebase -p_ as well.
