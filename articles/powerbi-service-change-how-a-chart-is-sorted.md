<properties
   pageTitle="Change how a chart is sorted in a Power BI report"
   description="Change how a chart is sorted in a Power BI report"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
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
   ms.date="10/05/2016"
   ms.author="mihart"/>

# Change how a chart is sorted in a Power BI report

In Power BI, you can sort charts alphabetically by the names of the categories in the chart, or by the numeric values of each category. For example, this chart is sorted by store name.

![](media/powerbi-service-change-how-a-chart-is-sorted/PBI_ChartSortCategory.png)

It's easy to sort it from highest to lowest sales per square feet instead.

1.  Select the ellipses (...) and choose <bpt id="p1">**</bpt>Sort by Sales Per Sq Ft<ept id="p1">**</ept>.

2.  If necessary, select the sort icon <ph id="ph1">![](media/powerbi-service-change-how-a-chart-is-sorted/sortIcon.png)</ph> to change to <bpt id="p1">**</bpt>Descending<ept id="p1">**</ept>.

    ![](media/powerbi-service-change-how-a-chart-is-sorted/sortby.gif)

    <bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Not all visuals can be sorted.  The following visuals cannot be sorted: Treemap, Map, Filled Map, Scatter, Gauge, Card, Multi Row Card, Waterfall.

##  Sorting using other criteria

Sometimes, you want to sort your visual using a different column or other criteria.  For example, you might want to sort by month (and not in alphabetical order) or you might want to sort by entire numbers instead of by digit (example, 0, 1, 9, 20 and not 0, 1, 20, 9).  Here are several solutions:

-   In Power BI Desktop, <bpt id="p1">[</bpt>use the Data Tools Modeling tab to sort by a different column<ept id="p1">](powerbi-desktop-sort-by-column.md)</ept>.

-   In Excel, if you own the dataset, add a new column that concatenates the month name and number. Then refresh or re-import the dataset to see the new column in the Fields area.

-   In Excel, ensure that your numerical columns are tagged as "whole number" or "decimal" and not as "text."

## 請參閱

More about <bpt id="p1">[</bpt>Visualizations in Power BI reports<ept id="p1">](powerbi-service-visualizations-for-reports.md)</ept>.

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
