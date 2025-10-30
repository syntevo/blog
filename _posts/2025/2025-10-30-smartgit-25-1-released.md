---
title: "SmartGit 25.1 released!"
date: "2025-10-30"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

We are delighted to announce the official release of [SmartGit 25.1](https://www.smartgit.dev/).
First, a big thank you to everyone who tried the preview and RC builds and sent feedback -- you helped shape this release.

SmartGit 25.1 comes with

* **AI assistance**
  * AI **commit message generation and rewording**, including background mode using `@ai` and WIP friendly rewording
  * **Automatic stash descriptions** to keep stashes searchable
  * **Explain commits** on demand, with results saved as **Git Notes**
  * **Privacy first** -- explicit opt in per repo/provider, configurable limits, and transparent logging
  * **Your AI, your prompts** -- use a cloud provider or an on-prem LLM, tune prompts, store results as Git Notes
* **Git Notes -- first class in the UI**: pick namespaces, add/view/edit notes, show them in Commit details and the Graph, and push/fetch them
* **Worktrees -- smoother and safer**: branch markers in the Log, smarter checkout into existing worktrees, Add/Remove/Prune commands, early detection of invalid worktrees
* **Octopus merge**: create merges with more than two parents either directly or by amending a merge into a merge commit
* **SmartGit as Credential Helper**: configure once in Preferences and use it for commands invoked from SmartGit or for shell scripts and external tools
* **Forced push policy**: choose between disallow, allow on feature branches (recommended), or allow on all branches
* **Squash commits of different authors**: keep credit with a selected author and `Co-authored-by:` lines
* **LFS improvements**: clear Unexpanded pointer states, helpful tooltips, and faster refresh on large repos
* **Standard window improvements**
  * **Remote management** in All Branches + Tags (Fetch, Rename, Delete, Copy URL, Properties)
  * **My History**: customize Pull Request display and get a **focused rebasing view**
  * **Discard** can now undo complete renames and delete untracked files (with confirmation)
  * **More branch commands**: Push To..., Set Tracked Branch..., Stop Tracking...
  * **Preferences**: manage API tokens and search Low-level Properties; **Update Check channels** for tailored notifications
* **Licensing**: **All features** are available for **non-commercial licenses** (open source, academic, and supported charitable institutions)

Check out [What's New](https://www.smartgit.dev/whats-new/25_1/) for a more detailed list of improvements in version 25.1.

SmartGit is a graphical front-end for the distributed version control systems Git which also can be used to work with Subversion repositories.
SmartGit runs on 64-bit systems of Windows, macOS and Linux.

OpenSource developers, students, teachers or members of certain welfare institutions can request a [free non-commercial license](https://www.syntevo.com/register-non-commercial/).
For commercial use or if support is needed, you can [purchase commercial licenses](https://www.smartgit.dev/purchase/) starting at 59 USD/year net.

[Download SmartGit 25.1](https://www.smartgit.dev/download/)

**Note**: if you already have an existing installation of SmartGit and your license covers updates until 2025-10-30 or later, you will be upgraded automatically during the next couple of weeks.
