<properties
    title="required"
    pageTitle="在我們的技術文件中使用的自訂 Markdown 擴充功能"
    description="列出自訂 markdown 延伸，讓內嵌的視訊、 資訊和秘訣、 可重複使用的內容和 powerbi.microsoft.com 技術文件中的其他項目。"
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

## Powerbi.microsoft.com 的 markdown

一般的 markdown 提示，請參閱 [Markdown 基本概念](https://help.github.com/articles/markdown-basics/) 和 [markdown cheatsheet](./media/documents/markdown-cheatsheet.pdf?raw=true)。 如果您需要在 markdown 中建立文件的交互連結，請參閱 [連結指南] (。 / create-links-markdown.md#markdown-syntax-for-acom-relative-links.md/)。

powerbi.microsoft.com 支援 [納入範圍之程式碼區塊](https://help.github.com/articles/github-flavored-markdown/#fenced-code-blocks) 和 [語法反白顯示](https://help.github.com/articles/github-flavored-markdown/#syntax-highlighting)。 但是，Power BI 支援只有一個語法醒目提示色彩配置，不論您在程式碼區塊中指定的語言。

## 在我們的技術文件中使用的自訂 Markdown 擴充功能

我們的文章會針對大部分的文章格式 (段落、連結、清單、標題等) 使用 GitHub 形式的 Markdown。但我們使用自訂的 markdown 擴充功能，我們需要更豐富的格式化 powerbi.microsoft.com 上呈現的網頁中。 以下是我們目前使用的擴充功能：

+ [附註和秘訣]
+ [包含]
+ [內嵌的影片]
+ [技術與平台選取器]

## 附註和秘訣

您可以選擇 4 種類型的附註和秘訣︰

- AZURE。附註
- AZURE。警告
- AZURE。秘訣
- AZURE。重要

###使用方式
一般而言，整篇文章中應儘量少用附註和秘訣。 當您使用它們時，請選擇適當類型的附註或提示︰

- 使用 AZURE。請注意反白顯示中性或正面的資訊來強調或補充主要文字的關鍵點。 附註會提供僅適用於特殊情況的資訊。

  ![](./media/custom-markdown-extensions/Notes-note.PNG)

- 使用 AZURE。警告來提醒使用者可在未來可能會造成問題的情況。 例如，選取特定選項或進行特定選擇，可能會將您永久鎖定於特定的案例中。

  ![](./media/custom-markdown-extensions/Notes-warning.PNG)

- 使用 AZURE。秘訣協助您套用自己的需求文字中所述的程序和技術的使用者。 秘訣或許也會建議可能不明顯的替代方法。 不過，秘訣不需對內文有基本的了解。

  ![](./media/custom-markdown-extensions/Notes-tip.PNG)

- 使用 AZURE。提供非常重要的工作完成的資訊就很重要。

  ![](./media/custom-markdown-extensions/Notes-important.PNG)

雖然這些附註和秘訣支援程式碼區塊、影像、清單和連結，但請試著以簡單又直接的方式來保留您的附註和秘訣。 如果您發現自己建立了具備大量格式設定的複雜附註，這可能暗示您在文章的主文中應該需要另一個段落。 此外，文章中有太多附註可能會讓人分散注意力，而且很難瀏覽或閱讀。

###範例 Markdown

所有的範例會示範在 AZURE。附註。 若要使用 TIP、WARNING 或 IMPORTANT，請在 Markdown 中取代 "NOTE"：

    > [AZURE.TIP]

    > [AZURE.WARNING]

    > [AZURE.IMPORTANT]

單一段落：

    > [AZURE.NOTE] 若要完成本教學課程，您必須使用中的 Microsoft Power BI 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。

多個段落：

    > [AZURE.NOTE] 若要完成本教學課程，您必須使用中的 Microsoft Power BI 帳戶。
    >
    > 如果您沒有帳戶，您可以 [建立免費試用帳戶](http://www.windowsPower BI.com/pricing/free-trial/) 只需要幾分鐘的時間。

## 包含

我們的 GitHub 儲存機制中的可重複使用的文字片段稱為 「 包含 」。 當您需要在多篇文章中使用某些文字時，可以在 Markdown 檔中包含文字片段的參考。 文字片段 （包含） 本身是簡單的 markdown (.md) 檔案。 它可以包含任何有效的 Markdown，包括文字、連結和影像。 所有包含的檔案必須位在 markdown [包含目錄 /](https://github.com/azure/powerbi-content/tree/master/includes) 儲存機制的根目錄中。 當發行項發行時，包含文字是緊密整合已發行的主題。

- 我們可以使用特定的語法來參考包含。

- 您將放在包含的媒體檔案必須建立媒體資料夾中包含特定。 媒體的資料夾包含屬於 [powerbi 內容/包含/媒體資料夾](https://github.com/azure/powerbi-content/tree/master/includes/media)。 在 media 目錄不應包含任何映像的根目錄中。 如果包含沒有映像，然後對應的媒體目錄不需要。

###使用方式

- 使用包含任何出現在多個發行項相同的文字位置。
- 包含要用於大量的段落或兩個、 一個共用的程序或共用的區段的內容。 不要針對比一個句子還少的內容使用語彙基元；它們不適用產品名稱或不完整的句子。
- 不要內嵌包含內其他包含。 發佈系統中發生問題！
- 不要在檔案之間共用媒體。 使用不同的檔案與每個包含] 和 [發行項的唯一名稱。 將媒體檔案儲存在與包含相關聯的媒體資料夾。
- 請勿使用包含做為發行項的唯一內容。  包含的僅限補充文件的其餘部分中的內容。
- 因為所有包含必須在 / 包含目錄中，一律為發行項中包含的路徑

    ..包含 /

- 請不要重複連結或影像檔名中的參考文件和 include。 新增"-包含 」 來連結參考或媒體檔案名稱，以避免重複的參考︰

 **連結參考**

 變更︰ 若要 odata.org: odata.org 包括

 **影像參考**

 變更︰ 若要 table.png︰ 資料表 include.png

###範例 Markdown
包含加入文件本文的語法如下︰

    [AZURE.INCLUDE [include-short-name](../includes/include-file-name.md)]

範例

    [AZURE.INCLUDE [howto-blob-storage](../includes/howto-blob-storage.md)]

包含的第一個部分是包含名稱不包含路徑且不含.md 副檔名。 第二個部分是包含在中的相對路徑 / 包含.md 副檔名的目錄。

###轉譯

在轉譯的 GitHub 頁面中，包含將呈現，如下所示︰

 [AZURE。包含如何 blob 儲存體]

在 powerbi.microsoft.com，從 HTML 轉譯的 HTML 中包含的 HTML 文件的其餘部分會合併。 然而，HTML 會包含 HTML 與原始的註解包含 markdown 檔名和 GitHub 認可雜湊。 基於疑難排解用途包含此註解，如此一來，就可輕易地在 GitHub 中識別並找出來源內容︰

  ![](./media/custom-markdown-extensions/include.png)


## 內嵌的影片

我們的技術文章將技術文件中支援 embeddeded 影片、 詳細資料會 TBD （Azure 需要有 Channel 9，但我們想要使用 YouTube）。


## 技術與平台選取器

> [AZURE.NOTE] 此資訊適用於 Azure，但我們未來可能採用的選取器。

當您針對同一篇文章撰寫多個版本來處理跨技術或平台實作的差異時，請使用技術文件中的技術與平台切換程式。 對開發人員而言，這通常最適合我們的行動平台內容。 目前有兩種不同類型的選取器：[簡單的選取器](#simple-selectors)和[雙向選取器](#two-way-selectors)。

因為相同的選取器 markdown 當選取範圍中每個主題中，我們建議將您的主題的選取器放入 include 然後參考該包含在所有您使用相同的選取器的主題。

###<a id="simple-selectors"></a>簡單的選取器

簡單 (單向) 的選取器會轉譯為標題正下方的一組選項按鈕。 當客戶僅需要從單一平台或技術集合，例如.NET、 Node.js 和 Java 中的主題，請使用這些按鈕。  請使用以下任何選取器的自訂 markdown 格式。  請勿使用 HTML 的選取器函式。  

請參閱[開始使用通知中樞](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/)來了解作者如何針對同一篇文章建立 8 個版本，但使用了選取器來瀏覽這些所有版本。

![簡單的選取器範例](./media/custom-markdown-extensions/selectors.PNG)

####語法

    > [AZURE.SELECTOR]
    - 
            [連結標籤 #1](link #1 url)
    - [連結 #2 標籤](link #2 url)

範例：

    > [AZURE.SELECTOR]
    - 
            [Windows 通用](../articles/notification-hubs-windows-store-dotnet-get-started/)
    - [Windows Phone](../articles/notification-hubs-windows-phone-get-started/)
    - [iOS](../articles/notification-hubs-ios-get-started/)
    - [Android](../articles/notification-hubs-android-get-started/)
    - [Kindle](../articles/notification-hubs-kindle-get-started/)
    - [百度](../articles/notification-hubs-baidu-get-started/)
    - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
    - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)

#### 轉譯

上述圖顯示 powerbi.microsoft.com 呈現。 在轉譯的 GitHub 頁面中，選取器會轉譯為連結的項目符號清單。

###<a id="two-way-selectors"></a>雙向選取器

雙向選取器可讓使用者從雙向矩陣中選取主題。 Azure 的技術，例如，在行動服務支援多個後端平台，以及多個用戶端時，這是不可或缺的。 請記住下列事項︰

- 雖然它的設計是作為 `(Platform | Backend)`, ，現在您可以自訂 dropwdown 文字。
- 您不需要針對矩陣中的每個點使用清單項目，但只能有一個主題 URL 存在且不重複的項目。
- 儘管連結通常是另一個 GitHub 主題，但其可以是任意的 URL。

請參閱[開始使用行動服務](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/)來了解作者如何針對同一篇文章建立 15 個版本 (9 個行動用戶端平台，2 個後端平台)，但使用了選取器來瀏覽這些所有版本。 請注意，有 3 篇文章不需要這兩個後端版本。

![雙向選取器範例](./media/custom-markdown-extensions/selector-list.png)

####語法

    > [AZURE。選取器清單 (Dropdown1 |Dropdown2)]     - [(Dropdown1Text1 |Dropdown2Text1)](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text1 |Dropdown2Text2)](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text2 |Dropdown2Text3)](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text3 |Dropdown2Text4)](../articles/dropdown1-text1-dropdown2-text1.md)

範例：

    > [AZURE。選取器清單 (平台 |後端）]     - [(iOS |.NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
    - [(iOS |JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
    - [(Windows 通用 C# |.NET)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows 通用 C# |Javascript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Phone |.NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
    - [(Windows Phone |Javascript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
    - [(Android |.NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
    - [(Android |Javascript)](./mobile-services-javascript-backend-android-get-started-push.md)
    - [(Xamarin iOS |Javascript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
    - [(Xamarin Android |Javascript)](./partner-xamarin-mobile-services-android-get-started-push.md)

#### 轉譯

上圖顯示 azure.microsoft.com 上的轉譯。 在轉譯的 GitHub 頁面中，選取器會轉譯為連結的項目符號清單。

<!--Anchors-->
[附註和秘訣]: #notes-and-tips
[包含]: #includes
[內嵌的影片]: #embedded-videos
[技術與平台選取器]: #technology-and-platform-selectors

###著作指南的連結

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)
