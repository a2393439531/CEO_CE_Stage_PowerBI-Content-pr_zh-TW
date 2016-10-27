<properties
   pageTitle="Troubleshooting Analyze in Excel"
   description="Solutions to common issues for Analyze in Excel"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus=""
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/27/2016"
   ms.author="davidi"/>

# Troubleshooting Analyze in Excel

There may be times when using Analyze in Excel that you get an unexpected result, or the feature doesn't work as you expected. This page provides solutions for common issues when using Analyze in Excel.

> <bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> There's a separate page dedicated to describing and enabling <bpt id="p2">[</bpt>Analyze in Excel<ept id="p2">](powerbi-service-analyze-in-excel.md)</ept>.

> If you encounter a scenario that is not listed below, and it is causing you issues, you can ask for further assistance on the <bpt id="p1">[</bpt>community site<ept id="p1">](http://community.powerbi.com/)</ept>, or you can create a <bpt id="p2">[</bpt>support ticket<ept id="p2">](https://powerbi.microsoft.com/support/)</ept>.

This article contains the following troubleshooting sections:

-   Update Excel libraries for the OLE DB provider
-   Determining whether you need to update your Excel libraries
-   Connection cannot be made error
-   Forbidden error
-   No data models
-   Token expired error
-   Unable to access on-premises Analysis services
-   Can't drag anything to the PivotTable Values area (no measures)


## Update Excel libraries for the OLE DB provider
To use <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept>, your computer must have a current AS OLE DB provider installed. This <bpt id="p1">[</bpt>community post<ept id="p1">](http://community.powerbi.com/t5/Service/Analyze-in-Excel-Initialization-of-the-data-source-failed/m-p/30837#M8081)</ept> is a great source to verify your installation of the OLE DB provider, or to download a recent version.

The Excel libraries need to match your version of Windows in terms of its bit-level. If you have 64-bit Windows installed, you need to install the 64-bit OLE DB provider.

To download the latest Excel libraries, visit Power BI and select the <bpt id="p1">**</bpt>down arrow<ept id="p1">**</ept> in the upper right corner of the Power BI service, then select <bpt id="p2">**</bpt>Analyze in Excel updates<ept id="p2">**</ept>.

![](media/powerbi-desktop-troubleshooting-analyze-in-excel/tshoot-analyze-excel_1.png)

In the dialog that appears, select <bpt id="p1">**</bpt>Download (preview)<ept id="p1">**</ept>.

![](media/powerbi-desktop-troubleshooting-analyze-in-excel/tshoot-analyze-excel_2.png)

## Determining whether you need to update your Excel libraries
You can download the most recent version of the Excel OLE DB provider libraries from the links in the previous section. Once you download the appropriate OLD DB provider library and begin installation, checks are performed against your current installed version.

If your Excel OLE DB provider client libraries are up to date, you'll be presented with a dialog that looks like the following:

![](media/powerbi-desktop-troubleshooting-analyze-in-excel/troubleshoot-analyze-excel_3.png)

C:\Users\davidi\Desktop\powerbi-content-pr\articles\media\powerbi-desktop-troubleshooting-analyze-in-excel

Alternatively, if the new version you are installing is newer than the version on your computer, the following dialog appears:

![](media/powerbi-desktop-troubleshooting-analyze-in-excel/troubleshoot-analyze-excel_2.png)

If you see the dialog prompting you to upgrade, you should continue with the installation to get the most recent version of the OLE DB provider installed in your computer.

## Connection cannot be made error
The primary cause for a <bpt id="p1">*</bpt>connection cannot be made<ept id="p1">*</ept> error is that your computer's OLE DB provider client libraries are not current. For information about how to determine the correct update, and for download links, see <bpt id="p1">**</bpt>Update Excel libraries for the OLE DB provider<ept id="p1">**</ept> earlier in this article.

## Forbidden error
Some users have more than one Power BI account, and when Excel attempts to connect to Power BI using existing credentials, it may use credentials that do not have access to the dataset or report you want to access.

When this occurs, you may  receive an error titled <bpt id="p1">**</bpt>Forbidden<ept id="p1">**</ept>, which means you may be signed into Power BI with credentials that do not have permissions to the dataset. After encountering the <bpt id="p1">**</bpt>forbidden<ept id="p1">**</ept> error, when prompted to enter your credentials, use the credentials that have permission to access the dataset you're trying to use.

If you still run into errors, log into Power BI with the account that has permission, and verify that you can view and access the dataset in Power BI that you're attempting to access in Excel.

## No data models
If you encounter an error that states <bpt id="p1">**</bpt>Can't find OLAP cube model<ept id="p1">**</ept>, then the dataset you're trying to access has no data model, and therefore cannot be analyzed in Excel.

## Token expired error
If you receive a <bpt id="p1">**</bpt>token expired<ept id="p1">**</ept> error, it means you haven't recently used the <bpt id="p2">**</bpt>Analyze in Excel<ept id="p2">**</ept> feature on the computer you're using. Simply re-enter your credentials, or reopen the file, and the error should go away.

## Unable to access on-premises Analysis Services
If you're trying to access a dataset that has connections to on-premises Analysis Services data, you may receive an error message. <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept> does support connecting to datasets and reports on on-premises <bpt id="p2">**</bpt>Analysis Services<ept id="p2">**</ept> with a connection string, as long as your computer is on the same domain as the <bpt id="p3">**</bpt>Analysis Services<ept id="p3">**</ept> server, and your account has access to that <bpt id="p4">**</bpt>Analysis Services<ept id="p4">**</ept> server.

currently does not support connections to on-premises Analysis Services.

## Can't drag anything to the PivotTable Values area (no measures)

When <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept> connects to an external OLAP model (which is how Excel connects to Power BI), the <bpt id="p2">*</bpt>PivotTable<ept id="p2">*</ept> <bpt id="p3">[</bpt>requires <bpt id="p4">**</bpt>measures<ept id="p4">**</ept> to be defined in the external model<ept id="p3">](https://support.microsoft.com/kb/234700)</ept>, since all calculations are performed on the server. This is different than when you work with a local data source (such as tables in Excel, or when you're working with datasets in <bpt id="p1">**</bpt>Power BI Desktop<ept id="p1">**</ept> or the <bpt id="p2">**</bpt>Power BI service<ept id="p2">**</ept>), in which case the tabular model is available locally, and <bpt id="p3">[</bpt>you can use implicit measures<ept id="p3">](https://msdn.microsoft.com/library/gg399077.aspx)</ept>, which are measures that are generated dynamically and are not stored in the data model. In these cases, the behavior in Excel is different from the behavior in <bpt id="p1">**</bpt>Power BI Desktop<ept id="p1">**</ept> or the <bpt id="p2">**</bpt>Power BI service<ept id="p2">**</ept>: there may be columns in the data that can be treated as measures in Power BI, but can't be used as values (measures) in Excel.

To address this issue, you have a few options:

1.  Create <bpt id="p1">[</bpt>measures in your data model in <bpt id="p2">**</bpt>Power BI Desktop<ept id="p2">**</ept><ept id="p1">](powerbi-desktop-tutorial-create-measures.md)</ept>, then publish the data model to the <bpt id="p3">**</bpt>Power BI service<ept id="p3">**</ept> and access that published dataset from Excel.
2.  Create <bpt id="p1">[</bpt>measures in your data model from Excel PowerPivot<ept id="p1">](https://support.office.com/article/Create-a-Measure-in-Power-Pivot-d3cc1495-b4e5-48e7-ba98-163022a71198)</ept>.
3.  If you imported data from an Excel workbook that had only tables (and no data model), then you can <bpt id="p1">[</bpt>add the tables to the data model<ept id="p1">](https://support.office.com/article/Add-worksheet-data-to-a-Data-Model-using-a-linked-table-d3665fc3-99b0-479d-ba09-a37640f5be42)</ept>, then follow the steps in option 2, directly above, to create measures in your data model.

Once your measures are defined in the model in the Power BI service, you'll be able to use them in the <bpt id="p1">**</bpt>Values<ept id="p1">**</ept> area in Excel PivotTables.



## 另請參閱  

[Analyze in Excel](powerbi-service-analyze-in-excel.md)

[Tutorial: Create your own measures in Power BI Desktop](powerbi-desktop-tutorial-create-measures.md)

[Measures in PowerPivot](https://msdn.microsoft.com/library/gg399077.aspx)

[Create a Measure in PowerPivot](https://support.office.com/article/Create-a-Measure-in-Power-Pivot-d3cc1495-b4e5-48e7-ba98-163022a71198)

[Add worksheet data to a Data Model using a linked table](https://support.office.com/article/Add-worksheet-data-to-a-Data-Model-using-a-linked-table-d3665fc3-99b0-479d-ba09-a37640f5be42)

[Differences between OLAP and non-OLAP PivotTables in Excel](https://support.microsoft.com/kb/234700)
