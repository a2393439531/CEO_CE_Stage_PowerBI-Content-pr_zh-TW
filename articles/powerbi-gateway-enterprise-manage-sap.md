<properties
pageTitle="Manage your SAP HANA data source"
description="How to manage the on-premises data gateway and data sources that belong to that gateway. This article is specific to SAP HANA."
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="erikre"
backup=""
editor=""
tags=""
qualityFocus="no"
qualityDate=""/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/01/2016"
ms.author="asaxton"/>
# Manage your SAP HANA data source

Once you have installed the On-premises Data Gateway, you will need to add data sources that can be used with the gateway. This article will look at how to work with gateways and data sources. You can use the SAP HANA data source either for scheduled refresh or for DirectQuery.

## Download and install the gateway

You can download the gateway from the Power BI service. Select <bpt id="p1">**</bpt>Downloads<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Data Gateway<ept id="p2">**</ept>, or by going to the <bpt id="p3">[</bpt>gateway download page<ept id="p3">](https://go.microsoft.com/fwlink/?LinkId=698861)</ept>.

![](media/powerbi-gateway-onprem/powerbi-download-data-gateway.png)

## Add a gateway

To add a Gateway, simply <bpt id="p1">[</bpt>download<ept id="p1">](https://go.microsoft.com/fwlink/?LinkId=698861)</ept> and install the gateway on a server in your environment. After you have installed the gateway, it will show in the lists of gateways under <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept>.

> [AZURE.NOTE] <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept> will not show up until you are the admin of at least one gateway. This can happen either by being added as an admin or you installing and configuring a gateway.

## Remove a gateway

Removing a gateway will also delete any data sources under that gateway.  This will also break any dashboards and reports that rely on those data sources.

1.  Select the gear icon <ph id="ph1">![](media/powerbi-gateway-enterprise-manage/pbi_gearicon.png)</ph> in the upper-right corner &gt; <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept>.

2.  Gateway &gt; <bpt id="p1">**</bpt>Remove<ept id="p1">**</ept>

    ![](media/powerbi-gateway-enterprise-manage/datasourcesettings7.png)

## Add a data source

You can add a data source by either selecting a gateway and click <bpt id="p1">**</bpt>Add data source<ept id="p1">**</ept>, or go to Gateway &gt; <bpt id="p2">**</bpt>Add data source<ept id="p2">**</ept>.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings1.png)

You can then select the <bpt id="p1">**</bpt>Data Source Type<ept id="p1">**</ept> from the list.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings2-sap.png)

You will then want to fill in the information for the data source which includes the <bpt id="p1">**</bpt>Server<ept id="p1">**</ept>, <bpt id="p2">**</bpt>Username<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Password<ept id="p3">**</ept>. 

> [AZURE.NOTE] All queries to the data source will run using these credentials. For more information, see the main on-premises data gateway article to learn more about how <bpt id="p1">[</bpt>credentials<ept id="p1">](powerbi-gateway-onprem.md#credentials)</ept> are stored.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings3-sap.png)

You can click <bpt id="p1">**</bpt>Add<ept id="p1">**</ept> after you have everything filled in.  You can now use this data source for scheduled refresh, or DirectQuery, against a SAP HANA server that is on-premises. You will see <bpt id="p1">*</bpt>Connection Successful<ept id="p1">*</ept> if it succeeded.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings4.png)

### 進階設定

You can configure the privacy level for your data source. This controls how data can be mashed up. This is only used for scheduled refresh. It does not apply to DirectQuery. [進一步了解](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

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

## Using the data source

After you have created the data source, it will be available to use with either DirectQuery connections, or through scheduled refresh. 

> [AZURE.NOTE] Server and database name have to match between Power BI Desktop and the data source within the on-premises data gateway!

The link between your dataset and the data source within the gateway is based on your server name and database name. These have to match. For example, if you supply an IP Address for the server name, within Power BI Desktop, you will need to use the IP Address for the data source within the gateway configuration. If you use <bpt id="p1">*</bpt>SERVER\INSTANCE<ept id="p1">*</ept>, in Power BI Desktop, you will need to use the same within the data source configured for the gateway.

This is the case for both DirectQuery and scheduled refresh.

### Using the data source with DirectQuery connections

You will need to make sure the server and database name matches between Power BI Desktop and the configured data source for the gateway. You will also need to make sure your user is listed in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab of the data source in order to publish DirectQuery datasets. The selection for DirectQuery occurs within Power BI Desktop when you first import data. [進一步了解](powerbi-desktop-use-directquery.md)

After you publish, either from Power BI Desktop or <bpt id="p1">**</bpt>Get Data<ept id="p1">**</ept>, your reports should start working. It may take several minutes, after creating the data source within the gateway, for the connection to be usable.

### Using the data source with scheduled refresh

If you are listed in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab of the data source configured within the gateway, and the server and database name match, you will see the gateway as an option to use with scheduled refresh.

![](media/powerbi-gateway-enterprise-manage/powerbi-gateway-enterprise-schedule-refresh.png)

## 另請參閱

[On-premises Data Gateway](powerbi-gateway-onprem.md)  
[On-premises Data Gateway - in-depth](powerbi-gateway-onprem-indepth.md)  
[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)