## 閘道器的運作方式 

![on-prem-data-gateway-how-it-works](./media/gateway-onprem-how-it-works-include/on-prem-data-gateway-how-it-works.png)

讓我們先看看使用者與連線至內部部署資料來源的項目互動時，會發生什麼事。 

> [AZURE.NOTE] Power bi，您必須設定閘道器的資料來源。

1.  將雲端服務，以及內部資料來源的加密認證所建立的查詢，並將它傳送至閘道處理佇列中。

2.  閘道器雲端服務會分析查詢，並將推播要求 [Azure 服務匯流排](https://azure.microsoft.com/documentation/services/service-bus/)。

3.  內部資料閘道民調 [Azure 服務匯流排](https://azure.microsoft.com/documentation/services/service-bus/) 的暫止要求。

4.  閘道取得的查詢、 解密認證，並連接到資料來源，使用這些認證。

5.  閘道會將查詢傳送至資料來源，以便執行。

6.  結果資料來源傳送至閘道器，再到雲端服務。 服務接著會將結果。