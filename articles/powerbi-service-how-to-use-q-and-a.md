<properties
   pageTitle="How to use Power BI Q&amp;A"
   description="How to use Power BI Q&amp;A"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="qMf7OLJfCz8"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="mihart"/>

# How to use Power BI Q&amp;A  

## Ask questions of your data using natural language  
The Q&amp;A question box is where you type your question using natural language. Q&amp;A recognizes the words you type and figures out where (which dataset) to find the answer. Q&amp;A also helps you form your question with auto-completion, restatement, and other textual and visual aids.

![](media/powerbi-service-how-to-use-q-and-a/powerbi-qna.png)

The answer to your question is displayed as an interactive visualization and updates as you modify the question.

Q&amp;A is interactive and even fun, and, more often than not, one question will lead to many others as the visualizations reveal interesting paths to pursue. Watch Amanda demonstrate using Q&amp;A to create visuals, dig into those visuals, and pin them to dashboards.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## Use natural language to ask questions about your data

1.  Place your cursor in the question box. Even before you start typing, Q&amp;A displays a new screen with suggestions to help you form your question.

    ![](media/powerbi-service-how-to-use-q-and-a/powerbi-qna-cursor.png)  

    This  list contains:  
    - the questions used to create <bpt id="p1">[</bpt>tiles <ept id="p1">](powerbi-service-dashboard-tiles.md)</ept>that are already pinned to the dashboard, and  

    - the name of tables in the <bpt id="p1">[</bpt>underlying dataset(s)<ept id="p1">](powerbi-service-get-data.md)</ept>.  

    You can always choose one of these questions as a starting point and continue to refine the question to find the specific answer you are looking for.  Or, use a table name to help you word a new question.

2.  Select from the dropdown or begin typing your own question.  
    ![](media/powerbi-service-how-to-use-q-and-a/powerbi-qna-list.png)

3.  As you type a question, Power BI Q&amp;A picks the best <bpt id="p1">[</bpt>visualization <ept id="p1">](powerbi-service-visualization-types-for-reports-and-q-and-a.md)</ept>to display your answer; and the visualization changes dynamically as you modify the question. Q&amp;A also helps you formulate your question with auto-completion, by restating your question, and with other textual and visual aids.  
    ![](media/powerbi-service-how-to-use-q-and-a/powerbi-qna-viz.png)

4.  When you type a query, Power BI looks for an answer in any dataset that has a tile on that dashboard.  If all the tiles are from <bpt id="p1">*</bpt>datasetA<ept id="p1">*</ept>, then your answer will come from <bpt id="p2">*</bpt>datasetA<ept id="p2">*</ept>.  If there are tiles from <bpt id="p1">*</bpt>datasetA <ept id="p1">*</ept>and <bpt id="p2">*</bpt>datasetB<ept id="p2">*</ept>, then Q&amp;A will search for the best answer from those 2 datasets.

    The dataset(s) that is used to create the visualization is visible below the visualization.  

    ><bpt id="p1">**</bpt>Tip:<ept id="p1">**</ept> So be careful, if you only have one tile from <bpt id="p2">*</bpt>datasetA <ept id="p2">*</ept>and you remove it from your dashboard, Q&amp;A will no longer have access to <bpt id="p3">*</bpt>datasetA<ept id="p3">*</ept>.

5.  When you're happy with the result, <bpt id="p1">[</bpt>pin the visualization to a dashboard<ept id="p1">](powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box.md)</ept> by selecting the pin icon in the top right corner.

    ![](media/powerbi-service-how-to-use-q-and-a/PBI_QnA_finish-typing-question.jpg)

## Tell Q&amp;A which visualization to use.  
With Q&amp;A, not only can you ask your data to speak for itself, you can tell it how you want it displayed. Just add "as a <ph id="ph1">&amp;lt;</ph>visualization type<ph id="ph2">&amp;gt;</ph>" to the end of your question.  For example, "show inventory volume by plant as a map" and "show total inventory as a card".  Try it for yourself.


## How does Q&amp;A know how to answer questions?  
### Which datasets does Q&amp;A use?

How does Q&amp;A know how to answer data-specific questions? It relies on the names of the tables, columns, and calculated fields in the underlying dataset. So what you (or the dataset owner) call things is important! 

For example, suppose you had an Excel table named “Sales”, with columns titled “Product”, “Month”, “Units Sold”, “Gross Sales”, and “Profit”. You could ask questions about any of those entities.  You could ask "show <bpt id="p1">*</bpt>sales"<ept id="p1">*</ept>, "total <bpt id="p2">*</bpt>profit <ept id="p2">*</ept>by <bpt id="p3">*</bpt>month"<ept id="p3">*</ept>, "sort <bpt id="p4">*</bpt>products <ept id="p4">*</ept>by <bpt id="p5">*</bpt>units sold"<ept id="p5">*</ept>, and more.

Q&amp;A can answer questions that are based on how your dataset is organized. How would this work for data in Salesforce? When you connect to your salesforce.com account, Power BI generates a dashboard automatically.  Before you start asking questions with Q&amp;A, take a look at the data displayed in the dashboard visualizations and also at the data displayed in the Q&amp;A dropdown.

-   If the visualizations' axis labels and values include "sales",  "account", "month", and “opportunities”, then you can confidently ask questions such as: “Which <bpt id="p1">*</bpt>account <ept id="p1">*</ept>has the highest <bpt id="p2">*</bpt>opportunity<ept id="p2">*</ept>”, or “show <bpt id="p3">*</bpt>sales <ept id="p3">*</ept>by month as a bar chart”.
 
-   If the dropdown includes "salesperson", "state", and "year", then you can confidently ask questions such as: "which <bpt id="p1">*</bpt>salesperson <ept id="p1">*</ept>had the lowest <bpt id="p2">*</bpt>sales <ept id="p2">*</ept>in <bpt id="p3">*</bpt>Florida<ept id="p3">*</ept> in <bpt id="p4">*</bpt>2013<ept id="p4">*</ept>."

If you have website performance data in Google Analytics, you could ask Q&amp;A about time spent on a web page, number of unique page visits, and user engagement rates. Or, if you’re querying demographic data, you might ask questions about age and household income by location.

### Which visualization does Q&amp;A use?  
Q&amp;A picks the best visualization based on the data being displayed. Sometimes data in the underlying dataset(s) is defined as a certain type or category and this helps Q&amp;A know how to display it. For example, if data is defined as a date type, it is more likely to be displayed as a line chart. Data that is categorized as a city is more likely to be displayed as a map.

You can also tell Q&amp;A which visualization to use by adding it to your question. But keep in mind that it may not always be possible for Q&amp;A to display the data in the visualization type you requested.

For information about keywords that Q&amp;A recognizes, see <bpt id="p1">[</bpt>Tips for asking questions<ept id="p1">](powerbi-service-q-and-a-tips.md)</ept>.

## 請參閱  
Back to <bpt id="p1">[</bpt>Q&amp;A in Power BI<ept id="p1">](powerbi-service-q-and-a.md)</ept>  
[Tutorial: Use Q&amp;A with the Retail Sales sample](powerbi-service-tutorial-introduction-to-q-and-a.md)  
[Tips for asking questions in Q&amp;A](powerbi-service-q-and-a-tips.md)  
[Prepare a workbook for Q&amp;A](powerbi-service-make-your-data-work-well-with-q-and-a.md)  
[Pin a tile to the dashboard from Q&amp;A](powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box.md)  

More questions? [Try the Power BI Community](http://community.powerbi.com/)
