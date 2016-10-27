<properties
   pageTitle="More Advanced Data Sources and Transformation"
   description="Connect and combine two data sources - it's easy"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""
   featuredVideoId="8WsY0R2V_bw"
   courseDuration="8m"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/29/2016"
   ms.author="davidi"/>

# More Advanced Data Sources and Transformation

In this article, we investigate some advanced data import and cleaning techniques for <bpt id="p1">**</bpt>Power BI Desktop<ept id="p1">**</ept>. Once you've shaped your data in <bpt id="p1">**</bpt>Query Editor<ept id="p1">**</ept> and brought it into <bpt id="p2">**</bpt>Power BI Desktop<ept id="p2">**</ept>, you can look at it in a few different ways. There are three views in Power BI Desktop: <bpt id="p1">**</bpt>Report<ept id="p1">**</ept> view, <bpt id="p2">**</bpt>Data<ept id="p2">**</ept> view, and <bpt id="p3">**</bpt>Relationships<ept id="p3">**</ept> view. You see each view by selecting its icon in the upper left side of the canvas. In the following image, <bpt id="p1">**</bpt>Report<ept id="p1">**</ept> view is selected. The yellow bar beside the icon indicates which view is active.

![](media/powerbi-learning-1-4-advanced-data-sources-and-transformation/1-4_1.png)

To change the view, just select either of other two icons. The yellow bar beside the icon indicates which view is active.

Power BI Desktop can combine data from multiple sources into a single report, at any time during the modelling process. To add additional sources to an existing report, select <bpt id="p1">**</bpt>Edit Queries<ept id="p1">**</ept> in the <bpt id="p2">**</bpt>Home<ept id="p2">**</ept> ribbon and then select <bpt id="p3">**</bpt>New Source<ept id="p3">**</ept> in <bpt id="p4">**</bpt>Query Editor<ept id="p4">**</ept>.

There are many different possible data sources you can use in <bpt id="p1">**</bpt>Power BI Desktop<ept id="p1">**</ept>, including Folders. By connecting to a folder, you can import data from multiple files at once, such as a series of Excel files of CSV files. The files contained within your selected folder appear in <bpt id="p1">**</bpt>Query Editor<ept id="p1">**</ept> as binary content, and clicking the double-arrow icon at the top of the <bpt id="p2">**</bpt>Content<ept id="p2">**</ept> column loads their values.

![](media/powerbi-learning-1-4-advanced-data-sources-and-transformation/1-4_2.png)

One of Power BI's most useful tools is its <bpt id="p1">*</bpt>Filters<ept id="p1">*</ept>. For example, selecting the drop-down arrow next to a column opens a checklist of text filters that you can use to remove values from your model.

You can also merge and append queries, and turn multiple tables (or data from various files, in folders) into a single table that contains just the data you want. You can use the <bpt id="p1">**</bpt>Append Queries<ept id="p1">**</ept> tool to add the data from a new table to an existing query. Power BI Desktop attempt to match up the columns in your queries, which you can then adjust as necessary in <bpt id="p1">**</bpt>Query Editor<ept id="p1">**</ept>.

![](media/powerbi-learning-1-4-advanced-data-sources-and-transformation/1-4_3.png)

Finally, the <bpt id="p1">**</bpt>Add Custom Column<ept id="p1">**</ept> tool gives advanced users the option of writing query expressions from scratch using the powerful M language. You can add a custom column based on M query language statements, and get your data just the way you want it.

![](media/powerbi-learning-1-4-advanced-data-sources-and-transformation/1-4_4.png)
