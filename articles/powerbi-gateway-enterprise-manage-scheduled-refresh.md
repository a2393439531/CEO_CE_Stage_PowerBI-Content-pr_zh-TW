<properties
pageTitle="Manage your data source - Import/Scheduled Refresh"
description="How to manage the on-premises data gateway gateway and data sources that belong to that gateway. This article is specific to data sources that can be used with import/scheduled refresh."
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="erikre"
backup=""
editor=""
tags=""
qualityFocus="monitoring"
qualityDate="05/16/2016"/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/01/2016"
ms.author="asaxton"/>
# Manage your data source - Import/Scheduled Refresh

Once you have installed the On-premises Data Gateway, you will need to add data sources that can be used with the gateway. This article will look at how to work with gateways and data sources that are used for scheduled refresh as opposed to DirectQuery or live connections.

## Download and install the gateway

You can download the gateway from the Power BI service. Select <bpt id="p1">**</bpt>Downloads<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Data Gateway<ept id="p2">**</ept>, or by going to the <bpt id="p3">[</bpt>gateway download page<ept id="p3">](https://go.microsoft.com/fwlink/?LinkId=698861)</ept>.

![](media/powerbi-gateway-onprem/powerbi-download-data-gateway.png)

## Add a gateway

To add a gateway, simply <bpt id="p1">[</bpt>download<ept id="p1">](https://go.microsoft.com/fwlink/?LinkId=698863)</ept> and install the enterprise gateway on a server in your environment. After you have installed the gateway, it will show in the lists of gateways under <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept>.

> [AZURE.NOTE] <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept> will not show up until you are the admin of at least one gateway. This can happen either by being added as an admin or you installing and configuring a gateway.

## Remove a gateway

Removing a gateway will also delete any data sources under that gateway.  This will also break any dashboards and reports that rely on those data sources.

1.  Select the gear icon <ph id="ph1">![](media/powerbi-gateway-enterprise-manage/pbi_gearicon.png)</ph> in the upper-right corner &gt; <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept>.

2.  Gateway &gt; <bpt id="p1">**</bpt>Remove<ept id="p1">**</ept>

    ![](media/powerbi-gateway-enterprise-manage/datasourcesettings7.png)

## Add a data source

You can add a data source by either selecting a gateway and click <bpt id="p1">**</bpt>Add data source<ept id="p1">**</ept>, or go to Gateway &gt; <bpt id="p2">**</bpt>Add data source<ept id="p2">**</ept>.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings1.png)

You can then select the <bpt id="p1">**</bpt>Data Source Type<ept id="p1">**</ept> from the list. All of the data sources listed can be used for scheduled refresh with the enterprise gateway. Analysis Services, SQL Server and SAP HANA can be used for either scheduled refresh, or DirectQuery/live connections.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings2.png)

You will then want to fill in the information for the data source which includes the source information and credentials used to access the data source.

> [AZURE.NOTE] All queries to the data source will run using these credentials. For more information, see the main on-premises data gateway article to learn more about how <bpt id="p1">[</bpt>credentials<ept id="p1">](powerbi-gateway-onprem.md#credentials)</ept> are stored.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings3-oracle.png)

You can click <bpt id="p1">**</bpt>Add<ept id="p1">**</ept> after you have everything filled in.  You can now use this data source for scheduled refresh with your on-premises data. You will see <bpt id="p1">*</bpt>Connection Successful<ept id="p1">*</ept> if it succeeded.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings4.png)

<!-- Shared Install steps Include -->
[AZURE.INCLUDE [gateway-onprem-datasources-include](../includes/gateway-onprem-datasources-include.md)]

### 進階設定

You can configure the privacy level for your data source. This controls how data can be mashed up. This is only used for scheduled refresh. [進一步了解](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/powerbi-gateway-enterprise-manage/datasourcesettings9.png)

## Remove a data source

Removing a data source will break any dashboards or reports that rely on the given data source.  

To remove a Data Source, go to the Data Source &gt; <bpt id="p1">**</bpt>Remove<ept id="p1">**</ept>.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings6.png)

## Manage administrators

On the Administrators tab, for the gateway, you can add, and remove, users that can administer the gateway. You can only add users at this time. Security groups cannot be added.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings8.png)

## 管理使用者

On the Users tab, for the data source, you can add, and remove, users, or security groups, that can use this data source.

> [AZURE.NOTE] The users list only controls who are allowed to publish reports. The report owners can create dashboards, or content packs, and share those with other users.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings5.png)

## Using the data source for scheduled refresh

After you have created the data source, it will be available to use with either DirectQuery connections, or through scheduled refresh. 

> [AZURE.NOTE] Server and database name have to match between Power BI Desktop and the data source within the on-premises data gateway!

The link between your dataset and the data source within the gateway is based on your server name and database name. These have to match. For example, if you supply an IP Address for the server name, within Power BI Desktop, you will need to use the IP Address for the data source within the gateway configuration. If you use <bpt id="p1">*</bpt>SERVER\INSTANCE<ept id="p1">*</ept>, in Power BI Desktop, you will need to use the same within the data source configured for the gateway.

If you are listed in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab of the data source configured within the gateway, and the server and database name match, you will see the gateway as an option to use with scheduled refresh.

![](media/powerbi-gateway-enterprise-manage/powerbi-gateway-enterprise-schedule-refresh.png)

> [AZURE.WARNING] If your dataset contains multiple data sources, each data source must be added within the gateway. If one or more data sources are not added to the gateway, you will not see the gateway as available for scheduled refresh.

## 限制

- OAuth is not a supported authentication scheme with the On-Premises Data Gateway. You cannot add data sources that require OAuth. If your dataset has a data source requiring OAuth, you will not be able to use the gateway for scheduled refresh.

## 另請參閱

[On-premises Data Gateway](powerbi-gateway-onprem.md)  
[On-premises Data Gateway - in-depth](powerbi-gateway-onprem-indepth.md)  
[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)