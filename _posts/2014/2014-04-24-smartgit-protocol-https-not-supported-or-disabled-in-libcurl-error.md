---
title: "SmartGit: \"protocol https not supported or disabled in libcurl...\" error"
date: "2014-04-24"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

One of our **Windows** users recently ran into a strange error when trying to clone a GitHub repository, telling him "protocol https not supported or disabled in libcurl...". As it has turned out, he is using **PureData** which seems to cause troubles in combination with Git, according to [this stackoverflow posting](http://stackoverflow.com/a/18352068/241453).

Switching from his custom Git to **SmartGit's bundled Git** has solved the problem for him.
