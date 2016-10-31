## 更新為最新版本 
 
閘道器版本已過期時，可能出現很多問題。  它是一般最好先確定您是在最新版本。  一個月以上未更新閘道，您可能要考慮安裝最新版的閘道，並查看可以重現問題。

## 常見的問題

以下是幾個常見的問題與解決方案已協助限制網際網路存取的環境中的客戶數目。

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### Proxy 伺服器的驗證

您的 proxy 可能 rquire 驗證網域使用者帳戶。 根據預設，閘道會使用 windows 服務登入使用者的服務 SID。 變更到網域的使用者登入使用者能提供協助。 如需詳細資訊，請參閱 [的閘道服務帳戶變更為網域使用者](powerbi-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user)。

### 您的 proxy 只允許連接埠 80 和 443 的流量

某些 proxy 來限制流量只連接埠 80 和 443。 根據預設，Azure 服務匯流排通訊會發生連接埠 443 以外。 

您可以強制閘道與 Azure 服務匯流排，而不直接 TCP 使用 HTTPS 通訊。 雖然這會大幅降低效能。 您必須修改 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* 檔案。 將值從 `AutoDetect` 到 `Https`。 這個檔案位於，根據預設，在 *C:\Program Files\On 內部資料閘道*。

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## 安裝

### 錯誤︰ 無法將使用者新增到群組。  （-2147463168 PBIEgwService 效能記錄使用者）

如果您嘗試在網域控制站上安裝閘道，您可能會收到這個錯誤。 不支援在網域控制站上部署。 您必須部署在不是網域控制站的電腦上的閘道。