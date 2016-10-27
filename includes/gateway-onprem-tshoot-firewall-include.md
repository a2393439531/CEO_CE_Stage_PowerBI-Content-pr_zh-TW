## Firewall or Proxy

For information on providing proxy information for your gateway, see <bpt id="p1">[</bpt>Configuring proxy settings for the Power BI Gateways<ept id="p1">](powerbi-gateway-proxy.md)</ept>.

You can test to see if your firewall, or proxy, may be blocking conections by running the following command from a PowerShell prompt. This will test connectivity to the Azure Service Bus. This only tests network connectivity and doesn't have anything to do with the cloud server service or the gateway. It helps to determine if your machine can actually get out to the internet.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

The results should look similar to the following. The difference will be with TcpTestSucceeded. If <bpt id="p1">**</bpt>TcpTestSucceeded<ept id="p1">**</ept> is not <bpt id="p2">*</bpt>true<ept id="p2">*</ept>, then you may be blocked by a firewall.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

If you want to be exhaustive, substitute the <bpt id="p1">**</bpt>ComputerName<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Port<ept id="p2">**</ept> values with those listed for <bpt id="p3">[</bpt>ports<ept id="p3">](powerbi-gateway-onprem.md#ports)</ept>

The firewall may also be blocking the connections that the Azure Service Bus makes to the Azure data centers. If that is the case, you will want to whitelist (unblock) the IP addresses for your region for those data centers. You can get a list of Azure IP addresses <bpt id="p1">[</bpt>here<ept id="p1">](https://www.microsoft.com/download/details.aspx?id=41653)</ept>.