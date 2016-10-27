<properties
   pageTitle="Create a new Power BI report"
   description="Create a new Power BI report"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/05/2016"
   ms.author="mihart"/>
# Create a new Power BI report

There are many different ways to create a new report. This topic shows you two of them.

-   From a dataset

-   From an existing report

## Create a new report from a dataset

This method creates a new report from scratch. To follow along, <bpt id="p1">[</bpt>download the Retail Analysis sample<ept id="p1">](powerbi-sample-downloads.md)</ept>.

1.  Start in Power BI service and select a dataset to open it. Opening a dataset actually opens the report editor.  You'll see a blank canvas and the report editing tools.

    ![](media/powerbi-service-create-a-new-report/powerbi-select-datasetnew.png)

2.  Explore your data and <bpt id="p1">[</bpt>add visuals<ept id="p1">](powerbi-service-visualizations-for-reports.md)</ept>. For this report, let's add a Gauge visual that tracks this year's sales.

   -  In the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> pane, select <bpt id="p2">**</bpt>Sales<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>This Year Sales<ept id="p3">**</ept> &gt; Value.

        ![](media/powerbi-service-create-a-new-report/powerbi-report-step1.png)

   -  Convert the visual to a Gauge by selecting the Gauge template <ph id="ph1">![](media/powerbi-service-create-a-new-report/powerbi-gauge-icon.png)</ph> from the <bpt id="p1">**</bpt>VIsualizations<ept id="p1">**</ept> pane.

        ![](media/powerbi-service-create-a-new-report/powerbi-report-step2.png)

   -  Drag <bpt id="p1">**</bpt>Sales<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>This Year Sales<ept id="p2">**</ept><ph id="ph2"> &gt; </ph><bpt id="p3">**</bpt>Goal<ept id="p3">**</ept> to the <bpt id="p4">**</bpt>Target value<ept id="p4">**</ept> well.

        ![](media/powerbi-service-create-a-new-report/powerbi-report-step3.png)

3.  Optionally, continue adding visuals, and then <bpt id="p1">[</bpt>save your report<ept id="p1">](powerbi-service-save-a-report.md)</ept>.

    ![](media/powerbi-service-create-a-new-report/powerbi-save.png)


## Create a new report from an existing report
Maybe you have a report that already connects to your dataset and has some visuals that you'd like to re-use or modify.  Why not simply copy that report as a basis for a new report?  To do that:

1.  <bpt id="p1">[</bpt>Open a report<ept id="p1">](powerbi-service-open-a-report-in-reading-view.md)</ept>.

2.  From the <bpt id="p1">**</bpt>File<ept id="p1">**</ept> menu, select <bpt id="p2">**</bpt>Save As<ept id="p2">**</ept>.

    ![](media/powerbi-service-create-a-new-report/powerbi-save-as.png)

3.  Type a name for the new report and select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.

    ![](media/powerbi-service-create-a-new-report/SaveReport.png)

    A Success message lets you know that the new report was saved to Power BI.

    ![](media/powerbi-service-create-a-new-report/saveSuccess1.png)

4.  Back in your Power BI navigation pane, select the new report to open it. Optionally, delete visuals you don't want to keep, modify other visuals, and add new ones.

    ![](media/powerbi-service-create-a-new-report/newReportNavPane.png)

5.  Have fun updating and editing your new report.


## Next Steps:

[Create new visualizations](powerbi-service-add-visualizations-to-a-report-ii.md)

<bpt id="p1">[</bpt>Delete visualizations<ept id="p1">](powerbi-service-delete-a-visualization.md)</ept> you don't need

## 請參閱

Read more about <bpt id="p1">[</bpt>reports in Power BI<ept id="p1">](powerbi-service-reports.md)</ept>

[Get started with Power BI](powerbi-service-get-started.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
