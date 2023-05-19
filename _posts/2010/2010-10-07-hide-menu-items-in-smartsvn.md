---
title: "Hide menu items in SmartSVN"
date: "2010-10-07"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

To hide SmartSVN, the default plug-in hideMenuItems.jar is responsible. This means, that this tip only works with SmartSVN Professional or Enterprise which can launch plug-ins. If not already available, SmartSVN will create the file menuItemsToHide.config in its [settings directory](http://www.syntevo.com/smartsvn/documentation.html?page=installation#installation.home) on application start and fill it with all known menu item IDs:

`# Uncomment entries to hide them   #add   #annotate   #apply-patch   #changeset-delete   ...`

To hide a menu item, you have to open this file in a text editor and remove the leading comment character # in front of the lines containing the ID of the menu item to hide, e.g.:

`# Uncomment entries to hide them   #add   #annotate   apply-patch   #changeset-delete   ...`

Save the file and restart SmartSVN.
