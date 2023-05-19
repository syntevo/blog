---
title: "Log vs. Working Tree Window"
date: "2019-03-29"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

From time to time people ask us why we don't implement the Log into the Working Tree window. The answer is: we have already done that the reverse way in version 18.2. Here we have added all working tree features from the main window (now called "Working Tree window") which do not result in (conceptual) problems. Why is the old "main window" still there? Mainly, because it has been there since ever and contains certain functionality which (i) simply does not fit into the new Log window but (ii) which can't be removed to not frustrate existing users. In short, these are

1. open multiple repositories in a group and see all files of them, including their submodules in one view
2. see the exact directory structure of the repository, including the position of the submodules
3. have an optimized display of the current branch's history and optionally of one additional branch in the Journal view
4. show additional columns in the Files view that only make sense for the working tree: Size, Last Changed On

If one of the above points is important to you, you might want to stick with the working tree window. Otherwise, we recommend to make the Log window your main window (this can be configured in the Preferences).

Now in more detail, why the above features do not fit into the Log window:

1. Combining the set of files from multiples repositories works fine, but already now, certain actions will be disabled and certain views (like the Journal) will go blank when having such a "meta-selection" of repositories. Combining log graphs can't be done in a reasonable way and thus the log graph -- the central component of the Log window -- would go blank or only show the "WT/Index" nodes. This is not reasonable and hence we don't provide selection of multiple repositories in the Log window.
2. The Repositories view of the Working Tree window shows exactly the file system content. For the Log window, it's not reasonable to include non-submodule directories in the Repositories view, because then the most intuitive expectation will be to limit the graph to sub-directory commits, too. However, this is problematical:
    1. Filtering Commits based on folders is a quite expensive operation and it will take significant time until the Log is populated. It may even take significant time until the first commit is found and reported, if the repository is large enough and the last commits for the selected directory are old enough. This will make the UI will look sluggish. Also, considering users which are navigating through the Repository tree using keyboard, this will put a significant load on SmartGit.
    2. Sub-directory Logs are seldom used, based on feedback we have received from our users. File Logs are more frequently used, but still rather seldom compared to the repository root Log. Thus, for users, which only want to invoke a command on the sub-directory, it may even be unexpected/unwanted having graph being rebuilt.
    3. Sub-directory and File Logs provide slightly different functionality (e.g. which operations are provided, which Branches categories are displayed), so the same Log window would have to behave differently when in "sub-directory" mode.
3. The Journal view has developed over several SmartGit versions and shows the history in a way optimized for the current branch. The Log graph is no exact replacement for the Journal, hence the Journal must be kept somehow. Having Log view and Journal view present in the same window isn't reasonable, though.
4. The Files view is the central component of the Working Tree window and consists of many columns, for which only a few (like Name, State and Relative Directory) are interesting for the majority of users. Still, lots of other columns are available which either do not make sense for commit files at all or which would be too expensive to populate for commit files. Now, depending on the graph selection (WT vs. Index vs. Commit) we could switch visible and available columns of the Files view. But as most of the additional working tree columns are less important, we decided against providing them at all, in favor of a more stable and less fidgety GUI.
