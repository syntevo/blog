---
title: "SmartGit/Hg: sparse checkout"
date: "2014-08-29"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

From time to time we are asked whether SmartGit supports _sparse checkout_? The answer is: **it does once configured**. Let's assume you have a remote repository with two top-level directories:

/
/dir1
/dir2

To have a sparse clone of only directory dir1, initialize a new local repository:

$ mkdir sparse
$ cd sparse
$ git init

Enable sparse checkouts in .git/config by:

git config core.sparsecheckout true

Add

dir1/

to .git/info/sparse-checkout, open the repository in SmartGit and use **Remote > Add** to add your remote repository and finally **Fetch** and **Checkout**.

If you already have an existing local repository which you want to make sparse, enable the git config option and configure .git/info/sparse-checkout as above and finally re-read the repository tree using:

git read-tree -m -u HEAD

Now SmartGit will only show dir1.
