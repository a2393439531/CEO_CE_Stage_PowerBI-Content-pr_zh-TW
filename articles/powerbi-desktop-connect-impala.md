<properties
   pageTitle="Connect to an Impala database in Power BI Desktop (Preview)"
   description="Easily connect to and use an Impala database in Power BI Desktop"
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
   ms.date="10/03/2016"
   ms.author="davidi"/>

# Connect to an Impala database in Power BI Desktop (Preview)

In Power BI Desktop, you can connect to an <bpt id="p1">**</bpt>Impala<ept id="p1">**</ept> database and use the underlying data just like any other data source in Power BI Desktop. This release of the <bpt id="p1">**</bpt>Impala<ept id="p1">**</ept> connector is in Preview, and is subject to change.

## Enable the Impala (Preview) feature

To get access to the <bpt id="p1">**</bpt>Impala<ept id="p1">**</ept> connector, you first need to enable this preview feature. In <bpt id="p1">**</bpt>Power BI Desktop<ept id="p1">**</ept>, select <bpt id="p2">**</bpt>File &gt; Options and settings &gt; Option<ept id="p2">**</ept> then in the <bpt id="p3">**</bpt>Options<ept id="p3">**</ept> window, select the <bpt id="p4">**</bpt>Preview Features<ept id="p4">**</ept> section and enable <bpt id="p5">**</bpt>Impala<ept id="p5">**</ept>, as shown below.

![](media/powerbi-desktop-connect-impala/connect_impala_1.png)

When you check that box, you turn on the <bpt id="p1">**</bpt>Impala<ept id="p1">**</ept> preview feature. You'll need to restart Power BI Desktop for the change to take effect. Once you do, the preview feature is available.

## Connect to an Impala database

Once you've enabled to preview feature, to connect to an <bpt id="p1">**</bpt>Impala<ept id="p1">**</ept> database select <bpt id="p2">**</bpt>Get Data<ept id="p2">**</ept> from the <bpt id="p3">**</bpt>Home<ept id="p3">**</ept> ribbon in Power BI Desktop. Select <bpt id="p1">**</bpt>Database<ept id="p1">**</ept> from the categories on the left, and you see <bpt id="p2">**</bpt>Impala (Beta)<ept id="p2">**</ept>.

![](media/powerbi-desktop-connect-impala/connect_impala_2.png)

In the <bpt id="p1">**</bpt>Impala<ept id="p1">**</ept> window that appears, type or paste the name of your Impala server into the box, and select <bpt id="p2">**</bpt>OK<ept id="p2">**</ept>. Note that you can choose to <bpt id="p1">**</bpt>Import<ept id="p1">**</ept> data directly into Power BI, or you can use <bpt id="p2">**</bpt>DirectQuery<ept id="p2">**</ept>. You can learn more about <bpt id="p1">[</bpt>using DirectQuery<ept id="p1">](powerbi-desktop-use-directquery.md)</ept>.

![](media/powerbi-desktop-connect-impala/connect_impala_3a.png)

When prompted, put in your username and password, or connect anonymously - either is supported.

![](media/powerbi-desktop-connect-impala/connect_impala_4.png)

><bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> Once you put in your username and password for a particular <bpt id="p2">**</bpt>Impala<ept id="p2">**</ept> server, Power BI Desktop uses those same credentials in subsequent connection attempts. You can modify those credentials by going to <bpt id="p1">**</bpt>File &gt; Options and settings &gt; Data source settings<ept id="p1">**</ept>.

Once you successfully connect, a <bpt id="p1">**</bpt>Navigator<ept id="p1">**</ept> window appears and displays the data available on the server, from which you can select one or multiple elements to import and use in <bpt id="p2">**</bpt>Power BI Desktop<ept id="p2">**</ept>.

![](media/powerbi-desktop-connect-impala/connect_impala_5.png)

## Considerations and Limitations

There are a few limits and considerations to keep in mind in this preview version of the <bpt id="p1">**</bpt>Impala<ept id="p1">**</ept> connector:

-   Future plans include enabling refresh support using the <bpt id="p1">**</bpt>Power BI Gateway<ept id="p1">**</ept>.

## 詳細資訊

﻿There are all sorts of data you can connect to using Power BI Desktop. For more information on data sources, check out the following resources:

-   [Getting Started with Power BI Desktop](powerbi-desktop-getting-started.md)

-   [Data Sources in Power BI Desktop](powerbi-desktop-data-sources.md)

-   [Shape and Combine Data with Power BI Desktop](powerbi-desktop-shape-and-combine-data.md)

-   [Connect to Excel workbooks in Power BI Desktop](powerbi-desktop-connect-excel.md)   

-   [Enter data directly into Power BI Desktop](powerbi-desktop-enter-data-directly-into-desktop.md)   
