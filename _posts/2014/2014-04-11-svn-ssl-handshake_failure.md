---
title: "SVN: SSL handshake_failure"
date: "2014-04-11"
categories: 
  - "smartgit"
tags: 
  - "smartgit"
---

Usually, an SSL **handshake\_failure** is caused by providing a bad _client certificate_. If this is not the case, you may add following line to smartgit.properties:

`javax.net.debug=ssl`

and launch SmartGit from the console (on Windows, use smartgithgc.exe). The resulting debug output may give hints on possible other reasons. Sometimes it may still be meaningless as it was the case for a support request we have received today. The relevant part immediately before the error just showed up:

`QThreadPoolThread-12 (smartgit.SZ), READ: SSLv3 Alert, length = 2   QThreadPoolThread-12 (smartgit.SZ), RECV TLSv1 ALERT: warning, handshake_failure   SSL - handshake alert: handshake_failure   QThreadPoolThread-12 (smartgit.SZ), handling exception: javax.net.ssl.SSLProtocolException: handshake alert: handshake_failure   QThreadPoolThread-12 (smartgit.SZ), SEND TLSv1 ALERT: fatal, description = unexpected_message`

As it turned out, the SSLv2Hello protocol needs to be enabled by adding following line to smartgit.properties:

`svnkit.http.sslProtocols=SSLv2Hello,SSLv3`

After restarting SmartGit, the problem should be gone.
