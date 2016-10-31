<properties 
   pageTitle="Windows 10 的 Power BI 行動應用程式上檢視 Reporting Services 行動報表及 Kpi"
   description="Windows 10 的 Power BI 行動應用程式提供對您的內部重要商務資訊的即時、 觸控式行動存取。"
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
   ms.date="10/14/2016"
   ms.author="maggies"/>

# <a name="view-reporting-services-mobile-reports-and-kpis-on-the-power-bi-mobile-app-for-windows-10"></a>Windows 10 的 Power BI 行動應用程式上檢視 Reporting Services 行動報表及 Kpi 

Windows 10 的 Power BI 行動應用程式提供對您的內部重要商務資訊的即時、 觸控式行動存取。 

![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)


            [建立 Reporting Services 行動報表](https://msdn.microsoft.com/library/mt652547.aspx) 與 SQL Server Mobile 報表發行者 」 並將它們發行至 [Reporting Services web 入口網站](https://msdn.microsoft.com/library/mt637133.aspx)。 在入口網站中建立 Kpi 權限。 組織資料夾中，標示 [我的最愛]，讓您可以輕鬆地找到它們。 

然後在 Windows 10 的 Power BI 行動應用程式，檢視行動報表及 Kpi，在資料夾中組織或所收集的 [我的最愛]。 

> [AZURE.NOTE]  您的裝置必須執行 Windows 10。 應用程式最適合使用最少 1 GB RAM 和 8 GB 的內部儲存裝置。

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>瀏覽範例不使用 SQL Server 2016 Reporting Services 伺服器

即使您沒有存取 Reporting Services web 入口網站，您仍然可以瀏覽行動的 Reporting Services 報表的功能。 

-  點選全域瀏覽按鈕 ![](media/powerbi-mobile-win10-kpis-mobile-reports/powerbi_windows10_options_icon.png) 左上角向下捲動並點選 **Reporting Services 範例**。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-samples-menu.png)

瀏覽 Kpi 和行動的報告與互動的範例。

## <a name="connect-to-a-server-to-view-reporting-services-mobile-reports"></a>連接到伺服器，才能檢視行動的 Reporting Services 報表 

1.  在 Windows 10 裝置中，開啟 Power BI 應用程式。
  
2.  點選全域瀏覽按鈕 ![](media/powerbi-mobile-win10-kpis-mobile-reports/powerbi_windows10_options_icon.png) 左上角和點選 **連接到伺服器**。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-connect-server-menu.png)


4. 填入伺服器位址，以及使用者名稱和密碼。

    >
            **請注意**︰ 包含 **http** 或 **https** 前面的連接字串。 例如，http://*servername*/報告。

    點選 **進階選項** ，如果您想要授與伺服器名稱。

5.  點選 **下一步** 連線的核取記號。 

    現在，您會看到在左側的導覽列中的伺服器。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)

    >
            **秘訣**︰ 點選全域導覽按鈕 ![](media/powerbi-mobile-win10-kpis-mobile-reports/powerbi_windows10_options_icon.png) 隨時以進入您的行動 Reporting Services 報表和儀表板中的 Power BI 服務之間。 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>檢視 Reporting Services Kpi 和行動 Power BI 應用程式中的報表

Reporting Services Kpi 和行動的報表會顯示在同一個資料夾它們在 Reporting Services web 入口網站上。

![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

- 點選以查看聚焦模式中的 KPI。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)

- 點選行動報表中，以開啟，並在 Power BI 應用程式互動。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>您最愛的 Kpi 和報表檢視

您可以在 Reporting Services web 入口網站中將 Kpi 和行動報表標示為 [我的最愛]，然後檢視一個方便存取的資料夾中的這些 Windows 10 裝置，以及您的 Power BI 最愛的儀表板和報表。

-  點選 **我的最愛**。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
   
    您從入口網站的最愛都在此頁面。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-favorites.png)

深入了解 [Power BI 行動應用程式中的最愛](powerbi-mobile-favorites.md)。


## <a name="remove-a-connection-to-a-report-server"></a>移除報表伺服器的連線

您只能連接到一部報表伺服器一次從 Power BI 行動應用程式。 如果您想要連接到另一部伺服器，您需要一個從目前中斷連線。

1. 在左側的導覽列下方，點選 **設定** ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-settings-icon.png)。
2. 點選並按住不想連接到伺服器名稱。
3. 點選 **移除 server**。

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)


## <a name="create-reporting-services-mobile-reports-and-kpis"></a>建立行動的 Reporting Services 報表和 Kpi

您不在 Power BI 行動應用程式中建立 Reporting Services Kpi 和行動的報告。 您在 SQL Server Mobile 報表簽發者和 SQL Server 2016 Reporting Services 入口網站中建立它們。

- 
            [建立您自己的行動 Reporting Services 報告](https://msdn.microsoft.com/library/mt652547.aspx), ，並將它們發行至 Reporting Services web 入口網站。
- 建立 [Reporting Services web 入口網站上的 Kpi](https://msdn.microsoft.com/library/mt683632.aspx)

### <a name="see-also"></a>請參閱  
- 
            [開始使用 Power BI 行動應用程式的 Windows 10](powerbi-mobile-win10phone-app-get-started.md)  
- 
            [開始使用 Power BI](powerbi-service-get-started.md)  
- 問題了嗎？ 
            [請嘗試詢問 Power BI 社群](http://community.powerbi.com/)