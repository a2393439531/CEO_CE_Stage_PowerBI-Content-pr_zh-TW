<properties 
   pageTitle="View Reporting Services mobile reports and KPIs on the Power BI mobile app for Windows 10"
   description="The Power BI mobile app for Windows 10 offers live, touch-enabled mobile access to your important on-premises business information."
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

# <a name="view-reporting-services-mobile-reports-and-kpis-on-the-power-bi-mobile-app-for-windows-10"></a>View Reporting Services mobile reports and KPIs on the Power BI mobile app for Windows 10 

The Power BI mobile app for Windows 10 offers live, touch-enabled mobile access to your important on-premises business information. 

![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

<bpt id="p1">[</bpt>Create Reporting Services mobile reports<ept id="p1">](https://msdn.microsoft.com/library/mt652547.aspx)</ept> with SQL Server Mobile Report Publisher and publish them to the <bpt id="p2">[</bpt>Reporting Services web portal<ept id="p2">](https://msdn.microsoft.com/library/mt637133.aspx)</ept>. Create KPIs right in the web portal. Organize them in folders and mark your favorites, so you can find them easily. 

Then in the Power BI mobile app for Windows 10, view the mobile reports and KPIs, organized in folders or collected as favorites. 

> [AZURE.NOTE]  Your device needs to be running Windows 10. The app works best on devices with at least 1 GB RAM and 8 GB internal storage.

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>Explore samples without a SQL Server 2016 Reporting Services server

Even if you don't have access to a Reporting Services web portal, you can still explore the features of Reporting Services mobile reports. 

-  Tap the global navigation button <ph id="ph1">![](media/powerbi-mobile-win10-kpis-mobile-reports/powerbi_windows10_options_icon.png)</ph> in the upper-left corner, scroll down and tap <bpt id="p1">**</bpt>Reporting Services samples<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-samples-menu.png)

Browse the samples to interact with KPIs and mobile reports.

## <a name="connect-to-a-server-to-view-reporting-services-mobile-reports"></a>Connect to a server to view Reporting Services mobile reports 

1.  In your Windows 10 device, open the Power BI app.
  
2.  Tap the global navigation button <ph id="ph1">![](media/powerbi-mobile-win10-kpis-mobile-reports/powerbi_windows10_options_icon.png)</ph> in the upper-left corner, and tap <bpt id="p1">**</bpt>Connect to server<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-connect-server-menu.png)


4. Fill in the server address and your user name and password.

    ><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Include <bpt id="p2">**</bpt>http<ept id="p2">**</ept> or <bpt id="p3">**</bpt>https<ept id="p3">**</ept> in front of the connection string. For example, http://<bpt id="p1">*</bpt>servername<ept id="p1">*</ept>/reports.

    Tap <bpt id="p1">**</bpt>Advanced option<ept id="p1">**</ept> to give the server a name, if you'd like.

5.  Tap the <bpt id="p1">**</bpt>Next<ept id="p1">**</ept> check mark to connect. 

    Now you see the server in the left navigation bar.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)

    ><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: Tap the global navigation button <ph id="ph1">![](media/powerbi-mobile-win10-kpis-mobile-reports/powerbi_windows10_options_icon.png)</ph> anytime to go between your Reporting Services mobile reports and your dashboards in the Power BI service. 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>View Reporting Services KPIs and mobile reports in the Power BI app

Reporting Services KPIs and mobile reports are displayed in the same folders they're in on the Reporting Services web portal.

![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

- Tap a KPI to see it in focus mode.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)

- Tap a mobile report to open and interact with it in the Power BI app.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>View your favorite KPIs and reports

You can mark KPIs and mobile reports as favorites on your Reporting Services web portal, and then view them in one convenient folder on your Windows 10 device, along with your Power BI favorite dashboards and reports.

-  Tap <bpt id="p1">**</bpt>Favorites<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
   
    Your favorites from the web portal are all on this page.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-favorites.png)

Read more about <bpt id="p1">[</bpt>favorites in the Power BI mobile apps<ept id="p1">](powerbi-mobile-favorites.md)</ept>.


## <a name="remove-a-connection-to-a-report-server"></a>Remove a connection to a report server

You can only be connected to one report server at a time from your Power BI mobile app. If you want to connect to a different server, you need to disconnect from the current one.

1. At the bottom of the left navigation bar, tap <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> <ph id="ph1">![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-settings-icon.png)</ph>.
2. Tap and hold the server name you don't want to be connected to.
3. Tap <bpt id="p1">**</bpt>Remove server<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-win10-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)


## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Create Reporting Services mobile reports and KPIs

You don't create Reporting Services KPIs and mobile reports in the Power BI mobile app. You create them in SQL Server Mobile Report Publisher and a SQL Server 2016 Reporting Services web portal.

- <bpt id="p1">[</bpt>Create your own Reporting Services mobile reports<ept id="p1">](https://msdn.microsoft.com/library/mt652547.aspx)</ept>, and publish them to a Reporting Services web portal.
- Create <bpt id="p1">[</bpt>KPIs on a Reporting Services web portal<ept id="p1">](https://msdn.microsoft.com/library/mt683632.aspx)</ept>

### <a name="see-also"></a>請參閱  
- <bpt id="p1">[</bpt>Get started with the Power BI mobile app for Windows 10<ept id="p1">](powerbi-mobile-win10phone-app-get-started.md)</ept>  
- <bpt id="p1">[</bpt>Get started with Power BI<ept id="p1">](powerbi-service-get-started.md)</ept>  
- Questions? <bpt id="p1">[</bpt>Try asking the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>