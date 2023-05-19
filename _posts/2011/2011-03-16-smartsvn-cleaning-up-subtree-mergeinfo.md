---
title: "SmartSVN - cleaning up subtree mergeinfo"
date: "2011-03-16"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

When merging, a common source of confusion are property-only modifications of various files and/or directories which have not actually been affected by the merged commits. Usually, these are modifications only in the _svn:mergeinfo_ property of the respective entries. Why does that happen and how can this be resolved?

_svn:mergeinfo_ is a Subversion-internal property which stores important information used for merge-tracking. Usually, merges should only performed on the trunk or branch **root directory** and hence _svn:mergeinfo_ is also present only on the corresponding root directories.

When performing a merge on a sub-directory, or even a single file, _svn:mergeinfo_ will be introduced on these entries as well. This is how troubles start: once introduced, it will remain and will be updated with every new merge, even when performed only on the root directory. This is the reason, why it's not recommended to perform subtree merges at all. If you still need subtree merges, you unfortunately have to take these _svn:mergeinfo_ inconveniences into account. If subtree merges have happened by accident, there is following receipt to fix this situation:

- Be sure to have a clean working copy and update to _HEAD_.
- Use **Properties|Set or Delete Property** on your trunk or branch root directory, select **svn:mergeinfo**, select **Delete Property**, keep **Depth** set to **Fully recursive** and _unselect_ **Include this directory**
Once finished, all files and sub-directories which previously had _svn:mergeinfo_ attached will show up as modified. From now on there are two ways to go:- The hard one: use **Properties|Edit** to find out which _svn:mergeinfo_ every modified file or directory had before. Manually compare this to the _svn:mergeinfo_ of your root (which should still be present). If revision changes are significant, this indicates that many subtree merges had been performed on the file or directory. Unfortunately, this requires further investigation and you will have to decide whether to **record-only** merge certain revisions to your root, so these subtree-merges will be tracked in the root's _svn:mergeinfo_, too. To get this correct, it may also be necessary to actually merge all other changes outside of the subtree for the record-only revisions. When you are actually faced with this situation, this indicates that subtree merges have been performed by intention and maybe subtree mergeinfo should be kept for the corresponding entry. In this case, you may simply **Revert** your changes to restore the _svn:mergeinfo_ properties.
- The easy way: you may not pay attention to what subtree mergeinfo has been removed and risk unexpected conflicts on later merges. If subtree mergeinfo had been introduced to a couple of files by accident and these subtree merges for these files didn't occur frequently, it will usually be no problem to resolve conflict later (if any at all occur).

In either way, you should be aware that changing respesctively deleting subtree mergeinfo possibly affects Subversion's merge tracking and hence should be performed with caution. For an in-depth understanding, we recommend to read [Paul Burba's](http://www.collab.net/community/subversion/articles/merge-info.html) article.
