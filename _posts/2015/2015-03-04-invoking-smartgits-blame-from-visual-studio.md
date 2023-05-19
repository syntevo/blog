---
title: "Invoking SmartGit's blame from Visual Studio"
date: "2015-03-04"
categories: 
  - "smartgit"
---

One of our users has just shared a solution with us to invoke SmartGit's Blame directly from within Visual Studio: in **Tools|External Tools**, SmartGit has to be configured as new tool with appropriate command line parameters:

**Title:**   `Any title you want` **Command:**   `Path to smartgit.exe` **Arguments:**   `--blame $(ItemPath):$(CurLine)`

The configuration might finally look like:

[![blame](/assets/images/blame-300x130.png)](/assets/images/blame.png)

With the tool configured as described, you will just invoke **Tools|Git Blame** when there's a file open, and SmartGit will blame that file and scroll to the line which has the caret in Visual Studio.
