## Update to the latest version 
 
A lot of issues can surface when the gateway version is out of date.  It is a good general practice to make sure you are on the latest version.  If you haven't updated the gateway for a month, or longer, you may want to consider installing the latest version of the gateway and see if you can reproduce the issue.

## Common issues

Here are a few common issues and resolutions that have helped a number of customers in environments that restrict internet access.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### Authentication to proxy server

Your proxy may rquire authentication from a domain user account. By default, the gateway uses a Service SID for the windows service log on user. Changing the log on user to a domain user can help with this. For more information, see <bpt id="p1">[</bpt>Changing the gateway service account to a domain user<ept id="p1">](powerbi-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user)</ept>.

### Your proxy only allows ports 80 and 443 traffic

Some proxies restrict traffic to only ports 80 and 443. By default, communication to Azure Service Bus will occur on ports other than 443. 

You can force the gateway to communicate with Azure Service Bus using HTTPS instead of direct TCP. Although, this will greatly reduce performance. You will need to modify the <bpt id="p1">*</bpt>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config<ept id="p1">*</ept> file. Change the value from <ph id="ph1">`AutoDetect`</ph> to <ph id="ph2">`Https`</ph>. This file is located, by default, at <bpt id="p1">*</bpt>C:\Program Files\On-premises data gateway<ept id="p1">*</ept>.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## 安裝

### Error: Failed to add user to group.  (-2147463168   PBIEgwService   Performance Log Users   )

You may receive this error if you are trying to install the gateway on a domain controller. Deploying on a domain controller is not supported. You will need to deploy the gateway on a machine that is not a domain controller.