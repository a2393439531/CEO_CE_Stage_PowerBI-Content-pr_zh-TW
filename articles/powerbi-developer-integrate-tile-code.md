<properties
   pageTitle="將 Power BI 磚整合到應用程式程式碼清單"
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

# 將磚整合到應用程式程式碼清單

## 簡介

在 [磚整合應用程式逐步解說](powerbi-developer-integrate-tile.md) 您了解如何將內嵌 **磚** 使用 **IFrame**。 您可以下載完整 [整合並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app) 會顯示內嵌方塊的所有組件。 或者，您可以檢視下列基本來源的程式碼。 請注意這是只有基本來源的程式碼，不是整個 web 專案。

**範例的原始程式碼**

- [將方塊載入 IFrame (Default.aspx) 的範例 JavaScript](#default-aspx)
- [範例 C# 程式碼來取得存取權杖，取得儀表板，並取得並排顯示 (Default.aspx.cs)](#default-code)

<a name="default-aspx"/>
## 將方塊載入 IFrame (Default.aspx) 的範例 JavaScript
```
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <script type="text/javascript">
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
    </script>
    <asp:HiddenField ID="accessToken" runat="server" />
    <asp:Button ID="getTileButton" runat="server" OnClick="getTileButton_Click" Text="Get Tile" />
    <table>
        <tr><td>Tile Embed URL</td> <td><asp:Textbox ID="tileEmbedUrl" runat="server" Width="900px"></asp:Textbox></td></tr>

        <tr><td>Dashboard Tile</td><td></td></tr>
        <tr><td></td><td>
            <iframe ID="iFrameEmbedTile" height="500px" width="900px"></iframe>
        </td></tr>
    </table>
</asp:Content>
```

<a name="default-code"/>
## 範例 C# 程式碼來取得存取權杖，取得儀表板，並取得並排顯示 (Default.aspx.cs)
```
/* NOTE: This code is for sample purposes only. In a production application, you could use a MVC design pattern.
* In addition, you should provide appropriate exception handling and refactor authentication settings into
* a secure configuration. Authentication settings are hard-coded in the sample to make it easier to follow the flow of authentication.
* In addition, the sample uses a single web page so that all code is in one location. However, you could refactor the code into
* your own production model.
*/
public partial class _Default : Page
{
    string baseUri = "https://api.powerbi.com/beta/myorg/";

    protected void Page_Load(object sender, EventArgs e)
    {

        //Need an Authorization Code from Azure AD before you can get an access token to be able to call Power BI operations
        //You get the Authorization Code when you click Get Tile (see below).
        //After you call AcquireAuthorizationCode(), Azure AD redirects back to this page with an Authorization Code.
        if (Request.Params.Get("code") != null)
        {
            //After you get an AccessToken, you can call Power BI API operations such as Get Tile
            Session["AccessToken"] = GetAccessToken(
                Request.Params.GetValues("code")[0],
                Settings.Default.ClientID,
                Settings.Default.ClientSecret,
                Settings.Default.RedirectUri);

            //Redirect again to get rid of code=
            Response.Redirect("/Default.aspx");
        }

        //After the redirect above to get rid of code=, Session["authResult"] does not equal null, which means you have an
        //Access Token. With the Acccess Token, you can call the Power BI Get Tiles operation. Get Tiles returns information
        //about a tile, not the actual tile visual. You get the tile visual later with some JavaScript. See postActionLoadTile()
        //in Default.aspx.
        if (Session["AccessToken"] != null)            
        {
            //You need the Access Token in an HTML element so that the JavaScript can load a tile visual into an IFrame.
            //Without the Access Token, you can not access the tile visual.
            accessToken.Value = Session["AccessToken"].ToString();

            //Get first dashbaord. Sample assumes one dashbaord with one tile
            string dashboardId = GetDashboard(0);

            //You can get the Dashboard ID with the Get Dashboards operation. Or go to your dashboard, and get it from the url for the dashboard.
            //The dashboard id is at the end if the url. For example, https://msit.powerbi.com/groups/me/dashboards/00b7e871-cb98-48ed-bddc-0000c000e000              
            //In this sample, you get the first tile in the first dashbaord. In a production app, you would create a more robost
            //solution
            GetTile(dashboardId, 0);
        }
    }

    protected void getTileButton_Click(object sender, EventArgs e)
    {
        //You need an Authorization Code from Azure AD so that you can get an Access Token
        //Values are hard-coded for sample purposes.
        GetAuthorizationCode();
    }


    //Get a dashbaord id. In this sample, you get the first tile.
    protected string GetDashboard(int index)
    {
        string dashboardId = string.Empty;

        //Configure tiles request
        System.Net.WebRequest request = System.Net.WebRequest.Create(
            String.Format("{0}Dashboards",
            baseUri)) as System.Net.HttpWebRequest;

        request.Method = "GET";
        request.ContentLength = 0;
        request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

        //Get dashboards response from request.GetResponse()
        using (var response = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get reader from response stream
            using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
            {
                //Deserialize JSON string
                PBIDashboards dashboards = JsonConvert.DeserializeObject<PBIDashboards>(reader.ReadToEnd());

                //Sample assumes at least one Dashboard with one Tile.
                //You could write an app that lists all tiles in a dashboard
                dashboardId = dashboards.value[index].id;
            }
        }

        return dashboardId;
    }


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

    public void GetAuthorizationCode()
    {
        //NOTE: Values are hard-coded for sample purposes.
        //Create a query string
        //Create a sign-in NameValueCollection for query string
        var @params = new NameValueCollection
        {
            //Azure AD will return an authorization code.
            {"response_type", "code"},

            //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
            //You get the client id when you register your Azure app.
            {"client_id", Settings.Default.ClientID},

            //Resource uri to the Power BI resource to be authorized
            //The resource uri is hard-coded for sample purposes
            {"resource", "https://analysis.windows.net/powerbi/api"},

            //After app authenticates, Azure AD will redirect back to the web app. In this sample, Azure AD redirects back
            //to Default page (Default.aspx).
            { "redirect_uri", Settings.Default.RedirectUri}
        };

        //Create sign-in query string
        var queryString = HttpUtility.ParseQueryString(string.Empty);
        queryString.Add(@params);

        //Redirect to Azure AD Authority
        //  Authority Uri is an Azure resource that takes a client id and client secret to get an Access token
        //  QueryString contains
        //      response_type of "code"
        //      client_id that identifies your app in Azure AD
        //      resource which is the Power BI API resource to be authorized
        //      redirect_uri which is the uri that Azure AD will redirect back to after it authenticates

        //Redirect to Azure AD to get an authorization code
        Response.Redirect(String.Format("https://login.windows.net/common/oauth2/authorize?{0}", queryString));
    }

    public string GetAccessToken(string authorizationCode, string clientID, string clientSecret, string redirectUri)
    {
        //Redirect uri must match the redirect_uri used when requesting Authorization code.
        //Note: If you use a redirect back to Default, as in this sample, you need to add a forward slash
        //such as http://localhost:13526/

        // Get auth token from auth code       
        TokenCache TC = new TokenCache();

        //Values are hard-coded for sample purposes
        string authority = "https://login.windows.net/common/oauth2/authorize";
        AuthenticationContext AC = new AuthenticationContext(authority, TC);
        ClientCredential cc = new ClientCredential(clientID, clientSecret);

        //Set token from authentication result
        return AC.AcquireTokenByAuthorizationCode(
            authorizationCode,
            new Uri(redirectUri), cc).AccessToken;
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
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

## 請參閱

[將磚整合到應用程式逐步解說](powerbi-developer-integrate-tile.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
