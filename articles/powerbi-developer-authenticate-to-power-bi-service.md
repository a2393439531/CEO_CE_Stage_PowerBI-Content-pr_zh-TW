<properties
   pageTitle="Power BI 服務驗證"
   description="Power BI 服務驗證"
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

# Power BI 服務驗證

這篇文章是驗證 Power BI，以及如何取得存取權杖使用的用戶端識別碼的簡介。 若要開始建立 Power BI 應用程式，請參閱 [開始建立 Power BI 應用程式](powerbi-developer-steps-to-create-a-power-bi-app.md)。

Power BI API 提供以程式設計方式存取儀表板資源，例如資料集、 資料表和資料列。 這些資源會受到 **Azure Active Directory** (Azure AD)。 若要存取 **Power BI** 驗證您的應用程式資源， **Azure AD**。

<a name="intro"/>
## 在 Power BI 驗證的簡介
Power BI 應用程式整合在一起 **Azure Active Directory** (Azure AD) 以提供安全登入和授權您的應用程式。 若要使用 Azure AD 整合 Power BI 應用程式，您註冊詳細資料與 Azure AD 的應用程式的相關使用 Azure 管理入口網站。 當您在 Azure Active Directory 註冊應用程式時，應用程式將驗證外包給 Azure AD。 應用程式註冊必須向 Azure AD 說明您的應用程式包括它所在的 URL 傳送驗證後，回覆 URL，來識別您的應用程式的 URI。 當您在 Azure AD 中註冊用戶端應用程式或 web 應用程式時，您會授與 Power BI REST API 的應用程式存取。

Power BI 應用程式會使用 **用戶端識別碼** 向 Azure AD 識別其身分。 請參閱 [Azure 應用程式用戶端識別碼](#clientID)。 Web 應用程式，您也需要用戶端秘密金鑰。 請參閱 [Azure web 應用程式用戶端秘密金鑰](#clientSecret)。

若要了解如何註冊並驗證 Power BI 應用程式︰

- 
            **Power BI 用戶端應用程式**︰ 請參閱 [註冊用戶端應用程式](powerbi-developer-register-a-client-app.md) 和 [驗證 Power BI 用戶端應用程式](powerbi-developer-authenticate-a-client-app.md)。

- 
            **Power BI web 應用程式**︰ 請參閱 [註冊 web 應用程式](powerbi-developer-register-a-web-app.md) 和 [驗證 Power BI web 應用程式](powerbi-developer-authenticate-a-web-app.md)。

- 若要了解如何在不同平台上使用 Azure 驗證︰ [Azure 驗證程式庫](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/) 位於不同的平台，可協助開發人員輕鬆地驗證使用者，以雲端或內部部署 Active Directory (AD) 以取得存取權杖來保護 API 呼叫。 本主題包含可用於不同平台的驗證程式庫的藍圖，以及對這些程式庫有用之資源的藍圖，包括原始碼和範例。

<a name="clientID"/>
## Azure 應用程式用戶端識別碼
Azure 應用程式具有 **用戶端識別碼** 應用程式用來向要求權限的使用者識別自己。 您使用 **用戶端識別碼** 以取得驗證權杖。 若要取得 Azure **用戶端識別碼**, ，請參閱 [如何取得用戶端應用程式識別碼](powerbi-developer-register-a-client-app.md#clientID)。

如需完整的範例，說明如何使用 Azure **用戶端識別碼** 驗證用戶端應用程式，請參閱 [驗證用戶端應用程式](powerbi-developer-authenticate-a-client-app.md)。

例如，下列 C# 程式碼會使用 Azure 應用程式的用戶端識別碼取得存取權杖。

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
            //  To learn how to register a client app and get a Client ID, see https://msdn.microsoft.com/en-US/library/dn877542(Azure.100).aspx   
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            return token;
      }

<a name="clientSecret"/>
## Azure web 應用程式用戶端秘密金鑰
當您註冊 web 應用程式時，您會收到用戶端密碼 **金鑰**。 用戶端密碼 **金鑰** 供 web 應用程式用來安全地識別本身以 **Power BI 服務**。 若要取得 Azure 用戶端秘密 **金鑰**, ，請參閱 [如何取得用戶端秘密金鑰](powerbi-developer-register-a-web-app.md#clientSecret)。

如需完整的範例，說明如何使用 Azure **用戶端識別碼** 和用戶端密碼 **金鑰** 驗證 web 應用程式，請參閱 [驗證 web 應用程式](powerbi-developer-authenticate-a-web-app.md)。

## 請參閱

[開始建立 Power BI 應用程式](powerbi-developer-steps-to-create-a-power-bi-app.md)  
[如何取得 Azure Active Directory 租用戶](https://azure.microsoft.com/en-us/documentation/articles/active-directory-howto-tenant/)  
[建立 Azure Active Directory 租用戶](powerbi-developer-create-an-azure-active-directory-tenant.md)  
[註冊用戶端應用程式](powerbi-developer-register-a-client-app.md)  
[註冊 web 應用程式](powerbi-developer-register-a-web-app.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)