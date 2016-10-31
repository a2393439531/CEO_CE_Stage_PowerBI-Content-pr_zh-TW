<properties
   pageTitle="取得 Power BI 報表"
   description="逐步解說將報表整合到應用程式-取得 Power BI 報表"
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

# 步驟 2︰ 取得報表

## 簡介

在 **步驟 1** 整合至應用程式中，報表的 [向 Azure AD 註冊 web 應用程式](powerbi-developer-integrate-report-register.md), ，您註冊 web 應用程式，讓您的應用程式可以驗證至 **Azure Active Directory**。 在此步驟中，您會使用 **存取權杖**, ，而 **Power BI** API 來取得報表。

![](media\powerbi-developer-integrate-report\integrate-report-get-report.png)

若要取得 **Power BI** 報告，您使用 [取得報表](https://msdn.microsoft.com/library/mt634543.aspx) 作業就會取得一份 **Power BI** 報表。 從清單中的報表，您可以看到一個報告 **embedUrl**。 一旦您有一份報表 **embedUrl**, ，您可以載入至報表 **IFrame**。

您可以呼叫之前 [取得報表](https://msdn.microsoft.com/library/mt634543.aspx) 作業，或任何其他 **Power BI** 作業，您需要取得 Azure Active Directory **驗證存取權杖** （存取權杖）。  **存取權杖** 可讓您的應用程式存取 **Power BI** 報表。 若要深入了解 Azure Active Directory **存取權杖** 流程，請參閱 [Azure AD 授權碼授與流程](https://msdn.microsoft.com/library/azure/dn645542.aspx)。 下一節中會示範如何取得 **存取權杖** 的 web 應用程式。

<a name="get-token"/>
## 取得驗證存取權杖

以下是如何取得驗證的存取權杖來呼叫 **Power BI** 作業。

-   
            **步驟 1:** [從 Azure AD 取得授權碼](#auth-code)
-   
            **步驟 2:** [從授權碼取得存取權杖](#access-token)

<a name="auth-code"/>
### 步驟 1︰ 從 Azure AD 取得授權碼

若要取得第一個步驟 **存取權杖** 是取得授權碼從 **Azure AD**。 若要這樣做，請建構查詢字串具有下列屬性，並重新導向至 **Azure AD**。


**授權程式碼查詢字串**

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

建構查詢字串之後，您重新導向至 **Azure AD** 取得 **授權碼**。  以下是完整 C# 方法來建構 **授權碼** 查詢字串，並重新導向至 **Azure AD**。 在下一個步驟中，您會得到 **存取權杖** 使用 **授權碼**。

**取得授權碼**

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
### 步驟 2︰ 取得存取權杖的授權碼

在步驟 1 中取得驗證存取權杖，您會得到 **授權碼** 從 Azure AD。 一次 **Azure AD** 重新導向回到您的 web 應用程式與 **授權碼**, ，您使用 **授權碼** 以取得存取權杖。 以下是 C# 方法來取得 **存取權杖**。 在下一節中，您會得到 **報表** 使用 **存取權杖**。

**取得存取權杖**

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

## 取得報表使用存取權杖

您現在已 **存取權杖**, ，您可以呼叫 [取得報表](https://msdn.microsoft.com/library/mt634543.aspx) 作業。  [取得報表](https://msdn.microsoft.com/library/mt634543.aspx) 作業會傳回一份報表。 您可以取得報表的報表清單中。 以下是完整 C# 方法以取得報告。 一旦 **報表**, ，您可以將它載入 **IFrame**。 請參閱 [步驟 3: Power BI 報表載入 IFrame](powerbi-developer-integrate-report-load-report-iframe.md)。

**取得報表**

```
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
                ReportEmbedUrl.Text = Reports.value[index].embedUrl;
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

## 下一個步驟

若要將報表整合到應用程式，您載入報表 IFrame。 在下一個步驟中，您了解如何 [報表載入 IFrame](powerbi-developer-integrate-report-load-report-iframe.md)。

[下一步 >](powerbi-developer-integrate-report-load-report-iframe.md)

## 請參閱

[註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[將報告整合到應用程式逐步解說](powerbi-developer-integrate-report.md)  
[整合的報表範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  
[設定整合的報表範例](powerbi-developer-integrate-report-register.md#configure-sample)  
[Azure AD 授權碼授與流程](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[取得報表作業](https://msdn.microsoft.com/library/mt634543.aspx)  
[步驟 3︰ 將 IFrame 載入 Power BI 報表](powerbi-developer-integrate-report-load-report-iframe.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)