<properties 
   pageTitle="View Reporting Services mobile reports and KPIs in the iPhone app"
   description="The iPhone app (Power BI for iOS) offers live, touch-enabled mobile access to your important on-premises business information."
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
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
   ms.date="10/18/2016"
   ms.author="maggies"/>

# <a name="view-sql-server-reporting-services-mobile-reports-and-kpis-in-the-iphone-app-(power-bi-for-ios)"></a>View SQL Server Reporting Services mobile reports and KPIs in the iPhone app (Power BI for iOS)  

The iPhone app for Microsoft Power BI for iOS offers live, touch-enabled mobile access to your important on-premises business information. 

 ![](media/powerbi-mobile-iphone-kpis-mobile-reports/PBI_iPh_SSMRP_MobRpt.png)

<bpt id="p1">[</bpt>Create Reporting Services mobile reports<ept id="p1">](https://msdn.microsoft.com/library/mt652547.aspx)</ept> with SQL Server Mobile Report Publisher and publish them to the <bpt id="p2">[</bpt>Reporting Services web portal<ept id="p2">](https://msdn.microsoft.com/library/mt637133.aspx)</ept>. Create KPIs right in the web portal. Organize them in folders and mark your favorites, so you can find them easily. 

Then in the iPhone app for Power BI, view the mobile reports and KPIs, organized in folders or collected as favorites. 

><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Your iPhone needs to be at least an iPhone 5, running at least iOS 9.0.

## <a name="explore-samples-without-an-ssrs-server"></a>Explore samples without an SSRS server

Even if you don't have access to a Reporting Services web portal, you can still explore the features of Reporting Services mobile reports. 

1. Tap the global navigation button <ph id="ph1">![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-global-nav-button.png)</ph> in the upper-left corner, scroll down and tap <bpt id="p1">**</bpt>Reporting Services samples<ept id="p1">**</ept>.

2.  Browse to interact with the sample KPIs and mobile reports.

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-a-server-to-view-reporting-services-mobile-reports"></a>Connect to a server to view Reporting Services mobile reports 

1.  In the iPhone, open the Power BI app.
  
2.  To view your Reporting Services mobile reports and KPIs, tap <bpt id="p1">**</bpt>SQL Server Reporting Services<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-connect-ssrs-server.png)

    If you're already in the Power BI app, tap the global navigation button <ph id="ph1">![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-global-nav-button.png)</ph> in the upper-left corner, and tap <bpt id="p1">**</bpt>Connect Server<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-connect-ssrs.png)

4. Fill in the server address and your user name and password.

    ><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Include <bpt id="p2">**</bpt>http<ept id="p2">**</ept> or <bpt id="p3">**</bpt>https<ept id="p3">**</ept> in front of the connection string. For example, http://<bpt id="p1">*</bpt>servername<ept id="p1">*</ept>.com/reports.

    Tap <bpt id="p1">**</bpt>Advanced option<ept id="p1">**</ept> to give the server a name, if you'd like.

5.  Now you see the server in the left navigation bar--in this example, called "work server."

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-ssrs-server.png)

><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: Tap the global navigation button <ph id="ph1">![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-global-nav-button.png)</ph> anytime to go between your Reporting Services mobile reports and your dashboards in the Power BI service. 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>View Reporting Services KPIs and mobile reports in the Power BI app

Reporting Services KPIs and mobile reports are displayed in the same folders they're in on the Reporting Services web portal. 

- Tap a KPI to see it in focus mode.

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/PBI_iPh_SSMRP_Tile.png)

- Tap a mobile report to open and interact with it in the Power BI app.

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/PBI_iPh_SSMRP_MobRpt.png)

## <a name="view-your-favorite-kpis-and-reports"></a>View your favorite KPIs and reports

You can mark KPIs and mobile reports as favorites on your Reporting Services web portal, and then view them in one convenient folder on your iPhone, along with your Power BI favorite dashboards and reports.

-  Tap <bpt id="p1">**</bpt>Favorites<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-favorite-menu.png)
   
    Your favorites from the web portal are all on this page.

    ![](media/powerbi-mobile-iphone-kpis-mobile-reports/power-bi-iphone-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Remove a connection to a report server

You can only be connected to one report server at a time from your iPhone app. If you want to connect to a different server, you need to disconnect from the current one.

1. At the bottom of the left navigation bar, tap <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept>.
2. Tap the server name you don't want to be connected to.
3. Tap <bpt id="p1">**</bpt>Remove Server<ept id="p1">**</ept>.

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Create Reporting Services mobile reports and KPIs

You don't create Reporting Services KPIs and mobile reports in the Power BI mobile app. You create them in SQL Server Mobile Report Publisher and a SQL Server 2016 Reporting Services web portal.

- <bpt id="p1">[</bpt>Create your own Reporting Services mobile reports<ept id="p1">](https://msdn.microsoft.com/library/mt652547.aspx)</ept>, and publish them to the Reporting Services web portal.
- Create <bpt id="p1">[</bpt>KPIs on the Reporting Services web portal<ept id="p1">](https://msdn.microsoft.com/library/mt683632.aspx)</ept>

### <a name="see-also"></a>請參閱  
- <bpt id="p1">[</bpt>Get started with the iPhone app for Power BI<ept id="p1">](powerbi-mobile-iphone-app-get-started.md)</ept>  
- <bpt id="p1">[</bpt>Get started with Power BI<ept id="p1">](powerbi-service-get-started.md)</ept>  
- Questions? <bpt id="p1">[</bpt>Try asking the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>