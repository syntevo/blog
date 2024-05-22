---
title: "Git Vulnerabilities"
date: "2024-05-22"
categories:
  - "smartgit"
tags:
  - "git"
  - "smartgit"
---

Git 2.45.1 fixes the vulnerabilies
- [CVE-2024-32002](https://github.com/git/git/security/advisories/GHSA-8h77-4q3w-gfgv) (critical, Windows and macOS): Git repositories with submodules might cause the `.git` directory to be modified, e.g. to add/override some hooks
- [CVE-2024-32004](https://github.com/git/git/security/advisories/GHSA-xfc6-vwr8-r389) (high, multi-user machine): Remote Code Execution while cloning special-crafted local repositories
- [CVE-2024-32465](https://github.com/git/git/security/advisories/GHSA-vm9j-46j9-qvq4) (high, all setups): Protections for cloning untrusted repositories can be bypassed
- [CVE-2024-32020](https://github.com/git/git/security/advisories/GHSA-5rfh-556j-fhgj) (low, multi-user machines): Cloning local repository by untrusted user allows the untrusted user to modify objects in the cloned repository at will
- [CVE-2024-32021](https://github.com/git/git/security/advisories/GHSA-mvxm-9j2h-qjx7) (low, multi-user machines): Local clone may hardlink arbitrary user-readable files into the new repository's "objects/" directory

We recommend to update to this version:
- install [Git 2.45.1](https://git-scm.com/downloads)
- select that Git executable in SmartGit's preferences, page *Git executables*
