<properties
   pageTitle="驗證用戶端應用程式"
   description="驗證用戶端應用程式"
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

# 驗證用戶端應用程式


            [下載.NET 用戶端應用程式範例](http://go.microsoft.com/fwlink/?LinkId=619280) | [GitHub 上檢視的程式碼](http://go.microsoft.com/fwlink/?LinkId=619429)

本文將說明如何驗證 Power BI 用戶端應用程式。 在 C# 中，包含範例不過，在驗證程序也適用於其他程式設計語言。

如需完整 C# 範例示範如何驗證 Power BI 用戶端應用程式，請參閱 [用戶端應用程式範例](https://msdn.microsoft.com/library/mt186159.aspx)。

Power BI 用戶端應用程式使用 **Azure Active Directory** (AAD) 來驗證使用者及保護應用程式。 驗證是識別應用程式或使用者的程序。 若要識別用戶端應用程式在 AAD 中的，您可以註冊應用程式與 AAD。 當您在 AAD 中註冊用戶端應用程式時，您將應用程式存取權授與 Power BI Api。 若要了解如何註冊 Power BI 用戶端應用程式，請參閱 [註冊用戶端應用程式](powerbi-developer-register-a-client-app.md)。

Power BI REST API 呼叫會代表驗證的使用者藉由要求的 「 授權 」 標頭中傳遞權杖。 透過 Azure Active Directory 取得權杖。


            **請注意** 的 Power BI Private Preview 中，為多租用戶應用程式使用 Azure 管理入口網站建立應用程式。

<a name="What"></a>
## 您需要驗證 Power BI 用戶端應用程式
若要驗證 Power BI 用戶端應用程式及執行 REST web 要求，您需要︰

1. 
            **註冊用戶端應用程式** -若要註冊 Power BI 用戶端應用程式，請參閱 [註冊用戶端應用程式](powerbi-developer-register-a-client-app.md)。   當您註冊中的用戶端應用程式 **Azure Active Directory**, ，您將應用程式存取權授與 Power BI Api。
2. 
            **指定您的應用程式的用戶端識別碼** -若要取得應用程式的用戶端識別碼，請參閱 [如何取得用戶端應用程式識別碼](powerbi-developer-register-a-client-app.md#clientID)。 用戶端識別碼的應用程式用於向要求權限的使用者識別自己。
    - 在用戶端應用程式程式碼，將指派 **clientID** 變數設為 Azure 應用程式的用戶端識別碼。
3. 
            **將指定的重新導向 Uri** -用戶端應用程式重新導向 uri 提供 AAD 詳細資訊就會進行驗證的特定應用程式。 統一資源識別元 (URI) 是資源的要識別名稱的值。
    - 在用戶端應用程式程式碼，將指派 **redirectUri** 給"https://login.live.com/oauth20_desktop.srf"。 由於用戶端應用程式並沒有重新導向至外部服務，此 URI 是標準的替代符號，用戶端應用程式。

4. 
            **指派 Power BI API 資源 Uri** -資源 Uri 可識別 Power BI API 資源。
    - 在用戶端應用程式程式碼，將指派 **resourceUri** 給"https://analysis.windows.net/powerbi/api"。
5. 
            **指派 OAuth2 授權單位 uri** -授權單位 Uri 可識別 OAuth2 授權單位資源。
    - 在用戶端應用程式程式碼，將指派給"https://login.windows.net/common/oauth2/authorize"的授權單位 Uri。
6. 
            **指派 Power BI API 資料集的資料集 Uri** -資料集 Uri 可識別 Power BI API 資料集的資源。
    - 在用戶端應用程式程式碼，將指派 **datasetsUri** 給"https://api.powerbi.com/v1.0/myorg/datasets"。

若要讓 Power BI REST 服務的資料要求，您需要提供存取權杖。 在.NET 用戶端應用程式，您可以使用 [.NET nuget 套件的 Azure AD 驗證程式庫](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) 以取得存取權杖。 以下是此程序。 以下是範例 **accesstoken （)** 方法。

如果您沒有 Windows Azure 驗證程式庫 (ADAL)，請參閱 [如何新增 Azure Active Directory Authentication Library](#Library)。


            **重要** 驗證用戶端應用程式，您必須新增指向 **Microsoft.IdentityModel.Clients.ActiveDirectory** 隨附在 Windows Azure 驗證程式庫 (ADAL)。

## 若要取得存取權杖的步驟
1. 
            **建立 AuthenticationContext 的執行個體** -AuthenticationContext 是代表發行授權單位，Azure AD 資源之權杖的主要類別。 建構函式︰
    - 一個 OAuth2 authorityUri

    ```
            //OAuth2 authority Uri
            string authorityUri = "https://login.windows.net/common/oauth2/authorize";
    AuthenticationContext  authContext = new AuthenticationContext(authorityUri);
    ```
2. 
            **呼叫 authenticationcontext.acquiretoken （） 來取得權杖** -此方法會採用︰
    - Power BI API resourceUri
    - 您的 Power BI 應用程式 clientID
    - Power BI 應用程式 redirectUri

    ```
    string token = authContext.AcquireToken(resourceUri, clientId, new Uri(redirectUri), PromptBehavior.RefreshSession).AccessToken;
    ```

如需 AuthenticationContext 的詳細資訊並取得權杖，請參閱 [Azure 驗證內容流程](#Flow)。

## C# 範例-取得存取權杖

在.NET 用戶端應用程式，您可以使用 **AuthenticationContext** 以取得存取權杖。

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
## 使用權杖的 Power BI REST api 提出資料要求

從 Active Directory (AAD) 取得存取權杖之後，您可以使用權杖向 Power BI REST API 提出 web 要求。 若要建立 Power BI REST web 要求，您加入要求標頭做為存取權杖︰


```
request.Headers.Add("Authorization", String.Format("Bearer {0}", AccessToken()));
```


## C# 範例-使用權杖的 Power BI REST API 資料要求

如需完整 C# 範例示範如何驗證 Power BI 用戶端應用程式，並呼叫所有 Power BI REST 作業，請參閱 [用戶端應用程式範例](https://msdn.microsoft.com/library/mt186159.aspx) 或 [GitHub 上檢視的程式碼](http://go.microsoft.com/fwlink/?LinkId=619429)。

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
## Azure 驗證內容流程
在.NET 用戶端應用程式，您可以使用 **AuthenticationContext** 取得 Azure 存取權杖。 
            **AuthenticationContext** 是代表發行授權單位，Azure AD 資源之權杖的主要類別。 
            **AuthenticationContext** 會進行下列作業︰

1. AuthenticationContext 將使用者代理程式重新導向至 Azure Active Directory 授權端點，以啟動流程。 使用者會驗證並同意 (如果需要同意的話)。

2. Azure Active Directory 授權端點會將使用者代理程式重新導向回到 AuthenticationContext，並提供授權碼。 使用者代理程式會將授權碼傳回至用戶端應用程式重新導向 URI。

3. AuthenticationContext 向 Azure Active Directory 權杖發行端點要求存取權杖。 它會出示授權碼來證明使用者已同意。

4. Azure Active Directory 權杖發行端點傳回存取權杖。

5. 用戶端應用程式會使用存取權杖來對 Web API 進行驗證。

6. 驗證用戶端應用程式之後, Power BI REST API 會傳回所要求的資料。


若要深入了解 Azure Active Directory (Azure AD) 授權流程，請參閱 [授權碼授與流程](https://msdn.microsoft.com/library/azure/dn645542.aspx)。

<a name="Library"></a>
## 如何新增 Azure Active Directory 驗證程式庫

在.NET 用戶端應用程式，您可以使用 **AuthenticationContext** 中 **Active Directory Authentication Library** 取得 Azure 存取權杖。 您可以安裝 **Active Directory Authentication Library** 從 Visual Studio 的 NuGet 封裝。 當您安裝 NuGet 套件時，Visual Studio 會建立必要的組件的參考。

1. 以滑鼠右鍵按一下方案。

2. 選擇 **Manage NuGet Packages**。

3. 搜尋 **Active Directory Authentication Library**。

4. 選擇 **Active Directory Authentication Library** 清單中的封裝，然後按一下 [ **安裝**。

## 請參閱

[.NET nuget 套件的 azure AD 驗證程式庫](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Active Directory 驗證.net 程式庫 (ADAL) v1](http://www.cloudidentity.com/blog/2013/09/12/active-directory-authentication-library-adal-v1-for-net-general-availability/)  
[Azure AD 中的 OAuth 2.0](https://msdn.microsoft.com/library/azure/dn645545.aspx)  
[授權碼授與流程](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Azure AD 的驗證案例](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-scenarios/)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)