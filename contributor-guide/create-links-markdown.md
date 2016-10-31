<properties
   pageTitle="Markdown 文件中建立連結" description="說明如何撰寫程式碼 markdown 的交互連結。" metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Power BI 技術內容的連結指引
## 技術文件上 powerbi.microsoft.com 指導方針

| 連結案例 | 指導方針  |
|---------------|-----------|
|正在從 Power BI 文件連結到另一個 Power BI 文件|使用相對連結。 不包含 en-us-我們在相對的連結中的語言地區設定。|
|連結至 MSDN library 主題、 TechNet library 主題或知識庫文件|使用實際連結移至文件或主題，但移除 en-us-我們從連結的語言地區設定。|
|從 Power BI 文件連結至其他網頁|使用直接連結|

### Power BI 相對連結的 markdown 語法

若要從 Power BI 技術文件中建立內嵌連結至另一個 Power BI 技術文件中，使用此連結的格式。

> [AZURE.NOTE] 連結的某些方面仍 TBD b/c 我們需要 github 儲存機制的最終結構。

從子目錄到根目錄中文章的文件連結︰

    [link text](../article-name.md)

Root directory 連結子目錄中的文章中的文件︰ 

    [link text](section-folder/article-name.md)

小節子目錄會連結至另一個區段子目錄中的文件中的文件︰

    [link text](../section-folder/article-name.md)
 
目錄中的文章會連結到同一個目錄中的另一篇文章︰

    [link text](article-name.md)


您不需要建立錨點-在發佈的所有 H2 標題會自動產生。 您唯一必須做的是建立 H2 區段的連結︰

    [link](#the-text-of-the-H2-section-separated-by-hyphens)
    [Create cache](#create-cache)

若要連結至同一個子目錄的另一篇文章中的錨點︰

    [link text](article-name.md#anchor-name)
    [Configure your profile](media-services-create-account.md#configure-your-profile)

若要連結至另一個服務子目錄中的錨點︰

    [link text](section-folder/article-name.md#anchor-name)
    [Configure your profile](section-folder/media-services-create-account.md#configure-your-profile)


## 自訂的 Markdown 連結語法

因為包含檔案位於另一個目錄，所以您必須使用相對路徑，如下所示。 針對從包含檔案到單一文章的連結，請使用下列格式︰

    [link text](../articles/section-folder/article-name.md)
    
深入了解如何使用包含在檔案 [自訂 markdown 擴充功能的指導方針](custom-markdown-extensions.md#includes)。

如果您在包含檔案中內嵌選取器，就能使用這類連結︰ 

    > [AZURE。選取器清單 (Dropdown1 |Dropdown2)]     - [(Text1 |範例 1)](../articles/section-folder/article-name1.md)
    - [(Text1 |範例 2)](../articles/section-folder/article-name2.md)
    - [(Text2 |範例 3)](../articles/section-folder/article-name3.md)
    - [(Text2 |範例 4)](../articles/section-folder/article-name4.md)

若要連結至 Power bi 頁面 （例如 [定價] 頁面上，或不是文件的發行項的任何其他的 SLA 頁面），使用絕對 URL，但省略的地區設定。 此處的目標是讓連結可在 GitHub 中和轉譯的網站上運作︰

    [link text](http://powerbi.microsoft.com/pricing/)

若要測試您的連結，將您的頁面推送至您的 「 分叉 」 檢視中呈現的檢視和發佈至預備環境。 GitHub 版本的頁面上的交互連結應該正常運作，只要 Url 中的目標會出現在您的 「 分叉 」。

我們 [技術文件的 markdown 範本](../markdown templates/markdown-template-for-new-articles.md/) 顯示 markdown 中建立的交互連結，讓所有交互連結會自動程式碼一起結尾的發行項，即使它們顯示內嵌的替代方式。

## 參考樣式連結

您可以使用參考樣式連結，方便讀取您的來源內容。 參考樣式連結會使用簡化的語法來取代內嵌連結語法，讓您能夠將完整的 URL 移至文章結尾處。 以下是 Daring Fireball 範例︰

內嵌的文字︰

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

位於文章結尾處的連結參考︰

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/  
    [3]: http://search.msn.com/

## FWLinks

避免 FWLinks （我們重新導向的系統） powerbi.microsoft.com 內容中。 它們應只作為最後的方法時，您必須建立的連結，您還不知道其 URL 的頁面。 在幾乎不會實際需要。 Power BI，您定義的檔案名稱，讓您知道它將會是事先。 文件庫主題尚未發佈，您可以建立使用主題 GUID，所以您不必使用 FWLink 的連結。

如果您必須在網頁上使用 FWLink，包括 P 參數，讓它永久重新導向︰

    http://go.microsoft.com/fwlink/p/?LinkId=389595

當您將目標 URL 貼到 FWLink 工具時，請記得如果目標連結是 Power BI 或 MSDN 或 TechNet 程式庫移除地區設定。

### 著作指南的連結

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/create-tables-markdown/table-markdown.png
[2]: ./media/create-tables-markdown/break-tables.png
