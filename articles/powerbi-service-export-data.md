<properties
   pageTitle="Export data from a visualization"
   description="Export data from a report visualization and dashboard visualization"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="jtlLGRKBvXY"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/25/2016"
   ms.author="mihart"/>

# Export data from Power BI visualizations
Data can be exported from visuals on a dashboard and in reports.  

>[AZURE.NOTE] The maximum number of rows that can be downloaded is 10,000.

Watch Amanda export the data used in her dashboard and save it as a .csv file. Then follow the step-by-step instructions below the video to try it out yourself.

<iframe width="560" height="315" src="https://www.youtube.com/embed/jtlLGRKBvXY?start=61" frameborder="0" allowfullscreen></iframe>

## Export a dashboard visual's data

1. Select the ellipses in the top right corner of the visualization.

    ![](media/powerbi-service-export-data/pbi-export-tile3.png)

2. Choose the  <bpt id="p1">**</bpt>Export data<ept id="p1">**</ept> icon.

    ![](media/powerbi-service-export-data/pbi_export_dash.png)

    The data is exported to a CSV file. If the visual is filtered, then the downloaded data will also be filtered.

3. Open the CSV file in Excel.

    ![](media/powerbi-service-export-data/pbi-export-to-excel.png)

    >[AZURE.NOTE] If there is unicode in the .csv file, the text in Excel may not display properly. Although, opening it in Notepad will work fine. Examples of unicode are currency symbols and foreign words. the workaround for this is to import the csv into Excel, instead of opening the csv directly. To do this: 1. Open Excel 2. From the <bpt id="p1">**</bpt>Data<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Get external data<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>From text<ept id="p3">**</ept>.


## Export a report visual's data

1. Select the ellipses in the top right corner of the visualization. Choose  <bpt id="p1">**</bpt>Export data<ept id="p1">**</ept>.

    ![](media/powerbi-service-export-data/pbi_export_dialog.png)

    >[AZURE.NOTE] The option to remove a visual is only available in <bpt id="p1">[</bpt>report Editing View<ept id="p1">](powerbi-service-go-from-reading-view-to-editing-view.md)</ept>.

2. See step 3 above.

## 請參閱

[Dashboards in Power BI](powerbi-service-dashboards.md)

[Reports in Power BI](powerbi-service-reports.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
