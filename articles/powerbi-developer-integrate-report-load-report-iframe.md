<properties
   pageTitle="Power BI 報表載入 IFrame"
   description="若要將報告整合到應用程式的逐步解說 IFrame 中載入報表"
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

# 步驟 3︰ 將報表載入 IFrame

## 簡介

在 **步驟 2** 整合至應用程式中，報表的 [取得 Power BI 報表](powerbi-developer-integrate-report-get-report.md), ，取得 Power BI 報表。 您可以在此步驟中，載入至報表 **IFrame**。

![](media\powerbi-developer-integrate-report\integrate-report-load-report-iframe.png)

若要載入至報表 **IFrame**, ，您設定 **src** 屬性 **IFrame** 至 **embedUrl** 屬性 **報表**, ，並建立 **onload** 張貼的訊息處理常式 **存取權杖** 才能存取報表視覺化。 以下是載入至報表的 JavaScript 程式碼 **IFrame**。

**IFrame 中載入報表**

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

如果您下載並執行 [整合報表範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app), ，看起來類似下列範例。

![](media\powerbi-developer-integrate-report\integrate-report-sample.png)

## 結論
在本逐步解說中，您學會如何取得在報表中，然後載入至報表將報表整合到應用程式 **IFrame**。 您可以下載完整 [整合報表範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  會顯示所有組件，將報表內嵌至 ASP.NET web 應用程式運作。 您也可以檢視完整 [將報告整合到應用程式程式碼清單](powerbi-developer-integrate-report-code.md)。

## 請參閱

[註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[將報告整合到應用程式逐步解說](powerbi-developer-integrate-report.md)  
[整合的報表範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  
[設定整合的報表範例](powerbi-developer-integrate-report-register.md#configure-sample)  
[取得報表作業](https://msdn.microsoft.com/library/mt634543.aspx)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)