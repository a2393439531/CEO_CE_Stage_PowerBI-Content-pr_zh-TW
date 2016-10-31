<properties 
   pageTitle="在 iPad 應用程式中檢視行動的 Reporting Services 報表和 Kpi"
   description="IPad 應用程式 (適用於 iOS 的 Power BI) 提供對您的內部重要商務資訊的即時、 觸控式行動存取。"
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
   manager="erikre" 
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
   ms.date="10/11/2016"
   ms.author="maggies"/>

# <a name="view-reporting-services-mobile-reports-and-kpis-in-the-ipad-app-(power-bi-for-ios)"></a>在 iPad 應用程式 (適用於 iOS 的 Power BI) 中檢視行動的 Reporting Services 報表和 Kpi  

IOS 的 Microsoft Power BI 的 iPad 應用程式提供對您的內部重要商務資訊的即時、 觸控式行動存取。 

![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-home.png)

首要之務第一次︰

-  建立 [行動的 Reporting Services 報表](https://msdn.microsoft.com/library/mt652547.aspx) 與 SQL Server Mobile 報表發行者 」 並將它們發行至 [Reporting Services web 入口網站](https://msdn.microsoft.com/library/mt637133.aspx)。 
-  建立 [Reporting Services web 入口網站上的 Kpi](https://msdn.microsoft.com/library/mt683632.aspx)。 組織資料夾中，標示 [我的最愛]，讓您可以輕鬆地找到它們。 

然後在 Power BI 的 iPad 應用程式，檢視行動報表及 Kpi，在資料夾中組織或所收集的 [我的最愛]。 

> [AZURE.NOTE]  您的 iPad 必須至少執行 iOS 8.0。 

## <a name="explore-samples-without-an-ssrs-server"></a>瀏覽沒有 SSRS 伺服器範例

即使您沒有存取 Reporting Services web 入口網站，您仍然可以瀏覽行動的 Reporting Services 報表的功能。 

-  點選全域瀏覽按鈕 ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-iphone-global-nav-button.png) 左上角向下捲動並點選 **Reporting Services 範例**。

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-samples.png)


瀏覽 Kpi 和行動的報告與互動的範例。

## <a name="connect-to-a-server-to-view-reporting-services-mobile-reports"></a>連接到伺服器，才能檢視行動的 Reporting Services 報表 

1.  在 iPad，開啟 Power BI 應用程式。
  
2.  點選全域瀏覽按鈕 ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-iphone-global-nav-button.png) 左上角和點選 **連線伺服器**。

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-connect-server.png)

4. 填入伺服器位址，以及使用者名稱和密碼。

    >
            **請注意**︰ 包含 **http** 或 **https** 前面的連接字串。 例如，http://*servername*.com/reports。

    （選擇性）點選 **進階選項** 來指定伺服器的名稱。

5.  點選 **連接**。 

6.  現在，您會看到在左側的導覽列中的伺服器。

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-menu.png)

>
            **秘訣**︰ 點選全域導覽按鈕 ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-iphone-global-nav-button.png) 隨時為您的行動 Reporting Services 報表和儀表板中的 Power BI 服務之間移。 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>檢視 Reporting Services Kpi 和行動 Power BI 應用程式中的報表

Reporting Services Kpi 和行動的報表會顯示在同一個資料夾它們在 Reporting Services web 入口網站上。 

- 點選以查看聚焦模式中的 KPI。

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/PBI_iPad_SSMRP_Tile.png)

- 點選行動報表中，以開啟，並在 Power BI 應用程式互動。

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/PBI_iPad_SSMRP_MobRpt.png)

## <a name="view-your-favorite-kpis-and-reports"></a>您最愛的 Kpi 和報表檢視

您可以在 Reporting Services web 入口網站中將 Kpi 和行動報表標示為 [我的最愛]，然後檢視一個方便存取的資料夾中的它們 ipad 程式，以及您的 Power BI 最愛的儀表板和報表。

-  點選 **我的最愛**。

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-favorites-menu.png)
   
    您從入口網站的最愛都在此頁面。

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-favorites-page.png)

## <a name="remove-a-connection-to-a-report-server"></a>移除報表伺服器的連線

您只能連接到一部報表伺服器一次從 iPad 應用程式。 如果您想要連接到另一部伺服器，您需要一個從目前中斷連線。

1. 在左側的導覽列下方，點選 **設定**。
2. 點選您不想連接到伺服器名稱。
3. 點選 **移除連線**。


## <a name="create-reporting-services-mobile-reports-and-kpis"></a>建立行動的 Reporting Services 報表和 Kpi

您不在 Power BI 行動應用程式中建立 Reporting Services Kpi 和行動的報告。 您在 SQL Server Mobile 報表簽發者和 SQL Server 2016 Reporting Services 入口網站中建立它們。

- 
            [建立您自己的行動 Reporting Services 報告](https://msdn.microsoft.com/library/mt652547.aspx), ，並將它們發行至 Reporting Services web 入口網站。
- 建立 [Reporting Services web 入口網站上的 Kpi](https://msdn.microsoft.com/library/mt683632.aspx)


### <a name="see-also"></a>請參閱  
- 
            [開始著手 Power bi 的 iPad 應用程式](powerbi-mobile-ipad-app-get-started.md)  
- 
            [開始使用 Power BI](powerbi-service-get-started.md)  
- 問題了嗎？ 
            [請嘗試詢問 Power BI 社群](http://community.powerbi.com/)