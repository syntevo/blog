---
title: "MSI-Installer does not overwrite files reliable"
date: "2009-11-08"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

Some users reported that installing a new version of our [SVN client SmartSVN](http://www.syntevo.com/smartsvn) over a previous version did not work correctly. Starting SmartSVN still showed the old version, although the installation process went well without any error message and the "Programs and Features" item of the Windows Control Panel showed the new installed version.

What has gone wrong? The most important information came from one user who told that he had copied the new .jar files from the [SmartSVN intermediate build](http://www.syntevo.com/smartsvn/intermediate-builds.html) over the old SmartSVN installation, before installing the new SmartSVN version.

Unfortunately, I first could not reproduce the problem, because I used [Altap Salamander](http://www.altap.cz/salam_en/index.html), a classical two-pane file manager which I can recommend, to copy the files from the intermediate build over the old installation. But — thanks to the helpful tips in the [WiX](http://wix.sourceforge.net/) mailing list — I found out, that Altap Salamander copies files in a different way than the Windows Explorer. While the Explorer only changes the file's modification time, Altap Salamander also updates the file's creation time, an important detail when working with MSI.

According to the [File Versioning Rules](http://msdn.microsoft.com/en-us/library/aa368599(VS.85).aspx) of the MSI SDK, the .jar files will be treated by MSI as user data and hence the creation and modification times define whether a file will be overwritten by an update: if the modification time is newer than the creation time, MSI will _not_ overwrite the file when updating.

Originally, our WiX-script for one component/file looked like this

<Component Id="componentSmartsvnJar" Guid="...">
  <File Id="smartsvn.jar" Name="smartsvn.jar" Source="..." />
</Component>

I had to add a RemoveFile element to the component to ensure that the previously existing file always would be removed before installing the new file:

<Component Id="componentSmartsvnJar" Guid="...">
  _<RemoveFile Id="smartsvn.jar" Name="smartsvn.jar" On="both"/>_
  <File Id="smartsvn.jar" Name="smartsvn.jar" Source="..." />
</Component>
