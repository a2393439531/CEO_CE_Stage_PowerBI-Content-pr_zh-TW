## 疑難排解的工具

<a name="logs" />
### Collecting logs from the gateway configurator

There are several logs you can collect for the gateway. Always start with the logs!

**Installer logs**

    %localappdata%\Temp\On-premises_data_gateway_*.log

**Configuration logs**

    %localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log

**On-premises data gateway service logs**

    C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log

### 事件記錄檔  
The <bpt id="p1">**</bpt>On-premises data gateway service<ept id="p1">**</ept> event logs are present under <bpt id="p2">**</bpt>Application and Services Logs<ept id="p2">**</ept>.

![on-prem-data-gateway-event-logs](./media/gateway-onprem-tshoot-tools-include/on-prem-data-gateway-event-logs.png)

<a name="fiddler" />
### Fiddler Trace  
<bpt id="p1">[</bpt>Fiddler<ept id="p1">](http://www.telerik.com/fiddler)</ept> is a free tool from Telerik that monitors HTTP traffic.  You can see the back and forth with the Power BI service from the client machine. This may show errors and other related information.

![](media/gateway-onprem-tshoot-tools-include/fiddler.png)