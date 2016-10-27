<properties
   pageTitle="Power BI Pro content - what is it?"
   description="Power BI Pro content - what is it?"
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
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/29/2016"
   ms.author="davidi"/>

# Power BI Pro content - what is it?  

Power BI free and Pro licenses are different based on the kind of content users can consume. If your content contains any of the following items, it's Power BI Pro content:

-   Data from a DirectQuery dataset, such as <bpt id="p1">[</bpt>SQL Server Analysis Services<ept id="p1">](powerbi-sql-server-analysis-services-tabular-data.md)</ept> tabular data, <bpt id="p2">[</bpt>Azure SQL Database<ept id="p2">](powerbi-azure-sql-database-with-direct-connect.md)</ept>, <bpt id="p3">[</bpt>Azure SQL Data Warehouse<ept id="p3">](powerbi-azure-sql-data-warehouse-with-direct-connect.md)</ept>, or Apache <bpt id="p4">[</bpt>Spark for HDInsight<ept id="p4">](powerbi-spark-on-hdinsight-with-direct-connect.md)</ept>.

-   Data from a <bpt id="p1">[</bpt>dataset that refreshes more frequently than daily<ept id="p1">](powerbi-refresh-data.md)</ept>.

-   Data from a dataset that connects to on-premises data using the <bpt id="p1">[</bpt>Power BI Gateway - Personal <ept id="p1">](powerbi-personal-gateway.md)</ept> or the <bpt id="p2">[</bpt>On-premises Data Gateway<ept id="p2">](powerbi-gateway-onprem.md)</ept>.

-   Data (including reports, dashboards or tiles) from a dataset that uses <bpt id="p1">[</bpt>Row-level security (RLS)<ept id="p1">](powerbi-admin-rls.md)</ept>.

-   A dashboard or report that's installed from an <bpt id="p1">[</bpt>organizational content pack<ept id="p1">](powerbi-service-organizational-content-packs-introduction.md)</ept>.

-   A dashboard, report, or dataset that's contained in a <bpt id="p1">[</bpt>group workspace<ept id="p1">](powerbi-service-create-a-group-in-power-bi.md)</ept>.

-   A dashboard that contains data streamed at a rate above 10k rows/hour.

Conversely, if your content contains only the following items it will be consumable by both Power BI free and Pro users:

-   A dashboard or report connected to content packs for services (e.g. Dynamics CRM, Salesforce, and Google Analytics).

-   A dashboard or report with data imported from files such as Excel spreadsheets, Power BI Desktop, and CSV.

-   <bpt id="p1">[</bpt>Tiles pinned<ept id="p1">](https://msdn.microsoft.com/library/mt604784.aspx)</ept> from a report in SQL Server Reporting Services.


For example, if you create a manufacturing dashboard that updates progress multiple times during the day, anyone <bpt id="p1">*</bpt>consuming<ept id="p1">*</ept> that dashboard would need a Power BI Pro license. Or, if you create a report using the Power BI Gateway - Enterprise, then another that uses the personal gateway, anyone <bpt id="p1">*</bpt>consuming or interacting<ept id="p1">*</ept> with either of those reports would need a Power BI Pro license.

If you want to share your Power BI Pro content with users, they can sign up for a <bpt id="p1">[</bpt>free trial of Power BI Pro<ept id="p1">](powerbi-service-self-service-signup-for-power-bi.md#power-bi-pro-60-day-trial)</ept>, and gain access to your content during the trial period.

For a list of Power BI Pro features (and how those features compare to a free Power BI license), take a look at <bpt id="p1">[</bpt>Power BI Pricing<ept id="p1">](https://powerbi.microsoft.com/pricing)</ept>.
