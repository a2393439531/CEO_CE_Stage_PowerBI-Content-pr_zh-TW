

#Power BI 技術文件的中繼資料

所有的 Power BI 技術文件包含兩個中繼資料區段的內容區段以及標記] 區段中。 內容區段可讓某些網站自動化及搜尋引擎最佳化 (SEO) 內容，而標記區段可報告大量的內部內容。 兩個區段都是必要的。

- [語法]
- [使用方式]
- [屬性和值的屬性區段]
- [屬性和 [標記] 區段的值]

##語法

[內容] 區段中，會使用此語法︰

    <properties
       pageTitle="<Page title that displays in search results and the browser tab | Microsoft Power BI>"
       description="<Article description that will be displayed on landing pages and in most search results>"
       services="powerbi"
       documentationCenter="NA"
       authors="GitHub-alias-of-only-one-author"
       manager="mblythe"
       editor="NA"
       tags="NA"/>

[標記] 區段中，會使用此語法︰

    <tags
       ms.service="powerbi"
       ms.devlang="NA"
       ms.topic="<typically "article"; see list below>"
       ms.tgt_pltfrm="<typically "NA"; see list below>"
       ms.workload="powerbi"
       ms.date="mm/dd/yyyy"
       ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

##使用方式

- 元素名稱與屬性名稱會區分大小寫。
- 錯誤 <properties> 區段必須是檔案的您的第一行。
- 在每個中繼資料區段以及頁面標題之前保留空白列，以確保頁面標題在發佈程序期間會正確地轉換為 HTML。

## 屬性和值的屬性區段

![](./media/article-metadata/checkmark-small.png)
            **pageTitle**: SEO 很重要，則為必要。 此屬性的文字會出現在瀏覽器的索引標籤中，並且在搜尋結果內做為標題。 使用 55 60 個字元包括空格和包括站台識別碼 *|Microsoft Power BI* (型別為︰ 空間管道空間 Microsoft Power BI)。

![](./media/article-metadata/checkmark-small.png)
            **描述**︰ 必要; 重要的 SEO （相關） 與站台功能。 使用至少 140 個字元，但不能超過 170 字元包括空格。 說明內容的目的，讓客戶將會知道是否要從搜尋結果的清單中選擇。 此值通常顯示為描述或抽象搜尋結果中的段落。

![](./media/article-metadata/checkmark-small.png)
            **服務**︰ 一律 「 powerbi 」 （Azure 有多個選項） 的 Power BI 內容。

![](./media/article-metadata/checkmark-small.png)
            **documentationCenter**:"NA"Power BI 內容。

![](./media/article-metadata/checkmark-small.png)
            **作者**︰ 所需，只有一個值。 列出主要作者或文章主題專家 (SME) 的 GitHub 帳戶。 這項屬性會影響已發行文章上的署名。 即便屬性有多個名稱，也僅會顯示一個。

![](./media/article-metadata/checkmark-small.png)
            **管理員**︰ 如果您 Microsoft 參與者所需。 清單內容的發佈管理員技術領域的別名。 如果您是社群參與者，請包含此屬性，但保留空白，以便我們填寫。

![](./media/article-metadata/checkmark-small.png)
            **編輯器**:"NA"-不使用。 請勿將它用於其他用途。

![](./media/article-metadata/checkmark-small.png)
            **標記**:"NA"Power BI 內容。


## 屬性和 [標記] 區段的值

![](./media/article-metadata/checkmark-small.png)
            **ms.service**︰ 一律 「 powerbi 」 （Azure 有多個選項） 的 Power BI 內容。

![](./media/article-metadata/checkmark-small.png)
            **ms.devlang**:"NA"Power BI 內容。

![](./media/article-metadata/checkmark-small.png)
            **ms.topic**︰ 必要。 指定主題型別。 大多數參與者建立的新頁面會是文章或參考。 附註︰ 下列清單是從 Azure 中，我已移除的某些選項一定不是有效的 Power BI。 我們會決定如何使用我們的站台架構開發的其餘的選項。 如果有疑問，使用 「 文件 」。 

 - 
            **article**：概念性主題、教學課程、功能指南，或其他非參考文章

 - 
            **行銷頁面**︰ 頁面專為外部活動的登陸頁面，也不 IA.的主要站台的一部分  不應該使用文件的文件或一般登陸頁面的文件。

 - 
            **取得啟動文章**︰ 指派給文章中開始使用] 區段的左側導覽中的服務。

 - 
            **英雄文章**: 「 英雄 」 教學課程是設計用來介紹一項服務或功能，會取得訪客使用服務快速啟動並免費試用註冊及 MSDN 啟用磁碟機。 請將這個值只指派給顯示在您的服務之文章登陸頁面頂端的文章。

 - 
            **首頁**︰ 上方層級的文件首頁。

 - 
            **資訊圖頁面**︰ 功能可瀏覽資訊圖或海報的頁面。

 - 
            **參考**︰ 的 API 或語言 （包括 REST API） 的參考頁面。

 - 
            **影片頁面**︰ 功能視訊的頁面。

![](./media/article-metadata/checkmark-small.png)
            **ms.tgt_pltfrm**︰ 必要。 指定目標平台。 這個值會是 **NA** 大部分主題。 注意︰ 仍然 detemining 是否應該使用這我們行動的內容。

 - **mobile-android**
 - **mobile-html**
 - **mobile-ios**
 - **mobile-multiple**
 - **多個**
 - **na**

![](./media/article-metadata/checkmark-small.png)
            **ms.workload**︰ 一律 「 powerbi 」 （Azure 有多個選項） 的 Power BI 內容。

![](./media/article-metadata/checkmark-small.png) 
            **ms.date**︰ 必要。 指定文章上次被檢閱相關性、準確性、修正螢幕擷取畫面和可運作連結的日期。 以 mm/dd/yyyy 格式輸入日期。 此日期也會顯示於已發行文章上做為上次更新日期。

![](./media/article-metadata/checkmark-small.png) 
            **ms.author**︰ 必要。 指定與主題相關的作者。 若要指定多個值，您應該以分號將值分開。 可接受 Microsoft 別名或完整的電子郵件地址。 長度不能超過 200 個字元。


###著作指南的連結

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)


<!--Anchors-->
[語法]: #syntax
[使用方式]: #usage
[屬性和值的屬性區段]: #attributes-and-values-for-the-properties-section
[屬性和 [標記] 區段的值]: #attributes-and-values-for-the-tags-section
