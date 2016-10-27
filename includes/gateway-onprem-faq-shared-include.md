## 一般

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What is the actual Windows service called?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> The gateway is called On-premises data gateway service in Services

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What are the requirements for the gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Take a look at the requirements section of the main <bpt id="p2">[</bpt>gateway article<ept id="p2">](powerbi-gateway-onprem.md)</ept>.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What data sources are supported with the gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> See the data sources table in the main <bpt id="p2">[</bpt>gateway article<ept id="p2">](powerbi-gateway-onprem.md)</ept>.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Do I need a gateway for cloud data sources like Azure SQL Database?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No! The service will be able to connect to that data source without a gateway.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Are there any inbound connections to the gateway from the cloud?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. The gateway uses outbound connections to Azure Service Bus.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What if I block outbound connections? What do I need to open?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> See the <bpt id="p2">[</bpt>list of ports<ept id="p2">](powerbi-gateway-onprem.md#ports)</ept> and hosts that the gateway uses.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Does the gateway have to be installed on the same machine as the data source?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. The gateway will connect to the data source using the connection information that was provided. Think of the gateway as a client application in this sense. It will just need to be able to connect to the server name that was provided.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What is the latency for running queries to a data source from the gateway? What is the best architecture?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> It is recommended to have the gateway as close to the data source as possible to avoid network latency. If you can install the gateway on the actual data source, it will minimize the latency introduced. Consider the data centers as well. For example, if your service is making use of the West US data center, and you have SQL Server hosted in an Azure VM, you will want to have the Azure VM in West US as well. This will minimize latency and avoid egress charges on the Azure VM.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Are there any requirements for network bandwidth?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> It is recommended to have good throughput for your network connection. Every environment is different and this is also dependent on the amount of data being sent. Using ExpressRoute could help to guarantee a level of throughput between on-premises and the Azure data centers.

You can use the 3rd party <bpt id="p1">[</bpt>Azure Speed Test app<ept id="p1">](http://azurespeedtest.azurewebsites.net/)</ept> to help gauge what your throughput is. 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can the gateway Windows service run with an Azure Active Directory account?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. The Windows service needs to have a valid Windows account. By default it will run with the Service SID, <bpt id="p1">*</bpt>NT SERVICE\PBIEgwService<ept id="p1">*</ept>.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> How are results sent back to the cloud?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> This is done by way of the Azure Service Bus. For more information, see <bpt id="p1">[</bpt>how it works<ept id="p1">](powerbi-gateway-onprem.md#how-the-gateway-works)</ept>.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Where are my credentials stored?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> The credentials you enter for a data source are stored encrypted in the gateway cloud service. The credentials are decrypted at the gateway on-premises.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can I place the gateway in a perimeter network (also known as DMZ, demilitarized zone, and screened subnet)?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> The gateway requires connectivity to the data source. If the data source is not accessable in your perimeter network, the gateway may not be able to connect to it. For example, your SQL Server may not be in your perimeter network. And, you cannot connect to your SQL Server from the perimeter network. If you placed the gateway in your perimeter network, it would not be able to reach the SQL Server.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Is it possible to force the gateway to use HTTPS traffic with Azure Service Bus instead of TCP?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes. Although, this will greatly reduce performance. You will want to modify the <bpt id="p1">*</bpt>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config<ept id="p1">*</ept> file. You will want to change the value from <ph id="ph1">`AutoDetect`</ph> to <ph id="ph2">`Https`</ph>. This file is located, by default, at <bpt id="p1">*</bpt>C:\Program Files\On-premises data gateway<ept id="p1">*</ept>.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## High Availability/Disaster Recovery

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Are there any plans for enabling high availability scenarios with the gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes. This is on the roadmap, but we don’t have a timeline yet.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What options are available for disaster recovery?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> You can use the recovery key to restore or move a gateway. When you install the gateway, supply the recovery key.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What is the benefit of the recovery key?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> It provides a way to migrate or recover your gateway settings. This is also used for disaster recovery.

## 疑難排解

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Where are the gateway logs located?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> See the tools section of the <bpt id="p2">[</bpt>troubleshooting article<ept id="p2">](powerbi-gateway-onprem-tshoot.md#tools)</ept>.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> How can I see what queries are being sent to the on-premises data source?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> You can enable query tracing.  This will include the queries being sent. Remember to change it back to the original value when done troubleshooting. Having query tracing enabled will cause the logs to be larger.

You can also look at tools your data source has for tracing queries. For example, for SQL Server and Analysis Services you can use Extended Events or SQL Profiler.