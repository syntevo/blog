---
title: "SmartGit: the new Standard window"
date: "2021-11-23"
categories: 
  - "smartgit"
---

For version 22.1 (currently in development), we have introduced a new main window in addition to the existing Log and Working tree window: we call it the _Standard window_ because it enforces some standards on the way Git is used.

SmartGit is known to be a very powerful and flexible client when it comes to Git functionality. This is especially great for power users, but it may be overwhelming to less experienced Git users. With the Standard window we are closing this gap by channeling Git functionality into workflows, to avoid potential pitfalls.

### Mode-adjusting GUI layout

The most important difference compared to the existing Log and Working tree windows is a GUI layout with different _modes_ for **Local Changes**, **My History**, **All Tags + Branches** and **Stashes**. Every mode serves a specific purpose and is optimized for certain workflows and repository states:

- the visible Git information is restricted to what is required by the workflows
- the toolbar offers the most important operations, guiding the user through the workflows

More specifically,

- the **Local Changes** mode serves for committing, resolving conflicts, searching or modifying local files in the _Working Tree_ and _Index_
- the **My History** mode shows your local branches and will be sufficient for 95% of the daily commit-related tasks
- the **All Branches + Tags** mode gives an overview of all branches and tags and can be used for checking out non-local branches or merging/cherry-picking from these branches
- the **Stashes** mode allows to inspect the content of stashes and to apply or drop them
- the GUI automatically switches between **Local Changes** and **My History**, as appropriate for the current workflow

[![](/assets/images/standard-window-history-1024x669.png)](/assets/images/standard-window-history.png)

### Optimized for common workflows

Another important principle of the Standard window is to make common workflows easier, at the expense of making uncommon workflows harder:

- several operations have less options and sometimes do not even require a dialog anymore (e.g. Push, Pull)
- some operations are more restrictive, e.g., require a clean working copy
- inspired by Git-Flow, we have implemented a robust feature branch life-cycle: **Start**, **Integrate**, **Finish**

### Clean GUI

The mode-adjusting layout allows to give sufficient space for the relevant information. This eliminates the need to permanently resize views. On top of that, the GUI has been further simplified and cleaned up:

- one tab per repository
- clear separation of _Working Tree_ vs. _Index_ vs. _Commit graph_
- sets of independent orthogonal GUI operations have been compressed into simple lists of excluding configurations (for example, show **Changed files** vs. **All files**)

[![](/assets/images/standard-window-local-changes-1024x669.png)](/assets/images/standard-window-local-changes.png)

### Give the Standard window a try

To give the Standard window a try, get SmartGit 22.1 Preview from:

[https://www.syntevo.com/smartgit/preview/](https://www.syntevo.com/smartgit/preview/)

You need to have a commercial license registered.
