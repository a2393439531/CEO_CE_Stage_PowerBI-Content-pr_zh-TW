<properties
   pageTitle="Hyperlinks in tables"
   description="Hyperlinks in tables"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="identified"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/05/2016"
   ms.author="mihart"/>
# Hyperlinks in tables

This topic teaches you how to create and work with hyperlinks in tables and matrixes.  URLs in Power BI tables (and matrixes) can function as hyperlinks. Underlined text in a table or matrix that changes color as you hover over it, is a hyperlink.  Clicking on it will take you to the linked URL. 

![](media/powerbi-service-hyperlinks-in-tables/hyperlinkedTable.png)

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Hyperlinks can also be added to <bpt id="p2">[</bpt>tiles on dashboards<ept id="p2">](powerbi-service-edit-a-tile-in-a-dashboard.md)</ept>, <bpt id="p3">[</bpt>text boxes in reports<ept id="p3">](powerbi-service-add-a-hyperlink-to-a-text-box.md)</ept>, and <bpt id="p4">[</bpt>text boxes on dashboards<ept id="p4">](powerbi-service-add-a-widget-to-a-dashboard.md)</ept>.

## To create a hyperlink in Power BI table or matrix

Hyperlinks in tables and matrixes can be created in Power BI Desktop, but not from Power BI Service. Hyperlinks can also be created in Excel Power Pivot before the workbook is imported into Power BI. Both methods are described below.

## Create a table or matrix hyperlink in Power BI Desktop
The procedure for adding a hyperlink depends on whether you've imported the data or connected to it using DirectQuery. Both scenarios are described below.

### For data imported into Power BI  

1. If the hyperlink doesn't already exist as a field in your dataset, use Desktop to add it as a <bpt id="p1">[</bpt>custom column<ept id="p1">](powerbi-desktop-common-query-tasks.md)</ept>.

2. Select the column and in the <bpt id="p1">**</bpt>Modeling<ept id="p1">**</ept> tab choose the dropdown for <bpt id="p2">**</bpt>Data Category<ept id="p2">**</ept>.

    ![](media/powerbi-service-hyperlinks-in-tables/PBI_data_category.png)

3. Select <bpt id="p1">**</bpt>Web URL<ept id="p1">**</ept>.

4. Switch to Report view and create a table or matrix using the field categorized as a Web URL. The hyperlinks will be blue and underlined.

    ![](media/powerbi-service-hyperlinks-in-tables/power-bi-table-with-hyperlinks.png)

4. <bpt id="p1">[</bpt>Publish the report from Desktop to Power BI service<ept id="p1">](powerbi-learning-4-1-publish-reports.md)</ept> and open the report in Power BI service. The hyperlinks will work there as well.

### For data connected with DirectQuery

You won't be able to create a new column in DirectQuery mode.  But if your data already contains URLs, you can turn those into hyperlinks.

2. In Report view, create a table using a field that contains URLs.

3. Select the column, and in the <bpt id="p1">**</bpt>Modeling<ept id="p1">**</ept> tab, choose the dropdown for <bpt id="p2">**</bpt>Data Category<ept id="p2">**</ept>.

3. Select <bpt id="p1">**</bpt>Web URL<ept id="p1">**</ept>. The hyperlinks will be blue and underlined.

4. <bpt id="p1">[</bpt>Publish the report from Desktop to Power BI service<ept id="p1">](powerbi-learning-4-1-publish-reports.md)</ept> and open the report in Power BI service. The hyperlinks will work there as well.

## Create a table or matrix hyperlink in Excel Power Pivot

1.  Open the workbook in Excel.

2.  Select the <bpt id="p1">**</bpt>PowerPivot<ept id="p1">**</ept> tab and then choose <bpt id="p2">**</bpt>Manage<ept id="p2">**</ept>.

    ![](media/powerbi-service-hyperlinks-in-tables/createHyperlinkInPowerPivot2.png)

3.  When Power Pivot opens, select the <bpt id="p1">**</bpt>Advanced <ept id="p1">**</ept>tab.

    ![](media/powerbi-service-hyperlinks-in-tables/createHyperlinkInPowerPivot3.png)

4.  Place your cursor in the column that contains the URLs that you'd like to turn into hyperlinks in Power BI tables.

    ><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: The URLS must start with either <bpt id="p2">**</bpt>http:// , https://<ept id="p2">**</ept> or <bpt id="p3">**</bpt>www<ept id="p3">**</ept>.

5.  In the <bpt id="p1">**</bpt>Reporting Properties<ept id="p1">**</ept> group, select the <bpt id="p2">**</bpt>Data Category<ept id="p2">**</ept> dropdown and choose <bpt id="p3">**</bpt>Web URL<ept id="p3">**</ept>. 

    ![](media/powerbi-service-hyperlinks-in-tables/createHyperlinksNew.png)

6.  From the Power BI service, connect to this workbook.

7.  Create a table visualization that includes the URL field.

    ![](media/powerbi-service-hyperlinks-in-tables/hyperlinksInTables.gif)


## 請參閱

[Visualizations in Power BI reports](powerbi-service-visualizations-for-reports.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
