<properties
   pageTitle="取得要加入資料列的資料集"
   description="逐步解說來發送資料-取得 Power BI 資料表加入資料列的資料集"
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

# 步驟 4︰ 取得資料集，以便將資料列加入至 Power BI 資料表

逐步解說的這篇文章屬於 [資料推送至儀表板](powerbi-developer-walkthrough-push-data.md)。

在 **步驟 3** 的推播資料到儀表板， [Power BI 儀表板中建立資料集](powerbi-developer-walkthrough-push-data-create-dataset.md), ，您呼叫 [建立資料集](https://msdn.microsoft.com/library/mt203562.aspx) 儀表板中建立資料集的作業。 在此步驟中，您會使用 [取得資料集](https://msdn.microsoft.com/library/mt203567.aspx) 作業和 Newtonsoft.Json 來取得資料集識別碼。 您使用在步驟 4 中的資料集的識別碼將資料列加入資料集。

將資料發送到 Power BI 儀表板，您需要參考資料集中的資料表。 若要參考的資料表中資料集，您首先需要取得 **集識別碼**。 您取得 **集識別碼** 使用 [取得資料集](https://msdn.microsoft.com/library/mt203567.aspx) 作業。  **取得資料集** 作業會傳回 JSON 字串，包含 Power BI 儀表板中的所有資料集的清單。 還原序列化的 JSON 字串的建議的方式是使用 [Newtonsoft.Json](http://www.newtonsoft.com/json)。

以下是如何將資料集。

## 取得 Power BI 資料集

>
            **請注意**︰ 開始使用之前，請確定您已經依照先前的步驟中 [資料推送至儀表板](powerbi-developer-walkthrough-push-data.md) 逐步解說。

1. 在主控台應用程式專案中建立在步驟 2︰ 發送資料的逐步解說 [取得驗證存取權杖](powerbi-developer-walkthrough-push-data-get-token.md), ，安裝 Newtonsoft.Json NuGet 封裝。 若要安裝封裝的方法如下︰

     a. 在 Visual Studio 2015 中，選擇 [ **工具** > **NuGet 封裝管理員** > **Package Manager Console**。

     b。 在 **Package Manager Console**, ，輸入 Install-package Newtonsoft.Json。

2. 安裝封裝之後，加入 **使用 Newtonsoft.Json;** program.cs。

3. 在 Program.cs 中，新增下列取得程式碼 **集識別碼**。

4. 執行主控台應用程式，並登入您的 Power BI 帳戶。 您應該會看到 **集識別碼︰** 後面接著在主控台視窗中的識別碼。

**資料集的範例 get**

將此程式碼加入至 Program.cs。

- 在靜態 void Main (string [] args):

  ```
  static void Main(string[] args)
  {

    //Get an authentication access token
    token = GetToken();

    //Create a dataset in a Power BI dashboard
    CreateDataset();

    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```

- 新增 GetDatset() 方法︰

  ```
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";

        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();

                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                //Get the first id
                datasetId = results["value"][0]["id"];

                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();

                return datasetId;
            }
        }
    }
    #endregion
```

下一個步驟顯示如何以 [將資料列加入至 Power BI 資料表](powerbi-developer-walkthrough-push-data-add-rows.md)。

以下是 [完整程式碼清單](#code)。

[下一步 >](powerbi-developer-walkthrough-push-data-add-rows.md)

## 請參閱
- [將資料列加入至 Power BI 資料表](powerbi-developer-walkthrough-push-data-add-rows.md)
- [Newtonsoft.Json](http://www.newtonsoft.com/json)
- [取得資料集](https://msdn.microsoft.com/library/mt203567.aspx)
- [將資料發送到 Power BI 儀表板](powerbi-developer-walkthrough-push-data.md)
- [Power BI REST API 概觀](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Power BI REST API 參考](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## 完整程式碼清單

    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;
    using Newtonsoft.Json;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

                //Create a dataset in a Power BI dashboard
                CreateDataset();

                //Get a dataset to add rows into a Power BI table
                string datasetId = GetDataset();

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

            #region Create a dataset in a Power BI dashboard
            private static void CreateDataset()
            {
                //TODO: Add using System.Net and using System.IO

                //Push data into a Power BI dashboard

                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "POST";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                //Create dataset JSON for POST request
                string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                    "[{\"name\": \"Product\", \"columns\": " +
                    "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                    "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                    "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                    "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                    "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                    "]}]}";

                //POST web request
                byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                request.ContentLength = byteArray.Length;

                //Write JSON byte[] into a Stream
                using (Stream writer = request.GetRequestStream())
                {
                    writer.Write(byteArray, 0, byteArray.Length);

                    var response = (HttpWebResponse)request.GetResponse();

                    Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                    Console.ReadLine();
                }
            }
            #endregion

            #region Get a dataset to add rows into a Power BI table
            private static string GetDataset()
            {
                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "GET";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                string datasetId = string.Empty;
                //Get HttpWebResponse from GET request
                using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
                {
                    //Get StreamReader that holds the response stream
                    using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                    {
                        string responseContent = reader.ReadToEnd();

                        //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                        //and add using Newtonsoft.Json
                        var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                        //Get the first id
                        datasetId = results["value"][0]["id"];

                        Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                        Console.ReadLine();

                        return datasetId;
                    }
                }
            }
            #endregion
        }
    }

更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)