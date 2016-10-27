<properties
   pageTitle="Power BI and ExpressRoute"
   description="Power BI and ExpressRoute"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/10/2016"
   ms.author="davidi"/>

# Power BI and ExpressRoute

With <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ExpressRoute<ept id="p2">**</ept>, you can create a private network connection from your organization to Power BI (or using an ISP’s colocation facility), bypassing the Internet to better secure your sensitive Power BI data and connections.

<bpt id="p1">**</bpt>ExpressRoute<ept id="p1">**</ept> is an Azure service that lets you create private connections between Azure datacenters (where Power BI resides) and your on-premises infrastructure, or create private connections between Azure datacenters and your colocation environment.


![](media/powerbi-admin-power-bi-expressroute/pbi_expressroute_1.png)

You can get <bpt id="p1">[</bpt>more information about ExpressRoute<ept id="p1">](https://azure.microsoft.com/services/expressroute/)</ept> or learn <bpt id="p2">[</bpt>how to sign up<ept id="p2">](https://azure.microsoft.com/pricing/details/expressroute/)</ept>.


## Power BI ExpressRoute Exceptions

Power BI is compliant with ExpressRoute, with a few exceptions where Power BI gets or sends data over the public Internet. These specific exceptions often include static data, such as browser configuration files that are downloaded from the nearest <bpt id="p1">**</bpt>Content Delivery Network (CDN)<ept id="p1">**</ept> node. There are some broad exceptions which apply to all of Power BI, and there are some service- or feature-specific exceptions, each of which are documented in the following sections.

### Overall Exceptions to Power BI and ExpressRoute

An exception to <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ExpressRoute<ept id="p2">**</ept> means that the data being transmitted to or from Power BI goes over the public Internet, rather than being transmitted over the private ExpressRoute link.

The two overall exceptions to Power BI using ExpressRoute are:

-   Static files downloaded from the <bpt id="p1">**</bpt>Content Delivery Network (CDN)<ept id="p1">**</ept> and websites

-   <bpt id="p1">**</bpt>Telemetry<ept id="p1">**</ept> data sent over the public Internet

Power BI uses multiple <bpt id="p1">**</bpt>Content Delivery Networks (CDNs)<ept id="p1">**</ept> or web sites to efficiently distribute the necessary static content and files to users based on geographical locale through the public Internet. These static files include product downloads (such as <bpt id="p1">**</bpt>Power BI Desktop<ept id="p1">**</ept>, <bpt id="p2">**</bpt>On-premises Data Gateway<ept id="p2">**</ept>, or <bpt id="p3">**</bpt>Power BI Content Packs<ept id="p3">**</ept> from various independent service providers), browser configuration files that are used to initiate and establish any subsequent connections with Power BI, as well as the initial secure Power BI login page – the actual credentials are only sent over ExpressRoute.   

Certain <bpt id="p1">**</bpt>telemetry data<ept id="p1">**</ept> is also sent over the public Internet and over ExpressRoute. Telemetry data includes usage statistics and similar data, which is transmitted to services that are used to monitor usage and activity.

### Power BI SaaS Application and ExpressRoute

When a user initiates a connection to the Power BI service (powerbi.com or through Cortana), the Power BI Landing Page, the login page, and static files that prepare the browser to connect and interact with Power BI are retrieved from a CDN or websites, which connects over the public Internet.

Once the login is established, subsequent Power BI data interactions occur over ExpressRoute, with the exception of certain features and services that depend on public Internet data:

-   <bpt id="p1">**</bpt>Map visuals<ept id="p1">**</ept> require connection and data transmission to the Bing Virtual Earth service or the Bing geocoding service, each of which is established over the public Internet.

-   Power BI integration with <bpt id="p1">**</bpt>Cortana<ept id="p1">**</ept> requires access to Bing over the public Internet.

-   When <bpt id="p1">**</bpt>custom links<ept id="p1">**</ept> are added by a user, such as an image widget or a video, Power BI requests data based on the link provided by the user, which may or may not use ExpressRoute.

-   Users can send <bpt id="p1">**</bpt>feedback to Power BI<ept id="p1">**</ept> in text (and optionally images) over the User Voice feedback mechanism, which uses the public Internet for transmission.

-   The <bpt id="p1">**</bpt>Bing News content provider<ept id="p1">**</ept> downloads content from Bing using the public Internet.

-   When connecting to <bpt id="p1">**</bpt>apps<ept id="p1">**</ept> (for example, content packs), users are often required to enter credentials and settings using pages provided by the SaaS provider. Such pages may or may not use ExpressRoute.


|使用者活動 |Destination|
|---|---|
|Landing page (prior to login)| `maxcdn.bootstrapcdn.com ; ajax.aspnetcdn.com ; netdna.bootstrapcdn.com ; cdn.optimizely.com; google-analytics.com ` |
|登入 | `*.mktoresp.com ; *.aadcdn.microsoftonline-p.com ; *.msecnd.com ; *.localytics.com ; ajax.aspnetcdn.com`  |
|Dashboard, report, dataset management (includes maps and geocoding)| `*.localytics.com ; *.virtualearch.net ; platform.bing.com; powerbi.microsoft.com; c.microsoft.com; app.powerbi.com; *.powerbi.com; dc.services.visualstudio.com `  |
|支援| `support.powerbi.com ; powerbi.uservoice.com ; go.microsoft.com `|


### Power BI Desktop and ExpressRoute

Power BI Desktop is also ExpressRoute compliant, with a few exceptions that are described in the following list:

-   <bpt id="p1">**</bpt>Update notifications<ept id="p1">**</ept>, used to detect whether users have the most recent version of Power BI Desktop, go over the public Internet.

-   Certain <bpt id="p1">**</bpt>telemetry data<ept id="p1">**</ept> goes over the public Internet.

-   <bpt id="p1">**</bpt>Map visuals<ept id="p1">**</ept> require connection and data transmission to the <bpt id="p2">**</bpt>Bing Virtual Earth<ept id="p2">**</ept> service or the <bpt id="p3">**</bpt>Bing geocoding<ept id="p3">**</ept> service, each of which is established over the public Internet.

-   <bpt id="p1">**</bpt>Get Data<ept id="p1">**</ept> from several data sources such as <bpt id="p2">**</bpt>Web<ept id="p2">**</ept> or third party SaaS providers go over the public Internet.


### Power BI PaaS and ExpressRoute

Power BI offers APIs and other platform-based features that enable developers to create customized Power BI solutions and apps. The following services, in addition to telemetry and CDN data discussed earlier in this topic, are used when transmitting Power BI PaaS data over the public Internet:

|PaaS Activity |Additional destinations used |
|---|---|
|Public embed (telemetry)| `c1.microsoft.com` |
|Custom visuals (CDN) | `*.azureedge.net`  |

Some <bpt id="p1">**</bpt>custom visuals<ept id="p1">**</ept> are created by third-parties, some are created by Microsoft. These may or may not use ExpressRoute.

### Power BI Mobile and ExpressRoute

This document does not cover the use of Power BI Mobile apps.  


### On-premises Data Gateway and ExpressRoute

When an <bpt id="p1">**</bpt>On-premises Data Gateway<ept id="p1">**</ept> is used with Power BI, transmissions are ExpressRoute compliant, with the exception of the user activities documented in the <bpt id="p2">**</bpt>Power BI SaaS Application and ExpressRoute<ept id="p2">**</ept> section found earlier in this topic.  
