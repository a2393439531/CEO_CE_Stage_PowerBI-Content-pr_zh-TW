<properties
   pageTitle="DirectQuery for Oracle and Teradata databases"
   description="DirectQuery for Oracle and Teradata databases"
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
   ms.date="09/29/2016"
   ms.author="davidi"/>

# DirectQuery for Oracle and Teradata Databases

With Power BI Desktop you can connect to Oracle and Teradata databases directly using DirectQuery.

In this release, you can choose to connect to Oracle or Teradata databases using either <bpt id="p1">**</bpt>Import<ept id="p1">**</ept> or <bpt id="p2">**</bpt>DirectQuery<ept id="p2">**</ept>:

-   If you connect using <bpt id="p1">**</bpt>DirectQuery<ept id="p1">**</ept>, no data is imported or copied into Power BI Desktop. As you create or interact with a visualization, Power BI Desktop queries the underlying data source to get the necessary data to respond to your interaction, which means you’re always viewing current data. See <bpt id="p1">[</bpt>Use DirectQuery in Power BI Desktop<ept id="p1">](powerbi-desktop-use-directquery.md)</ept> for a description of DirectQuery.

-   If you connect with <bpt id="p1">**</bpt>Import<ept id="p1">**</ept>, data is imported into Power BI Desktop upon connection to the database, and interaction with the data is based on what was imported.

DirectQuery for Oracle and Teradata databases is available for Power BI Desktop and for the Power BI service.
