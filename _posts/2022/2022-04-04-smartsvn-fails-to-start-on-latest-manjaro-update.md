---
title: "SmartSVN fails to start on latest Manjaro update"
date: "2022-04-04"
categories: 
  - "smartsvn"
tags: 
  - "linux"
  - "smartsvn"
---

If SmartSVN does not start any more on some Linux systems, e.g. Manjaro, the file ~/.config/smartsvn/14.2/logs/log.txt.0 might indicate a problem loading libcrypt.so.1. This could be related to a recent update of the **glibc** bundle where /usr/lib/libcrypt.so.1 had been removed. To fix this, please find out which bundle contains this file now:

`$ pacman -F libcrypt.so.1`

On Manjaro one has to install the libxcrypt-compat bundle.
