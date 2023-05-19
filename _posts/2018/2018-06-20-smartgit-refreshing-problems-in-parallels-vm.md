---
title: "SmartGit refreshing problems in Parallels VM"
date: "2018-06-20"
categories: 
  - "smartgit"
---

One of our OS X users has reported SmartGit refreshing problems when running in a Windows 10 Parallels VM. SmartGit's low-level Java timers are relying on a "consistent" system time (which will only be advancing). But, as it has turned out, due to clock synchronization issues, this may not be the case for such a setup:

> Finally got to the bottom of this! Turns out to be a mismatch in the way that Parallels is emulating the real-time clock (RTC). When you install under bootcamp it sets this registry key to tell Windows that the RTC is in GMT:
> 
> https://superuser.com/questions/482860/does-windows-8-support-utc-as-bios-time/497666#497666
> 
> Parallels is however incorrectly configured and is emulating the RTC in LOCAL time, not GMT! And for some reason, something in Windows keeps triggering it to correct itself to the RTC while the OS is booted (I can see that in the event logs). Not sure why it does that, but it happens quite regularly during the day. Since the RTC is not correct, it puts the system to LOCAL - 8 hours, (GMT - 16), and if I have the Parallels time sync service active it quickly notices and corrects it.

One way to work-around this problem is to disable the time sync service:

> I have the Parallels time sync service off at the moment and have told Windows to expect the RTC to be in LOCAL time, and now it is all working nicely.
> 
> I have also been on calls with Parallels second level support who is talking to their engineers and they hopefully can make it work correctly in a patch release of Parallels, because if I boot my Mac into bootcamp natively right now the time will be off because Windows will think the RTC is LOCAL time, while in fact the Mac always has it set to GMT.
