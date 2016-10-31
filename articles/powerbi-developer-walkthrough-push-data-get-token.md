<properties
   pageTitle="取得驗證存取權杖"
   description="逐步解說來發送資料-取得驗證存取權杖"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="04/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# 步驟 2︰ 取得驗證存取權杖

逐步解說的這篇文章屬於 [資料推送至儀表板](powerbi-developer-walkthrough-push-data.md)。

在 **步驟 1** 的推播資料到儀表板， [與 Azure AD 註冊應用程式](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md), ，Azure AD 中註冊用戶端應用程式。 在此步驟中，您會收到驗證存取權杖。 Power BI 應用程式整合在一起 **Azure AD** 來為您的應用程式提供安全登入和授權。 您可以使用權杖來向 **Azure AD** ，並取得 Power BI 資源的存取權。

以下是如何取得驗證存取權杖。

## 取得驗證存取權杖

>
            **請注意**︰ 開始使用之前，請確定您已經依照先前的步驟中 [資料推送至儀表板](powerbi-developer-walkthrough-push-data.md) 逐步解說。

1. 在 Visual Studio 2015 中，建立 **主控台應用程式** 專案。
2. 安裝 [.NET NuGet 套件的 Azure AD 驗證程式庫](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。 若要取得驗證安全性權杖中的.NET 應用程式，您可以使用此封裝。 若要安裝封裝的方法如下︰

     a. 在 Visual Studio 2015 中，選擇 [ **工具** > **NuGet 封裝管理員** > **Package Manager Console**。

     b。 在 **Package Manager Console**, ，輸入 Install-package Microsoft.IdentityModel.Clients.ActiveDirectory-2.21.301221612 版本。

3. 將下列程式碼新增至類別程式 {...}。
4. 取代"{ClientID}" **用戶端識別碼** 註冊應用程式時，您得到的結果。 請參閱 [與 Azure AD 註冊應用程式](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)。
5. 安裝 Microsoft.IdentityModel.Clients.ActiveDirectory 套件之後，加入 **使用 Microsoft.IdentityModel.Clients.ActiveDirectory;** program.cs。
6. 執行主控台應用程式，並登入您的 Power BI 帳戶。 您應該會看到在主控台視窗中的語彙基元字串。

**若要取得驗證安全性權杖的範例程式碼**

將此程式碼加入至程式 {...}。

- 若要呼叫作業的語彙基元變數︰

  ```
  private static string token = string.Empty;

  static void Main(string[] args)
  {
  }
  ```

- 在靜態 void Main (string [] args):

  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```

- 新增 gettoken （） 方法︰

```
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

取得驗證權杖之後，您可以呼叫任何 Power BI 作業。 下一個步驟會示範如何呼叫 [建立資料集](https://msdn.microsoft.com/library/mt203562.aspx) 作業，以建立資料集資料發送到儀表板。

下一個步驟顯示如何以 [Power BI 儀表板中建立資料集](powerbi-developer-walkthrough-push-data-create-dataset.md)。

以下是 [完整程式碼清單](#code)。

[下一步 >](powerbi-developer-walkthrough-push-data-create-dataset.md)

## 請參閱
- [建立 Power BI 儀表板中的資料集](powerbi-developer-walkthrough-push-data-create-dataset.md)
- [使用 Azure AD 註冊應用程式](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)
- [.NET NuGet 套件的 azure AD 驗證程式庫](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- [將資料發送到 Power BI 儀表板](powerbi-developer-walkthrough-push-data.md)
- [Power BI REST API 概觀](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Power BI REST API 參考](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## 完整程式碼清單

    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion

        }
    }

更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)