---
title: "Shelves in SmartSVN"
date: "2010-10-09"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

"Shelves" can be helpful in various situations to "save" the changes of your working copy away for later application. In his [article](http://markphip.blogspot.com/2007/01/shelves-in-subversion.html), Mark Phippard points out five common scenarios:

- **Interrupt** When you have pending changes that are not ready for check in but you need to work on a different task, you can shelve your pending changes to set them aside.

- **Integration** When you have pending changes that are not ready for check in but you need to share them with another team member, you can shelve your pending changes and ask your team member to unshelve them.

- **Review** When you have pending changes that are ready for check-in and have to be code-reviewed, you can shelve your changes and inform the code reviewer of the shelveset.

- **Backup** When you have work in progress that you want to back up, but are not ready to check in, you can shelve your changes to have them preserved on the Team Foundation server.

- **Handoff** When you have work in progress that is to be completed by another team member, you can shelve your changes to make a handoff easier.

# How shelves in Subversion work

In SVN, shelves can be implemented using short-living branches. To have a better distinction from branches, it's advisable to create a new top-level directory _shelves_ in your project, which will receive these branches. Also, shelves are usually assigned to individual users, thus introducing one more level of hierarchy to also keep a large amount of shelves manageable easily. Here is an excerpt of SmartSVN's own repository structure:

/smartsvn  
 + branches  
   + release-6.6  
   ...  
 + shelves  
   + marc  
     + svn-1.7  
     ...  
   + tom  
     + quaqua  
     + docking-manager  
   ...  
 + tags  
   + release-6.6.0  
   + release-6.6.1  
   ...  
 + _trunk_  

# How to use shelves in SmartSVN

In SmartSVN, you have to configure the _tag-branch-layout_ of your project to recognize shelves as well: use **Tag+Branch**|**Configure Layout** and enter branches/\*, shelves/\*/\* in the **Branches** input field.

Now you can shelve your local changes by **Tag+Branch**|**Add Branch**. Enter a reasonable **Name** for the shelve there, in our example e.g. shelves/marc/log-refactoring. Have the **Source** set to **Working Copy** and have **Skip local changes** selected, to start a clean branch. Select **Switch to branch** and finally create the shelf using **Add Branch**.

After the shelf has been created and the working copy has been switched to the shelf, you can commit your local changes using one or more commits, whatever will be appropriate for the purpose of the shelf. You can finally switch back (**Modify**|**Switch**) to the trunk resp. the former branch you had been working and start a new task.

To reintegrate your changes into the desired branch, switch to the desired branch, use **Modify**|**Merge** and pick the shelf.
