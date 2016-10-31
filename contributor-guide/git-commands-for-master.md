<properties pageTitle="建立新的文章或更新現有文章的 Git 命令" description="Power BI 技術處理步驟的內容的 GitHub 儲存機制。" metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# 建立新的文章或更新現有文章的 Git 命令


## 標準程序 （從主要）
遵循您的電腦上建立本機工作分支，以便您可以建立新的發行項的技術文件區段的 powerbi.microsoft.com 或更新現有的發行項的這篇文章中的步驟。

![](./media/git-commands-for-master/githubcommands1.png)

1. 啟動 Git Bash （或您使用 Git 的命令列工具）。

 
            **注意︰** 如果您使用公用儲存機制中，變更 powerbi-內容-pr powerbi 內容中的所有命令。

2. Powerbi-內容-pr 變更︰

        cd powerbi-content-pr
3. 查看主要分支︰

        git checkout master

4. 建立新本機工作分支衍生自主要分支︰

        git pull upstream master:<working branch>


5. 將移至新的工作分支︰

        git checkout <working branch>

6. 可讓您知道您建立的本機工作分支的分岔︰

        git push origin <working branch>

7. 建立您的新文章或變更現有的文章。 使用 Windows 檔案總管] 來開啟並建立新的 markdown 檔案，以及使用 Atom (http://atom.io) 做為 markdown 編輯器。 在您建立或修改您的文章和影像之後，請移至下一個步驟。

8. 加入並認可您所做的變更︰

        git add .
        git commit –m "<comment>"
        
   或者，您也可以加入只特定檔案，以將您修改︰

        git add <file path>
        git commit –m "<comment>"

9. 更新您的本機工作分支的變更與上游︰

        git pull upstream master

10. 在 GitHub 上的變更發送至您的 「 分叉 」:

        git push origin <working branch>

12. 當您準備好要送出您預備、 驗證和/或發行上游主要分支的內容在 GitHub UI 中，提取要求從建立分叉主要分支。

13. 提取要求接受器會檢閱您的提取要求、 提供意見反應，及/或接受您的提取要求。 

14. 確認您的發行的項或變更

 http://powerbi.microsoft.com/documentation/articles/*name-of-your-article-without-the-MD-extension*

**注意：**

- 在此階段中，一旦 10 時間是太平洋標準時間 (PST)，週一至週五周圍每日發行技術文件。 請記住，提取要求已被接受之前執行的下一個排程發佈中所含的變更。
- 如果您是在專用的儲存機制中工作的員工，所有的提取要求受限於需要加以處理之前提取要求可接受的驗證規則。 
- 私用的儲存機制中自動預備您送出的變更和暫存連結寫入中提取要求。 請檢閱您設置的內容，並登入的提取要求註解，表示變更已準備好要推入即時。 如果您不想要接受的提取要求，如果您只預備變更-加入提取要求該便箋。

## 使用發行分支

當您使用發行分支之後時，從版本分支建立本機工作分支的最佳方式是使用這個命令語法︰

    git checkout upstream/<upstream branch name> -b <local working branch name>

這會建立本機分支直接從上游分支，避免任何本機合併。

