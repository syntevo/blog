---
title: "Importing a Git repository into a Subversion repository"
date: "2012-06-26"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

In the following, we will assume that you have a Git repository in a directory named _git.repo_, with 3 commits in the master branch.

Step 1. Prepare the SVN repository. If it doesn't exist yet, create it and run svnserve to make it accessible:

$ svnadmin create svn.repo

$ svnserve -d -r svn.repo

Then open _svn.repo/conf/svnserve.conf_  and set _anon-access=write_.

Now your SVN repository can be accessed via svn://localhost. If you already have an SVN repository, create a directory for a new project in it and use the SVN URL of that directory instead of svn://localhost for the rest of this tutorial.

SmartGit can handle repositories with the standard trunk/branches/tags layout, as well as repositories without any specific layout (i.e. just a directory with data in it). However, it's highly recommended to use the aforementioned standard layout. Let's create these standard directories:

$ svn mkdir svn://localhost/trunk svn://localhost/branches svn://localhost/tags -m "Initial structure."

Committed revision 1.

Step 2. With SmartGit, clone svn://localhost into a new directory. We'll name it "svn.clone". SmartGit will autodetect an existing trunk/branches/tags layout and, if one exists, configure Git to map SVN branches to Git branches.

Step 3. Now you can transfer commits from your local Git repository at _git.repo_ to your SVN repository at _svn.clone:_

$ cd svn.clone

$ git fetch /tmp/git.repo refs/heads/master:refs/heads/fetched  
warning: no common commits  
remote: Counting objects: 9, done.  
remote: Compressing objects: 100% (3/3), done.  
remote: Total 9 (delta 0), reused 0 (delta 0)  
Unpacking objects: 100% (9/9), done.  
From /tmp/git.repo  
 \* \[new branch\]      master     -> fetched

Now _svn.clone_ contains all commits of the _master_ branch from _git.repo_.

Step 4. We now need to apply these commits on top of refs/heads/trunk branch in _svn.clone_. This can be done with the Git rebase or Git cherry-pick operation. Here we'll do this with rebase: Open _svn.clone_ in SmartGit and select Branch | Rebase. Choose the "Selected commit(s) to HEAD" option. On the next page, select the commit marked with _fetched_. Make sure the "Commit Range" option is selected. Press Rebase.

Step 5. Push commits to SVN. To do so, simply press Push.
