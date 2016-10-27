<properties
   pageTitle="Get a dataset to add rows"
   description="Walkthrough to push data - Get a dataset to add rows into a Power BI table"
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

# Step 4: Get a dataset to add rows into a Power BI table

This article is part of a step-by-step walkthrough to <bpt id="p1">[</bpt>push data into a dashboard<ept id="p1">](powerbi-developer-walkthrough-push-data.md)</ept>.

In <bpt id="p1">**</bpt>step 3<ept id="p1">**</ept> of Push data into a dashboard, <bpt id="p2">[</bpt>Create a dataset in a Power BI dashboard<ept id="p2">](powerbi-developer-walkthrough-push-data-create-dataset.md)</ept>, you called the <bpt id="p3">[</bpt>Create Dataset<ept id="p3">](https://msdn.microsoft.com/library/mt203562.aspx)</ept> operation to create a dataset in a dashboard. In this step, you use the <bpt id="p1">[</bpt>Get Datasets<ept id="p1">](https://msdn.microsoft.com/library/mt203567.aspx)</ept> operation and Newtonsoft.Json to get a dataset id. You use the dataset id in step 4 to add rows to a dataset.

To push data into a Power BI dashboard, you need to reference the table in the dataset. To reference a table in a dataset, you first need to get a <bpt id="p1">**</bpt>Dataset ID<ept id="p1">**</ept>. You get a <bpt id="p1">**</bpt>Dataset ID<ept id="p1">**</ept> using the <bpt id="p2">[</bpt>Get Dataset<ept id="p2">](https://msdn.microsoft.com/library/mt203567.aspx)</ept> operation. The <bpt id="p1">**</bpt>Get Dataset<ept id="p1">**</ept> operation returns a JSON string containing a list of all datasets in a Power BI dashboard. The recommended way to deserialize a JSON string is with <bpt id="p1">[</bpt>Newtonsoft.Json<ept id="p1">](http://www.newtonsoft.com/json)</ept>.

Here's how you get a dataset.

## Get a Power BI dataset

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Before you get started, make sure you have followed the previous steps in the <bpt id="p2">[</bpt>push data into a dashboard<ept id="p2">](powerbi-developer-walkthrough-push-data.md)</ept> walkthrough.

1. In the Console Application project you created in Step 2: Walkthrough to push data, <bpt id="p1">[</bpt>Get an authentication access token<ept id="p1">](powerbi-developer-walkthrough-push-data-get-token.md)</ept>, install the Newtonsoft.Json NuGet package. Here's how to install the package:

     a. In Visual Studio 2015, choose <bpt id="p1">**</bpt>Tools<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>NuGet Package Manager<ept id="p2">**</ept><ph id="ph2"> &gt; </ph><bpt id="p3">**</bpt>Package Manager Console<ept id="p3">**</ept>.

     b。 In <bpt id="p1">**</bpt>Package Manager Console<ept id="p1">**</ept>, enter Install-Package Newtonsoft.Json.

2. After the package is installed, add <bpt id="p1">**</bpt>using Newtonsoft.Json;<ept id="p1">**</ept> to Program.cs.

3. In Program.cs, add the code below to get a <bpt id="p1">**</bpt>Dataset ID<ept id="p1">**</ept>.

4. Run the Console App, and login to your Power BI account. You should see <bpt id="p1">**</bpt>Dataset ID:<ept id="p1">**</ept> followed by an id in the Console Window.

**Sample get a dataset**

Add this code into Program.cs.

- In static void Main(string[] args):

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

- Add a GetDatset() method:

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

The next step shows you how to <bpt id="p1">[</bpt>add rows to a Power BI table<ept id="p1">](powerbi-developer-walkthrough-push-data-add-rows.md)</ept>.

Below is the <bpt id="p1">[</bpt>complete code listing<ept id="p1">](#code)</ept>.

[Next Step &gt;](powerbi-developer-walkthrough-push-data-add-rows.md)

## 請參閱
- [Add rows to a Power BI table](powerbi-developer-walkthrough-push-data-add-rows.md)
- [Newtonsoft.Json](http://www.newtonsoft.com/json)
- [Get Datasets](https://msdn.microsoft.com/library/mt203567.aspx)
- [Push data into a Power BI Dashboard](powerbi-developer-walkthrough-push-data.md)
- [Overview of Power BI REST API](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Power BI REST API reference](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## Complete code listing

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

More questions? [Try the Power BI Community](http://community.powerbi.com/)