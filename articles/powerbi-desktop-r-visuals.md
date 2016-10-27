<properties
   pageTitle="Create Power BI visuals using R"
   description="Create Power BI visuals using R"
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
   ms.date="09/08/2016"
   ms.author="davidi"/>

# Create Power BI visuals using R  

With Power BI Desktop, you can use R to visualize your data.

### Installing R

Power BI Desktop does not include, deploy or install the R engine. To run R scripts in Power BI Desktop, you must separately install <bpt id="p1">**</bpt>R<ept id="p1">**</ept> on your local computer. You can download and install <bpt id="p1">**</bpt>R<ept id="p1">**</ept> for free from many locations, including the <bpt id="p2">[</bpt>Revolution Open download page<ept id="p2">](https://mran.revolutionanalytics.com/download/)</ept>, and the <bpt id="p3">[</bpt>CRAN Repository<ept id="p3">](https://cran.r-project.org/bin/windows/base/)</ept>. The current release of R scripting in Power BI Desktop supports Unicode characters as well as spaces (empty characters) in the installation path.

### Enabling R Visuals
1.   To enable R visuals, select <bpt id="p1">**</bpt>File &gt; Options and settings &gt; Options<ept id="p1">**</ept> and in the <bpt id="p2">**</bpt>Options<ept id="p2">**</ept> page that appears, make sure your local R installation is specified in the <bpt id="p3">**</bpt>R Scripting<ept id="p3">**</ept> section of the <bpt id="p4">**</bpt>Options<ept id="p4">**</ept> window, as shown in the following image. In the following image, the path local installation of R is <bpt id="p1">**</bpt>C:\Program Files\R\R-3.2.0<ept id="p1">**</ept> and that path is explicitly provided in the text box. Make sure the path it displays properly reflects the local R installation you want Power BI Desktop to use.

    ![](media/powerbi-desktop-r-visuals/r-visuals-2.png)

Once you specify your R installation, you’re ready to begin creating R visuals.

#### Creating R visuals in Power BI Desktop

1.   Select the <bpt id="p1">**</bpt>R Visual<ept id="p1">**</ept> icon in the <bpt id="p2">**</bpt>Visualization<ept id="p2">**</ept> pane, as shown in the following image, to add an R visual.

    ![](media/powerbi-desktop-r-visuals/r-visuals-3.png)

2.   When you add an R visual to a report, Power BI Desktop does the following:

   a) A placeholder R visual image appears on the report canvas.

   b) The <bpt id="p1">**</bpt>R script editor<ept id="p1">**</ept> appears along the bottom of the center pane.

  ![](media/powerbi-desktop-r-visuals/r-visuals-4.png)

3.   Next, add fields you want to consume in your R script to the <bpt id="p1">**</bpt>Values<ept id="p1">**</ept> section in the <bpt id="p2">**</bpt>Fields<ept id="p2">**</ept> well, just as you would with any other Power BI Desktop visual. Only fields that have been added to the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> well are available to your R script, and you can add new fields, or remove unneeded fields from the <bpt id="p2">**</bpt>Fields<ept id="p2">**</ept> well while working on your R script in the Power BI Desktop <bpt id="p3">**</bpt>R script editor<ept id="p3">**</ept>. Power BI Desktop automatically detects which fields you have added or removed.

> <bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> The default aggregation type for R visuals is <bpt id="p2">*</bpt>do not summarize<ept id="p2">*</ept>.

4.   Now you can use the data you selected to create a plot. As you select fields, the <bpt id="p1">**</bpt>R script editor<ept id="p1">**</ept> generates supporting R script binding code based on your selections in the gray section along the top of the editor pane. As you select or remove additional fields, supporting code in the R script editor is automatically generated or removed accordingly.

    In the example shown in the following image, three fields were selected: hp, gear, and drat. As a result of those selections, the R script editor generated the following binding code:
      -  A dataframe called <bpt id="p1">**</bpt>dataset<ept id="p1">**</ept> was created
        -  That dataframe is comprised of the different fields selected by the user
      -  The default aggregation is <bpt id="p1">*</bpt>do not summarize<ept id="p1">*</ept>
      -  Similar to table visuals, fields are grouped and duplicate rows only appear once

    ![](media/powerbi-desktop-r-visuals/r-visuals-5.png)

    ><bpt id="p1">**</bpt>Tip:<ept id="p1">**</ept> In certain cases you may not want automatic grouping to occur, or you may want all rows to appear, including duplicates. In that case you can add an index field to your dataset which causes all rows to be considered unique, and prevents grouping.

    The generated dataframe is called <bpt id="p1">**</bpt>dataset<ept id="p1">**</ept>, and selected columns can be accessed by their respective names. For example, the gear field can be accessed by writing <bpt id="p1">*</bpt>dataset$gear<ept id="p1">*</ept> in your R script. For fields with spaces or special characters, use single quotes.

5. With the dataframe automatically generated by the fields you selected, you’re ready to write R script that results in plotting to the R default device. When the script is complete, select <bpt id="p1">**</bpt>Run<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>R script editor<ept id="p2">**</ept> title bar (<bpt id="p3">**</bpt>Run<ept id="p3">**</ept> is on the right side of the title bar).

    When <bpt id="p1">**</bpt>Run<ept id="p1">**</ept> is selected, Power BI Desktop identifies the plot and present it on the canvas.
Since the process is executed on your local R installation, make sure required packages are installed.

    Power BI Desktop replots the visual when any of the following events occur:
      - <bpt id="p1">**</bpt>Run<ept id="p1">**</ept> is selected from the <bpt id="p2">**</bpt>R script editor<ept id="p2">**</ept> title bar
      - Whenever a data change occurs, due to data refresh, filtering, or highlighting

The following image shows an example of the correlation plot code, and plots the correlations between attributes of different types of cars.

![](media/powerbi-desktop-r-visuals/r-visuals-6.png)

To get a larger view of the visualizations, you can minimize the <bpt id="p1">**</bpt>R script editor<ept id="p1">**</ept>. And of course, like other visuals in Power BI Desktop, you can cross filter the correlation plot by selecting only sport cars in the donut visual (the round visual on the right, in the above example image).

![](media/powerbi-desktop-r-visuals/r-visuals-7.png)

You can also modify the R script to customize the visual, and take advantage of the power of R by adding parameters to the plotting command.

The original plotting command was the following:

    corrplot(M, method = "color",  tl.cex=0.6, tl.srt = 45, tl.col = "black")

With a few changes in the R script, the command is now the following:

    corrplot(M, method = "circle", tl.cex=0.6, tl.srt = 45, tl.col = "black", type= "upper", order="hclust")

As a result, the R visual now plots circles, only considers at the upper half, and reorders the matrix to cluster correlated attributes, as shown in the following image.

![](media/powerbi-desktop-r-visuals/r-visuals-8.png)

When executing a R script that results in an error, the R visual is not plotted and an error message is displayed on the canvas. For details on the error, select <bpt id="p1">**</bpt>See details<ept id="p1">**</ept> from the R visual error on the canvas.

![](media/powerbi-desktop-r-visuals/r-visuals-9.png)

> <bpt id="p1">**</bpt>R scripts security:<ept id="p1">**</ept> R visuals are created from R scripts, which could contain code with security or privacy risks. When attempting to view or interact with an R visual the first time, a user is presented with a security warning message. Only enable R visuals if you trust the author and source, or after you review and understand the R script.

#### Known Limitations

R visuals in Power BI Desktop has a few limitations:

-  Data size limitations – data used by the R visual for plotting is limited to 150,000 rows. If more than 150,000 rows are selected, only the top 150,000 rows are used and a message is displayed on the image.

-  Calculation time limitation – if an R visual calculation exceeds 5 minutes the execution times out, resulting in an error.

-  Relationships – as with other Power BI Desktop visuals, if data fields from different tables with no defined relationship between them are selected, an error occurs.

-  R visuals are refreshed upon data updates, filtering, and highlighting. However, the image itself is not interactive and cannot be the source of cross-filtering.

-  R visuals respond to highlighting other visuals, but you cannot click on elements in the R visual in order to cross filter other elements.

-  Only plots that are plotted to the R default display device are displayed correctly on the canvas. Avoid explicitly using a different R display device.

-  In this release, RRO installations are not automatically identified by the 32-bit version of Power BI Desktop, so you must manually provide the path to the R installation directory in <bpt id="p1">**</bpt>Options and settings &gt; Options &gt; R Scripting<ept id="p1">**</ept>.

### 詳細資訊

Take a look at the following additional information about R in Power BI.

-   [Running R Scripts in Power BI Desktop](powerbi-desktop-r-scripts.md)

-   [Use an external R IDE with Power BI](powerbi-desktop-r-ide.md)
