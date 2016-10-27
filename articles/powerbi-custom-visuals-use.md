<properties
   pageTitle="Add a custom visual to a report (Desktop)"
   description="Add a custom visual to a report in Desktop"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="03/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/30/2016"
   ms.author="mihart"/>

# Add a custom visual to a report (Desktop)  

You've <bpt id="p1">[</bpt>downloaded a custom visual template<ept id="p1">](powerbi-custom-visuals-download-from-the-gallery.md)</ept> and saved it to your computer or another location.  The next step is to import that visual template into a report so that it is added, as an option, to your Visualization pane.

![](media/powerbi-custom-visuals-use/pbi-custom-viz-icon.png)

>[AZURE.IMPORTANT]
A custom visual template is added to a specific report when imported. If you'd like to use the visual template in another report, you need to import it into that report as well.
When a report with a custom visual is saved using the <bpt id="p1">**</bpt>Save As<ept id="p1">**</ept> option, a copy of the custom visual template is saved with the new report.


1. Open Power BI Desktop and select the report where you want to add the custom visualization.  Open the report in <bpt id="p1">[</bpt>Editing View<ept id="p1">](powerbi-service-interact-with-a-report-in-editing-view.md)</ept>.

2.  There are two options to import a custom visual template: from the <bpt id="p1">**</bpt>File<ept id="p1">**</ept> menu or from the <bpt id="p2">**</bpt>Visualizations<ept id="p2">**</ept> pane.

    **From the Desktop File menu**

    - On the report <bpt id="p1">**</bpt>File<ept id="p1">**</ept> menu, choose <bpt id="p2">**</bpt>Import<ept id="p2">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p3">**</bpt>Power BI Custom Visual<ept id="p3">**</ept>. You must be in the editing view.  
      ![](media/powerbi-custom-visuals-use/power-bi-import.png)

    **From the Visualization pane**
    - In the <bpt id="p1">**</bpt>Visualizations<ept id="p1">**</ept> pane, choose <bpt id="p2">**</bpt>Insert (…)<ept id="p2">**</ept>.
      ![](media/powerbi-custom-visuals-use/InsertPane.png)  

    - Select <bpt id="p1">**</bpt>Import a custom visual<ept id="p1">**</ept>.  
      ![](media/powerbi-custom-visuals-use/InsertPane.png)  

3. <bpt id="p1">**</bpt>Review the warning<ept id="p1">**</ept>.

    A custom visual has access to the data in the report you use in the custom visual, and can perform actions on your behalf. If you share the report with others, when they view the report the custom visual can do the same, but for your co-workers. Take care to review the custom visual to ensure it comes from a trustworthy source. Microsoft recommends you work with your IT department if you're not sure whether to use a specific Custom Visual you obtained from the Power BI visuals gallery, through email, or from some other source.  

    ![](media/powerbi-custom-visuals-use/caution.png)

4. Select a .pbiviz file in the <bpt id="p1">**</bpt>Open<ept id="p1">**</ept> dialog.

5. An icon (also called a <bpt id="p1">*</bpt>template<ept id="p1">*</ept>) is added to your <bpt id="p2">**</bpt>Visualizations<ept id="p2">**</ept> pane.  

    ![](media/powerbi-custom-visuals-use/VisualUse.png)

6. Select the custom visual template to add it to your report as you would with any of the other templates in the Visualizations pane. Add fields and filters and build your visual.

7.  Format the custom visual as you would any other visual.  From the <bpt id="p1">**</bpt> Visualizations<ept id="p1">**</ept> pane, select the paintbrush icon. The formatting options available will vary by visual type.

### 請參閱

[Add a custom visual to a report in the Power BI Service](powerbi-custom-visuals-add-to-report.md)  
[Create and submit a custom visual](powerbi-custom-visuals-create-for-the-gallery.md)  
[Visualizations in Power BI](powerbi-service-visualizations-for-reports.md)  
Back to <bpt id="p1">[</bpt>Custom Visualizations in Power BI<ept id="p1">](powerbi-custom-visuals.md)</ept>  
[The Power BI custom visuals gallery](https://app.powerbi.com/visuals)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
