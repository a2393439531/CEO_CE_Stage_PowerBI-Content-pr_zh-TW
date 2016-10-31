<properties
   pageTitle="資料推送至儀表板"
   description="將資料發送到 Power BI 儀表板"
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
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# 將資料發送到 Power BI 儀表板

使用 Power BI API，您可以將資料推送到 Power BI 儀表板。 例如，您要擴充現有索引鍵的資料推送至您的儀表板商務工作流程。 在此情況下，您會想要推送銷售行銷的資料集，其中有一個儀表板將產品資料表。

開始將資料發送到儀表板之前，您需要 Azure Active Directory (Azure AD) 和 [Power BI 帳戶](powerbi-admin-free-with-custom-azure-directory.md)。

若要了解如何將推播到儀表板的資料集，請遵循下列步驟。 在範例中，您可以推送銷售行銷資料集具備 Product 資料表到儀表板。

## 推入儀表板的 [資料集的步驟

- 步驟 1: [與 Azure AD 註冊應用程式](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)
- 步驟 2: [取得驗證存取權杖](powerbi-developer-walkthrough-push-data-get-token.md)
- 步驟 3: [Power BI 儀表板中建立資料集](powerbi-developer-walkthrough-push-data-create-dataset.md)
- 步驟 4: [到 Power BI 資料表加入資料列的資料集](powerbi-developer-walkthrough-push-data-get-datasets.md)
- 步驟 5: [Power BI 資料表加入資料列](powerbi-developer-walkthrough-push-data-add-rows.md)

下一節會將資料推送的 Power BI API 作業的一般討論。

## 資料發送到 power BI API 作業

透過 Power BI REST API，您可以推送至 Power BI 的資料來源。 當應用程式會將資料列加入至資料集時，會自動更新的資料更新儀表板上的磚。 若要將資料推送，您使用 [建立資料集](https://msdn.microsoft.com/library/mt203562.aspx) 連同作業 [加入資料列](https://msdn.microsoft.com/library/mt203561.aspx) 作業。 若要找出資料集，您使用 [取得資料集](https://msdn.microsoft.com/library/mt203567.aspx) 作業。 針對任何一項作業，您可以傳遞至群組的群組識別碼。 使用 [取得群組](https://msdn.microsoft.com/library/mt243842.aspx) 作業，以取得群組識別碼的清單

以下是將資料發送到儀表板的作業︰

- [建立資料集](https://msdn.microsoft.com/library/mt203562.aspx)
- [取得資料集](https://msdn.microsoft.com/library/mt203567.aspx)
- [加入資料列](https://msdn.microsoft.com/library/mt203561.aspx)
- [取得群組](https://msdn.microsoft.com/library/mt243842.aspx)

您建立資料集，您可以在 Power BI 中傳遞至 Power BI 服務的 JavaScript 物件標記法 (JSON) 字串。 若要深入了解 JSON，請參閱 [JSON 簡介](http://json.org/)。

資料集的 JSON 字串具有下列格式︰

**Power BI 資料集 JSON 物件**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

因此，我們銷售行銷資料集的範例，您會傳遞 JSON 字串，如以下範例。 在此範例中， **SalesMarketing** 是資料集的名稱和 **產品** 是資料表的名稱。 定義資料表之後，您會定義資料表的結構描述。 如 **SalesMarketing** 資料集時，資料表結構描述具有下列資料行︰ ProductID、 製造商、 類別、 區段、 產品和 IsCompete。

**範例資料集物件 JSON**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Power BI 資料表結構描述中，您可以使用下列資料類型。

## Power BI 資料表資料類型

|**資料類型**|**限制**
|---|---
|Int64|Int64.MaxValue 和 Int64.MinValue 不允許。
|Double|Double.MaxValue 和 Double.MinValue 值不允許。 不支援 NaN。 + Infinity 和-Infinity 不支援某些功能 (例如 Min、 Max)。
|布林值|無
|Datetime|在資料載入期間值量化為一天時間分數 1/300 秒 （3.33 毫秒） 的整數倍數來使用。
|字串|目前允許最多 128 個字元。


## 深入了解將資料發送到 Power BI

若要開始使用推播資料給儀表板，請參閱 [步驟 1︰ 註冊應用程式與 Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md) 左的導覽窗格中。

[下一步 >](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)

## 請參閱

[註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[建立資料集](https://msdn.microsoft.com/library/mt203562.aspx)  
[取得資料集](https://msdn.microsoft.com/library/mt203567.aspx)  
[加入資料列](https://msdn.microsoft.com/library/mt203561.aspx)  
[取得群組](https://msdn.microsoft.com/library/mt243842.aspx)  
[JSON 簡介文章](http://json.org/)  
[Power BI REST API 概觀](powerbi-developer-overview-of-power-bi-rest-api.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)