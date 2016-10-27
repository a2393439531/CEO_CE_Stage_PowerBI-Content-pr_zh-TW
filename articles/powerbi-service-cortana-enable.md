<properties
   pageTitle="Enable Cortana for Power BI"
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
   ms.date="09/20/2016"
   ms.author="mihart"/>


# <a name="enable-cortana-for-power-bi"></a>Enable Cortana for Power BI

Ask natural language questions in Cortana and find answers from data stored in Power BI.

Before Cortana can look for answers in your Power BI datasets and reports, you'll need:

-  a dataset in Power BI enabled for Cortana to access

-  to add the account you use with Power BI for Windows.

  >[AZURE.NOTE] Cortana for Power BI is currently only available in English. Cortana is not currently available on mobile devices.

## <a name="enable-cortana-to-access-data-in-power-bi"></a>Enable Cortana to access data in Power BI
In the Power BI service, you'll need to repeat these steps for each dataset that you want Cortana to be able to access.

1.  Sign-in to Power BI service.

2. In the upper right corner, select the cog icon and choose <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept>.

    ![](media/powerbi-service-cortana-enable/PBI_cortana_settings.png)

3. Select the <bpt id="p1">**</bpt>Datasets<ept id="p1">**</ept> tab and select the dataset from the list on the left.

4.  Select <bpt id="p1">**</bpt>Q&amp;A and Cortana<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Allow Cortana to access this dataset<ept id="p2">**</ept><ph id="ph2"> &gt; </ph><bpt id="p3">**</bpt>Apply<ept id="p3">**</ept>.

    ![](media/powerbi-service-cortana-enable/PBI_cortana-enable-new.png)

    In this example, we're enabling Cortana on the Retail Analysis Sample dataset.

    >[AZURE.NOTE] When a new dataset or custom Cortana Answer Page is added to Power BI and enabled for Cortana, it can take up to 30 minutes for results to begin appearing.  Logging in and out of Windows 10, or otherwise restarting the Cortana process in Windows 10, will allow new content to appear immediately.

    >[AZURE.IMPORTANT]If you enable a dataset for Cortana, and that dataset is part of a content pack you own, you will need to re-publish for your colleagues to also be able to use it with Cortana.

5. Determine which Windows 10 version you are running. Check which version you have by selecting <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>System<ept id="p2">**</ept><ph id="ph2"> &gt; </ph><bpt id="p3">**</bpt>About<ept id="p3">**</ept>.

   -  If you have <bpt id="p1">[</bpt>Windows 10 version 1511 (Windows 10 November Update) up until 1607<ept id="p1">](http://blogs.windows.com/windowsexperience/2015/11/12/first-major-update-for-windows-10-available-today/)</ept>, add your work or school account and Microsoft account (complete steps 6 and 7 below).

   -  If you have <bpt id="p1">[</bpt>Windows 10 version 1607 (Windows 10 July 2016 update) or later<ept id="p1">](https://support.microsoft.com/en-us/kb/3176929)</ept>, add your work or school account (complete only step 6 below).

6. Add your work or school account for Cortana.
   -  Open Windows Settings &gt; Accounts.

         ![](media/powerbi-service-cortana-enable/power-bi-windows-accounts.png)

   -  Scroll to the bottom and select <bpt id="p1">**</bpt>Add a work or school account<ept id="p1">**</ept>.

         ![](media/powerbi-service-cortana-enable/power-bi-add-work-account.png)

7. On the <bpt id="p1">**</bpt>Accounts<ept id="p1">**</ept> page, scroll to the bottom where you'll see <bpt id="p2">**</bpt>Add a Microsoft account<ept id="p2">**</ept>.
      ![](media/powerbi-service-cortana-enable/power-bi-add-microsoft-account.png)

   -  Sign in with the account you use with Power BI.

Cortana will use this work or school account to check Power BI for potential answers to your questions in Cortana.

## <a name="see-also"></a>請參閱
<bpt id="p1">[</bpt>Using Cortana with Power BI<ept id="p1">](powerbi-service-cortana-intro.md)</ept>

<bpt id="p1">[</bpt>Create Cortana <bpt id="p2">*</bpt>Answer pages<ept id="p2">*</ept> in Power BI<ept id="p1">](powerbi-service-cortana-desktop-entity-cards.md)</ept>

<bpt id="p1">[</bpt>Q&amp;A in Power BI<ept id="p1">](powerbi-service-q-and-a.md)</ept>

<bpt id="p1">[</bpt>Power BI basic concepts<ept id="p1">](powerbi-service-basic-concepts.md)</ept>

More questions? <bpt id="p1">[</bpt>Try the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>
