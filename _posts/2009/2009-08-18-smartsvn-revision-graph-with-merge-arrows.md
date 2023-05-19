---
title: "SmartSVN - Revision Graph with merge arrows"
date: "2009-08-18"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

Displaying "merge arrows" in the Revision Graph is a feature which has been requested rather frequently since Subversion has introduced "merge tracking". This request comes mainly from (former) ClearCase users.

My personal expectations regarding this feature haven't been too high. Rather, I was sure that it wouldn't work well for Subversion but result in an overwhelming maze of merge arrows: My concerns were that Subversion tracks its merge information by the _svn:mergeinfo_ property which can grow rather complex. It inherits merge information from merge sources, can contain holes and so on.

Nevertheless, after doing some experiments it turned out that these concerns weren't issues at all. Even for our most complex repository (which contains the shared code base of our products and primarily consists of merge revisions), results were looking promising, as the following screenshot shows:

[![SmartSVN Revision Graph with merge arrows](/assets/images/merge-arrows-small.png)](/assets/images/merge-arrows.png)

The only draw-back is that merge arrows require to scan the _svn:mergeinfo_ for all displayed revisions in the Revision Graph. Currently, SVN provides no efficient way to perform such a query and hence the displaying may take some time.

Finally, we decided that merge arrows will be part of SmartSVN 6.1 and hope to get a first beta build out within the next few weeks.
