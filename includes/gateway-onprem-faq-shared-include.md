## 一般


            **問題︰** 實際的 Windows 服務呼叫的動作？  

            **答案是︰** 閘道會在服務中呼叫內部部署資料閘道器服務


            **問題︰** 閘道的需求為何？  

            **答案是︰** 看看主要的需求一節 [閘道文章](powerbi-gateway-onprem.md)。


            **問題︰** 何種資料來源所支援的閘道？  

            **答案是︰** 請參閱資料來源資料表中主 [閘道文章](powerbi-gateway-onprem.md)。


            **問題︰** 並需要閘道的定域機組的資料來源，例如 Azure SQL Database？  

            **答案是︰** 否 ！ 服務將無法連線到該資料來源，且不含閘道。


            **問題︰** 是否有任何輸入的連線至閘道從雲端？  

            **答案是︰** [否]。 閘道會使用 Azure 服務匯流排的輸出連線。


            **問題︰** 要是我封鎖輸出連線嗎？ 我要開啟？  

            **答案是︰** 看到 [的連接埠清單](powerbi-gateway-onprem.md#ports) 和閘道使用的主機。


            **問題︰** 閘道必須安裝在同一部電腦做為資料來源？  

            **答案是︰** [否]。 在閘道將要連線至資料來源使用所提供的連接資訊。 閘道器視為這方面的用戶端應用程式。 它只需要能夠連線到所提供的伺服器名稱。


            **問題︰** 到資料來源執行查詢，來自閘道的延遲時間是什麼？ 什麼是最佳的架構？  

            **答案是︰** 建議閘道器已接近資料來源，以避免網路延遲。 如果您可以在實際的資料來源上安裝閘道，它會帶來的延遲降到最低。 請考慮在資料中心。 例如，如果您的服務正在使用的西部我們資料中心，而您必須裝載於 Azure VM 的 SQL Server，您會想要有 Azure VM，在美國西部。 將延遲降至最低，並避免在 Azure VM 上的出口流量費用。


            **問題︰** 是否有任何的網路頻寬的需求？  

            **答案是︰** 建議有網路連線良好的輸送量。 每個環境都不同，而且這也是所傳送的資料量而定。 使用 ExpressRoute 可以協助您確保內部部署與 Azure 資料中心之間的輸送量層級。

您可以使用第 3 方 [Azure 速度測試應用程式](http://azurespeedtest.azurewebsites.net/) 協助評估您的輸送量是什麼。 


            **問題︰** 可以使用 Azure Active Directory 帳戶執行閘道 Windows 服務嗎？  

            **答案是︰** [否]。 Windows 服務必須有有效的 Windows 帳戶。 根據預設，它會執行的服務 sid， *NT SERVICE\PBIEgwService*。


            **問題︰** 如何結果傳送至雲端？  

            **答案是︰** 這是透過 Azure 服務匯流排。 如需詳細資訊，請參閱 [它的運作方式](powerbi-gateway-onprem.md#how-the-gateway-works)。


            **問題︰** 我的認證儲存？  

            **答案是︰** 輸入資料來源的認證會加密方式儲存在閘道器雲端服務。 認證會在閘道內部進行解密。


            **問題︰** 可以放置閘道在周邊網路 （也稱為 DMZ、 非軍事區域及屏蔽子網路）？  

            **答案是︰** 閘道需要連線到資料來源。 如果不在周邊網路中存取資料來源，閘道可能無法連接到它。 例如，您的 SQL Server 可能無法在周邊網路中。 而且您無法從周邊網路連線到 SQL Server。 如果閘道置於周邊網路上時，它就無法連線到 SQL Server。


            **問題︰** 可強制使用 HTTPS 流量使用 Azure 服務匯流排，而不是 TCP 閘道嗎？  

            **答案是︰** [是]。 雖然這會大幅降低效能。 您會想要修改 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* 檔案。 您會想要將值從 `AutoDetect` 到 `Https`。 這個檔案位於，根據預設，在 *C:\Program Files\On 內部資料閘道*。

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## 高可用性/嚴重損壞修復


            **問題︰** 啟用高可用性案例的閘道器的計劃？  

            **答案是︰** [是]。 這在藍圖，但我們尚無時間軸。


            **問題︰** 災害復原有哪些選項？  

            **答案是︰** 您可以使用修復金鑰，以還原或移動的閘道。 當您安裝閘道時，提供修復金鑰。


            **問題︰** 修復金鑰的好處是什麼？  

            **答案是︰** 它可用來移轉或修復您的閘道設定。 這也用於嚴重損壞修復。

## 疑難排解


            **問題︰** 所在的閘道器記錄檔？  

            **答案是︰** 請參閱 < 工具 > 一節的 [疑難排解文件](powerbi-gateway-onprem-tshoot.md#tools)。


            **問題︰** 如何查看查詢所要傳送至內部部署資料來源？  

            **答案是︰** 您可以啟用查詢追蹤。  這包括正在傳送的查詢。 請務必將它變更完成疑難排解時的原始值。 啟用追蹤的查詢將會導致似乎較大的記錄檔。

您也可以查看您的資料來源有追蹤查詢的工具。 例如，SQL Server 和 Analysis Services，您可以使用擴充的事件或 SQL Profiler。