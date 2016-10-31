<properties pageTitle="Git 命令批次新的或更新的發行項" description="預覽全新和更新文件的步驟。" metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Git 命令批次內部預覽網站上的發行項

私用儲存機制提取要求現在就會自動執行。 請參閱 [Git 命令來建立新的發行項或更新現有的發行項](git-commands-for-master.md)

> [AZURE.NOTE] 將會重新審視這份文件，並新增根據我們如何設定接移適當的資訊。

<!--
Follow the steps in this article to stage content to the internal staging site prior to releasing the article to the public site.

[AZURE.IMPORTANT] The preview site is available for internal Microsoft contributors only. If you're an internal contributor, see the internal wiki to get the URL of the preview site.

![](./media/git-commands-for-sandbox/githubcommands2.png)


1. Start Git Bash.

2. Change to powerbi-content-pr:

        cd powerbi-content-pr

3. Check out the sandbox branch:

        git checkout sandbox
        
   Note: If you just cloned, you probably only have the master branch on your computer. You can run 'git branch' to see the     list of branches on your local computer. If sandbox is missing, run:
   
        git pull upstream sandbox:sandbox
        git checkout sandbox
        git pull upstream sandbox

4. If you get a merge conflict for files that aren’t yours, use these commands to copy the version of the conflicted file from the server to your local branch, resolving the conflict:

        git checkout upstream/sandbox articles/<filename.md>
        git commit –m "resolving merge conflict"

5. Move the file or files you want to stage from the local master-derived branch to the local sandbox-derived branch you are working in:

        git checkout <master-derived-local-branch> articles/<article_name.md>

 To move the media:

        git checkout <master-derived-local-branch> articles/media/<folder_name>

6. Commit the files in sandbox:

        git commit –m "<moved files to sandbox for staging>"

7. Push the changes to your fork on GitHub:

        git push origin sandbox

8. Create a pull request from your fork to the core repo, from your local sandbox-derived branch to the main sandbox branch:

 ![](./media/git-commands-for-sandbox/pullrequestsandbox.png)

9. The pull request acceptor accepts the pull request.

10. Review your content on the staging site. If you are happy with the staged content, go back to master and follow the steps to push your final version to your fork, and then file a pull request. Articles are staged three times a day, around 10 AM, 2 PM, and 5 PM PST.

 Don’t edit your article while working in a sandbox-derived branch. If you discover issues you need to fix after you stage, change back to your master-derived working branch, make the changes there, and then restage. Moving content to sandbox should always be a one-way trip.-->




