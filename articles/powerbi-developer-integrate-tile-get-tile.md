<properties
   pageTitle="取得 Power BI 磚"
   description="逐步解說-磚整合應用程式-向 Azure AD 註冊 web 應用程式"
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

# 步驟 3︰ 取得並排顯示

## 簡介

在 **步驟 2** 整合到應用程式磚的 [取得 Power BI 儀表板](powerbi-developer-integrate-tile-get-dashboard.md), ，取得 Power BI 儀表板。 在此步驟中，您會得到 **Power BI** 儀表板] 磚。

![](media\powerbi-developer-integrate-tile\integrate-tile-get-tile.png)

若要取得 **Power BI** 需要驗證的磚 **存取權杖**。 若要了解如何取得 **存取權杖**, ，請參閱 [在步驟 2 中取得驗證存取 token]((powerbi-developer-integrate-tile-get-dashboard.md#get-token)︰ 取得 Power BI 儀表板。 您使用 **存取權杖** 向 **Azure AD** 存取 **Power BI** 磚。

若要取得 Power BI 磚步驟如下︰

- 
            **步驟 1:** 從 Azure AD 取得授權碼。 請參閱 [從 Azure AD 取得授權碼](powerbi-developer-integrate-tile-get-dashboard.md#auth-code) 在步驟 2︰ 取得 Power BI 儀表板。
- 
            **步驟 2:** 取得存取權杖。 請參閱 [從授權碼取得存取權杖](powerbi-developer-integrate-tile-get-dashboard.md#access-token) 步驟 2︰ 取得 Power BI 儀表板。
- 
            **步驟 3:** [取得 Power BI 磚](#get-tile)

<a name="get-tile"/>
## 取得 Power BI 磚使用存取權杖

在步驟 2 的 [磚整合應用程式逐步解說](powerbi-developer-integrate-tile.md), ，得到 **存取權杖** 取得儀表板。 您可以使用這個 **存取權杖** 也取得並排顯示。 取得的磚 [取得磚](https://msdn.microsoft.com/library/mt465741.aspx)  作業會傳回清單中的並排 **儀表板**。 以下是 C# 方法來取得並排顯示。 一旦 **磚**, ，您可以載入到磚 **IFrame**。 請參閱 [Power BI 磚載入 IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md)。

**取得圖格**

```
//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

## 下一個步驟

將磚整合至應用程式，您載入磚 IFrame。 在下一個步驟中，您了解如何 [磚載入 IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md)。

[下一步 >](powerbi-developer-integrate-tile-load-tile-iframe.md)

## 請參閱

[註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[將磚整合到應用程式逐步解說](powerbi-developer-integrate-tile.md)  
[整合的並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[設定整合的並排顯示範例](powerbi-developer-integrate-tile-register.md#configure-sample)  
[取得作業儀表板](https://msdn.microsoft.com/library/mt465739.aspx)  
[取得圖格作業](https://msdn.microsoft.com/library/mt465741.aspx)  
[步驟 4︰ 將 IFrame 載入 Power BI 磚](powerbi-developer-integrate-tile-load-tile-iframe.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
