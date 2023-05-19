---
title: "Windows: Git error \"size of shared memory region changed\""
date: "2022-12-21"
categories: 
  - "smartgit"
---

One of our users has just reported persistent problems when invoking an **Interactive Rebase** on Windows:

```
sh (25880) shared\_info::initialize: size of shared memory region changed from 56248 to 49080
```

As it has turned out, this was caused by a zombie `bash.exe` process.
After killing the process, the problem was resolved.
