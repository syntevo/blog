---
title: "SmartSVN: missing/unversioned file pairs on OS X"
date: "2015-03-06"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

We are frequently getting bug reports of "normal" files showing up as a missing/unversioned file pairs on OS X.
This happens if they contain non-ASCII characters (like German Umlauts) in their names and they have been added from another platform, like Windows or Linux or directly from the Repository Browser.

## Known Subversion problem

This is a known problem of Subversion: in short, Subversion stores file names "as is".
When adding a file "`schön`" on Windows, its name is stored in this "composed" form in the repository.
When checking out the file on OS X, the filename is converted to "decomposed" form when writing to the file system, resulting in "`scho¨n`".
Thus, `svn status` will see a different file in the working copy than in the repository and hence report the missing/unversioned file pair.
Further details can be found at [Subversion issue #2464](http://subversion.tigris.org/issues/show_bug.cgi?id=2464) and in the [Subversion Wiki](http://wiki.apache.org/subversion/NonNormalizingUnicodeCompositionAwareness).

## Resolution/workaround

Unfortunately, it's currently not clear whether this problem will be solved for Subversion/when the fix will be present.
The only known workaround is to get rid of such special characters in the repository completely:

- in case there are only a few files, you may use the **Repository Browser** to **Rename** the offending files, then update your working copy
- in case there are many files affected, it will be better to check out a fresh working copy on Windows or Linux, rename all offending files in the working copy and finally commit all these renames at once
