---
title: "SmartSVN fails to load on Fedora 30"
date: "2019-05-06"
categories: 
  - "smartsvn"
tags: 
  - "linux"
  - "smartsvn"
---

If SmartSVN fails to load apr-1 on Fedora 30, it most likely is caused by the [removal of libcrypt.so.1](https://fedoraproject.org/wiki/Changes/FullyRemoveDeprecatedAndUnsafeFunctionsFromLibcrypt). To fix, you need to install the **libxcrypt-compat** bundle: `sudo yum install libxcrypt-compat`
