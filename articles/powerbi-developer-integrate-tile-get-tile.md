<properties
   pageTitle="Get a Power BI tile"
   description="Walkthrough - Integrate a tile into an app - Register a web app with Azure AD"
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

# Step 3: Get a tile

## 簡介

In <bpt id="p1">**</bpt>step 2<ept id="p1">**</ept> of Integrate a tile into an app, <bpt id="p2">[</bpt>Get a Power BI dashboard<ept id="p2">](powerbi-developer-integrate-tile-get-dashboard.md)</ept>, you get a Power BI dashboard. In this step, you get a <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> tile from a dashboard.

![](media\powerbi-developer-integrate-tile\integrate-tile-get-tile.png)

To get a <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> tile you need an authentication <bpt id="p2">**</bpt>access token<ept id="p2">**</ept>. To learn how to get an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept>, see [Get an authentication access token]((powerbi-developer-integrate-tile-get-dashboard.md#get-token) in Step 2: Get a Power BI dashboard. You use an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept> to authenticate to <bpt id="p2">**</bpt>Azure AD<ept id="p2">**</ept> to gain access to <bpt id="p3">**</bpt>Power BI<ept id="p3">**</ept> tiles.

Here are the steps to get a Power BI tile.

- <bpt id="p1">**</bpt>Step 1:<ept id="p1">**</ept> Get an authorization code from Azure AD. See <bpt id="p1">[</bpt>Get an authorization code from Azure AD<ept id="p1">](powerbi-developer-integrate-tile-get-dashboard.md#auth-code)</ept> in Step 2: Get a Power BI dashboard.
- <bpt id="p1">**</bpt>Step 2:<ept id="p1">**</ept> Get an access token. See <bpt id="p1">[</bpt>Get an access token from authorization code<ept id="p1">](powerbi-developer-integrate-tile-get-dashboard.md#access-token)</ept> Step 2: Get a Power BI dashboard.
- <bpt id="p1">**</bpt>Step 3:<ept id="p1">**</ept> <bpt id="p2">[</bpt>Get a Power BI tile<ept id="p2">](#get-tile)</ept>

<a name="get-tile"/>
## Get a Power BI tile using access token

In step 2 of the <bpt id="p1">[</bpt>Integrate a tile into an app walkthrough<ept id="p1">](powerbi-developer-integrate-tile.md)</ept>, you get an <bpt id="p2">**</bpt>access token<ept id="p2">**</ept> to get a dashboard. You can use this <bpt id="p1">**</bpt>access token<ept id="p1">**</ept> to also get a tile. You get a tile with the <bpt id="p1">[</bpt>Get Tiles<ept id="p1">](https://msdn.microsoft.com/library/mt465741.aspx)</ept>  operation which returns a list of tiles in a <bpt id="p2">**</bpt>dashboard<ept id="p2">**</ept>. Below is a C# method to get a tile. Once you have a <bpt id="p1">**</bpt>tile<ept id="p1">**</ept>, you can load the tile into an <bpt id="p2">**</bpt>IFrame<ept id="p2">**</ept>. See <bpt id="p1">[</bpt>Load a Power BI tile into an IFrame<ept id="p1">](powerbi-developer-integrate-tile-load-tile-iframe.md)</ept>.

**Get tile**

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

To integrate a tile into an app, you load a tile into an IFrame. In the next step, you learn how to <bpt id="p1">[</bpt>Load a tile into an IFrame<ept id="p1">](powerbi-developer-integrate-tile-load-tile-iframe.md)</ept>.

[Next Step &gt;](powerbi-developer-integrate-tile-load-tile-iframe.md)

## 請參閱

[Sign up for Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrate a tile into an app walkthrough](powerbi-developer-integrate-tile.md)  
[Integrate a tile sample](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configure the integrate a tile sample](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Get Dashboards operation](https://msdn.microsoft.com/library/mt465739.aspx)  
[Get Tiles operation](https://msdn.microsoft.com/library/mt465741.aspx)  
[Step 4: Load a Power BI tile into an IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
