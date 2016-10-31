<properties
   pageTitle="連接到 Power BI Desktop （預覽） 中的雪花式運算倉儲"
   description="輕鬆地連接到和使用 Power BI Desktop 中的雪花式運算倉儲"
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
   ms.date="09/30/2016"
   ms.author="davidi"/>

# 連接到 Power BI Desktop （預覽） 中的雪花式運算倉儲

在 Power BI Desktop，您可以連接到 **雪花式** 計算倉儲，並使用基礎資料，就像在 Power BI Desktop 中的任何其他資料來源。 這一版的 **雪花式** 連接器處於預覽狀態，並可能有所變更。

## 啟用雪花 （預覽） 功能

若要存取 **雪花式** 連接器，您必須先啟用這項預覽功能。 在 **Power BI Desktop**, ，請選取 **檔案 > 選項和設定 > 選項** 接著在 **選項** 視窗中，選取 **預覽功能** 區段，並啟用 **雪花式**, ，如下所示。

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_1.png)

您核取該方塊，當您開啟 **雪花式** 預覽功能。 您必須重新啟動 Power BI Desktop，變更才會生效。 一旦您這樣做，預覽功能使用。

您也 *必須* 安裝 **雪花式 ODBC 驅動程式** 使用之電腦上 **雪花式** 連接器，使用符合安裝的架構 **Power BI Desktop**, ，32 位元或 64 位元。 只要遵循下列連結和 [下載適當的雪花式 ODBC 驅動程式](http://go.microsoft.com/fwlink/?LinkID=823762)。

## 連接到的雪花式運算倉儲

一旦您已啟用預覽功能，來連接到 **雪花式** 計算倉儲選取 **取得資料** 從 **首頁** Power BI Desktop 在功能區。 選取 **資料庫** 從左邊，與您的類別，請參閱 **雪花 (Beta)**。

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_2.png)

在 **雪花式** 出現的視窗中，輸入或貼上名稱的雪花式運算倉儲到方塊，然後選取 **確定**。 請注意，您可以選擇 **匯入** 資料直接在 Power BI，或者您可以使用 **DirectQuery**。 您可以深入了解 [使用 DirectQuery](powerbi-desktop-use-directquery.md)。

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_3.png)

出現提示時，將放在您的使用者名稱和密碼。

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_4.png)

>
            **注意︰** 一旦您將放在您的使用者名稱和密碼為特定 **雪花式** 伺服器，Power BI Desktop 中的後續連接嘗試使用這些相同的認證。 您可以修改這些認證，請前往 **檔案 > 選項和設定 > 資料來源設定**。

成功連線之後， **導覽** ] 視窗隨即出現，並顯示在伺服器上，您可以從中選取一或多個項目匯入並使用中的可用資料 **Power BI Desktop**。

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_5.png)

您可以 **載入** 選取的資料表，將整個資料表，將 **Power BI Desktop**, ，或者您可以 **編輯** 查詢中，開啟 **查詢編輯器** 讓您可以篩選和精簡的一組您要使用的資料，然後載入該進一步調整成資料集 **Power BI Desktop**。

## 詳細資訊

﻿有各式各樣的資料，您可以連接到使用 Power BI Desktop。 如需有關資料來源的詳細資訊，請參閱下列資源︰

-   [開始使用 Power BI Desktop](powerbi-desktop-getting-started.md)

-   [Power BI Desktop 中的資料來源](powerbi-desktop-data-sources.md)

-   [圖形，並結合資料與 Power BI Desktop](powerbi-desktop-shape-and-combine-data.md)

-   [連接到 Power BI Desktop 中的 Excel 活頁簿](powerbi-desktop-connect-excel.md)   

-   [Power BI Desktop 中直接輸入資料](powerbi-desktop-enter-data-directly-into-desktop.md)   
