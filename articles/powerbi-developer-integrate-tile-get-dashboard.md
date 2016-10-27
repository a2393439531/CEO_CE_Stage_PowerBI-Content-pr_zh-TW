<properties
   pageTitle="Get a Power BI dashboard"
   description="Walkthrough to Integrate a tile into an app - Get a Power BI dashboard"
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

# Step 2: Get a dashboard

## 簡介

In <bpt id="p1">**</bpt>step 1<ept id="p1">**</ept> of Integrate a tile into an app, <bpt id="p2">[</bpt>Register a web app with Azure AD<ept id="p2">](powerbi-developer-integrate-tile-register.md)</ept>, you register a web app so that your app can authenticate to <bpt id="p3">**</bpt>Azure Active Directory<ept id="p3">**</ept>. In this step, you use an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept>, and the <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> API to get a dashboard. After you get a dashboard, you can get a <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> tile.

![](media\powerbi-developer-integrate-tile\integrate-tile-get-dashboard.png)

To get a <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> dashboard, you use the <bpt id="p2">[</bpt>Get Dashboards<ept id="p2">](https://msdn.microsoft.com/library/mt465739.aspx)</ept> operation which gets a list of <bpt id="p3">**</bpt>Power BI<ept id="p3">**</ept> dashboards. From the list of dashboards, you can get a dashboard id. Once you have a dashboard id, you can get a <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> tile.

Before you can call the <bpt id="p1">[</bpt>Get Dashboards<ept id="p1">](https://msdn.microsoft.com/library/mt465739.aspx)</ept> operation, or any other <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> operation, you need to get an Azure Active Directory <bpt id="p3">**</bpt>authentication access token<ept id="p3">**</ept> (access token). An <bpt id="p1">**</bpt>access token<ept id="p1">**</ept> is used to allow your app access to <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> dashboards and tiles. To learn more about Azure Active Directory <bpt id="p1">**</bpt>access token<ept id="p1">**</ept> flow, see <bpt id="p2">[</bpt>Azure AD Authorization Code Grant Flow<ept id="p2">](https://msdn.microsoft.com/library/azure/dn645542.aspx)</ept>. The next section shows you how to get an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept> in a web app.

<a name="get-token"/>
## Get an authentication access token

Here's how to get an authentication access token to call a <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> operation.

-   <bpt id="p1">**</bpt>Step 1:<ept id="p1">**</ept> <bpt id="p2">[</bpt>Get an authorization code from Azure AD<ept id="p2">](#auth-code)</ept>
-   <bpt id="p1">**</bpt>Step 2:<ept id="p1">**</ept> <bpt id="p2">[</bpt>Get an access token from authorization code<ept id="p2">](#access-token)</ept>

<a name="auth-code"/>
### Step 1: Get an authorization code from Azure AD

The first step to get an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept> is to get an authorization code from <bpt id="p2">**</bpt>Azure AD<ept id="p2">**</ept>. To do this, you construct a query string with the following properties, and redirect to <bpt id="p1">**</bpt>Azure AD<ept id="p1">**</ept>.


**Authorization code query string**

```
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
```

After you construct a query string, you redirect to <bpt id="p1">**</bpt>Azure AD<ept id="p1">**</ept> to get an <bpt id="p2">**</bpt>authorization code<ept id="p2">**</ept>.  Below is a complete C# method to construct an <bpt id="p1">**</bpt>authorization code<ept id="p1">**</ept> query string, and redirect to <bpt id="p2">**</bpt>Azure AD<ept id="p2">**</ept>. In the next step, you get an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept> using the <bpt id="p2">**</bpt>authorization code<ept id="p2">**</ept>.

**Get authorization code**

```
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
```

<a name="access-token"/>
### Step 2: Get an access token from authorization code

In step 1 to get an authentication access token, you get an <bpt id="p1">**</bpt>authorization code<ept id="p1">**</ept> from Azure AD. Once <bpt id="p1">**</bpt>Azure AD<ept id="p1">**</ept> redirects back to your web app with an <bpt id="p2">**</bpt>authorization code<ept id="p2">**</ept>, you use the <bpt id="p3">**</bpt>authorization code<ept id="p3">**</ept> to get an access token. Below is a C# method to get an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept>. In the next section, you get a <bpt id="p1">**</bpt>dashboard<ept id="p1">**</ept> using an <bpt id="p2">**</bpt>access token<ept id="p2">**</ept>.

**Get access token**

```
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
```

## Get dashboard using access token

Now that you have an <bpt id="p1">**</bpt>access token<ept id="p1">**</ept>, you can call the <bpt id="p2">[</bpt>Get Dashboards<ept id="p2">](https://msdn.microsoft.com/library/mt465739.aspx)</ept> operation. The <bpt id="p1">[</bpt>Get Dashboards<ept id="p1">](https://msdn.microsoft.com/library/mt465739.aspx)</ept> operation returns a list of dashboards. You can get a dashboard from the list of dashboards. Below is a complete C# method to get a dashboard. Once you have a <bpt id="p1">**</bpt>dashboard<ept id="p1">**</ept>, you can get a <bpt id="p2">**</bpt>tile<ept id="p2">**</ept>. See <bpt id="p1">[</bpt>Step 3: Get a Power BI tile<ept id="p1">]( powerbi-developer-integrate-tile-get-tile.md)</ept>.

**Get dashboard**

```
//Get a dashboard id.
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
```

## 下一個步驟

To integrate a tile into an app, you need to get a tile. In the next step, you learn how to <bpt id="p1">[</bpt>Get a Power BI tile<ept id="p1">](powerbi-developer-integrate-tile-get-tile.md)</ept>.

[Next Step &gt;](powerbi-developer-integrate-tile-get-tile.md)

## 請參閱

[Sign up for Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrate a tile into an app walkthrough](powerbi-developer-integrate-tile.md)  
[Integrate a tile sample](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configure the integrate a tile sample](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Azure AD Authorization Code Grant Flow](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Get Dashboards operation](https://msdn.microsoft.com/library/mt465739.aspx)  
[Step 3: Get a Power BI tile](powerbi-developer-integrate-tile-get-tile.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)