<properties
   pageTitle="Integrate a Power BI tile into an app"
   description="Walkthrough to integrate a tile into an app, sample code"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Integrate a tile into an app

## 簡介

In this walkthrough, you integrate, or embed, a tile into a web app using C# and the <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> API, some JavaScript code, and an IFrame.

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: To get started with this walkthrough, you need a <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> account. If you don't have an account, see <bpt id="p1">[</bpt>Sign up for Power BI<ept id="p1">]( powerbi-admin-free-with-custom-azure-directory.md)</ept>.

To integrate a tile into a web app, you use the <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> API, and an Azure Active Directory (AD) authorization <bpt id="p2">**</bpt>access token<ept id="p2">**</ept> to get a dashboard and tile. Then, you load the tile into an <bpt id="p1">**</bpt>IFrame<ept id="p1">**</ept> using the same access token. The <bpt id="p1">**</bpt>Power BI<ept id="p1">**</ept> API provides programmatic access to certain <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> resources. See <bpt id="p1">[</bpt>Overview of Power BI REST API<ept id="p1">](https://msdn.microsoft.com/library/dn877544.aspx)</ept>. The illustration below shows the general flow to integrate a tile.

![](media\powerbi-developer-integrate-tile\integrate-tile-flow.png)

Here are the steps to integrate, or embed, a tile into a web page.

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: This article shows the code used in the <bpt id="p2">[</bpt>Integrate a tile sample<ept id="p2">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)</ept> on GitHub. To follow along with this walkthrough, you should download the sample. To run the sample, see <bpt id="p1">[</bpt>Configure the integrate a tile sample<ept id="p1">](powerbi-developer-integrate-tile-register.md#configure-sample)</ept> in the Register a web app with Azure AD step .

## Steps to integrate a tile into an app

- <bpt id="p1">[</bpt>Step 1: Register a web app with Azure AD<ept id="p1">](powerbi-developer-integrate-tile-register.md)</ept>. You need to register your web app with <bpt id="p1">**</bpt>Azure Active Directory (AD)<ept id="p1">**</ept> so that Azure AD can identify your application when you need to access <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> tiles.
- [Step 2: Get a Power BI dashboard](powerbi-developer-integrate-tile-get-dashboard.md)
- [Step 3: Get a Power BI tile](powerbi-developer-integrate-tile-get-tile.md)
- [Step 4: Load a Power BI tile into an IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md)
- [Integrate a tile into an app code listing](powerbi-developer-integrate-tile-code.md)

## 下一個步驟

In the next step, you learn how to <bpt id="p1">[</bpt>Register a web app with Azure AD<ept id="p1">](powerbi-developer-integrate-tile-register.md)</ept> to get a <bpt id="p2">**</bpt>Client ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Client Secret<ept id="p3">**</ept> to authenticate the web app with <bpt id="p4">**</bpt>Azure AD<ept id="p4">**</ept>. A Client ID and Client Secret is used to identify your app in Azure AD. After you get a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Client Secret<ept id="p2">**</ept>, you can configure the <bpt id="p3">[</bpt>Integrate a tile sample<ept id="p3">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)</ept>. See <bpt id="p1">[</bpt>Configure the integrate a tile sample<ept id="p1">](powerbi-developer-integrate-tile-register.md#configure-sample)</ept>.

[Next Step &gt;](powerbi-developer-integrate-tile-register.md)

## 請參閱

[Sign up for Power BI]( powerbi-admin-free-with-custom-azure-directory.md)  
[Integrate a tile sample](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configure the integrate a tile sample](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Step 1: Register a web app with Azure AD](powerbi-developer-integrate-tile-register.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)