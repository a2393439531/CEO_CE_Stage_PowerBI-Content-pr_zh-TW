## 登入帳戶

使用者將會使用工作或學校帳戶。 這是您的組織帳戶。 如果您註冊 Office 365 供應項目，而且未提供實際的公司電子郵件，看起來像 nancy@contoso.onmicrosoft.com。 您的帳戶，在雲端服務中，會儲存在 Azure Active Directory (AAD) 租用戶中。 在大部分情況下，AAD 帳戶的 UPN 會比對電子郵件地址。

## Windows 服務帳戶

內部資料閘道設定為使用 *NT SERVICE\PBIEgwService* windows 服務的登入認證。 根據預設，它對記錄檔的權限為服務。 這是您要將閘道安裝所在電腦的內容。 

> [AZURE.NOTE]  如果您選取個人模式時，會分別設定 windows 服務帳戶。

這不是用來連接到內部部署資料來源的帳戶。  這也不是您的工作或學校帳戶登入雲端服務使用。

如果您遇到的問題與您的 proxy 伺服器，因為驗證，您可能想要將 Windows 服務帳戶變更為網域使用者或受管理的服務帳戶。 您可以了解如何變更帳戶中的 [proxy 設定](powerbi-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user)。

## 連接埠

閘道會建立 Azure 服務匯流排的輸出連線。 輸出連接埠上進行通訊︰ TCP 443 （預設）、 5671，5672，9350 到 9354。  閘道不需要輸入連接埠。 [進一步了解](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/)

建議您，您允許清單資料區域，在防火牆中的 IP 位址。 您可以下載 [Microsoft Azure 資料中心 IP 清單](https://www.microsoft.com/download/details.aspx?id=41653)。 每週更新此清單。 

> [AZURE.NOTE]  Azure 資料中心 IP 清單中列出的 IP 位址是以 CIDR 標記法。 例如，10.0.0.0/24 並不表示透過 10.0.0.24 10.0.0.0。 深入了解 [CIDR 標記法](http://whatismyipaddress.com/cidr)。

以下是閘道所使用的完整的網域名稱的清單。

|網域名稱|輸出連接埠|說明|
|---|---|---|
|*。 powerbi.com|80|HTTP 用於下載安裝程式。|
|*。 powerbi.com|443|HTTPS|
|*。 analysis.windows.net|443|HTTPS|
|*。 login.windows.net|443|HTTPS|
|*.servicebus.windows.net|5671-5672|進階的訊息佇列通訊協定 (AMQP)|
|*.servicebus.windows.net|443, 9350-9354|透過 TCP （需要存取控制權杖取得 443） 的服務匯流排轉送的接聽程式|
|*。 frontend.clouddatahub.net|443|HTTPS|
|*。 core.windows.net|443|HTTPS|
|login.microsoftonline.com|443|HTTPS|
|*。 msftncsi.com|443|用來測試網際網路連線，如果閘道的 Power BI 服務無法連線。|
|*.microsoftonline-p.com|443|用於驗證視設定而定。|

> [AZURE.NOTE] 前往 visualstudio.com 或 visualstudioonline.com 流量適用於應用程式情資，，則不需要在閘道將函式。

### 強制使用 Azure 服務匯流排的 HTTPS 通訊

您可以強制閘道與 Azure 服務匯流排，而不直接 TCP 使用 HTTPS 通訊。 雖然這會大幅降低效能。 您必須修改 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* 檔案。 將值從 `AutoDetect` 到 `Https`。 這個檔案位於，根據預設，在 *C:\Program Files\On 內部資料閘道*。

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## 高可用性的比較

高可用性選項均為閘道的藍圖。 敬請期待更多的更新。

## 如何重新啟動閘道

閘道執行為 windows 服務。 您可以啟動並停止任何 windows 服務類似。 有多種方式可以執行這項操作。 以下是如何您可以從命令提示字元它。

1.  閘道器執行所在電腦上啟動 [系統管理員命令提示字元。

2.  使用下列命令來停止服務。

    net stop PBIEgwService 

3.  使用下列命令來啟動服務。

    net start PBIEgwService