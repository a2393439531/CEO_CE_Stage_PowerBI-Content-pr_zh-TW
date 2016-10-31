## 疑難排解的工具

<a name="logs" />
### 從閘道設定程式收集記錄檔

有數個閘道，您可以收集的記錄檔。 開頭一律記錄檔 ！

**安裝程式記錄檔**

    %localappdata%\Temp\On-premises_data_gateway_*.log

**設定記錄檔**

    %localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log

**內部資料閘道器服務記錄檔**

    C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log

### 事件記錄檔  
 **內部資料閘道器服務** 事件記錄檔存在於 **應用程式及服務記錄檔**。

![on-prem-data-gateway-event-logs](./media/gateway-onprem-tshoot-tools-include/on-prem-data-gateway-event-logs.png)

<a name="fiddler" />
### Fiddler 追蹤  

            [Fiddler](http://www.telerik.com/fiddler) 是透過監視 HTTP 流量的 Telerik 免費的工具。  您可以請參閱上一步]，並提出的 Power bi 服務從用戶端電腦。 這可能會顯示錯誤和其他相關的資訊。

![](media/gateway-onprem-tshoot-tools-include/fiddler.png)