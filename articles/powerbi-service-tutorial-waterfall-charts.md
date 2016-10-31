<properties
   pageTitle="在 Power BI 中的教學課程︰ 瀑布圖"
   description="在 Power BI 中的教學課程︰ 瀑布圖"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="maTzOJSRB3g"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/07/2016"
   ms.author="mihart"/>
# 在 Power BI 中的教學課程︰ 瀑布圖

瀑布圖顯示執行總數加入或減去的值時。 它可用於了解如何起始值 （例如，淨收入） 會受到一系列的正數和負數的變更。

資料行是色彩編碼，好讓您快速地告訴增加或減少。 初始和最終值資料行通常 [水平軸上啟動](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "水平軸上啟動"), ，而中繼值浮點數資料行。 此 「 查詢 」，因為瀑布圖也稱為橋接器圖表。

<iframe width="560" height="315" src="https://www.youtube.com/embed/maTzOJSRB3g?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## 何時使用瀑布圖

瀑布圖是相當好的選擇︰

-   當您有變更量值在時間序列或不同類別

-   若要稽核的總計值造成重大的變更

-   若要繪製貴公司的年度收益顯示各種來源的營收，並到達總收益 （或遺失）。

-   一年中說明的開始和結束的人數為您的公司

-   以視覺化方式檢視多少錢您使花費和每個月和日常餘額為您的帳戶。 

## 建立瀑布圖

要跟著做，請登入 Power BI，然後選取 **取得資料 \> 範例 \> 零售分析範例**。 

1. 「 零售分析範例 」 儀表板中，選取 **總商店** 磚以開啟 「 零售分析範例 」 報告。

2. 選取 **編輯報表** 編輯檢視中開啟報表。

3. 
            [加入新的報表頁面](powerbi-service-add-a-page-to-a-report.md)。

4. 建立依月份顯示本年度的銷售額與銷售目標瀑布圖。

  - 從 **欄位** 窗格中，選取 **銷售 \> 總銷售變異數**。

    - 轉換圖表以 **瀑布**。 

        ![](media/powerbi-service-tutorial-waterfall-charts/convertWaterfall.png)

    - 如果 **總銷售變異數** 不在 **Y 軸** 區域中，將它拖曳到那里。

    - 選取 **時間** \> **FiscalMonth** 將它加入至 **類別** 良好。 

    ![](media/powerbi-service-tutorial-waterfall-charts/first_new.png)

## 反白顯示和交叉篩選

使用 [篩選] 窗格的相關資訊，請參閱 [將篩選加入至報表](powerbi-service-add-a-filter-to-a-report.md)。

反白顯示瀑布圖中的資料行交叉篩選...在報表頁面上的其他視覺效果，反之亦然。 不過，總計的資料行不會觸發反白顯示或回應交叉篩選。

## 請參閱

[在 Power BI 中的報表](powerbi-service-reports.md)

[在 Power BI 中的視覺效果類型](powerbi-service-visualization-types-for-reports-and-q-and-a.md)

[Power BI 報表中的視覺效果](powerbi-service-visualizations-for-reports.md)

[Power BI-基本概念](powerbi-service-basic-concepts.md)

更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
