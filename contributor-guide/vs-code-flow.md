<properties
pageTitle="Visual Studio Code - Flow"
description="Walkthough of how to use Visual Studio code with the Power BI repo."
services=""
documentationCenter=""
authors="guyinacube"
manager="mblythe"
editor=""/>

<tags
ms.service="contributor-guide"
ms.devlang=""
ms.topic="article"
ms.tgt_pltfrm=""
ms.workload=""
ms.date="11/09/2015"
ms.author="asaxton"/>

# Visual Studio Code - Flow

This will walk through how you can use Visual Studio Code with the Power BI Git repo. You can download VS Code from https://code.visualstudio.com/.

## 優點

There are a few advantages to using Visual Studio Code instead of another tool, like ATOM.  Mainly because of the Git integration that makes the process a little smoother, and allows you to work within a single tool for most activities. There is also a working files section which makes it nice to ignore the other articles.

## Update your local repro first

You still need to use the Git command line for a few operations.  The first of which is that we should always do a pull before you begin making changes.  This makes sure that your repo/branch is in line with the main Azure master branch.

To pull the updates from Azure/powerbi-content-pr, run the following command.

    git pull Azure master
    
![](media/vs-code-flow/gitpull.png)
 
You will see <bpt id="p1">**</bpt>Azure<ept id="p1">**</ept> listed in the command above.  In your case, it may be <bpt id="p1">**</bpt>upstream<ept id="p1">**</ept>.  You will get an error indicating it doesn't exist.  Also, it is <bpt id="p1">*</bpt>case sensitive<ept id="p1">*</ept>!  You can verify what yours is by doing a <bpt id="p1">*</bpt>git remote show<ept id="p1">*</ept>.

It is a good idea to run a status command to make sure we are in sync.

    git status

![](media/vs-code-flow/gitstatus.png)

In this case, the local repo was ahead of <bpt id="p1">**</bpt>origin<ept id="p1">**</ept>.

As it indicates, just do a <bpt id="p1">**</bpt>push<ept id="p1">**</ept> and <bpt id="p2">**</bpt>origin<ept id="p2">**</ept> should match your local repo.  

    git push

![](media/vs-code-flow/gitpush.png)

## Local folder

This assumes that you already have cloned the repro to your computer, and it resides in a local folder. 

After you open VS Code, go to <bpt id="p1">**</bpt>File<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Open folder...<ept id="p2">**</ept>.  Point it to your local clone folder.  This will display all files in that structure.

![](media/vs-code-flow/vs-code-folders.png)

## Working files

As you edit files, they will display in the <bpt id="p1">**</bpt>Working files<ept id="p1">**</ept> section. You can remove them from working files by clicking on the X next to it.  

This list will persist as you open and close VS Code. It makes for a hand way to focus on the files you won, and ignore the others as noise. The only downside to this area is you can't resize it.

## Markdown preview

You can see the preview of the markdown by doing one of the following.

- Right click on a file and select <bpt id="p1">**</bpt>Open Preview<ept id="p1">**</ept>.

    ![](media/vs-code-flow/vs-code-preview1.png)

- Select the <bpt id="p1">**</bpt>Open Preview<ept id="p1">**</ept> icon in the upper right, when you have the article opened.

    ![](media/vs-code-flow/vs-code-preview2.png)

## Git Commits

This is where VS Code is nice.  As you make changes, VS Code will track the changes you make for checkin purposes.  As you change items, the Git icon, on the left, will have a number indicator next to it showing the number of changes.

![](media/vs-code-flow/vs-code-git.png)

Selecting that icon will show us the list of changes.

![](media/vs-code-flow/vs-code-git2.png)

You can select the <bpt id="p1">**</bpt><ph id="ph1">+</ph><ept id="p1">**</ept> on the <bpt id="p2">**</bpt>Changes<ept id="p2">**</ept> bar by hovering over it.  Or, you can select a <bpt id="p1">**</bpt><ph id="ph1">+</ph><ept id="p1">**</ept> next to each individual file that you want to commit.  Selecting the <bpt id="p1">**</bpt><ph id="ph1">+</ph><ept id="p1">**</ept> will <bpt id="p2">*</bpt>stage<ept id="p2">*</ept> the file.

![](media/vs-code-flow/vs-code-stage.png)

![](media/vs-code-flow/vs-code-stage2.png)

Once you have your files staged, you can add a comment in the message box, and then select the check icon.  The checkmark icon will actually do the commit action for Git.

![](media/vs-code-flow/vs-code-commit.png)

## Pushing the files back to GitHub

Once you have committed some files, you will need to go back to the git command shell and issue a <bpt id="p1">**</bpt>push<ept id="p1">**</ept> command to send it back to GitHub.

    git push

You can keep going back into edit files, commit, and push as you work.

## Pull Request

Once you are don with all of your changes, you will need to issue a <bpt id="p1">**</bpt>Pull Request<ept id="p1">**</ept> which is done on the GitHub site itself.

