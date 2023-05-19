---
title: "Tips for Migrating from CVS to SVN"
date: "2009-10-09"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

I was asked by a couple of CVS users who want to start with SVN (using our [SVN client SmartSVN](http://www.syntevo.com/smartsvn)) about some tips how to avoid common pitfalls. So, from my personal experience and from problems we have got reported by our users, I would consider following issues as notable:

With SVN you don't have tags and branches as a built-in feature like in CVS. Instead, tags and branches are handled by using special paths and SVN's cheap copy feature. **Don't try to reinvent the wheel but better stick with a default repository layout**:

repository-root  
\[-\] project1  
| \[-\] branches  
| | \[+\] branch1  
| | \[+\] branch2  
...  
| \[-\] tags  
| | \[+\] tag1  
| | \[+\] tag2  
...  
| \[+\] trunk  
\[-\] project2  
| \[-\] branches  
| | \[+\] branch1  
| | \[+\] branch2  
...  
| \[-\] tags  
| | \[+\] tag1  
| | \[+\] tag2  
...  
| \[+\] trunk  
...  

Quite often people check out the whole repository or project including all tags and branches. Don't do that but **only check out either the trunk or a specific tag or branch**. It is quite easy to "switch" between them.

With CVS it often was common practice to add a certain tag to only a few files. **Forget about tagging individual files in SVN.** SVN can tag (aka copy) large parts of the repository as effective as just a small part. Another advantage of tagging always the full repository is that you are able to switch easily to that project state. If you have used file-based (not (only) project-based) tags in CVS and history doesn't really matter to you, better import fresh project states in the SVN repository and don't convert the CVS repository to SVN.

A lot of projects consist of multiple parts. With CVS you might have used CVS modules or shell scripts to check out from different repository locations or different repositories. **SVN's [externals](http://www.syntevo.com/smartsvn/documentation.html?page=commands.externals) are a much better concept** and should be used instead.
