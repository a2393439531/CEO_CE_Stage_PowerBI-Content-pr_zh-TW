<properties
   pageTitle="驗證 web 應用程式"
   description="驗證 web 應用程式"
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

# 驗證 web 應用程式


            [下載 web 應用程式範例](http://go.microsoft.com/fwlink/?LinkId=619279) |在 GitHub 上檢視的程式碼︰ [Default.aspx.cs](https://github.com/Microsoft/PowerBI-CSharp/blob/master/samples/webforms/get-started-web-app-asp.net/PBIWebApp/Default.aspx.cs) | [Redirect.aspx.cs](https://github.com/Microsoft/PowerBI-CSharp/blob/master/samples/webforms/get-started-web-app-asp.net/PBIWebApp/redirect.aspx.cs)

本文將說明如何驗證 Power BI web 應用程式。 在 C# 中，包含範例不過，在驗證程序是相同的其他 web 程式設計語言。 沒有 [GitHub 上的 web 應用程式範例](http://go.microsoft.com/fwlink/?LinkId=619279)。 若要了解如何執行範例，請參閱 [Web 應用程式範例](https://msdn.microsoft.com/library/mt186158.aspx)。

Power BI web 應用程式會使用 Active Directory (AAD) 來驗證使用者及保護應用程式。 驗證是識別應用程式或使用者的程序。 若要識別您的 web 應用程式在 AAD 中，您可以註冊應用程式與 AAD。 當您在 AAD 中註冊的 web 應用程式時，您會提供將應用程式存取 Power BI REST API 資源。 若要了解如何註冊 Power BI web 應用程式，請參閱 [註冊 web 應用程式](powerbi-developer-register-a-web-app.md)。

若要深入了解 Azure Active Directory (Azure AD) 授權流程，請參閱 [授權碼授與流程](https://msdn.microsoft.com/library/azure/dn645542.aspx)。


            **請注意** Power Bi 應用程式會建立成多租用戶應用程式使用 Azure 管理入口網站。

## 您需要驗證 Power BI web 應用程式
以下是驗證 Power BI web 應用程式及執行 REST web 要求的步驟。 這些步驟適用於 ASP.NET web 應用程式。不過，步驟適用於其他平台。 若要深入了解 OAuth 2.0 在 Azure AD 中，請參閱 [Azure AD 中的 OAuth 2.0](https://msdn.microsoft.com/library/azure/dn645545.aspx)。
<a name="register"/>
### 步驟 1-註冊您的 web 應用程式
當您在 Azure Active Directory 中註冊的 web 應用程式時，您將應用程式存取權授 Power BI REST API 資源。 若要註冊 Power BI web 應用程式，請參閱 [註冊 web 應用程式](powerbi-developer-register-a-web-app.md)。
<a name="configure"/>
### 步驟 2-將向 Azure AD 的 Power BI 設定
以下是您需要驗證與 Azure AD 的 Power BI web 應用程式的設定。

|設定|描述|值|
|:--|:--|:--|
|用戶端識別碼|用戶端識別碼的應用程式用於向要求權限的使用者識別自己。|若要取得 Power BI 應用程式的用戶端識別碼，請參閱 [如何取得用戶端應用程式識別碼](powerbi-developer-register-a-web-app.md#clientID)。|
|用戶端機密|用戶端秘密金鑰是隨用戶端識別碼一起驗證時，傳送至 Azure AD 來呼叫 web API。|若要取得 Power BI 應用程式用戶端秘密金鑰，請參閱 [如何取得用戶端秘密金鑰](powerbi-developer-register-a-web-app.md#clientSecret)。|
|資源 Uri|要授權之 Power BI 資源資源 Uri。 您必須使用此 Uri。|https://analysis.windows.net/powerbi/api|
|授權單位 Uri|授權單位 Uri 是採用用戶端識別碼取得存取權杖的 Azure 資源。|https://login.windows.net/common/oauth2/authorize|
|重新導向 Url|Web 應用程式的 url 重新導向 Url。 Azure AD 服務將重新導向回 web 應用程式 url，並附上驗證碼。|範例︰ Http://localhost:13526/redirect|

<a name="create"/>
### 步驟 3-建立查詢字串，以從 Azure AD 取得授權碼
若要驗證 Power BI web 應用程式，您可以先建立 url 查詢字串來重新導向至 Azure AD 驗證服務。 提供有效的認證之後，Azure AD 傳回授權碼。 以下是完整的 Azure AD url 查詢字串的範例。 您可以使用如下所示的 url 從 Azure AD 取得授權碼。 使用 **Response.Redirect**（)，以重新導向至 Azure AD 服務會從 Azure AD 傳回授權碼。 您可以在步驟 4 中使用授權碼取得存取權杖的授權碼。

    https://login.windows.net/common/oauth2/authorize
      ?response_type=code
      &client_id=1861585d...9a79c296
      &resource= https://analysis.windows.net/powerbi/api
      &redirect_uri= http://localhost:13526/Redirect

**Power BI 驗證查詢字串設定**

|設定|描述|
|:--|:--|
|response_type = 程式碼|Azure AD 傳回授權碼。|
|client_id = 1861585 d...9a79c296|用戶端識別碼的應用程式用於向要求權限的使用者識別自己。 當您註冊您的 Azure 應用程式時，您會取得用戶端識別碼。|
|資源 = https://analysis.windows.net/powerbi/api|要授權之 Power BI 資源的資源 uri。 您必須使用此 Uri。|
|redirect_uri = Http://localhost:13526/redirect|使用者驗證之後，Azure AD 會重新導向回 web 應用程式。|

以下是建立 Azure AD 授權 url 查詢字串，並將重新導向至 Azure AD 授權服務的 C# 程式碼範例。

**範例 – C# 登入**

        protected void signInButton_Click(object sender, EventArgs e)
        {
            //Create a query string
            //Create a sign-in NameValueCollection for query string
            var @params = new NameValueCollection
            {
                //Azure AD will return an authorization code.
                //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
                {"response_type", "code"},

                //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
                //You get the client id when you register your Azure app.
                {"client_id", Properties.Settings.Default.ClientID},

                //Resource uri to the Power BI resource to be authorized
                {"resource", "https://analysis.windows.net/powerbi/api"},

                //After user authenticates, Azure AD will redirect back to the web app
                {"redirect_uri", "http://localhost:13526/Redirect"}
            };

            //Create sign-in query string
            var queryString = HttpUtility.ParseQueryString(string.Empty);
            queryString.Add(@params);

            //Redirect authority
            //Authority Uri is an Azure resource that takes a client id to get an Access token
            string authorityUri = "https://login.windows.net/common/oauth2/authorize/";
            Response.Redirect(String.Format("{0}?{1}", authorityUri, queryString));       
        }
<a name="acquire"/>
### 步驟 4 – 取得使用授權碼 Azure AD 存取權杖

若要讓 Power BI REST 服務的資料要求，您需要提供存取權杖。 在.NET web 應用程式中，您可以使用 [.NET nuget 套件的 Azure AD 驗證程式庫](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) 以取得存取權杖。 如果您沒有 Windows Azure 驗證程式庫 (ADAL)，請參閱 [如何新增 Azure Active Directory Authentication Library](#add)。

您的應用程式重新導向至 Azure AD 授權單位 Uri 並取得授權碼之後，您的應用程式會取得權杖的授權碼。 以下是您的應用程式如何取得授權碼並取得存取權杖︰ **中重新導向類別**:

1.  取得 Azure AD 驗證程式碼所傳回的 Azure AD。

    ```
    string code = Request.Params.GetValues(0)[0];
    ```
2.  建立 **AuthenticationContext** 傳遞授權單位 uri 及 TokenCache。

    ```
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ```

3.  建立 **ClientCredential** 傳遞 Azure 應用程式 **用戶端識別碼** 和 Azure 應用程式 **用戶端密碼**。

    ```
    ClientCredential cc = new ClientCredential(Properties.Settings.Default.ClientID, Properties.Settings.Default.ClientSecretKey);
    ```

4.  取得權杖的授權碼傳遞 **驗證碼** 傳回由 Azure AD 和 **重新導向 url**。

    ```
    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);
    ```

5.  重新導向回 default.aspx。

    ```
    Response.Redirect("/Default.aspx");
    ```

6.  設定工作階段"authResult"索引字串設為 AuthenticationResult，以便您可以使用 default.aspx 頁面中的結果。

    ```
    Session["authResult"] = AR;
    ```


            **在 Default.aspx 頁面**:

1.  取得 **AuthenticationResult** 從工作階段。 在步驟 4 中，您會使用 **AuthenticationResult** 取得授權 **AccessToken**。

    ```
    AuthenticationResult authResult = (AuthenticationResult)Session["authResult"];
    ```

以下是完整的程式碼取得 Azure 存取權杖的授權程式碼和重新導向回 default.aspx。


            **請注意** 的重新導向 Uri 必須符合要求授權碼時使用的 redirect_uri。

    public partial class Redirect : System.Web.UI.Page
    {
      protected void Page_Load(object sender, EventArgs e)
      {
          //Redirect uri must match the redirect_uri used when requesting Authorization code.
          string redirectUri = "http://localhost:13526/Redirect";
          string authorityUri = "https://login.windows.net/common/oauth2/authorize/";

          // Get the auth code
          string code = Request.Params.GetValues(0)[0];

          // Get auth token from auth code       
          TokenCache TC = new TokenCache();

          AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
          ClientCredential cc = new ClientCredential
              (Properties.Settings.Default.ClientID,
              Properties.Settings.Default.ClientSecret);

          AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

          //Set Session "authResult" index string to the AuthenticationResult
          Session["authResult"] = AR;

          //Redirect back to Default.aspx
          Response.Redirect("/Default.aspx");
      }
    }

    public partial class _Default : Page
    {
      public AuthenticationResult authResult { get; set; }
      string baseUri = "https://api.powerbi.com/beta/myorg/";

      protected void Page_Load(object sender, EventArgs e)
      {

          //Test for AuthenticationResult
          if (Session["authResult"] != null)
          {
              //Get the authentication result from the session
              authResult = (AuthenticationResult)Session["authResult"];

              //Show Power BI Panel
              signInStatus.Visible = true;

              //Set user and token from authentication result
              userLabel.Text = authResult.UserInfo.DisplayableId;
              accessTokenTextbox.Text = authResult.AccessToken;
          }
      }

      ...
    }

<a name="use"/>
### 步驟 5︰ 使用 Azure AD 存取權杖呼叫 Power BI 作業

Power BI REST API 呼叫會代表驗證的使用者藉由傳遞 「 授權 」 標頭中透過 Azure Active Directory 取得存取權杖。 從 Active Directory (AAD) 取得存取權杖之後，您可以使用權杖向 Power BI REST API 提出 web 要求。

一旦您設定 **AuthenticationResult** 的授權碼取得語彙基元 (**Authenticationresult**)，您取得 Azure 存取權杖取得 **AccessToken** 屬性 **AuthenticationResult**。
下列程式碼可取得 Power BI **資料集**。  此程式碼範例會建立 **WebRequest** 和還原序列化回應字串至資料集。
若要存取 Power BI REST API，您可以建立 「 授權 」 設為"Bearer {AccessToken}"的要求標頭︰

    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

**C# 範例-取得 Power BI 資料集**

        protected void getDatasetsButton_Click(object sender, EventArgs e)
        {
            string responseContent = string.Empty;

            //The resource Uri to the Power BI REST API resource
            string datasetsUri = "https://api.powerbi.com/v1.0/myorg/datasets";

            //Configure datasets request
            System.Net.WebRequest request = System.Net.WebRequest.Create(datasetsUri) as System.Net.HttpWebRequest;
            request.Method = "GET";
            request.ContentLength = 0;
            request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

            //Get datasets response from request.GetResponse()
            using (var response = request.GetResponse() as System.Net.HttpWebResponse)
            {
                //Get reader from response stream
                using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
                {
                    responseContent = reader.ReadToEnd();

                    //Deserialize JSON string
                    //JavaScriptSerializer class is in System.Web.Script.Serialization
                    JavaScriptSerializer json = new JavaScriptSerializer();
                    Datasets datasets = (Datasets)json.Deserialize(responseContent, typeof(Datasets));

                    resultsTextbox.Text = string.Empty;
                    //Get each Dataset from
                    foreach (dataset ds in datasets.value)
                    {
                        resultsTextbox.Text += String.Format("{0}\t{1}\n", ds.Id, ds.Name);
                    }
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

<a name="add"/>
## 如何新增 Azure Active Directory 驗證程式庫
在.NET 用戶端應用程式，您可以使用 **AuthenticationContext** 在 Active Directory Authentication Library 來取得 Azure 存取權杖。 您可以從 Visual Studio 安裝 Active Directory Authentication Library NuGet 封裝。 當您安裝 NuGet 套件時，Visual Studio 會建立必要的組件的參考。

1. 以滑鼠右鍵按一下方案。
2. 選擇 [管理 NuGet 封裝。
3. 搜尋 Active Directory 驗證程式庫。
4. 選擇 Active Directory Authentication Library 封裝，清單中，按一下 [安裝]。

## 請參閱

[.NET nuget 套件的 azure AD 驗證程式庫](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Active Directory 驗證.net 程式庫 (ADAL) v1](http://www.cloudidentity.com/blog/2013/09/12/active-directory-authentication-library-adal-v1-for-net-general-availability/)  
[Azure AD 中的 OAuth 2.0](https://msdn.microsoft.com/library/azure/dn645545.aspx)  
[授權碼授與流程](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Azure AD 的驗證案例](https://msdn.microsoft.com/library/azure/dn499820.aspx)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
