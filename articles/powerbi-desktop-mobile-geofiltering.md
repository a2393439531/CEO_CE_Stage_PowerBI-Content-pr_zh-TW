<properties 
   pageTitle="Set geographic filtering in Power BI Desktop for the Power BI mobile apps"
   description="When you set geographic filtering in your model in Power BI Desktop, you can filter data for your location automatically in the Power BI mobile apps for iOS."
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
   manager="mblythe" 
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
   ms.date="10/12/2016"
   ms.author="maggies"/>

# Set geographic filtering in Power BI Desktop for the Power BI mobile apps

In Power BI Desktop, you can <bpt id="p1">[</bpt>categorize geographical data<ept id="p1">](powerbi-desktop-data-categorization.md)</ept> for a column, so Power BI Desktop knows how to treat values in visuals in a report. As an added benefit, when you or your colleagues view that report in the Power BI mobile app for iOS, Power BI automatically provides geographical filters that match where you are. 

For example, say you're a sales manager traveling to meet customers, and you'd like to quickly filter the total sales and revenue for the specific customer you're planning to visit. You want to break out the data for your current location, whether by state, city, or an actual address. Later, if you have time left, you'd like to visit other customers located nearby. You can <bpt id="p1">[</bpt>filter the report by your location to find those customers<ept id="p1">](powerbi-mobile-geofiltering.md)</ept>.

> [AZURE.NOTE] You can only filter by location in the mobile app if the geographic names in the report are in English &amp;#150; for example, "New York City" or "Germany".

## Identify geographic data in your report

1. In Power BI Desktop, switch to Data View <ph id="ph1">![](media/powerbi-desktop-mobile-geofiltering/pbi_desktop_data_icon.png)</ph>.

2. Select a column with geographic data &amp;#151; for example, a City column.

    ![](media/powerbi-desktop-mobile-geofiltering/power-bi-desktop-geo-column.png)

3. On the <bpt id="p1">**</bpt>Modeling<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Data Category<ept id="p2">**</ept>, then the correct category &amp;#151; in this example, <bpt id="p3">**</bpt>City<ept id="p3">**</ept>.

    ![](media/powerbi-desktop-mobile-geofiltering/power-bi-desktop-geo-category.png)

4. Continue setting geographic data categories for any other fields in the model. 

    > [AZURE.NOTE] You can set multiple columns for each data category in a model, but if you do the model can't filter for geography in the Power BI mobile app. To use geographic filtering in the mobile apps, set only one column for each data category &amp;#151; for example, only one <bpt id="p1">**</bpt>City<ept id="p1">**</ept> column, one <bpt id="p2">**</bpt>State or Province<ept id="p2">**</ept> column, and one <bpt id="p3">**</bpt>Country<ept id="p3">**</ept> column. 

## Create visuals with your geographic data

5. Switch to Report view <ph id="ph1">![](media/powerbi-desktop-mobile-geofiltering/power-bi-desktop-report-icon.png)</ph>, and create visuals that use the geographic fields in your data. 

    ![](media/powerbi-desktop-mobile-geofiltering/power-bi-desktop-geo-report.png)

    In this example, the model also contains a calculated column that brings city and state together in one column. Read about <bpt id="p1">[</bpt>creating calculated columns in Power BI Desktop<ept id="p1">](powerbi-desktop-calculated-columns.md)</ept>.

    ![](media/powerbi-desktop-mobile-geofiltering/power-bi-desktop-city-state-column.png)

6. Publish the report to the Power BI service.

## View the report in Power BI app for iOS

1. Open the report in the <bpt id="p1">[</bpt>Power BI app for iOS<ept id="p1">](powerbi-mobile-ipad-iphone-apps.md)</ept>.

2. If you're in a geographic location with data in the report, you can filter it automatically to your location.

    ![](media/powerbi-desktop-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

Read more about <bpt id="p1">[</bpt>filtering a report by location in the Power BI mobile apps for iOS<ept id="p1">](powerbi-mobile-geofiltering.md)</ept>.

### 請參閱  

- [Data categorization in Power BI Desktop](powerbi-desktop-data-categorization.md)  
- Questions? [Try asking the Power BI Community](http://community.powerbi.com/)