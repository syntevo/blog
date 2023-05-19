---
title: "Start a Command Line Shell Window on Windows"
date: "2009-10-17"
categories: 
  - "smartgit"
  - "smartsvn"
tags: 
  - "smartgit"
  - "smartsvn"
---

When I right click a directory in our [SVN client SmartSVN](http://www.syntevo.com/smartsvn) or [Git client SmartGit](http://www.syntevo.com/smartgit) on Windows — especially the latter, because it does not yet support all Git commands — I want to open a command line shell window. Although it is easy to execute a command with cmd.exe, it seems not _that_ obvious how to open a command line shell window.

Here is the solution:

- open the Preferences and select the page to configure the directory command (in SmartSVN it is named _Directory Command_, in SmartGit _Directory Tool_)
- in the _Command_ input field specify the path to the cmd.exe, for my Windows XP system C:\\Windows\\system32\\cmd.exe
- in the _Arguments_ input field enter  
    /c "start pushd ""${directoryPath}"""

The arguments are the tricky part. Basically, the cmd.exe needs two arguments, /c and the command to execute. Because our command contains spaces, we need to wrap it in quotes. If the actual directory path contains spaces, we need to surround the placeholder with quotes by specifying double quotes. If, for example, the command would be executed for the path E:\\my projects\\foo, the second parameter will actually be  
start pushd "E:\\my projects\\foo"

What does the switches and commands mean? The /c switch tells cmd.exe to execute the following command line parameter as command. The start command makes the command line window occur and the pushd seems to be some kind of hack to switch to the directory which is the next parameter.
