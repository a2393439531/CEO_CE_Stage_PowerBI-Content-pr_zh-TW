<properties
   pageTitle="Power BI publisher for Excel"
   description="Learn how to use the Power BI publisher for Excel"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="complete"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/12/2016"
   ms.author="davidi"/>

# Power BI publisher for Excel

With Microsoft <bpt id="p1">**</bpt>Power BI publisher for Excel<ept id="p1">**</ept>, you can take snapshots of your most important insights in Excel, like PivotTables, charts, and ranges and pin them to dashboards in Power BI.

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_pinobj_dashboard.png)

What can you pin? Just about anything in an Excel worksheet. You can select a range of cells from a simple sheet or table, a PivotTable or PivotChart, illustrations and images, text.

What you can't pin: you cannot pin 3D Maps or visualizations in Power View sheets. There are also some elements you can pin, but it wouldn't make much sense to, like a Slicer or Timeline filter.

When you pin an element from Excel, a new tile is added to a new or existing dashboard in Power BI. The new tile is a snapshot, so it's not dynamic but you can still update it. For example, if you make a change to a PivotTable or chart you've already pinned, the dashboard tile in Power BI isn't updated automatically, but you can still update your pinned elements by using <bpt id="p1">**</bpt>Pin Manager<ept id="p1">**</ept>. You'll learn more about <bpt id="p1">**</bpt>Pin Manager<ept id="p1">**</ept> in the following sections.

## 下載和安裝
Power BI publisher for Excel is an add-in you can download and install on desktop versions of Microsoft Excel 2007 and later.

[Download Power BI publisher for Excel](http://go.microsoft.com/fwlink/?LinkId=715729)

Once you have the publisher installed, you'll see a new <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> ribbon in Excel, where you can sign in (or sign out) of Power BI, pin elements to dashboards, and manage elements you've already pinned.

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_ribbon.png)

The <bpt id="p1">**</bpt>Power BI publisher for Excel<ept id="p1">**</ept> add-in is enabled by default, but if for some reason you don't see the Power BI ribbon tab in Excel, you'll need to enable it. Click <bpt id="p1">**</bpt>File<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Options<ept id="p2">**</ept><ph id="ph2"> &gt; </ph><bpt id="p3">**</bpt>Add-ins<ept id="p3">**</ept><ph id="ph3"> &gt; </ph><bpt id="p4">**</bpt>COM Add-ins<ept id="p4">**</ept>. Select <bpt id="p1">**</bpt>Microsoft Power BI Publisher for Excel<ept id="p1">**</ept>.


## Pin a range to a dashboard
You can select any range of cells from your worksheet, and pin a snapshot of that range to an existing or a new dashboard in Power BI. You can pin the same snapshot to multiple dashboards, too.

To begin, you need to make sure you're signed in to Power BI.

1.  Select <bpt id="p1">**</bpt>Profile<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> ribbon tab in Excel. If you're already signed in to Power BI, you'll see a dialog that shows which account you're currently signed in with. If that's the account you want to use, great - go to the next set of steps to pin your range. Select <bpt id="p1">*</bpt>Sign out<ept id="p1">*</ept> if you want to use a different Power BI account. If you're not signed in, go to the next step (Step 2).

    ![](media/powerbi-publisher-for-excel/pbi_excel_publish_connect-to-data_0.png)

2.  If you're not signed in, select the <bpt id="p1">**</bpt>Sign In<ept id="p1">**</ept> link that appears when you select <bpt id="p2">**</bpt>Profile<ept id="p2">**</ept> from the <bpt id="p3">**</bpt>Power BI<ept id="p3">**</ept> ribbon tab in Excel, in the <bpt id="p4">**</bpt>Connect to Power BI<ept id="p4">**</ept> dialog type in the email address of the Power BI account you want to use, then select <bpt id="p5">**</bpt>Sign In<ept id="p5">**</ept>.

    ![](media/powerbi-publisher-for-excel/pbi_excel_publish_connect-to-data_1a.png)

Once you're signed in, follow these steps to pin a range to a dashboard:

1.  In Excel, select the <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> ribbon tab to see the <bpt id="p2">**</bpt>Pin<ept id="p2">**</ept> ribbon button.
2.  Select a range from your Excel workbook.
3.  Click the <bpt id="p1">**</bpt>Pin<ept id="p1">**</ept> button from the <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> ribbon to show the <bpt id="p3">**</bpt>Pin to dashboard dialog<ept id="p3">**</ept>. If you're not already signed into Power BI, you'll be prompted to do so. Select a workspace from the <bpt id="p1">**</bpt>Workspace<ept id="p1">**</ept> dropdown list. If you want to pin to your own dashboard, verify <bpt id="p1">**</bpt>My Workspace<ept id="p1">**</ept> is selected. If you want to pin to a dashboard in a group workspace, select the group from the drop-down list.
4.  Choose whether you want to pin to an <bpt id="p1">*</bpt>existing dashboard<ept id="p1">*</ept> or create a <bpt id="p2">*</bpt>new dashboard<ept id="p2">*</ept>.
5.  Click <bpt id="p1">**</bpt>Okay<ept id="p1">**</ept> to pin your selection to the dashboard.
6.  In <bpt id="p1">**</bpt>Pin to dashboard<ept id="p1">**</ept>, select an existing dashboard in the workspace or create a new one, and then click the <bpt id="p2">**</bpt>Ok<ept id="p2">**</ept> button.

    ![](media/powerbi-publisher-for-excel/XL-publish.gif)


## Pin a Chart to a dashboard
Just click on the chart, and then click Pin <ph id="ph1">![](media/powerbi-publisher-for-excel/pbi_excel_publisher_pin.png)</ph>.

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_chart.png)


## Manage pinned elements
With <bpt id="p1">**</bpt>Pin Manager<ept id="p1">**</ept>, you can update (refresh) a pinned element's associated tile in Power BI. You can also remove the pin between an element you've already pinned to dashboards in Power BI.

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_pin_manager2.png)

To update tiles in your dashboard, in <bpt id="p1">**</bpt>Pin Manager<ept id="p1">**</ept> select one or more elements and then select <bpt id="p2">**</bpt>Update<ept id="p2">**</ept>.

To remove the mapping between a pinned element in Excel and the associated tile in a dashboard, remove <bpt id="p1">**</bpt>Remove<ept id="p1">**</ept>. When you select <bpt id="p1">**</bpt>Remove<ept id="p1">**</ept>, you're <bpt id="p2">*</bpt>not<ept id="p2">*</ept> removing the element from your worksheet in Excel or deleting the associated tile in the dashboard. You are removing the pin, or <bpt id="p1">*</bpt>mapping<ept id="p1">*</ept>, between them. The removed element will no longer appear in <bpt id="p1">**</bpt>Pin Manager<ept id="p1">**</ept>. If you pin the element again, it will appear as a new tile.

To remove a pinned element (a tile) from a dashboard, you'll need to do that in Power BI. In the tile you want to delete, select the <bpt id="p1">**</bpt>Open menu<ept id="p1">**</ept> icon <ph id="ph1">![](media/powerbi-publisher-for-excel/pbi_excel_publisher_tile_openmenu.png)</ph> and then select <bpt id="p2">**</bpt>Delete tile<ept id="p2">**</ept>   <ph id="ph2">![](media/powerbi-publisher-for-excel/pbi_excel_publisher_tile_trashcan.png)</ph>.

## Connect to data in Power BI

Beginning with the July 2016 release of <bpt id="p1">**</bpt>Power BI publisher for Excel<ept id="p1">**</ept> (including the current release, linked to above), you can connect directly to data in the Power BI service and analyze that data in Excel using PivotTables and PivotCharts. This features makes it easy to use Power BI data and Excel together to analyze data that's most important to you.

Improvements include the following:

-   Any drivers required to connect to data in Power BI are automatically updated with each release - no need to install or manage those drivers yourself.
-   You no longer need to download .odc files to create the connections - <bpt id="p1">**</bpt>Power BI publisher for Excel<ept id="p1">**</ept> creates the connections automatically when you select which report or dataset you want to use.
-   Now you can create multiple connections and PivotTables in the same workbook
-   Errors are improved and specific to <bpt id="p1">**</bpt>Power BI publisher for Excel<ept id="p1">**</ept>, rather than using default Excel messages

### How to connect to Power BI data in Excel

To connect to Power BI data using <bpt id="p1">**</bpt>Power BI publisher for Excel<ept id="p1">**</ept>, follow these easy steps:

1.  Make sure you're signed in to Power BI. The steps describing how to sign in (or to sign in with a different account) are provided earlier in this article.

2.    Once you're signed in to Power BI with the account you want to use, select <bpt id="p1">**</bpt>Connect to Data<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> ribbon tab in Excel.

    ![](media/powerbi-publisher-for-excel/pbi_excel_publish_connect-to-data_1.png)

3.  Excel connects to Power BI using an HTTPS connection and presents the <bpt id="p1">**</bpt>Connect to data in Power BI<ept id="p1">**</ept> dialog, where you can select the <bpt id="p2">*</bpt>workspace<ept id="p2">*</ept> from which you want to select your data (1, in the image below), which <bpt id="p3">*</bpt>type of data<ept id="p3">*</ept> you want to connect to, either a <bpt id="p4">**</bpt>report<ept id="p4">**</ept> or a <bpt id="p5">**</bpt>dataset<ept id="p5">**</ept> (2), and a drop down (3) that allows you to select which <bpt id="p6">*</bpt>available report or dataset<ept id="p6">*</ept> to which to connect.

    ![](media/powerbi-publisher-for-excel/pbi_excel_publish_connect-to-data_2.png)

4.  When you make your choices and select <bpt id="p1">**</bpt>Connect<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>Connect to data in Power BI<ept id="p2">**</ept> dialog, Excel prepares a PivotTable and displays the <bpt id="p3">**</bpt>PivotTable Fields<ept id="p3">**</ept> pane, where you can select fields from your connected Power BI data, and create tables or charts that help you analyze the data.

    ![](media/powerbi-publisher-for-excel/pbi_excel_publish_connect-to-data_3.png)

If you don't have any data in Power BI, Excel detects that and offers to create sample data for you to connect to and try.

![](media/powerbi-publisher-for-excel/pbi_excel_publish_connect-to-data_4.png)

There are a few things to consider in this release of <bpt id="p1">**</bpt>Power BI publisher for Excel<ept id="p1">**</ept>:

-   <bpt id="p1">**</bpt>Shared data<ept id="p1">**</ept> - Data that has been shared with you, but isn't directly visible to you in Power BI, is not available in <bpt id="p2">**</bpt>Connect to Data<ept id="p2">**</ept>.
-   <bpt id="p1">**</bpt>SSAS on-premises<ept id="p1">**</ept> - If the dataset you select originates from an on-premises SQL Server Analysis Services (SSAS) and the dataset in Power BI uses DirectQuery to access the data, <bpt id="p2">**</bpt>Power BI publisher for Excel<ept id="p2">**</ept> connects to that data through the on-premises network connection, and does <bpt id="p3">*</bpt>not<ept id="p3">*</ept> go through Power BI to connect to that data. As such, any user trying to connect to such datasets must be connected to the on-premises network, and is authenticated for access to that data using the authentication method employed by the Analysis Services instance where the data is stored.
-   <bpt id="p1">**</bpt>Required drivers<ept id="p1">**</ept><ph id="ph1"> - </ph><bpt id="p2">**</bpt>Power BI publisher for Excel<ept id="p2">**</ept> installs all the necessary drivers for this feature to work, and does so automatically. Among those automatically installed drivers is the Excel OLE DB driver for Analysis Services; if that driver is removed by the user (or for any other reason), the connection to Power BI data will not work.
-   <bpt id="p1">**</bpt>Dataset must have Measures<ept id="p1">**</ept> - The dataset must have explicit Measures defined in order for Excel to treat the Measures as values in PivotTables, and to correctly analyze the data. Learn more about <bpt id="p1">[</bpt>Measures<ept id="p1">](powerbi-desktop-measures.md)</ept>.
-   <bpt id="p1">**</bpt>Support for Groups<ept id="p1">**</ept> - Datasets shared with people outside the specified group are not supported, and cannot be connected to.
-   <bpt id="p1">**</bpt>Free versus Pro subscriptions<ept id="p1">**</ept> - Activities associated with groups are not supported for free users of Power BI, and thus won't see any datasets or reports shared with a group in their own workspace.
-   <bpt id="p1">**</bpt>Shared reports or datasets<ept id="p1">**</ept> - Reports or datasets that were shared with you cannot be connected to.
-   <bpt id="p1">**</bpt>Using Tables instead of Data models<ept id="p1">**</ept> - Datasets and reports that are created by importing only tables from Excel (without a data model) are not supported at this time, and cannot be connected to.

Once you've created compelling charts or other visuals such as a range of data, you can easily pin those to a dashboard in Power BI, as described earlier in this article.

## Related Articles

There are many ways to use Excel and Power BI together, and get the best out of both. Take a look at the following articles for more information.

-   [Analyze in Excel](powerbi-service-analyze-in-excel.md)

-   [Analyze in Excel troubleshooting](powerbi-desktop-troubleshooting-analyze-in-excel.md)
