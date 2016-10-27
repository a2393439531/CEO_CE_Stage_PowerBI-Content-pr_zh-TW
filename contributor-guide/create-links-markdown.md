<properties
   pageTitle="Create links in markdown articles" description="Explains how to code crosslinks in markdown." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Linking guidance for Power BI technical content
## Guidelines for technical articles on powerbi.microsoft.com

| 連結案例 | 指導方針  |
|---------------|-----------|
|Linking from a Power BI article to another Power BI article|使用相對連結。 Do not include the en-us language locale in your relative links.|
|Linking to an MSDN library topic, a TechNet library topic, or KB article|Use the actual link to the article or topic, but remove the en-us language locale from the link.|
|Linking from a Power BI article to any other web page|使用直接連結|

### Markdown syntax for Power BI relative links

To create an inline link from a Power BI technical article to another Power BI technical article, use this link format.

> [AZURE.NOTE] Some aspects of linking are still TBD b/c we need to settle on a final structure for the github repo.

從子目錄到根目錄中文章的文件連結︰

    [link text](../article-name.md)

Article in the root directory links to an article in a subdirectory: 

    [link text](section-folder/article-name.md)

Article in a section subdirectory links to an article that is in another section subdirectory:

    [link text](../section-folder/article-name.md)
 
目錄中的文章會連結到同一個目錄中的另一篇文章︰

    [link text](article-name.md)


You do not have to create anchors - they are automatically generated at publishing time for all H2 headings. 您唯一必須做的是建立 H2 區段的連結︰

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
    
Learn more about how to use an includes file in the <bpt id="p1">[</bpt>Custom markdown extensions guidelines<ept id="p1">](custom-markdown-extensions.md#includes)</ept>.

如果您在包含檔案中內嵌選取器，就能使用這類連結︰ 

    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )] <ph id="ph1">    - </ph><bpt id="p1">[</bpt>(Text1 | Example1 )<ept id="p1">](../articles/section-folder/article-name1.md)</ept><ph id="ph2">
    - </ph><bpt id="p2">[</bpt>(Text1 | Example2 )<ept id="p2">](../articles/section-folder/article-name2.md)</ept><ph id="ph3">
    - </ph><bpt id="p3">[</bpt>(Text2 | Example3 )<ept id="p3">](../articles/section-folder/article-name3.md)</ept><ph id="ph4">
    - </ph><bpt id="p4">[</bpt>(Text2 | Example4 )<ept id="p4">](../articles/section-folder/article-name4.md)</ept>

To link to a page on Power BI (such as a pricing page, SLA page or anything else that is not a documentation article), use an absolute URL, but omit the locale. 此處的目標是讓連結可在 GitHub 中和轉譯的網站上運作︰

    [link text](http://powerbi.microsoft.com/pricing/)

To test your links, push your page to your fork and view it in the rendered view and publish to staging. The cross links on the GitHub version of the page should work as long as the targets of the URLs are present in your fork.

Our <bpt id="p1">[</bpt>markdown template for technical articles<ept id="p1">](../markdown templates/markdown-template-for-new-articles.md/)</ept> shows an alternate way to create crosslinks in markdown so all the crosslinks are coded together at the end of the article, even while they display inline.

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

Avoid FWLinks (our redirection system) in powerbi.microsoft.com content. They should be used only as a last resort when you need to create a link for a page whose URL you don't yet know. They are almost never actually needed. For Power BI, you define the file name, so you can know what it will be ahead of time. For a library topic that is not yet published, you can create a link that uses the topic GUID so that you don't have to use an FWLink.

If you must use an FWLink on a web page, include the P parameter to make it a permanent redirect:

    http://go.microsoft.com/fwlink/p/?LinkId=389595

When you paste the target URL into the FWLink tool, remember to remove the locale if your target link is Power BI, or the MSDN or TechNet library.

### Contributors' Guide Links

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/create-tables-markdown/table-markdown.png
[2]: ./media/create-tables-markdown/break-tables.png
