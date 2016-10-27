<properties
pageTitle="On-premises data gateway FAQ"
description="This is the on-premises data gateway FAQ. This collects frequently asked questions into one spot for the gateway."
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="mblythe"
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
ms.date="10/12/2016"
ms.author="asaxton"/>
# On-Premises Data Gateway FAQ

<!-- Shared FAQ shared Include -->
[AZURE.INCLUDE [gateway-onprem-faq-shared-include](../includes/gateway-onprem-faq-shared-include.md)]

## Analysis Services

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can I use msdmpump.dll to create custom effective username mappings for Analysis Services?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. This is not supported at this time.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can I use the gateway to connect to a multidimensional (OLAP) instance.  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes! The enterprise gateway supports live connections to both Analysis Services Tabular and Multidimensional models.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What if I install the gateway on a computer in a different domain from my on-premises server that uses Windows authentication?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No guarantees here. It all depends on the trust relationship between the two domains. If the two different domains are in a trusted domain model, then the gateway might be able to connect to the Analysis Services server and the effective user name can be resolved. If not, you may encounter a login failure. 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> How can I find out what effective username is being passed to my on-premises Analysis Services server?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> We answer this in the <bpt id="p2">[</bpt>troubleshooting article<ept id="p2">](powerbi-gateway-onprem-tshoot.md)</ept>.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> I have 25 databases in Analysis Services, is there a way to have them all enabled for the gateway at once?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. This is on the roadmap, but we don’t have a timeframe.

## 系統管理

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can I have more than one admin for a gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes! When you manage a gateway, you can go to the administrator’s tab to add additional admins.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Does the gateway admin need to be an admin on the machine where the gateway is installed?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. The gateway admin is used to manage the gateway from within the service. 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can I prevent users in my organization from creating a gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. This is on the roadmap, but we don’t have a timeframe.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can I get usage and statistics information of the gateways in my organization?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. This is on the roadmap, but we don’t have a timeframe.

## Power BI

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> If I'm using the current Power BI gateway for enterprise deployments, do I need to upgrade?
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes, but it is simple to do so as it just works the same way you upgraded to the latest enterprise gateway. Simple install the new on-premises data gateway to upgrade your existing gateway.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Do i need to upgrade the personal gateway?
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No, you can keep using the personal gateway for Power BI.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> How often are tiles in a dashboard, in Power BI, refreshed when connected through the enterprise gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> About ten minutes. DirectQuery connections are just that. This doesn’t mean that a tile issues a query to your on-premises server, and shows new data, every ten minutes.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Can I upload Excel workbooks with Power Pivot data models that connect to on-premises data sources? Do I need a gateway for this scenario?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes, you can upload the workbook. And, no, you don’t need a gateway. But, because the data will reside in the Excel data model, reports in Power BI based on the Excel workbook will not be live. In order to refresh reports in Power BI, you’d have to re-upload an updated workbook each time. Or, use the gateway with scheduled refresh.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> If users share dashboards that has a DirectQuery connection, will those other users be able to see the data even though they might not have the same permissions.  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> For a dashboard connected to Analysis Services, users will only see the data they have access to. If the users do not have the same permissions, they will not be able to see any data. For other data sources, all users will share the credentials entered by the admin for that data source.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Is a Pro license required to use the gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Is a Pro license required for users when interacting with a dashboard or report that makes use of the gateway?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Why can't I connect to my Oracle server?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> You may need to install the Oracle client and configure the tnsnames.ora file with the proper server information in order to connect to your Oracle server. This is a separate install outside of the Gateway. For more information, see <bpt id="p1">[</bpt>Installing the Oracle Client<ept id="p1">](powerbi-gateway-onprem-manage-oracle.md#installing-the-oracle-client)</ept>.

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Will the gateway work with ExpressRoute?  
<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes. For more information about ExpressRoute and Power BI, see <bpt id="p1">[</bpt>Power BI and ExpressRoute<ept id="p1">](powerbi-admin-power-bi-expressroute.md)</ept>.

## 請參閱
[On-premises data gateway](powerbi-gateway-onprem.md)  
[On-premises data gateway in-depth](powerbi-gateway-onprem-indepth.md)  
[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)