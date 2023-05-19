---
title: "SmartGit 19.1's auto-stashing of untracked files"
date: "2019-08-29"
categories: 
  - "smartgit"
---

A couple of users have complained about changes to the auto-stashing behavior in version 19.1 (compared to 18.2): for various history-related operations (like reordering, squashing of splitting commits), SmartGit 19.1 is now requiring a clean working tree where SmartGit 18.2 did not and also Git command line does not.

In general, SmartGit considers untracked files more important than Git in various places (if not important, why not ignore them?). This is especially true for history-related operations, for which SmartGit is now using Git's interactive rebase feature. It's not clear whether all of these operations in combination with the interactive rebase can cope perfectly with untracked files for different scenarios (e.g. Modify/Split Commit). Hence, we require a clean working tree in general.

However there is some problem in SmartGit 19.1's logic though: SmartGit is not stashing untracked files by default, because certain SmartGit users think that SmartGit must not touch untracked files at all. That's behavior already present in version 18.2.

Now, combining both, you will run into the problem that SmartGit will ask you to auto-stash before performing a history-related operation, but then will not actually stash the untracked files and hence the operation fails because the working tree is not clean.

A quick solution to the problem is to enable stashing of untracked files in the **Preferences**, section **Commands**, **Stash**. For 19.2 we will try to be more selective here when to require a clean working tree and when not.
