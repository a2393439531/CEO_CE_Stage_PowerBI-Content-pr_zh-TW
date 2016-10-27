<properties
   pageTitle="Authenticate a client app"
   description="Authenticate a client app"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
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
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Authenticate a client app

<bpt id="p1">[</bpt>Download the .NET client app sample<ept id="p1">](http://go.microsoft.com/fwlink/?LinkId=619280)</ept><ph id="ph1"> | </ph><bpt id="p2">[</bpt>View the code on GitHub<ept id="p2">](http://go.microsoft.com/fwlink/?LinkId=619429)</ept>

This article shows you how to authenticate a Power BI client app. It includes examples in C#; however, the authentication process is the same for other programming languages.

For a complete C# sample that shows how to authenticate a Power BI client app, see <bpt id="p1">[</bpt>Client app sample<ept id="p1">](https://msdn.microsoft.com/library/mt186159.aspx)</ept>.

Power BI client apps use <bpt id="p1">**</bpt>Azure Active Directory<ept id="p1">**</ept> (AAD) to authenticate users and protect applications. Authentication is the process of identifying an app or user. To identify your client app in AAD, you register your app with AAD. When you register a client app in AAD, you give your app access to the Power BI APIs. To learn how to register your Power BI client app, see <bpt id="p1">[</bpt>Register a client app<ept id="p1">](powerbi-developer-register-a-client-app.md)</ept>.

Power BI REST API calls are made on behalf of an authenticated user by passing a token in the "Authorization" header of the request. The token is acquired through Azure Active Directory.

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept> For Power BI Private Preview, apps are created as multi-tenant apps using the Azure Management Portal.

<a name="What"></a>
## What you need to authenticate a Power BI client app
To authenticate a Power BI client app and perform a REST web request, you need to:

1. <bpt id="p1">**</bpt>Register your client app<ept id="p1">**</ept> - To register a Power BI client app, see <bpt id="p2">[</bpt>Register a client app<ept id="p2">](powerbi-developer-register-a-client-app.md)</ept>.   When you register a client app in <bpt id="p1">**</bpt>Azure Active Directory<ept id="p1">**</ept>, you give your app access to the Power BI APIs.
2. <bpt id="p1">**</bpt>Assign the client id for your app<ept id="p1">**</ept> - To get the client id for your app, see <bpt id="p2">[</bpt>How to get a client app id<ept id="p2">](powerbi-developer-register-a-client-app.md#clientID)</ept>. The Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
    - In your client app code, assign the <bpt id="p1">**</bpt>clientID<ept id="p1">**</ept> variable to the client id of your Azure application.
3. <bpt id="p1">**</bpt>Assign the redirect Uri<ept id="p1">**</ept> - For a client app, a redirect uri gives AAD more details about the specific application it will authenticate. A uniform resource identifier (URI) is a value to identify a name of a resource.
    - In your client app code, assign the <bpt id="p1">**</bpt>redirectUri<ept id="p1">**</ept> to "https://login.live.com/oauth20_desktop.srf". Since a client app does not have an external service to redirect to, this URI is the standard placeholder for client apps.

4. <bpt id="p1">**</bpt>Assign the resource Uri for Power BI API<ept id="p1">**</ept> - The resource Uri identifies the Power BI API resource.
    - In your client app code, assign the <bpt id="p1">**</bpt>resourceUri<ept id="p1">**</ept> to "https://analysis.windows.net/powerbi/api".
5. <bpt id="p1">**</bpt>Assign the OAuth2 authority uri<ept id="p1">**</ept> - The authority Uri identifies the OAuth2 authority resource.
    - In your client app code, assign an authority Uri to "https://login.windows.net/common/oauth2/authorize".
6. <bpt id="p1">**</bpt>Assign the dataset Uri for the Power BI API datasets<ept id="p1">**</ept> - The datasets Uri identifies the Power BI API datasets resource.
    - In your client app code, assign the <bpt id="p1">**</bpt>datasetsUri<ept id="p1">**</ept> to "https://api.powerbi.com/v1.0/myorg/datasets".

To make a data request to the Power BI REST service, you need to supply an access token. In a .NET client app, you use the <bpt id="p1">[</bpt>Azure AD Authentication Library for .NET nuget package<ept id="p1">](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</ept> to get an access token. Here’s the process. Below is an example <bpt id="p1">**</bpt>AccessToken()<ept id="p1">**</ept> method.

If you do not have Windows Azure Authentication Library (ADAL), see <bpt id="p1">[</bpt>How to add Azure Active Directory Authentication Library<ept id="p1">](#Library)</ept>.

<bpt id="p1">**</bpt>Important<ept id="p1">**</ept> To authenticate a client app, you must add a reference to <bpt id="p2">**</bpt>Microsoft.IdentityModel.Clients.ActiveDirectory<ept id="p2">**</ept> which is included in the Windows Azure Authentication Library (ADAL).

## Steps to get an access token
1. <bpt id="p1">**</bpt>Create an instance of AuthenticationContext<ept id="p1">**</ept> - AuthenticationContext is the main class representing the token issuing authority for Azure AD resources. The constructor takes:
    - An OAuth2 authorityUri

    ```
            //OAuth2 authority Uri
            string authorityUri = "https://login.windows.net/common/oauth2/authorize";
    AuthenticationContext  authContext = new AuthenticationContext(authorityUri);
    ```
2. <bpt id="p1">**</bpt>Call AuthenticationContext.AcquireToken() to get a token<ept id="p1">**</ept> -  The method takes:
    - Power BI API resourceUri
    - Your Power BI app clientID
    - Your Power BI app redirectUri

    ```
    string token = authContext.AcquireToken(resourceUri, clientId, new Uri(redirectUri), PromptBehavior.RefreshSession).AccessToken;
    ```

For more information about what AuthenticationContext does to get a token, see <bpt id="p1">[</bpt>Azure Authentication Context Flow<ept id="p1">](#Flow)</ept>.

## C# example - Get access token

In a .NET client app, you use <bpt id="p1">**</bpt>AuthenticationContext<ept id="p1">**</ept> to get an access token.

```
      static string AccessToken()
      {
            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            string clientId = {clientIDFromAzureAppRegistration};

            //A redirect uri gives AAD more details about the specific application that it will authenticate.
            //Since a client app does not have an external service to redirect to, this Uri is the standard placeholder for a client app.
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            // Create an instance of AuthenticationContext to acquire an Azure access token
            // OAuth2 authority Uri
            string authorityUri = "https://login.windows.net/common/oauth2/authorize";
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);

            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            //  AcquireToken takes a Client Id that Azure AD creates when you register your client app.
            //  To learn how to register a client app and get a Client ID, see https://msdn.microsoft.com/library/dn877542(Azure.100).aspx   
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            return token;
      }
```
<a name="Datarequest"></a>
## Make a data request to Power BI REST API using a token

After you get an access token from Active Directory (AAD), you use the token to make a web request to the Power BI REST API. To create a Power BI REST web request, you add an access token to the request header as:


```
request.Headers.Add("Authorization", String.Format("Bearer {0}", AccessToken()));
```


## C# example - Power BI REST API data request using a token

For a complete C# sample that shows how to authenticate a Power BI client app and call all Power BI REST operations, see <bpt id="p1">[</bpt>Client app sample<ept id="p1">](https://msdn.microsoft.com/library/mt186159.aspx)</ept> or <bpt id="p2">[</bpt>view the code on GitHub<ept id="p2">](http://go.microsoft.com/fwlink/?LinkId=619429)</ept>.

```
        static dataset[] GetDatasets()
        {
            //This is sample code to illustrate a Power BI operation.
            //In a production application, refactor code into specific methods and use appropriate exception handling.

            //Power BI Datasets Url
            string powerBIApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";

            //Get Azure AD access token (see above)
            string token = AccessToken();

            //GET web request to list all datasets.
            //To get a datasets in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "GET";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add access token to Request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            //Get HttpWebResponse from GET request
            using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
            {
                //Get StreamReader that holds the response stream
                using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                {
                    string responseContent = reader.ReadToEnd();

                    JavaScriptSerializer jsonSerializer = new JavaScriptSerializer();
                    Datasets datasets = (Datasets)jsonSerializer.Deserialize(responseContent, typeof(Datasets));

                    return datasets.value;
                }
            }
        }

public class Datasets
{
    public dataset[] value { get; set; }
}

public class dataset
{
    public string Id { get; set; }
    public string Name { get; set; }
}

```
<a name="Flow"></a>
## Azure Authentication Context Flow
In a .NET client app, you use <bpt id="p1">**</bpt>AuthenticationContext<ept id="p1">**</ept> to acquire an Azure access token. <bpt id="p1">**</bpt>AuthenticationContext<ept id="p1">**</ept> is the main class representing the token issuing authority for Azure AD resources. <bpt id="p1">**</bpt>AuthenticationContext<ept id="p1">**</ept> does the following:

1. AuthenticationContext starts the flow by redirecting the user agent to the Azure Active Directory authorization endpoint. 使用者會驗證並同意 (如果需要同意的話)。

2. The Azure Active Directory authorization endpoint redirects the user agent back to the AuthenticationContext with an authorization code. The user agent returns an authorization code to the client application’s redirect URI.

3. The AuthenticationContext requests an access token from the Azure Active Directory token issuance endpoint. 它會出示授權碼來證明使用者已同意。

4. The Azure Active Directory token issuance endpoint returns an access token.

5. 用戶端應用程式會使用存取權杖來對 Web API 進行驗證。

6. After authenticating the client application, the Power BI REST API returns the requested data.


To learn more about Azure Active Directory (Azure AD) authorization flow, see <bpt id="p1">[</bpt>Authorization Code Grant Flow<ept id="p1">](https://msdn.microsoft.com/library/azure/dn645542.aspx)</ept>.

<a name="Library"></a>
## How to add Azure Active Directory Authentication Library

In a .NET client app, you use <bpt id="p1">**</bpt>AuthenticationContext<ept id="p1">**</ept> in the <bpt id="p2">**</bpt>Active Directory Authentication Library<ept id="p2">**</ept> to acquire an Azure access token. You can install the <bpt id="p1">**</bpt>Active Directory Authentication Library<ept id="p1">**</ept> NuGet package from Visual Studio. When you install a NuGet package, Visual Studio creates a reference to the required assemblies.

1. Right click a solution.

2. Choose <bpt id="p1">**</bpt>Manage NuGet Packages<ept id="p1">**</ept>.

3. Search for <bpt id="p1">**</bpt>Active Directory Authentication Library<ept id="p1">**</ept>.

4. Choose <bpt id="p1">**</bpt>Active Directory Authentication Library<ept id="p1">**</ept> in the list of packages, and click <bpt id="p2">**</bpt>Install<ept id="p2">**</ept>.

## 請參閱

[Azure AD Authentication Library for .NET nuget package](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Active Directory Authentication Library (ADAL) v1 for .NET](http://www.cloudidentity.com/blog/2013/09/12/active-directory-authentication-library-adal-v1-for-net-general-availability/)  
[Azure AD 中的 OAuth 2.0](https://msdn.microsoft.com/library/azure/dn645545.aspx)  
[授權碼授與流程](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Azure AD 的驗證案例](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-scenarios/)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)