<properties
   pageTitle="Get an authentication access token"
   description="Walkthrough to push data - Get an authentication access token"
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

# Step 2: Get an authentication access token

This article is part of a step-by-step walkthrough to <bpt id="p1">[</bpt>push data into a dashboard<ept id="p1">](powerbi-developer-walkthrough-push-data.md)</ept>.

In <bpt id="p1">**</bpt>step 1<ept id="p1">**</ept> of Push data into a dashboard, <bpt id="p2">[</bpt>Register the app with Azure AD<ept id="p2">](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)</ept>, you registered a client app in Azure AD. In this step, you get an authentication access token. Power BI apps are integrated with <bpt id="p1">**</bpt>Azure AD<ept id="p1">**</ept> to provide secure sign in and authorization for your app. You use a token to authenticate to <bpt id="p1">**</bpt>Azure AD<ept id="p1">**</ept> and gain access to Power BI resources.

Here's how to get an authentication access token.

## Get an authentication access token

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Before you get started, make sure you have followed the previous steps in the <bpt id="p2">[</bpt>push data into a dashboard<ept id="p2">](powerbi-developer-walkthrough-push-data.md)</ept> walkthrough.

1. In Visual Studio 2015, create a <bpt id="p1">**</bpt>Console Application<ept id="p1">**</ept> project.
2. Install the <bpt id="p1">[</bpt>Azure AD Authentication Library for .NET NuGet package<ept id="p1">](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</ept>. To get an authentication security token in a .NET app, you use this package. Here's how to install the package:

     a. In Visual Studio 2015, choose <bpt id="p1">**</bpt>Tools<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>NuGet Package Manager<ept id="p2">**</ept><ph id="ph2"> &gt; </ph><bpt id="p3">**</bpt>Package Manager Console<ept id="p3">**</ept>.

     b。 In <bpt id="p1">**</bpt>Package Manager Console<ept id="p1">**</ept>, enter Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.

3. Add the code below into class Program {...}.
4. Replace "{ClientID}", with the <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> you got when you registered the app. See <bpt id="p1">[</bpt>Register the app with Azure AD<ept id="p1">](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)</ept>.
5. After installing the Microsoft.IdentityModel.Clients.ActiveDirectory package, add <bpt id="p1">**</bpt>using Microsoft.IdentityModel.Clients.ActiveDirectory;<ept id="p1">**</ept> to Program.cs.
6. Run the Console App, and login to your Power BI account. You should see a token string in the Console Window.

**Sample code to get authentication security token**

Add this code to Program {...}.

- A token variable to call operations:

  ```
  private static string token = string.Empty;

  static void Main(string[] args)
  {
  }
  ```

- In static void Main(string[] args):

  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```

- Add a GetToken() method:

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

After you get an authentication token, you can call any Power BI operation. The next step shows you how to call the <bpt id="p1">[</bpt>Create Dataset<ept id="p1">](https://msdn.microsoft.com/library/mt203562.aspx)</ept> operation to create a dataset to push data into a dashboard.

The next step shows you how to <bpt id="p1">[</bpt>create a dataset in a Power BI dashboard<ept id="p1">](powerbi-developer-walkthrough-push-data-create-dataset.md)</ept>.

Below is the <bpt id="p1">[</bpt>complete code listing<ept id="p1">](#code)</ept>.

[Next Step &gt;](powerbi-developer-walkthrough-push-data-create-dataset.md)

## 請參閱
- [Create a dataset in a Power BI dashboard](powerbi-developer-walkthrough-push-data-create-dataset.md)
- [Register an app with Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)
- [Azure AD Authentication Library for .NET NuGet package](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- [Push data into a Power BI Dashboard](powerbi-developer-walkthrough-push-data.md)
- [Overview of Power BI REST API](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Power BI REST API reference](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## Complete code listing

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

More questions? [Try the Power BI Community](http://community.powerbi.com/)