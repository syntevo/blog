---
title: "SmartGit 19.1 is now compatible with Git-Flow AVH 1.12"
date: "2019-07-10"
categories: 
  - "smartgit"
---

For SmartGit 19.1, we have changed the internal Git-Flow implementation to be compatible with [Git-Flow-AVH](https://github.com/petervanderdoes/gitflow-avh) (version 1.12.2), as requested in UserEcho [topic #409](https://smartgit.userecho.com/communities/1/topics/409-).

This brings new features, like customizable base branches of features, but also (slightly) alters the behavior of existing functionality. Most of these changes can be switched back to the old behavior by adding the appropriate defaults to  your .git/config . For more details, refer to [here](https://github.com/petervanderdoes/gitflow-avh/wiki/Reference:-git-flow-feature).

Examples:

- **Start Hotfix** only allows to have a single, active hotfix. To allow multiple hotfixes, add Git config option `gitflow.multi-hotfix=true`
- **Start Release** only allows to have a single, active release. To allow multiple releases, add Git config option `gitflow.multi-release=true`
