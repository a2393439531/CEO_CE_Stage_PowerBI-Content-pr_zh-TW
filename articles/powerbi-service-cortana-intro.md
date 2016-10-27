<properties
   pageTitle="Introduction to Cortana for Power BI"
   description="Use Cortana with Power BI to get answers from your data. Activate Cortana for each Power BI dataset and then enable Cortana to access your datasets from mobile devices."
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
   ms.date="09/19/2016"
   ms.author="mihart"/>


# <a name="introduction-to-cortana-for-power-bi"></a>Introduction to Cortana for Power BI

Ask natural language questions in Cortana and find answers from data stored in Power BI.

>[AZURE.NOTE]  Cortana for Power BI is currently only available in English. Cortana is not currently available on mobile devices.

## <a name="how-do-cortana-and-power-bi-work-together?"></a>How do Cortana and Power BI work together?

With the November 2015 update of Windows 10, Cortana can now find answers from data stored in Power BI through the integration between Cortana and Power BI.

Similar to Power BI Q&amp;A, ask or type your questions using natural language. Cortana will search your Cortana-enabled datasets in Power BI for answers and display results directly in your Windows 10 device.   

Cortana can find answers either directly from datasets in Power BI or from report pages published to Power BI and designed specifically for Cortana (called <bpt id="p1">*</bpt>Answer Pages<ept id="p1">*</ept>).  Interact with the visualizations as you would in Power BI or, to further explore an answer, simply open a result in Power BI.

>[AZURE.NOTE]  Cortana now works with on-premises data that has been <bpt id="p1">[</bpt>enabled for Q&amp;A<ept id="p1">](powerbi-service-q-and-a-direct-query.md)</ept>.

Cortana ranks the answers from Power BI, giving you one or more best matches if there is high confidence a result is a good answer. Other potential answers from Power BI are listed in a Power BI section below any best matches. If you're a dataset owner, you can help Cortana return better answers by <bpt id="p1">[</bpt>creating specialized reports (called <bpt id="p2">*</bpt>Answer Pages<ept id="p2">*</ept>) for Cortana<ept id="p1">](powerbi-service-cortana-desktop-entity-cards.md)</ept> in Power BI to answer the most-common questions and by optimizing your model for Power BI Q&amp;A.

## <a name="how-do-i-get-started?"></a>如何開始使用？

- Cortana looks for answers in Power BI datasets that you have access to. If you are a dataset owner, <bpt id="p1">[</bpt>enable Cortana to access the dataset (and its reports)<ept id="p1">](powerbi-service-cortana-enable.md)</ept>.  

- If you are a dataset owner, <bpt id="p1">[</bpt>create Answer Pages designed specifically for Cortana<ept id="p1">](powerbi-service-cortana-desktop-entity-cards.md)</ept>.

## <a name="tips-for-using-power-bi-with-cortana"></a>Tips for using Power BI with Cortana

### <a name="before-you-begin"></a>開始之前

In Power BI, you can work with datasets that you own or that have been shared with you. To access those same datasets in Cortana, a dataset owner must <bpt id="p1">[</bpt>enable each  dataset for Cortana<ept id="p1">](powerbi-service-cortana-enable.md)</ept>.  

### <a name="asking-questions"></a>Asking questions

Any Power BI user can use Cortana to ask questions about their Power BI datasets.  Dataset owners can <bpt id="p1">[</bpt>improve answers by creating Answer Pages in Power BI<ept id="p1">](powerbi-service-cortana-desktop-entity-cards.md)</ept>.  

1. Using Cortana, ask or type a question.  For example, ask "how many new stores opened in March?"

2. Cortana looks for answers in the Power BI reports and datasets available to you, and displays them under the heading <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> and marked with the Power BI icon.

3. Power BI first looks for answers in <bpt id="p1">[</bpt>Answer Pages<ept id="p1">](powerbi-service-cortana-desktop-entity-cards.md)</ept> and then searches your datasets and reports for other answers and displays them in the form of visualizations.  The highest-scoring results display first as <bpt id="p1">*</bpt>best matches<ept id="p1">*</ept>, followed by links to other possible answers and applications. Best matches come from Power BI Answer Pages or Power BI reports.
  >[AZURE.NOTE] If you speak your question, Cortana will only display <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> answers if it finds a best match.  

4. To open an answer in Power BI, select the link.


### <a name="other-tips"></a>Other Tips

-  If the report has a filter, Cortana will understand questions that specify items in the filter's list, and apply the filter on-the-fly.

- Cortana will only search for answers in Power BI if the question has 2 or more words.

- If you add the word "my" to your question, Cortana searches available datasets for answers that contain information found in your Windows 10 profile (the information you see when you click on your picture).

## <a name="see-also"></a>請參閱
<bpt id="p1">[</bpt>Enable Cortana for Power BI<ept id="p1">](powerbi-service-cortana-enable.md)</ept>

<bpt id="p1">[</bpt>Introduction to Power BI Q&amp;A<ept id="p1">](powerbi-service-q-and-a.md)</ept>

<bpt id="p1">[</bpt>Power BI basic concepts<ept id="p1">](powerbi-service-basic-concepts.md)</ept>

More questions? <bpt id="p1">[</bpt>Try the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>
