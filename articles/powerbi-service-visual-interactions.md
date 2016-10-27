<properties
   pageTitle="Change how visuals interact in a report"
   description="Documentation for how to set Visual interactions in a Microsoft Power BI report."
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="N_xYsCbyHPw"
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

# Visualization interactions in a Power BI report

By default, visualizations on a report page can be used to cross-filter and cross-highlight the other visualizations on the page.
For example, selecting a state on a map visualization highlights the column chart and filters the line chart to display only data that applies to that one state.
See <bpt id="p1">[</bpt>About filtering and highlighting<ept id="p1">](powerbi-service-about-filters-and-highlighting-in-reports.md)</ept>.

To change this default behavior, use the <bpt id="p1">**</bpt>Visuals Interaction<ept id="p1">**</ept> control.

>[AZURE.NOTE] The terms <bpt id="p1">*</bpt>cross-filter<ept id="p1">*</ept> and <bpt id="p2">*</bpt>cross-highlight<ept id="p2">*</ept> are used to distinguish the behavior described here from what happens when you use the <bpt id="p3">**</bpt>Filters<ept id="p3">**</ept> pane to filter and highlight visualizations.  

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1.  Select a visualization to make it active.  

2. Turn on <bpt id="p1">**</bpt>Visual Interactions<ept id="p1">**</ept> by selecting it from the top menu bar. Notice the filter and highlight icons that appear above the other visualizations on the report page.

    ![](media/powerbi-service-visual-interactions/pbi-visual-interaction-icon.png)

2.  Determine what impact the selected visualization should have on the others.  

    -   If it should cross-filter the other visualization, select the <bpt id="p1">**</bpt>filter<ept id="p1">**</ept> icon <ph id="ph1">![](media/powerbi-service-visual-interactions/pbi-filter-icon-outlined.png)</ph>.

    -   If it should cross-highlight that visualization, select the <bpt id="p1">**</bpt>highlight<ept id="p1">**</ept> icon <ph id="ph1">![](media/powerbi-service-visual-interactions/pbi-highlight-icon-outlined.png)</ph>.

    -   If it should have no impact, select the <bpt id="p1">**</bpt>no impact<ept id="p1">**</ept> icon <ph id="ph1">![](media/powerbi-service-visual-interactions/pbi-noimpact-icon-outlined.png)</ph>.

3.  Repeat for all other visualizations on the report page.

## 請參閱

 [How to use report filters](powerbi-service-how-to-use-a-report-filter.md)

[Filters and highlighting in reports](powerbi-service-about-filters-and-highlighting-in-reports.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
