---
title: "Taking programmatic control over SmartSVN"
date: "2009-10-15"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

While SmartSVN is running, it can receive commands to be executed, like _opening a file compare for a versioned file_. This is how the Windows Explorer Integration and the Mac OS X Finder Integration are working. This article will show how to use this socket-based command API for custom integrations of SmartSVN.

First of all, SmartSVN has to be started, either normally or by supplying the \--server-mode command line parameter (requires Java 6) which prevents a project window to occur. On Windows you may execute: bin/smartsvn.exe --server-mode. On Unix you may use bin/smartsvn.sh --server-mode. A platform-independent way to start SmartSVN is java --jar smartsvn.jar --server-mode which will work fine on Mac OS X.

Once SmartSVN has been started, it will create a port\-file within its settings directory immediately. It contains the port number for client connections. To perform a SmartSVN command, a new _socket_ should be created connecting to this port at host _127.0.0.1_, then the communication can start.

The protocol is very simple: The client sends the _command name_, terminated by \\n. Then it sends the absolute file paths to be used by the command, every path on a separate line, terminated by \\n. Finally it sends one more empty line, i.e. just \\n. For example:

get-states
d:\\\\working-copy\\\\a.txt
d:\\\\working-copy\\\\b.txt
d:\\\\working-copy\\\\c.txt
(empty line)

Note, that the text has to be escaped like character and string literals have to be escaped in Java source code, e.g. on Windows the backslash \\ has to be escaped \\\\.

Depending on the command, SmartSVN will return a response. In case of our get-states example, this could be:

d:\\\\working-copy\\\\a.txt <tab> unchanged
d:\\\\working-copy\\\\b.txt <tab> unchanged
d:\\\\working-copy\\\\c.txt <tab> modified
(empty line)

Here, file a.txt and b.txt are reported as _unchanged_ while file c.txt is modified.

Actually, only the get-states command has a response. For all other commands the socket will be closed immediately after having received the final trailing empty line. Other available commands are:

- add
- annotate
- cleanup
- commit
- compare
- ignore
- lock
- unlock

- log
- rename
- remove
- resolve
- revert
- revision-graph
- update

For example, to open SmartSVN's File Compare for c.txt, following lines should be sent:

compare
d:\\\\working-copy/c.txt
(empty line)

When implementing a communication with SmartSVN's server it may be helpful to set the logging level for the _smartsvn.server_ category to _debug_. For details refer to the [Technical Articles](http://www.syntevo.com/smartsvn/techarticles.html?page=debugging.logging).

The [attached Java class](./files/smartsvn/UsingSmartSVNServerMode.java) contains a complete example implementation, which connects to a running SmartSVN instance, scans a working copy directory for a _modified_ file and then opens the File Compare.
