---
title: "Solution to possible SmartSVN's SASL authentication problems"
date: "2010-03-17"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

For _svnserve_, SASL is configured in the _sasl_ section of _conf/svnserve.conf_, see below.

Depending on the Java Virtual Machine settings, high values for _min-encryption_ may cause the authentication to fail. A solution is either to decrease this value or to upgrade the JVM to support the requested cipher strength.

Another cause for failures may be usage of too old JVMs. SASL authentication requires Java 1.5 or higher.

## A working example

The [conf/svnserve.conf](http://blog.syntevo.net/files/smartsvn/sasl/svnserve.conf) file. For details refer to [here](http://svnbook.red-bean.com/en/1.5/svn.serverconfig.svnserve.html#svn.serverconfig.svnserve.sasl).

In _/etc/sasl2_ there are following files:

\-rw-r--r-- 1 root root 49152 Apr 01 2009 sasldb\_svn  
\-rw-rw-rw- 1 root root 135 Apr 01 2009 svn.conf

The [/etc/sasl2/svn.conf](http://blog.syntevo.net/files/smartsvn/sasl/svn.conf) is automatically read by svnserve (because it advertises itself as "svn"). Its list contains all possible mechanisms to use. When it comes to a handshake only those are used that satisfy _svnserve.conf_ conditions (anonymous access support, encryption support, etc). Users and their passwords are validated against _sasldb\_svn_ database. A possible output of

\# sasldblistusers2 /etc/sasl2/sasldb\_svn

might look like:

alex@svnkit.com: password  
ivan@somewhereelse: password

Only _alex_ has access to the repository with "svnkit.com" realm.
