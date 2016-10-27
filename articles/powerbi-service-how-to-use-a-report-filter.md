<properties
   pageTitle="Take a tour of the Filters pane"
   description="How to use report filters"
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
   ms.date="10/24/2016"
   ms.author="mihart"/>

# <a name="take-a-tour-of-the-report-filters-pane"></a>Take a tour of the report Filters pane
This article takes a deep look at the report Filters pane. You'll see the pane in Editing View and in Reading View for Power BI reports.

There are many different ways to filter data in Power BI and we recommend first reading <bpt id="p1">[</bpt>About filters and highlighting<ept id="p1">](powerbi-service-about-filters-and-highlighting-in-reports)</ept>.

## <a name="working-with-filters"></a>Working with filters  
Reports can be opened in <bpt id="p1">[</bpt>Editing View<ept id="p1">](powerbi-service-interact-with-a-report-in-editing-view.md)</ept> or <bpt id="p2">[</bpt>Reading View<ept id="p2">](powerbi-service-interact-with-a-report-in-reading-view.md)</ept>. In Editing View, report owners can <bpt id="p1">[</bpt>add filters to a report<ept id="p1">](powerbi-service-add-a-filter-to-a-report)</ept> and those filters are saved with the report. People viewing the report in Reading View can interact with the filters, but cannot save filter changes to the report.

## <a name="filters-in-reading-view"></a>Filters in Reading View

When a report is open in Reading View, the Filters pane displays along the right side of the report canvas.  

>[AZURE.NOTE] If you don't see the pane, select the arrow in the top-right corner to expand it.

In this example, we've selected a visual that has 6 filters. The report page also has filters, listed under the <bpt id="p1">**</bpt>Page level filters<ept id="p1">**</ept> heading. And the entire report has a filter too:  <bpt id="p1">**</bpt>FiscalYear<ept id="p1">**</ept> is 2013 or 2014.  

![](media/powerbi-service-how-to-use-a-report-filter/power-bi-filter-visual-level.png)

Some of the filters have the word <bpt id="p1">**</bpt>All<ept id="p1">**</ept> next to them and this means that the entire field is being included as a filter.  For example, <bpt id="p1">**</bpt>Chain(All)<ept id="p1">**</ept> in the screenshot below tells us that this report page includes data about all the store chains.  On the other hand, the report level filter of <bpt id="p1">**</bpt>FiscalYear is 2013 or 2014<ept id="p1">**</ept> tells us that the report only includes data for the fiscal years of 2013 and 2014.

Anyone viewing this report can interact with these filters.

-    view the details of the filter by hovering and selecting the arrow next to the filter.

      ![](media/powerbi-service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)

-  change the filter, for example, change <bpt id="p1">**</bpt>Lindseys<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Fashions Direct<ept id="p2">**</ept>.

      ![](media/powerbi-service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)

-  delete the filter by selecting the <bpt id="p1">**</bpt>x<ept id="p1">**</ept> next to the filter name.

   >[AZURE.NOTE]  Deleting a filter removes it from the list but does not delete the data from the report.  For example, if you delete the <bpt id="p1">**</bpt>FiscalYear is 2013 or 2014<ept id="p1">**</ept> filter, fiscal year data will still remain in the report but it will not longer be filtered to show only 2013 and 2014; it will show all fiscal years the data contains.  However, once you delete the filter, you won't be able to modify it again since it is removed from the list. A better option is to clear the filter by selecting the eraser icon <ph id="ph1">![](media/powerbi-service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png)</ph>.

   ![](media/powerbi-service-how-to-use-a-report-filter/power-bi-delete-filter.png)

## <a name="filters-in-editing-view"></a>Filters in Editing View

When a report is open in Editing View, the Filters pane displays along the right side of the report canvas in the bottom half of the <bpt id="p1">**</bpt>Visualization pane<ept id="p1">**</ept>.


            ![](media/powerbi-service-how-to-use-a-report-filter/PBI_FilterList.jpg)。  

>[AZURE.NOTE] If you don't see the pane, select the arrow in the top-right corner to expand it.


If no visual is selected in the canvas, then the Filters pane displays just the filters that apply to the entire report page and to the entire report (if any have been set). In the example below, no visual is selected and there are no page level filters but there is a report level filter.  
![](media/powerbi-service-how-to-use-a-report-filter/PBI_FilterListWithReportFilter.jpg)  

If a visual is selected in the canvas, you will also see the filters that apply to just that visual:  
![](media/powerbi-service-how-to-use-a-report-filter/PBI_FilterListWithReportAndVIsLevelFilters.jpg)

To display options for a particular filter, select the down arrow next to the filter name.  In the example below, the report level filter is set to 2013 and 2014. And this is an example of <bpt id="p1">**</bpt>basic filtering<ept id="p1">**</ept>.  To display the advanced options, select <bpt id="p1">**</bpt>Advanced Filtering<ept id="p1">**</ept>.

![](media/powerbi-service-how-to-use-a-report-filter/PBI_FilterListDropdown.jpg)

## <a name="clear-a-filter"></a>Clear a filter  
 In either advanced or basic filtering mode, select the eraser icon  <ph id="ph1">![](media/powerbi-service-how-to-use-a-report-filter/PBI_eraserIcon.jpg)</ph> to reset the filter. 

##   <a name="add-a-filter"></a>Add a filter
-  To add a filter to a page or report, select a field from the Fields pane and drag it below the <bpt id="p1">**</bpt>Report level filters<ept id="p1">**</ept>  or <bpt id="p2">**</bpt>Page level filters<ept id="p2">**</ept> heading, where you see the words <bpt id="p3">**</bpt>Drag data fields here<ept id="p3">**</ept>. Once a field has been added as a filter, fine-tune it using the Basic filtering and Advanced filtering controls (described below).

-  One way to add a filter to a visual is by using the fields that are being used to create that visual. First, select a visual to make it active. The fields that are being used in the visual are listed in the Visualizations pane and in the Filters pane under the <bpt id="p1">**</bpt>Visual level filters<ept id="p1">**</ept> heading.

    ![](media/powerbi-service-how-to-use-a-report-filter/power-bi-visual-filter.png)  

    Fine-tune any of these fields using the Basic filtering and Advanced filtering controls (described below).

-  Another way to add a filter to a visual is to drag-and-drop a field into the <bpt id="p1">**</bpt>Visual level filters<ept id="p1">**</ept> bucket. Dragging a new field here does not add that field to the visual, but it does allow you to filter that visual with this new field. In the example below, <bpt id="p1">**</bpt>Chain<ept id="p1">**</ept> is added as a new filter to the visual. Notice that simply adding <bpt id="p1">**</bpt>Chain<ept id="p1">**</ept> as a filter does not alter the visual until you use the Basic or Advanced filtering controls.

    ![](media/powerbi-service-how-to-use-a-report-filter/power-bi-visual-filter.gif)


## <a name="types-of-filters:-text-field-filters"></a>Types of filters: text field filters  
### <a name="list-mode"></a>List mode  
Ticking a checkbox either selects or deselects the value. The <bpt id="p1">**</bpt>All<ept id="p1">**</ept> checkbox can be used to toggle the state of all checkboxes on or off. The checkboxes represent all the available values for that field.  As you adjust the filter, the restatement updates to reflect your choices. 

![](media/powerbi-service-how-to-use-a-report-filter/PBI_restatement.png)

Note how the restatement now says "is Amarilla or Carretera"

### <a name="advanced-mode"></a>Advanced mode  
Select <bpt id="p1">**</bpt>Advanced Filtering<ept id="p1">**</ept> to switch to advanced mode. Use the dropdown controls and text boxes to identify which fields to include. By choosing between <bpt id="p1">**</bpt>And<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Or<ept id="p2">**</ept>, you can build complex filter expressions. Click the <bpt id="p1">**</bpt>Apply Filter<ept id="p1">**</ept> button when you've set the values you want.  

![](media/powerbi-service-how-to-use-a-report-filter/aboutFilters.png)

## <a name="types-of-filters:-numeric-field-filters"></a>Types of filters: numeric field filters  
### <a name="list-mode"></a>List mode  
If the values are finite, selecting the field name displays a list.  See <bpt id="p1">**</bpt>Text field filters<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>List mode<ept id="p2">**</ept> above for help using checkboxes.   

### <a name="advanced-mode"></a>Advanced mode  
If the values are infinite or represent a range, selecting the field name opens the advanced filter mode. Use the dropdown and text boxes to specify a range of values that you want to see. 

![](media/powerbi-service-how-to-use-a-report-filter/PBI_dropdown-and-text.png)

By choosing between <bpt id="p1">**</bpt>And<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Or<ept id="p2">**</ept>, you can build complex filter expressions. Select the <bpt id="p1">**</bpt>Apply Filter<ept id="p1">**</ept> button when you've set the values you want.

## <a name="types-of-filters:-date-and-time"></a>Types of filters: date and time  
### <a name="list-mode"></a>List mode  
If the values are finite, selecting the field name displays a list.  See <bpt id="p1">**</bpt>Text field filters<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>List mode<ept id="p2">**</ept> above for help using checkboxes.   

### <a name="advanced-mode"></a>Advanced mode  
If the field values represent date or time, you can specify a start/end time when using Date/Time filters.  

![](media/powerbi-service-how-to-use-a-report-filter/PBI_date-time-filters.png)

## <a name="see-also"></a>請參閱  
<bpt id="p1">[</bpt>Filters and highlighting in reports<ept id="p1">](powerbi-service-about-filters-and-highlighting-in-reports.md)</ept>  
<bpt id="p1">[</bpt>Interact with filters and highlighting in report Reading View<ept id="p1">](powerbi-service-interact-with-a-report-in-reading-view.md)</ept>  
<bpt id="p1">[</bpt>Create filters in report Editing View<ept id="p1">](powerbi-service-add-a-filter-to-a-report.md)</ept>  
<bpt id="p1">[</bpt>Change how report visuals cross-filter and cross-highlight each other<ept id="p1">](powerbi-service-visual-interactions.md)</ept>

Read more about <bpt id="p1">[</bpt>reports in Power BI<ept id="p1">](powerbi-service-reports.md)</ept>  
<bpt id="p1">[</bpt>Power BI - Basic Concepts<ept id="p1">](powerbi-service-basic-concepts.md)</ept>

More questions? <bpt id="p1">[</bpt>Try the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>
