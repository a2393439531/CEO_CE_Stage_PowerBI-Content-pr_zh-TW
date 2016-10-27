

#Metadata for Power BI technical articles

All Power BI technical articles contain two metadata sections - a properties section and a tags section. 內容區段可讓某些網站自動化及搜尋引擎最佳化 (SEO) 內容，而標記區段可報告大量的內部內容。 兩個區段都是必要的。

- [語法]
- [使用方式]
- [Attributes and values for the properties section]
- [Attributes and values for the tags section]

##語法

The properties section uses this syntax:

    <properties
       pageTitle="<Page title that displays in search results and the browser tab | Microsoft Power BI>"
       description="<Article description that will be displayed on landing pages and in most search results>"
       services="powerbi"
       documentationCenter="NA"
       authors="GitHub-alias-of-only-one-author"
       manager="mblythe"
       editor="NA"
       tags="NA"/>

The tags section uses this syntax:

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
- 錯誤 <properties> section must be the first line of your file.
- 在每個中繼資料區段以及頁面標題之前保留空白列，以確保頁面標題在發佈程序期間會正確地轉換為 HTML。

## Attributes and values for the properties section

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>pageTitle<ept id="p1">**</ept>: Required; important to SEO. 此屬性的文字會出現在瀏覽器的索引標籤中，並且在搜尋結果內做為標題。 Use 55-60 characters including spaces and including the site identifier <bpt id="p1">*</bpt>| Microsoft Power BI<ept id="p1">*</ept> (typed as: space pipe space Microsoft Power BI).

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>description<ept id="p1">**</ept>: Required; important for SEO (relevance) and site functionalities. Use at least 140 characters, but don't exceed 170 characters including spaces. Describe the  purpose of your content so customers will know whether to choose it from a list of search results. The value is usually displayed as the description or abstract paragraph in search results.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>services<ept id="p1">**</ept>: Always "powerbi" for Power BI content (Azure has multiple options).

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>documentationCenter<ept id="p1">**</ept>: "NA" for Power BI content.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>authors<ept id="p1">**</ept>: Required, one value only. 列出主要作者或文章主題專家 (SME) 的 GitHub 帳戶。 這項屬性會影響已發行文章上的署名。 即便屬性有多個名稱，也僅會顯示一個。

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>manager<ept id="p1">**</ept>: Required if you are a Microsoft contributor. List the alias of the content publishing manager for the technology area. 如果您是社群參與者，請包含此屬性，但保留空白，以便我們填寫。

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>editor<ept id="p1">**</ept>: "NA" - Not used. 請勿將它用於其他用途。

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>tags<ept id="p1">**</ept>: "NA" for Power BI content.


## Attributes and values for the tags section

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.service<ept id="p1">**</ept>: Always "powerbi" for Power BI content (Azure has multiple options).

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.devlang<ept id="p1">**</ept>: "NA" for Power BI content.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.topic<ept id="p1">**</ept>: Required. Specifies the topic type. 大多數參與者建立的新頁面會是文章或參考。 NOTE: the list below is from Azure, and I have removed some of the options that definitely aren't valid for Power BI. We will decide how to use the remaining options as our site architecture is developed. If in doubt, use "article". 

 - 
            **article**：概念性主題、教學課程、功能指南，或其他非參考文章

 - <bpt id="p1">**</bpt>campaign-page<ept id="p1">**</ept>: A page that is specifically designed as a landing page for external campaigns, and is not included as part of the primary site IA.  Should not be used for documentation articles or regular doc landing pages.

 - <bpt id="p1">**</bpt>get-started-article<ept id="p1">**</ept>: Assign to articles that are featured in the Get Started section of the left navigation for a service.

 - <bpt id="p1">**</bpt>hero-article<ept id="p1">**</ept>: A "hero" tutorial that is designed to provide an introduction to a service or feature that gets visitors started using the service quickly and drives free-trial sign-ups and MSDN activations. 請將這個值只指派給顯示在您的服務之文章登陸頁面頂端的文章。

 - <bpt id="p1">**</bpt>home-page<ept id="p1">**</ept>: Top level documentation home page.

 - <bpt id="p1">**</bpt>infographic-page<ept id="p1">**</ept>: A page that features a browsable infographic or poster.

 - <bpt id="p1">**</bpt>reference<ept id="p1">**</ept>: An API or language reference page (including REST API).

 - <bpt id="p1">**</bpt>video-page<ept id="p1">**</ept>: A page that features a video.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.tgt_pltfrm<ept id="p1">**</ept>: Required. Specifies the target platform. This value will be <bpt id="p1">**</bpt>NA<ept id="p1">**</ept> for most topics. NOTE: Still detemining whether we should use this for our mobile content.

 - **mobile-android**
 - **mobile-html**
 - **mobile-ios**
 - **mobile-multiple**
 - **多個**
 - **na**

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.workload<ept id="p1">**</ept>: Always "powerbi" for Power BI content (Azure has multiple options).

![](./media/article-metadata/checkmark-small.png) <bpt id="p1">**</bpt>ms.date<ept id="p1">**</ept>: Required. 指定文章上次被檢閱相關性、準確性、修正螢幕擷取畫面和可運作連結的日期。 以 mm/dd/yyyy 格式輸入日期。 此日期也會顯示於已發行文章上做為上次更新日期。

![](./media/article-metadata/checkmark-small.png) <bpt id="p1">**</bpt>ms.author<ept id="p1">**</ept>: Required. 指定與主題相關的作者。 若要指定多個值，您應該以分號將值分開。 可接受 Microsoft 別名或完整的電子郵件地址。 長度不能超過 200 個字元。


###Contributors' Guide Links

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)


<!--Anchors-->
[語法]: #syntax
[使用方式]: #usage
[Attributes and values for the properties section]: #attributes-and-values-for-the-properties-section
[Attributes and values for the tags section]: #attributes-and-values-for-the-tags-section
