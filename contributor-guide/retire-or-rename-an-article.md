<properties pageTitle="Git commands for staging an new or updated article" description="Steps for retiring and renaming articles." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Steps to follow when you retire or change the name of a Power BI technical article

This guidance is for SMEs who are listed as the author of an article that needs to be retired from the technical documentation section of powerbi.microsoft.com. 如果檔案已經重新命名，這些步驟也適用。

If you're a member of our Power BI community and you think an article should be retired for any reason, please leave a comment in the Disqus comment stream for the article to let the author know something is wrong with the article.

SME 作者必須依照幾個步驟來不著痕跡地淘汰內容，以避免在我們從網站淘汰內容時讓網站使用者產生不好的體驗。 刪除文章或變更文章名稱應為不得已之下的最後選擇！

## 步驟 1：管理輸入連結

判斷是否有任何非 Microsoft 輸入連結連結到您的內容。 Frequently, blogs, forums, and other content on the web points to articles. 通常，您可以和部落格擁有者合作來變更這些連結，而且您可以移除或更新來自論壇張貼文章的連結。 Web analytics tools can tell you if there are any high traffic inbound links you might need to manage in this way.

## Step 2: Remove all crosslinks to the article from the technical content repository

1. Ensure you are working in an up-to-date local branch – run <ph id="ph1">`git pull upstream master`</ph> (or the appropriate variation on this command.

2.  Scan the powerbi-content-pr/articles folder and the powerbi-content-pr/includes folder for any articles and includes that link to the article you want to retire, and either remove the crosslinks or replace them with appropriate new crosslinks. You can use a search and replace utility to find the crosslinks if you have one installed. 如果沒有，您可以免費使用 Windows PowerShell！ Here's how to use PowerShell to find the crosslinks:

 a. 啟動 Windows PowerShell。

 b。 At the PowerShell prompt, change into the powerbi-content-pr\articles folder:

 `cd powerbi-content-pr\articles`

 c. 輸入此命令，就會列出包含對您正要刪除之文章的參考的所有檔案：

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  如果您偏好將檔案名稱清單傳送至文字檔 (在此案例中，文字檔是命名為 psoutput.txt)，您可以：

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. Add and commit all your changes, push them to your fork, and create a pull request to move your changes from your fork to the master branch of the main repository.

## Step 3: Update the FWLink tool

Check the FWLink tool for any FWLinks that might point to the article. Point any FWLinks at replacement content; if you are not on the alias that owns the link, join it. If the owners won't update the link, file a ticket with MSCOM to have the link changed.

## Step 4: Create a redirect for the retired page, if appropriate

Send mail to mblythe by 4pm on Thursdays - with the URL that you are renaming or retiring and the URL to which it should redirect. He will submit links to engineering on Fridays so that engineering can put 301 redirects in place.

## Step 5: Update the TOC

Remove the TOC entry for the article. If the article was in the "featured" set, make sure the featured articles number is still appropriate.

## Step 6: Retire the article

在您完成前三個步驟，且變更已經生效之後，您就可以將文章從儲存機制刪除。

## Step 7: Remove cached pages from search engines

Go to these web pages to remove cached web pages from search engines: <bpt id="p1">[</bpt>Bing<ept id="p1">](https://www.bing.com/webmaster/tools/content-removal?rflid=1)</ept> and <bpt id="p2">[</bpt>Google<ept id="p2">](https://www.google.com/webmasters/tools/removals?pli=1)</ept>


### Contributors' guide links

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)
