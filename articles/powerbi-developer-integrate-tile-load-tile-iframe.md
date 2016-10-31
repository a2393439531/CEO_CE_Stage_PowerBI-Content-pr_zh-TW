<properties
   pageTitle="載入 IFrame Power BI 磚"
   description="逐步解說將磚整合到應用程式-載入 IFrame 磚"
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

# 步驟 4︰ 載入 IFrame 磚

## 簡介

在 **步驟 3** 整合到應用程式磚的 [取得 Power BI 磚](powerbi-developer-integrate-tile-get-tile.md), ，取得 Power BI] 磚。 在此步驟中，載入到磚 **IFrame**。

![](media\powerbi-developer-integrate-tile\integrate-tile-load-tile-iframe.png)

若要載入到磚 **IFrame**, ，您設定 **src** 屬性 **IFrame** 至 **embedUrl** 屬性 **磚**, ，並建立 **onload** 張貼的訊息處理常式 **存取權杖** 以存取磚視覺。 以下是 JavaScript 程式碼載入到磚 **IFrame**。

**載入 IFrame 磚**

```
//Configure IFrame for the tile after you have an Access Token. See Default.aspx.cs to learn how to get an Access Token
window.onload = function () {
    if ("" != document.getElementById('MainContent_accessToken').value)
    {
        var iframe = document.getElementById('iFrameEmbedTile');

        // To load a tile do the following:
        // Set the IFrame source to the EmbedUrl from the Get Tiles operation
        iframe.src = document.getElementById('MainContent_tileEmbedUrl').value;

        // Add an onload handler to submit the access token
        iframe.onload = postActionLoadTile;
    }
};

// Post the access token to the IFrame
function postActionLoadTile() {

    // Construct the push message structure
    // This is where you assign the Access Token to get access to the tile visual
    var messageStructure = {
        action: "loadTile",
        accessToken: document.getElementById('MainContent_accessToken').value,
        height: 500,
        width: 500
    };
    message = JSON.stringify(messageStructure);

    // Push the message
    document.getElementById('iFrameEmbedTile').contentWindow.postMessage(message, "*");;
}
```

如果您下載並執行 [整合並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), ，看起來類似下列範例。

![](media\powerbi-developer-integrate-tile\integrate-tile-sample.png)

## 結論
在本逐步解說中，您學會如何取得方塊在儀表板，然後載入到磚將磚整合到應用程式 **IFrame**。 您可以下載完整 [整合並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  會顯示所有組件，將磚內嵌至 ASP.NET web 應用程式運作。 您也可以檢視完整 [磚整合應用程式程式碼清單](powerbi-developer-integrate-tile-code.md)。

## 請參閱

[註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[將磚整合到應用程式逐步解說](powerbi-developer-integrate-tile.md)  
[整合的並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[設定整合的並排顯示範例](powerbi-developer-integrate-tile-register.md#configure-sample)  
[取得作業儀表板](https://msdn.microsoft.com/library/mt465739.aspx)  
[取得圖格作業](https://msdn.microsoft.com/library/mt465741.aspx)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)