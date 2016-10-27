<properties
    title="required"
    pageTitle="在我們的技術文件中使用的自訂 Markdown 擴充功能"
    description="Lists the custom markdown extensions that enable embedded videos, notes and tips, reusable content, and other item in powerbi.microsoft.com technical articles."
    services=""
    solutions=""
    documentationCenter=""
    authors="mblythe"
    manager="dongill"
    editor=""/>

<tags
    ms.service="contributor-guide"
    ms.devlang=""
    ms.topic="article"
    ms.tgt_pltfrm=""
    ms.workload=""
    ms.date="09/09/2015"
    ms.author="mblythe"/>

## Markdown for powerbi.microsoft.com

For general markdown tips, see <bpt id="p1">[</bpt>Markdown Basics<ept id="p1">](https://help.github.com/articles/markdown-basics/)</ept> and our <bpt id="p2">[</bpt>markdown cheatsheet<ept id="p2">](./media/documents/markdown-cheatsheet.pdf?raw=true)</ept>. If you need to create article crosslinks in markdown, see the [linking guidance] (./create-links-markdown.md#markdown-syntax-for-acom-relative-links.md/).

powerbi.microsoft.com supports <bpt id="p1">[</bpt>fenced code blocks<ept id="p1">](https://help.github.com/articles/github-flavored-markdown/#fenced-code-blocks)</ept> and <bpt id="p2">[</bpt>syntax highlighting<ept id="p2">](https://help.github.com/articles/github-flavored-markdown/#syntax-highlighting)</ept>. However, Power BI supports only one syntax highlighting color scheme, regardless of the language you specify in a code block.

## 在我們的技術文件中使用的自訂 Markdown 擴充功能

我們的文章會針對大部分的文章格式 (段落、連結、清單、標題等) 使用 GitHub 形式的 Markdown。 以下是我們目前使用的擴充功能：

+ [附註和秘訣]
+ [Includes]
+ [內嵌的影片]
+ [技術與平台選取器]

## 附註和秘訣

您可以選擇 4 種類型的附註和秘訣︰

- AZURE.NOTE
- AZURE.WARNING
- AZURE.TIP
- AZURE.IMPORTANT

###使用方式
一般而言，整篇文章中應儘量少用附註和秘訣。 當您使用它們時，請選擇適當類型的附註或提示︰

- Use AZURE.NOTE to highlight neutral or positive information that emphasizes or supplements key points of the main text. 附註會提供僅適用於特殊情況的資訊。

  ![](./media/custom-markdown-extensions/Notes-note.PNG)

- Use AZURE.WARNING to alert the user to a condition that might cause a problem in the future. 例如，選取特定選項或進行特定選擇，可能會將您永久鎖定於特定的案例中。

  ![](./media/custom-markdown-extensions/Notes-warning.PNG)

- Use AZURE.TIP to help your users apply the techniques and procedures described in the text to their specific needs. 秘訣或許也會建議可能不明顯的替代方法。 不過，秘訣不需對內文有基本的了解。

  ![](./media/custom-markdown-extensions/Notes-tip.PNG)

- Use AZURE.IMPORTANT to provide information that is essential to the completion of a task.

  ![](./media/custom-markdown-extensions/Notes-important.PNG)

雖然這些附註和秘訣支援程式碼區塊、影像、清單和連結，但請試著以簡單又直接的方式來保留您的附註和秘訣。 如果您發現自己建立了具備大量格式設定的複雜附註，這可能暗示您在文章的主文中應該需要另一個段落。 此外，文章中有太多附註可能會讓人分散注意力，而且很難瀏覽或閱讀。

###範例 Markdown

The samples all show a AZURE.NOTE. 若要使用 TIP、WARNING 或 IMPORTANT，請在 Markdown 中取代 "NOTE"：

    > [AZURE.TIP]

    > [AZURE.WARNING]

    > [AZURE.IMPORTANT]

單一段落：

    > [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Power BI account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。

多個段落：

    > [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Power BI account.
    >
    > If you don't have an account, you can <bpt id="p1">[</bpt>create a free trial account<ept id="p1">](http://www.windowsPower BI.com/pricing/free-trial/)</ept> in just a couple of minutes.

## Includes

Reusable text fragments in our GitHub repository are called "includes". 當您需要在多篇文章中使用某些文字時，可以在 Markdown 檔中包含文字片段的參考。 The text fragment (the include) itself is a simple markdown (.md) file. 它可以包含任何有效的 Markdown，包括文字、連結和影像。 All include markdown files must be in <bpt id="p1">[</bpt>the /includes directory<ept id="p1">](https://github.com/azure/powerbi-content/tree/master/includes)</ept> in the root of the repository. When the article is published, the include text is seamlessly integrated into the published topic.

- We use a specific syntax to reference an include.

- Media files you put in an include must be created in a media folder specific to the include. Media folders for includes belong in <bpt id="p1">[</bpt>the powerbi-content/includes/media folder<ept id="p1">](https://github.com/azure/powerbi-content/tree/master/includes/media)</ept>. The media directory should not contain any images in its root. If the include does not have images, then a corresponding media directory is not required.

###使用方式

- Use includes wherever you need the same text to appear in multiple articles.
- Includes are meant to be used for significant amounts of content - a paragraph or two, a shared procedure, or a shared section. 不要針對比一個句子還少的內容使用語彙基元；它們不適用產品名稱或不完整的句子。
- Don't embed includes within other includes. 發佈系統中發生問題！
- 不要在檔案之間共用媒體。 Use a separate file with a unique name for each include and article. Store the media file in the media folder associated with the include.
- Don't use an includes as the only content of an article.  Includes are meant to be supplemental to the content in the rest of the article.
- Because all includes must be in the /includes directory, the path to an include from an article is always

    ../includes

- Do NOT repeat a link or image filename reference in both the article and the include. Add "-include" to the link reference or media filename to avoid repeating the reference:

 **連結參考**

 Change: odata.org To: odata.org-include

 **影像參考**

 Change: table.png To: table-include.png

###範例 Markdown
The syntax for adding an include to a documentation article is:

    [AZURE.INCLUDE [include-short-name](../includes/include-file-name.md)]

範例

    [AZURE.INCLUDE [howto-blob-storage](../includes/howto-blob-storage.md)]

The first part of the include is the include name without the path and without the .md extension. The second part is the relative path to the include in the /includes directory, with the .md extension.

###轉譯

In the rendered GitHub page, the include will render as follows:

 [AZURE.INCLUDE howto-blob-storage]

In the rendered HTML on powerbi.microsoft.com, the HTML from the includes is merged into the rest of the document's HTML. However, the HTML will contain an HTML comment with the original include markdown filename and the GitHub commit hash. 基於疑難排解用途包含此註解，如此一來，就可輕易地在 GitHub 中識別並找出來源內容︰

  ![](./media/custom-markdown-extensions/include.png)


## 內嵌的影片

Our technical articles will support embeddeded videos in technical articles, details are TBD (Azure requires Channel 9, but we want to use YouTube).


## 技術與平台選取器

> [AZURE.NOTE] This info is for Azure but we might adopt selectors in the future.

當您針對同一篇文章撰寫多個版本來處理跨技術或平台實作的差異時，請使用技術文件中的技術與平台切換程式。 對開發人員而言，這通常最適合我們的行動平台內容。 目前有兩種不同類型的選取器：[簡單的選取器](#simple-selectors)和[雙向選取器](#two-way-selectors)。

Because the same selector markdown goes in each topic in the selection, we recommend placing the selector for your topic in an include, then referencing that include in all of your topics that use the same selector.

###<a id="simple-selectors"></a>簡單的選取器

簡單 (單向) 的選取器會轉譯為標題正下方的一組選項按鈕。 Use these buttons when customers only need to choose from topics in a single platform or technology set, such as .NET, Node.js, and Java.  Please use the below custom markdown format for any selectors.  Do not use HTML for selector functions.  

請參閱[開始使用通知中樞](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/)來了解作者如何針對同一篇文章建立 8 個版本，但使用了選取器來瀏覽這些所有版本。

![簡單的選取器範例](./media/custom-markdown-extensions/selectors.PNG)

####語法

    > [AZURE.SELECTOR]
    - <bpt id="p1">[</bpt>Link #1 Label<ept id="p1">](link #1 url)</ept><ph id="ph1">
    - </ph><bpt id="p2">[</bpt>Link #2 Label<ept id="p2">](link #2 url)</ept>

範例：

    > [AZURE.SELECTOR]
    - <bpt id="p1">[</bpt>Universal Windows<ept id="p1">](../articles/notification-hubs-windows-store-dotnet-get-started/)</ept><ph id="ph1">
    - </ph><bpt id="p2">[</bpt>Windows Phone<ept id="p2">](../articles/notification-hubs-windows-phone-get-started/)</ept><ph id="ph2">
    - </ph><bpt id="p3">[</bpt>iOS<ept id="p3">](../articles/notification-hubs-ios-get-started/)</ept><ph id="ph3">
    - </ph><bpt id="p4">[</bpt>Android<ept id="p4">](../articles/notification-hubs-android-get-started/)</ept><ph id="ph4">
    - </ph><bpt id="p5">[</bpt>Kindle<ept id="p5">](../articles/notification-hubs-kindle-get-started/)</ept><ph id="ph5">
    - </ph><bpt id="p6">[</bpt>Baidu<ept id="p6">](../articles/notification-hubs-baidu-get-started/)</ept><ph id="ph6">
    - </ph><bpt id="p7">[</bpt>Xamarin.iOS<ept id="p7">](../articles/partner-xamarin-notification-hubs-ios-get-started/)</ept><ph id="ph7">
    - </ph><bpt id="p8">[</bpt>Xamarin.Android<ept id="p8">](../articles/partner-xamarin-notification-hubs-android-get-started/)</ept>

#### 轉譯

The image above shows the rendering on powerbi.microsoft.com. 在轉譯的 GitHub 頁面中，選取器會轉譯為連結的項目符號清單。

###<a id="two-way-selectors"></a>雙向選取器

雙向選取器可讓使用者從雙向矩陣中選取主題。 This is essential when an Azure technology, such as Mobile Services, supports multiple backend platforms as well as multiple clients. 請記住下列事項︰

- While it was designed as <ph id="ph1">`(Platform | Backend)`</ph>, the dropwdown text can now be customized.
- 您不需要針對矩陣中的每個點使用清單項目，但只能有一個主題 URL 存在且不重複的項目。
- 儘管連結通常是另一個 GitHub 主題，但其可以是任意的 URL。

請參閱[開始使用行動服務](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/)來了解作者如何針對同一篇文章建立 15 個版本 (9 個行動用戶端平台，2 個後端平台)，但使用了選取器來瀏覽這些所有版本。 請注意，有 3 篇文章不需要這兩個後端版本。

![雙向選取器範例](./media/custom-markdown-extensions/selector-list.png)

####語法

    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )] <ph id="ph1">    - </ph><bpt id="p1">[</bpt>(Dropdown1Text1 | Dropdown2Text1 )<ept id="p1">](../articles/dropdown1-text1-dropdown2-text1.md)</ept><ph id="ph2">
    - </ph><bpt id="p2">[</bpt>(Dropdown1Text1 | Dropdown2Text2 )<ept id="p2">](../articles/dropdown1-text1-dropdown2-text1.md)</ept><ph id="ph3">
    - </ph><bpt id="p3">[</bpt>(Dropdown1Text2 | Dropdown2Text3 )<ept id="p3">](../articles/dropdown1-text1-dropdown2-text1.md)</ept><ph id="ph4">
    - </ph><bpt id="p4">[</bpt>(Dropdown1Text3 | Dropdown2Text4 )<ept id="p4">](../articles/dropdown1-text1-dropdown2-text1.md)</ept>

範例：

    > [AZURE.SELECTOR-LIST (Platform | Backend )] <ph id="ph1">    - </ph><bpt id="p1">[</bpt>(iOS | .NET)<ept id="p1">](./mobile-services-dotnet-backend-ios-get-started-push.md)</ept><ph id="ph2">
    - </ph><bpt id="p2">[</bpt>(iOS | JavaScript)<ept id="p2">](./mobile-services-javascript-backend-ios-get-started-push.md)</ept><ph id="ph3">
    - </ph><bpt id="p3">[</bpt>(Windows universal C# | .NET)<ept id="p3">](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)</ept><ph id="ph4">
    - </ph><bpt id="p4">[</bpt>(Windows universal C# | Javascript)<ept id="p4">](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)</ept><ph id="ph5">
    - </ph><bpt id="p5">[</bpt>(Windows Phone | .NET)<ept id="p5">](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)</ept><ph id="ph6">
    - </ph><bpt id="p6">[</bpt>(Windows Phone | Javascript)<ept id="p6">](./mobile-services-javascript-backend-windows-phone-get-started-push.md)</ept><ph id="ph7">
    - </ph><bpt id="p7">[</bpt>(Android | .NET)<ept id="p7">](./mobile-services-dotnet-backend-android-get-started-push.md)</ept><ph id="ph8">
    - </ph><bpt id="p8">[</bpt>(Android | Javascript)<ept id="p8">](./mobile-services-javascript-backend-android-get-started-push.md)</ept><ph id="ph9">
    - </ph><bpt id="p9">[</bpt>(Xamarin iOS | Javascript)<ept id="p9">](./partner-xamarin-mobile-services-ios-get-started-push.md)</ept><ph id="ph10">
    - </ph><bpt id="p10">[</bpt>(Xamarin Android | Javascript)<ept id="p10">](./partner-xamarin-mobile-services-android-get-started-push.md)</ept>

#### 轉譯

上圖顯示 azure.microsoft.com 上的轉譯。 在轉譯的 GitHub 頁面中，選取器會轉譯為連結的項目符號清單。

<!--Anchors-->
[附註和秘訣]: #notes-and-tips
[Includes]: #includes
[內嵌的影片]: #embedded-videos
[技術與平台選取器]: #technology-and-platform-selectors

###Contributors' Guide Links

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)
