---
title: "Be sure that core.ignoreCase matches your OS!"
date: "2020-04-24"
categories: 
  - "smartgit"
---

When copying repositories back and forth between Windows and Linux/MacOS, you may end up either with _core.ignoreCase=false_ on Windows or _core.ignoreCase=true_ on Linux. Both configurations will usually cause troubles and are not supported by Git \[1\].

To avoid this, you may unset the _core.ignoreCase_ configuration in your repository root:

`$ git config --unset core.ignoreCase`

As Git's internal default is _false_, there is nothing more to do on Linux/MacOS. On Windows, you have to add _core.ignoreCase=true_ as global default:

`$ git config --global core.ignoreCase true`

\[1\] https://git-scm.com/docs/git-config#Documentation/git-config.txt-coreignoreCase
