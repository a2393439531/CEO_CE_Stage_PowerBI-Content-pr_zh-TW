<properties 
   pageTitle="Reports on the iPad app"
   description="Learn about viewing reports in the Power BI mobile app for iOS on the iPad. You create reports in the Power BI service, then interact with them in the mobile apps."
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
   ms.date="10/10/2016"
   ms.author="maggies"/>
# <a name="reports-on-the-ipad-app-(power-bi-for-ios)"></a>Reports on the iPad app (Power BI for iOS)

A report is an interactive view of your data, with visualizations representing different findings and insights from that data. You <bpt id="p1">[</bpt>create and customize reports<ept id="p1">](powerbi-service-create-a-new-report.md)</ept> in the Power BI service <bpt id="p2">[</bpt>(https://powerbi.com)<ept id="p2">](https://powerbi.com)</ept>.

Then you view and interact with reports on the <bpt id="p1">[</bpt>iPad app for Microsoft Power BI<ept id="p1">](http://go.microsoft.com/fwlink/?LinkId=522062)</ept> for iOS.

## <a name="open-reports"></a>Open reports

-   Tap <bpt id="p1">**</bpt>Reports<ept id="p1">**</ept> at the top of <bpt id="p2">**</bpt>My Workspace<ept id="p2">**</ept>.

-   Or tap a tile on a dashboard, and tap the report icon <ph id="ph1">![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-open-report-icon.png)</ph>.

    > [AZURE.NOTE]  Not all tiles can open in a report. For example, tiles created by asking questions with Q&amp;A don't open reports.

-   Or tap the search icon <ph id="ph1">![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-search-icon.png)</ph> in the upper-right corner to search for it by name, or see the list of reports you've visited recently.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-report-search.png)

## <a name="see-other-pages-in-the-report"></a>See other pages in the report

-   Tap the tabs at the bottom of the app.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-report-tabs.png)


## <a name="cross-filter-a-report-page"></a>Cross-filter a report page

-   Tap a bar or column in a chart.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/PBI_iPad_Xflter.png)

    Tapping the <bpt id="p1">**</bpt>Raw Materials<ept id="p1">**</ept> column in the lower chart highlights related values in the upper chart.

## <a name="sort-a-chart"></a>Sort a chart

-  Tap the chart, tap the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and tap the field name.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-report-sort-order.png)

-   To reverse the sort order, tap the <bpt id="p1">**</bpt>Sort by<ept id="p1">**</ept> arrow, then tap the same field name again.

## <a name="drill-down-and-up-in-a-chart"></a>Drill down and up in a chart

Sometimes you can drill down in charts to see the values that make up one part of the chart. You can drill up and down in the iPad app, but you can't add it to a visualization. You can only <bpt id="p1">[</bpt>add drill down to a visualization<ept id="p1">](powerbi-service-drill-down-in-a-visualization.md)</ept> in a report in Power BI. 

> [AZURE.NOTE]  Currently, drill-down doesn't work on maps in the iPad.

-   Tap a visual. If it has a down arrow in the upper-right corner, then you can drill down. Tap the arrow, then tap a value in the visual &amp;#151; in this case, the <bpt id="p1">**</bpt>Oct<ept id="p1">**</ept> column.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/PBI_iPad_DrillDownNew.png)

-   To drill back up, tap the up arrow in the upper-left corner.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/PBI_iPad_DrillUpNew.png)

## <a name="filter-a-power-bi-report"></a>Filter a Power BI report

You can always filter individual visuals in a Power BI report by using the fields in the visual itself as filters. You can also filter whole pages in a report, if you or the report creator has <bpt id="p1">[</bpt>added filters to the page<ept id="p1">](powerbi-service-add-a-filter-to-a-report.md)</ept> in the Power BI service (<bpt id="p2">[</bpt>https://powerbi.com<ept id="p2">](http://powerbi.com/)</ept>). In the Power BI service, you can also add other fields as filters for a specific visual. 

> [AZURE.NOTE]  If you don't have Edit permission for a report, you can change the filters, but you can't save those changes. 

1. In a report, expand the Filters pane.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/PBI_WinAppCollapsFilter.png)

    If the report creator has set page-level filters, when you select a visual you see <bpt id="p1">*</bpt>visual-level filters<ept id="p1">*</ept> for that visual, and <bpt id="p2">*</bpt>page-level filters<ept id="p2">*</ept> for the whole page.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-report-filter-pane-basic-visual.png)

2. Select check boxes for the values you want.

3. Or you can switch the filtering mode. Tap <bpt id="p1">**</bpt>Basic filtering<ept id="p1">**</ept> and select <bpt id="p2">**</bpt>Advanced filtering<ept id="p2">**</ept> to select values using expressions instead.

    ![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-report-filter-type.png)

     Number fields offer expressions such as <bpt id="p1">**</bpt>is less than<ept id="p1">**</ept>, <bpt id="p2">**</bpt>is greater than<ept id="p2">**</ept>, <bpt id="p3">**</bpt>is not<ept id="p3">**</ept>, and <bpt id="p4">**</bpt>is blank<ept id="p4">**</ept>.

     Text fields offer expressions such as <bpt id="p1">**</bpt>contains<ept id="p1">**</ept>, <bpt id="p2">**</bpt>doesn't start with<ept id="p2">**</ept>, and <bpt id="p3">**</bpt>is not<ept id="p3">**</ept>.

       ![](media/powerbi-mobile-reports-on-the-ipad-app/power-bi-ipad-report-filter-pane-advanced.png)

4.  To add other fields to the Filters pane, go to the Power BI service (<bpt id="p1">[</bpt>https://powerbi.com<ept id="p1">](http://powerbi.com/)</ept>), <bpt id="p2">[</bpt>add filters to the page<ept id="p2">](powerbi-service-add-a-filter-to-a-report.md)</ept>, and save the report.

## <a name="go-back-to-my-workspace"></a>Go back to My Workspace

-  Tap the back arrow, or tap the report name &gt; <bpt id="p1">**</bpt>My Workspace<ept id="p1">**</ept>.

    ![](media/powerbi-mobile-reports-in-the-windows-app/power-bi-windows-10-report-breadcrumb.png)


### <a name="see-also"></a>請參閱 

-  <bpt id="p1">[</bpt>Get started with the iPad app<ept id="p1">](powerbi-mobile-iphone-app-get-started.md)</ept> for Power BI.
- Questions? <bpt id="p1">[</bpt>Try asking the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>


