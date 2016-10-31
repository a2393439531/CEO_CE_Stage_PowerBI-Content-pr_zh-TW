<properties
   pageTitle="第三方服務︰ Power BI Desktop 的 Facebook 連接器"
   description="第三方服務︰ Power BI Desktop 的 Facebook 連接器"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.date="09/29/2016"
   ms.author="davidi"/>
# 第三方服務︰ Power BI Desktop 的 Facebook 連接器

Power BI Desktop 中的 Facebook 連接器依賴 Facebook 圖形 API。 同樣地，功能與可用性可能隨時間變化。

您可以看到 [教學課程有關的 Power BI Desktop Facebook 連接器](powerbi-desktop-tutorial-facebook-analytics.md)。

Facebook 上年 4 月 30 過期的 Graph api v1.0<sup>th</sup> 2015年。 Power BI 使用 Graph API 在幕後 Facebook 連接器，可讓您連接到您的資料進行分析。

年 4 月 30 日之前所建立的查詢<sup>th</sup> 2015年可能不再運作或傳回較少的資料。 4 月 30 日之後<sup>th</sup> 2015，Power BI 會運用 v2.2 Facebook API 的所有呼叫中。 2015 年 4 月 30 日之前所建立的查詢，且不使用它之後，如果您將可能需要重新驗證，以核准的新的我們將要求的權限集。

我們嘗試發行更新，根據的任何變更，但可能會變更 API 的方式會影響我們產生的查詢的結果。 在某些情況下，某些查詢可能不受支援。 由於此相依性中，我們無法保證您的查詢結果時使用此連接器。

如需詳細資訊，在 Facebook API 中的變更 [這裡](https://developers.facebook.com/docs/apps/changelog#v2_0)。
