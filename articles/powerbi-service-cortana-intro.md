<properties
   pageTitle="Power bi Cortana 簡介"
   description="使用 Power BI 的 Cortana 解答您的資料。 Cortana 啟動每個 Power BI 資料集，然後啟用 [Cortana 從行動裝置存取您的資料集。"
   services="powerbi"
   documentationCenter=""
   authors="mihart"  
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/19/2016"
   ms.author="mihart"/>


# <a name="introduction-to-cortana-for-power-bi"></a>Power bi Cortana 簡介

詢問 Cortana 的自然語言問題並且尋找解答從 Power BI 中儲存的資料。

>[AZURE.NOTE]  Cortana Power bi 是目前僅提供英文版本。 無法在行動裝置上目前可用 Cortana。

## <a name="how-do-cortana-and-power-bi-work-together?"></a>如何 Cortana 和 Power BI 共同運作？

透過 Windows 10 2015 年 11 月更新，Cortana 現在可以尋找透過 Power BI 與 Cortana 整合 Power BI 中儲存資料的解答。

類似於 Power BI 問與答的要求，或是輸入您使用自然語言的問題。 Cortana 將 Power BI 中搜尋 Cortana 啟用資料集的答案，並直接在您的 Windows 10 裝置中顯示結果。   

Cortana 可以找到答案可能是直接從資料集在 Power BI 中或從發行至 Power BI，並特別為 Cortana 而設計的報表頁面 (稱為 *回應頁面*)。  Power BI 中或，若要進一步探索答案，請直接在 Power BI 中開啟結果一樣，視覺效果與互動。

>[AZURE.NOTE]  Cortana 運作方式與內部部署資料已 [啟用問與答](powerbi-service-q-and-a-direct-query.md)。

Cortana 排名從 Power BI，讓您有一或多個最佳的相符項目高度信賴程度，結果會是很好的回應時的答案。 從 Power BI 其他可能的答案會列出 Power BI 以下一節中最符合項目。 如果您的資料集擁有者，您可以協助 Cortana 傳回更好的解答 [建立特定的報表 (稱為 *回應頁面*) 的 Cortana](powerbi-service-cortana-desktop-entity-cards.md) 來回答最常見的 Power BI 中，以及最佳化您的模型的 Power BI 問與答。

## <a name="how-do-i-get-started?"></a>如何開始使用？

- Cortana 會尋找在您具有存取權的 Power BI 資料集的解答。 如果您是資料集擁有者 [允許 Cortana 存取資料集 （和其報告）](powerbi-service-cortana-enable.md)。  

- 如果您是資料集擁有者 [建立專為 Cortana 設計回應頁面](powerbi-service-cortana-desktop-entity-cards.md)。

## <a name="tips-for-using-power-bi-with-cortana"></a>使用 Cortana 與使用 Power BI 的秘訣

### <a name="before-you-begin"></a>開始之前

在 Power BI 中，您可以使用您所擁有，或與您已共用的資料集。 若要存取這些相同的資料集 Cortana 中，資料集擁有者必須 [啟用每個資料集的 Cortana](powerbi-service-cortana-enable.md)。  

### <a name="asking-questions"></a>詢問問題

Power BI 中的任何使用者可以使用 Cortana 來詢問 Power BI 資料集有關的問題。  資料集擁有者可以使用 [Power BI 中建立回應頁面改善解答](powerbi-service-cortana-desktop-entity-cards.md)。  

1. 使用 Cortana，要求，或是輸入需要解答問題。  例如，要求 「 多少新的存放區開啟在三月 」？

2. Cortana 求取在 Power BI 報表與可用的資料集的解答，並將其顯示標題下 **Power BI** 和 Power BI 圖示標示。

3. Power BI 會先尋找解答 [回應頁面](powerbi-service-cortana-desktop-entity-cards.md) 然後搜尋您的資料集，並報告其他解答，並顯示在表單的視覺效果。  最高評分結果會顯示第一個是 *最符合*, ，後面接著其他可能的答案與應用程式的連結。 最佳的相符項目是來自 Power BI 回應頁面，或 Power BI 報表。
  >[AZURE.NOTE] 如果您說您的問題，只會顯示 Cortana **Power BI** 解答，如果它找到最符合項目。  

4. 若要開啟解答 Power BI 中，選取的連結。


### <a name="other-tips"></a>其他的秘訣

-  如果報表包含篩選器，Cortana 就能了解，指定篩選器清單中的項目並套用篩選器上作業的問題。

- 如果這個問題有 2 個或多個字 Cortana 只會搜尋 Power BI 中的答案。

- 如果您加入文字"my"您的問題，Cortana 搜尋可用的資料集的解答，其中包含您的 Windows 10 設定檔 （當您按一下圖片時，您會看到的資訊） 中找到的資訊。

## <a name="see-also"></a>請參閱

            [允許 Cortana Power bi](powerbi-service-cortana-enable.md)


            [介紹 Power BI 問與答](powerbi-service-q-and-a.md)


            [Power BI 的基本概念](powerbi-service-basic-concepts.md)

更多的問題嗎？ 
            [試用 Power BI 社群](http://community.powerbi.com/)
