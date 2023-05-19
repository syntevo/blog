---
title: "Hard crash when viewing certain files on Linux"
date: "2015-03-16"
categories:
  - "smartgit"
tags:
  - "smartgit"
---

A few users have reported that SmartGit might crash when viewing certain files in the Changes preview of the repository or log window, or Compare. Until now this has to been reported only for Linux. Fortunately, a friendly user provided the details to make it reproducible for us.

When a Java process crashs hard, it will create a file hs\_err\_pid<id>.log in the current working directory. For this problem it should start with following lines

#
# A fatal error has been detected by the Java Runtime Environment:
#
#Â  SIGSEGV (0xb) at pc=0xb48a75e0, pid=2501, tid=3064257344
#
# JRE version: Java(TM) SE Runtime Environment (8.0\_40-b26) (build 1.8.0\_40-b26)
# Java VM: Java HotSpot(TM) Client VM (25.40-b25 mixed mode linux-x86 )
# Problematic frame:
# J 10 C1 java.lang.String.charAt(I)C (29 bytes) @ 0xb48a75e0 \[0xb48a75d0+0x10\]
#
# Failed to write core dump. Core dumps have been disabled. To enable core dumping, try "ulimit -c unlimited" before starting Java again
#
# If you would like to submit a bug report, please visit:
#Â Â  http://bugreport.java.com/bugreport/crash.jsp
#

---------------Â  T H R E A DÂ  ---------------

Current thread (0xb6807c00):Â  JavaThread "main" \[\_thread\_in\_Java, id=2502, stack(0xb69fd000,0xb6a4e000)\]

siginfo: si\_signo: 11 (SIGSEGV), si\_code: 2 (SEGV\_ACCERR), si\_addr: 0xb69fdffc

Registers:
EAX=0x82237f88, EBX=0x8015b558, ECX=0x84e4eab8, EDX=0x000076bb
ESP=0xb6a01ffc, EBP=0xb6a3227c, ESI=0x000076bb, EDI=0x84e4eab8
EIP=0xb48a75e0, EFLAGS=0x00210246, CR2=0xb69fdffc

Top of Stack: (sp=0xb6a01ffc)
0xb6a01ffc:Â Â  b4a3c755 00000000 00000000 00000000
0xb6a0200c:Â Â  00000000 00000000 00000000 000076bb
0xb6a0201c:Â Â  84e4eab8 00000000 00000000 00000000
0xb6a0202c:Â Â  00000000 00000000 00000000 b6a3227c
0xb6a0203c:Â Â  b4a3c3ef 00000000 00000000 00000000
0xb6a0204c:Â Â  00000000 00000000 00000000 00000000
0xb6a0205c:Â Â  00000000 8453a8f8 84e67978 00000000
0xb6a0206c:Â Â  7f2057c8 00000000 00000000 b6a3227c 

Instructions: (pc=0xb48a75e0)
0xb48a75c0:Â Â  f6 a8 05 70 0b 68 01 f8 82 ff 06 90 05 68 00 00
0xb48a75d0:Â Â  90 90 90 90 90 90 90 3b 41 04 0f 85 b0 3f f9 ff
0xb48a75e0:Â Â  89 84 24 00 c0 ff ff 55 83 ec 18 8b f2 83 fe 00
0xb48a75f0:Â Â  0f 8c 1e 00 00 00 8b 41 08 8b 50 08 3b f2 0f 8d 

Register to memory mapping:

EAX=0x82237f88 is pointing into metadata
EBX={method} {0x8015b558} 'match' '(Ljava/util/regex/Matcher;ILjava/lang/CharSequence;)Z' in 'java/util/regex/Pattern$CharProperty'
ECX=0x84e4eab8 is an oop
java.lang.String 
Â - klass: 'java/lang/String'
EDX=0x000076bb is an unknown value
ESP=0xb6a01ffc is pointing into the stack for thread: 0xb6807c00
EBP=0xb6a3227c is pointing into the stack for thread: 0xb6807c00
ESI=0x000076bb is an unknown value
EDI=0x84e4eab8 is an oop
java.lang.String 
Â - klass: 'java/lang/String'

I've reported this bug in regular expression code used for syntax highlighting to Oracle. The only work-around so far to prevent this crash is to disable syntax coloring for such files, e.g. by excluding the file extension from the pattern of the Language's entry in SmartGit preferences (Built-in Text Editors > Languages).
