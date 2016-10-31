## 防火牆或 Proxy

如需提供您的閘道器的 proxy 資訊，請參閱 [Power BI 閘道的 proxy 設定](powerbi-gateway-proxy.md)。

您可以測試，查看您的防火牆或 proxy 時，可能會封鎖連線從 PowerShell 提示字元執行下列命令。 這將會測試 Azure 服務匯流排連線。 這只會測試網路連線並沒有任何與定域機組伺服器服務或閘道。 它可以協助判斷是否您的電腦可以考到網際網路。

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

結果看起來應該如下所示。 差異將會以 TcpTestSucceeded。 如果 **TcpTestSucceeded** 不 *true*, ，則您可能會被防火牆封鎖。

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

如果您想要完整，替換 **ComputerName** 和 **連接埠** 所列的值 [連接埠](powerbi-gateway-onprem.md#ports)

防火牆可能也會封鎖對 Azure 資料中心的 Azure 服務匯流排連線。 如果是這樣，您會想要允許清單 （解除封鎖） 的 IP 位址，您對這些資料中心的地區。 您可以取得一份 Azure IP 位址 [這裡](https://www.microsoft.com/download/details.aspx?id=41653)。