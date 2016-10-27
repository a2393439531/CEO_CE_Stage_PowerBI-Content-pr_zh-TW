<properties
   pageTitle="Create Calculated Measures"
   description="Define custom calculations to evaluate time-based functions"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""
   featuredVideoId="yn2bXVQJLx8"
   featuredVideoThumb=""
   courseDuration="14m"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/29/2016"
   ms.author="davidi"/>

# Create measures and work with time-based functions

A <bpt id="p1">*</bpt>measure<ept id="p1">*</ept> is a calculation that exists in your Power BI data model. To create a measure, in <bpt id="p1">**</bpt>Report<ept id="p1">**</ept> view select <bpt id="p2">**</bpt>New Measure<ept id="p2">**</ept> from the <bpt id="p3">**</bpt>Modeling<ept id="p3">**</ept> tab.

![](media/powerbi-learning-2-5-create-calculated-measures/2-5_1.png)

One of the great things about DAX, the Data Analysis Expression language in Power BI, is that it has lots of useful functions, particularly around time-based calculations such as <bpt id="p1">*</bpt>Year to Date<ept id="p1">*</ept> or <bpt id="p2">*</bpt>Year Over Year<ept id="p2">*</ept>. With DAX you can define a measure of time once, and then slice it by as many different fields as you want from your data model.

In Power BI, a defined calculation is called a <bpt id="p1">*</bpt>measure<ept id="p1">*</ept>. To create a <bpt id="p1">*</bpt>measure<ept id="p1">*</ept>, select <bpt id="p2">**</bpt>New Measure<ept id="p2">**</ept> from the <bpt id="p3">**</bpt>Home<ept id="p3">**</ept> tab. This opens the Formula bar where you can enter the DAX expression that defines your measure. As you type, Power BI suggests relevant DAX functions and data fields as you enter your calculation, and you'll also get a tooltip explaining some of the syntax and function parameters.

![](media/powerbi-learning-2-5-create-calculated-measures/2-5_2.png)

If your calculation is particularly long, you can add extra line breaks in the Expression Editor by typing <bpt id="p1">**</bpt>ALT-Enter<ept id="p1">**</ept>.

![](media/powerbi-learning-2-5-create-calculated-measures/2-5_3.png)

Once you've created a new measure, it will appear in one of the tables on the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> pane, found on the right side of the screen. Power BI inserts the new measure into whichever table you have currently selected, and while it doesn't matter exactly where the measure is in your data, you can easily move it by selecting the measure and using the <bpt id="p1">**</bpt>Home Table<ept id="p1">**</ept> drop-down menu.

![](media/powerbi-learning-2-5-create-calculated-measures/2-5_4.png)

You can use a measure like any other table column: just drag and drop it onto the report canvas or visualization fields. Measures also integrate seamlessly with slicers, segmenting your data on the fly, which means you can define a measure once, and use it in many different visualizations.

The <bpt id="p1">**</bpt>Calculate<ept id="p1">**</ept> DAX function is a powerful function that enables all sorts of useful calculations, which is especially useful for financial reporting and visuals.
