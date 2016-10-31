<properties pageTitle="Git 命令批次新的或更新的發行項" description="淘汰並重新命名文件的步驟。" metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# 當您淘汰或 Power BI 技術文件的名稱變更時，請依照下列步驟

本指南是文章的供 Sme 列為需要淘汰從 powerbi.microsoft.com 的技術文件區段的作者。 如果檔案已經重新命名，這些步驟也適用。

如果您是我們的 Power BI 社群的成員，而且您認為應該淘汰發行項，因為任何原因，請 Disqus 註解資料流，讓作者就知道有問題的發行項之發行項中保留註解。

SME 作者必須依照幾個步驟來不著痕跡地淘汰內容，以避免在我們從網站淘汰內容時讓網站使用者產生不好的體驗。 刪除文章或變更文章名稱應為不得已之下的最後選擇！

## 步驟 1：管理輸入連結

判斷是否有任何非 Microsoft 輸入連結連結到您的內容。 通常，部落格、 論壇和其他 web 內容會指向文件。 通常，您可以和部落格擁有者合作來變更這些連結，而且您可以移除或更新來自論壇張貼文章的連結。 Web 分析工具可以告訴您是否有任何您可能需要以這種方式管理的高流量輸入的連結。

## 步驟 2︰ 文件移除所有的交互連結從技術內容的儲存機制

1. 請確定您目前處於最新的本機分支 – 執行 `git pull upstream master` （或適當的變體，該命令。

2.  掃描 powerbi 內容 pr/文章資料夾和 powerbi-內容-pr/包含在任何資料夾文件和包含您想要淘汰，發行項，並選擇移除交互連結的連結或以適當的新交互連結加以取代。 您可以使用搜尋和取代公用程式來尋找交互連結，如果您有一個安裝。 如果沒有，您可以免費使用 Windows PowerShell！ 以下是如何使用 PowerShell 來尋找交互連結︰

 a. 啟動 Windows PowerShell。

 b。 在 PowerShell 提示字元中，變更到 powerbi-內容-pr\articles 資料夾︰

 `cd powerbi-content-pr\articles`

 c. 輸入此命令，就會列出包含對您正要刪除之文章的參考的所有檔案：

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  如果您偏好將檔案名稱清單傳送至文字檔 (在此案例中，文字檔是命名為 psoutput.txt)，您可以：

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. 新增和認可您的變更、 將其推送到分叉，並建立將您的變更從您的 「 分叉 」 移至主要分支的主要儲存機制提取要求。

## 步驟 3︰ 更新 FWLink 工具

請檢查發行項可能指向任何 FWLinks FWLink 工具。 指向任何 FWLinks 取代內容;如果您不是在擁有連結的別名，請將它加入它。 如果擁有者將不會更新的連結，票證 MSCOM 變更連結的檔案。

## 步驟 4︰ 建立已停用] 頁面的重新導向，如果適用的話

傳送郵件給 mblythe 下午 4 星期四-含有您要重新命名或淘汰 URL 和應該重新導向的 URL。 他會提交給工程團隊預訂以便工程可以就地將 301 重新導向的連結。

## 步驟 5︰ 更新目錄

移除發行項的目錄項目。 如果發行項是在 「 功能 」 設定，請確定精選的文章數目仍適合。

## 步驟 6︰ 淘汰發行項

在您完成前三個步驟，且變更已經生效之後，您就可以將文章從儲存機制刪除。

## 步驟 7︰ 從搜尋引擎移除快取的頁面

移至這些網頁快取的網頁移除搜尋引擎︰ [Bing](https://www.bing.com/webmaster/tools/content-removal?rflid=1) 和 [Google](https://www.google.com/webmasters/tools/removals?pli=1)


### 著作指南的連結

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)
