<properties
   pageTitle="Make your data work well with Q&amp;A in Power BI"
   description="Make your data work well with Q&amp;A in Power BI"
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

# Make your data work well with Q&amp;A in Power BI  

If you are a person who creates data models or builds Excel workbooks that will be used with Power BI, read on...

In Power BI, Q&amp;A can search structured data and choose the right visualization for your question -- that's what makes it a compelling tool to use.   

Q&amp;A can work on any uploaded Excel file that has tables, ranges, or contains a PowerPivot model, but the more optimizations and data cleaning you do, the more robust Q&amp;A performance is. 

## How Q&amp;A works  
Q&amp;A has a set of core natural language understanding abilities that work across your data. It has context-dependent keyword search for your Excel table, column, and calculated field names. Second, it has built-in knowledge for how to filter, sort, aggregate, group, and display data. 

For example, in an Excel table named “Sales”, with columns “Product”, “Month”, “Units Sold”, “Gross Sales”, and “Profit”, you could ask questions about any of those entities.  You could ask to show sales, total profit by month, sort products by units sold, and many others. Read more about the <bpt id="p1">[</bpt>kinds of questions you can ask<ept id="p1">](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx)</ept>, and <bpt id="p2">[</bpt>asking questions using a question template<ept id="p2">](powerbi-service-q-and-a.md)</ept> and <bpt id="p3">[</bpt>visualization types you can specify in a Q&amp;A query<ept id="p3">](powerbi-service-visualization-types-for-reports-and-q-and-a.md)</ept>.

## Prepare a workbook for Q&amp;A  
Q&amp;A relies on the names of tables, columns, and calculated fields to answer data-specific questions, meaning what you call entities in your workbook is important!

Here are some tips for making the most of Q&amp;A in your workbook.

-   Make sure your data is in an Excel table. Here's <bpt id="p1">[</bpt>how to create an Excel table<ept id="p1">](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&amp;rs=en-US&amp;ad=US)</ept>.

-   Make sure the names of your tables, columns, and calculated field make sense in English.

    For example, if you have a table with sales data, call the table “Sales”. Column names like “Year”, “Product”, “Sales Rep”, and “Amount” will work well with Q&amp;A.

>[AZURE.NOTE]  If your workbook has a Power Pivot data model, you can do even more optimizations. Read more about <bpt id="p1">[</bpt>Demystifying Power BI Q&amp;A part 2<ept id="p1">](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx)</ept> from our in-house team of natural language experts.

## 請參閱  
[Q&amp;A in Power BI](powerbi-service-q-and-a.md)  
[Tutorial: Introduction to Power BI Q&amp;A](powerbi-service-tutorial-introduction-to-q-and-a.md)  
[Get data (for Power BI)](powerbi-service-get-data.md)  
[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
