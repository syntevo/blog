---
title: "Start Developing Plugin for SmartSVN Enterprise"
date: "2009-09-19"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

SmartSVN Enterprise offers a Plugin-API which allows to add own functionality to SmartSVN. In this article I want to show how to configure IntelliJ IDEA to compile a sample plugin and how to launch SmartSVN to load this plugin. Of course you should be able to use any other Java IDE, too.

Ensure that SmartSVN is installed and configured. It must have an Enterprise (demo) license registered. [How to get an Enterprise demo license](http://www.syntevo.com/smartsvn/comparison.html#pluginapi-non-enterprise).

Now create a project structure:

- create an empty directory (we will use C:\\projects\\mergeInfoColumn) as the root for the project
- create a lib directory and copy all .jar files from the SmartSVN installation into it (svnkit-cli.jar is not required and hence can be skipped)
- create a src directory and unpack the mergeInfoColumn directory from the plugin-sources.zip of the SmartSVN installation into it.

![](/assets/images/01-project-structure.png)

Create a new project in IDEA and add a Java module mergeInfoColumn and configure its Sources, Paths and Dependencies according to the following screenshots.

![](/assets/images/02-plugin-module-sources.png)

Remember this output path, we will need it later, so SmartSVN can load the plugin:

![](/assets/images/03-plugin-module-paths.png)

Every SmartSVN plugin depends on the openapi.jar, the mergeInfoColumn plugin also requires the svnkit.jar to compile:

![](/assets/images/04-plugin-module-dependencies.png)

Open the compiler settings and ensure that .properties files are copied from the sources to the classes directory.

![](/assets/images/05-compiler-properties.png)

To launch SmartSVN you will need all its jar files, hence we create another module named launcher just for launching purposes. Add all the .jar files from the lib directory as dependency. To ensure that the mergeInfoColumn module is also compiled before launching, add it also as dependency:

![](/assets/images/06-launcher-module-dependencies.png)

Create a Run/Debug configuration. Use the main class SmartSVN and tell SmartSVN where to look for the plugin classes by setting the VM property smartsvn.pluginLocations. Use the compiler output path configured above. You can use absolute paths, but also, as shown in this screenshot, relative ones.

![](/assets/images/07-run-debug-configuration.png)

Now you should be able to launch SmartSVN. If everything is done right, you should see "Plugin ... loaded." message on the console immediately after SmartSVN start up.

![](/assets/images/08-launch-success.png)
