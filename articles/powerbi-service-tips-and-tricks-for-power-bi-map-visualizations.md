<properties
   pageTitle="Tips and Tricks for Power BI Map visualizations"
   description="Tips and Tricks for Power BI Map visualizations"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="ajTPGNpthcg"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/22/2016"
   ms.author="mihart"/>

# Tips and Tricks for Power BI Map visualizations  

Power BI integrates with Bing to provide default map coordinates (a process called geo-coding) so it's easier for you to create maps. Bing uses some algorithms and hints to try to get the right location, but it's a best guess. To increase the likelihood of correct geo-coding, you can use the following tips:

**1.**

When columns are named based on the geographic designation, it helps Bing guess what you want to display. For example, if you have a field of US state names such as <bpt id="p1">*</bpt>California<ept id="p1">*</ept> and <bpt id="p2">*</bpt>Washington<ept id="p2">*</ept>, if the column is not named based on the geographic designation (state, in this case), Bing might return the location of <bpt id="p3">*</bpt>Washington, DC<ept id="p3">*</ept> instead of Washington State for the word <bpt id="p4">*</bpt>Washington<ept id="p4">*</ept>. Naming that column <bpt id="p1">*</bpt>State<ept id="p1">*</ept> will improve the geocoding. The same is true for columns named <bpt id="p1">*</bpt>Country<ept id="p1">*</ept>, <bpt id="p2">*</bpt>State<ept id="p2">*</ept>, and <bpt id="p3">*</bpt>City<ept id="p3">*</ept>.   

**2.**

Some designations are ambiguous when considered in the context of multiple countries or regions. You can increase the accuracy of geo-coding by building columns that append multiple fields together and use those for plotting data locations. For example, instead of passing only <bpt id="p1">*</bpt>Wiltshire<ept id="p1">*</ept>, you can pass <bpt id="p2">*</bpt>Wiltshire, England<ept id="p2">*</ept> to get a more accurate geo-coding result. 

**3.**

You can always provide specific latitude and longitude locations. When you do this, you also need to fill the <bpt id="p1">*</bpt>Location<ept id="p1">*</ept> field when creating your visualizations. Otherwise, the data is aggregated by default, so for example, the latitude and longitude would be paired at the state level, not the city level. Latitude and Longitude fields must be in <bpt id="p1">*</bpt>Decimal Number<ept id="p1">*</ept> format, which you can set in the data model.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>


## Categorizing geographic fields to hint Bing's geocoding  
In Power BI Desktop, you can ensure fields are correctly geocoded by setting the <bpt id="p1">*</bpt>Data Category<ept id="p1">*</ept> on the data fields. In Power BI Desktop, select the desired table, go to the <bpt id="p1">**</bpt>Advanced<ept id="p1">**</ept> ribbon and then set the <bpt id="p2">**</bpt>Data Category<ept id="p2">**</ept> to <bpt id="p3">**</bpt>Address<ept id="p3">**</ept>, <bpt id="p4">**</bpt>City<ept id="p4">**</ept>, <bpt id="p5">**</bpt>Continent<ept id="p5">**</ept>, <bpt id="p6">**</bpt>Country/Region<ept id="p6">**</ept>, <bpt id="p7">**</bpt>Country<ept id="p7">**</ept>, <bpt id="p8">**</bpt>Postal Code<ept id="p8">**</ept>, <bpt id="p9">**</bpt>State<ept id="p9">**</ept> or <bpt id="p10">**</bpt>Province<ept id="p10">**</ept>. These data categories help Bing correctly encode the date. To learn more, see <bpt id="p1">[</bpt>Data categorization in Power BI Desktop<ept id="p1">](powerbi-desktop-data-categorization.md)</ept>.

## Better geocoding with more specific locations  
Sometimes, even setting the data categories for mapping isn't enough for Bing to correctly guess your intent. Within the query, you can build a more specific location like a street address using <bpt id="p1">**</bpt>Query Editor<ept id="p1">**</ept> in Power BI Desktop.  Use the <bpt id="p1">**</bpt>Add Column<ept id="p1">**</ept> feature to build a custom column, then build the desired location as follows: 


    = [Field1] & " " & [Field2]

Then use the resulting field in the map visualizations. This approach is very useful for building Street addresses from Shipping Address fields, which are common in data sets. Note that concatenation only works with text fields. If necessary, convert the street number to a <bpt id="p1">*</bpt>text<ept id="p1">*</ept> data type before using it to build an address.  

## 請參閱

[Power Bi visualizations](powerbi-service-visualizations-for-reports.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
