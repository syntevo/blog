---
title: "SmartGit: upgrading to msysGit 1.7.10 (or higher)"
date: "2012-04-24"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

Since _msysGit 1.7.10_, file names are stored using _UTF-8_ encoding internally. This finally makes repositories containing file names with non-ASCII characters compatible to other operating systems, especially Mac OS and Linux. Unfortunately, non-ASCII file names which have been added with older msysGit versions will cause problems immediately after the upgrade and need to be fixed:

For working trees which are clean with _msysGit 1.7.9_ and earlier versions ('clean' means that neither SmartGit nor 'git status' shows any changes), file names containing non-ASCII characters will now show up as _unversioned_ in SmartGit. At the same time, there will be a corresponding _missing_ file showing up with '?'-characters. git status will only show the _unversioned_ file, what actually exposes the same problem. To continue working with such a repository and at the same time make it compatible with other platforms, such file names have to be converted to UTF-8. Following example illustrates how this is done for a test repository which contains one file called '_ä.txt_':

The repository is clean when invoking 'git status' using msysGit 1.7.9, however using msysGit 1.7.10, gives:

\> git status  
\# On branch master  
\# Untracked files:  
\# (use "git add ..." to include in what will be committed)  
#  
\# "\\303\\244.txt"  
nothing added to commit but untracked files present (use "git add" to track)  

In a first step we will use msysGit 1.7.9 to temporarily remove the file from the repository (i.e. you will still need a working installation of msysGit 1.7.9 to perform following step):

\> git-1.7.9 rm --cached ä.txt  
rm '?.txt'  

Now, we will use msysGit 1.7.10 (or higher) to re-add the file:

\> git add ä.txt  

'git status' now properly shows the rename:

\> git status  
\# On branch master  
\# Changes to be committed:  
\# (use "git reset HEAD ..." to unstage)  
#  
\# renamed: "\\344.txt" -> "\\303\\244.txt"  
#  

Finally, we will commit the conversion:

\> git commit -m "File names converted to UTF-8."  
\[master 6286cb7\] File names converted to UTF-8. 
1 file changed, 0 insertions(+), 0 deletions(-)  
rename "\\344.txt" => "\\303\\244.txt" (100%)  

Now SmartGit will show a clean working tree as well. If the repository has been cloned from a central remote, the commit should be pushed and other Git Windows users should be informed that they need to upgrade to msysGit 1.7.10 as well, so they will see correct file names after checking out the commit. If they should encounter problems when trying to check out the commit, it may be necessary to use **Local|Reset** with **Hard** option to _reset_ to this commit.
