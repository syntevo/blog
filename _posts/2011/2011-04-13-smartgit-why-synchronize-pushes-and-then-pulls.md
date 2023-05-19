---
title: "SmartGit: why Synchronize pushes and then pulls?"
date: "2011-04-13"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

A couple of SmartGit users wondered why the Synchronize command first pushes, then pulls and not doing the reverse order.

Well, if SmartGit would first pull and then push, local changes either would be rebased on top of the pulled remote changes or remote changes silently merged to local changes. **This would mean to push untested changes.**

SmartGit first tries to push, then pulls. If the push failed because of remote changes, you will have the remote changes already locally available and can test **the local changes** before pushing them by invoking Push or Synchronize a second time.

**Summary:** just treat the Synchronize command as a convenient and save Push
