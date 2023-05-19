---
title: "Tuning rebase performance on Windows"
date: "2021-09-20"
categories: 
  - "smartgit"
---

One of our Windows users has reported that _rebasing_ a large feature branch takes significantly longer with recent SmartGit versions.

SmartGit comes with its own Git bundled which we are usually updating for every major SmartGit release. As it turns out, since Git version 2.26, the _rebase backend_ has been switched from "apply" to "merge" which is in general superior, but which seems to run slower on Windows, at least for specific scenarios (we couldn't identify any significant slowdown on Linux).

To improve rebase performance to pre-Git 2.26, you can switch back to the old "apply" backend. To better understand whether this is a viable solution for you, first make sure that the [subtle differences between both backends](https://git-scm.com/docs/git-rebase/2.26.0#_behavioral_differences) will be acceptable. If so, you may configure per-repository:

`$ git config rebase.backend apply`

or globally:

`$ git config --global rebase.backend apply`
