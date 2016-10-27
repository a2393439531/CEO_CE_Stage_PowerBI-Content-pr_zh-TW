<properties
   pageTitle="Load a Power BI report into an IFrame"
   description="Walkthrough to Integrate a report into an app - Load a report into an IFrame"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Step 3: Load a report into an IFrame

## 簡介

In <bpt id="p1">**</bpt>step 2<ept id="p1">**</ept> of Integrate a report into an app, <bpt id="p2">[</bpt>Get a Power BI report<ept id="p2">](powerbi-developer-integrate-report-get-report.md)</ept>, you get a Power BI report. In this step, you load a report into an <bpt id="p1">**</bpt>IFrame<ept id="p1">**</ept>.

![](media\powerbi-developer-integrate-report\integrate-report-load-report-iframe.png)

To load a report into an <bpt id="p1">**</bpt>IFrame<ept id="p1">**</ept>, you set the <bpt id="p2">**</bpt>src<ept id="p2">**</ept> attribute of an <bpt id="p3">**</bpt>IFrame<ept id="p3">**</ept> to the <bpt id="p4">**</bpt>embedUrl<ept id="p4">**</ept> property of a <bpt id="p5">**</bpt>report<ept id="p5">**</ept>, and create an <bpt id="p6">**</bpt>onload<ept id="p6">**</ept> handler to post a message with an <bpt id="p7">**</bpt>access token<ept id="p7">**</ept> to get access to the report visual. Below is JavaScript code to load a report into an <bpt id="p1">**</bpt>IFrame<ept id="p1">**</ept>.

**Load a report into an IFrame**

```
//Configure IFrame for the report after you have an Access Token. See Default.aspx.cs to learn how to get an Access Token
window.onload = function () {
    if ("" != document.getElementById('MainContent_accessToken').value)
    {
        var iframe = document.getElementById('iFrameEmbedReport');

        // To load a Report do the following:
        // Set the IFrame source to the EmbedUrl from the Get Reports operation
        iframe.src = document.getElementById('MainContent_ReportEmbedUrl').value;

        // Add an onload handler to submit the access token
        iframe.onload = postActionLoadReport;
    }
};

// Post the access token to the IFrame
function postActionLoadReport() {

    // Construct the push message structure
    // this structure also supports setting the reportId, groupId, height, and width.
    // when using a report in a group, you must provide the groupId on the iFrame SRC
    var m = {
        action: "loadReport",
        accessToken: document.getElementById('MainContent_accessToken').value
    };
    message = JSON.stringify(m);

    // push the message.
    iframe = document.getElementById('iFrameEmbedReport');
    iframe.contentWindow.postMessage(message, "*");;
}
```

If you downloaded and ran the <bpt id="p1">[</bpt>Integrate a report sample<ept id="p1">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)</ept>, the sample will look similar to below.

![](media\powerbi-developer-integrate-report\integrate-report-sample.png)

## 結論
In this walkthrough you learned how to integrate a report into an app by getting a report, and then loading the report into an <bpt id="p1">**</bpt>IFrame<ept id="p1">**</ept>. You can download the complete <bpt id="p1">[</bpt>Integrate a report sample<ept id="p1">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)</ept>  which shows all the parts working to embed a report into an ASP.NET web app. You can also view the complete <bpt id="p1">[</bpt>Integrate a report into an app code listing<ept id="p1">](powerbi-developer-integrate-report-code.md)</ept>.

## 請參閱

[Sign up for Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrate a report into an app walkthrough](powerbi-developer-integrate-report.md)  
[Integrate a report sample](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  
[Configure the integrate a report sample](powerbi-developer-integrate-report-register.md#configure-sample)  
[Get Reports operation](https://msdn.microsoft.com/library/mt634543.aspx)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)