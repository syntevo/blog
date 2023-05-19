---
title: "Performance Improvements for the Revision Graph"
date: "2009-06-24"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

In contrast to other SVN clients, SmartSVN is caching log information locally in a so-called "Log Cache". The local log information is used to display transactions as well as speeding up the Log and Revision Graph commands.

Generating a Revision Graph from log information is a quite complex operation with SVN (usually the complete repository history has to be analyzed, I don't want to go into the technical details here). So, for instance showing a Revision Graph on the "build.xml" file from our source tree took approx. one minute with SmartSVN 6. Now, with the new optimized storage and code it takes approx. 5 seconds.
