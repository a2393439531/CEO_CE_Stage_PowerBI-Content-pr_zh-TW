<properties
   pageTitle="Register an app with Azure AD"
   description="Walkthrough - Push data into a dashboard - Register an app with Azure AD"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="04/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Step 1: Register an app with Azure AD

This article is part of a step-by-step walkthrough to <bpt id="p1">[</bpt>push data into a dashboard<ept id="p1">](powerbi-developer-walkthrough-push-data.md)</ept>.

The first step to push data into a Power BI dashboard is to register your app in Azure AD. You need to do this first so that you have a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> that identifies your app in Azure AD. Without a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept>, Azure AD cannot authenticate your app.

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Before you register an app for Power BI, you need to <bpt id="p2">[</bpt>Sign up for Power BI<ept id="p2">](powerbi-admin-free-with-custom-azure-directory.md)</ept>.

Here are the steps to register an app in Azure AD.

## Register an app in Azure AD

1. Go to dev.powerbi.com/apps.
2. Click <bpt id="p1">**</bpt>Sign in with your existing account<ept id="p1">**</ept>, and sign into your Power BI account.
3. Enter an <bpt id="p1">**</bpt>App Name<ept id="p1">**</ept> such as "Sample push data app".
4. For <bpt id="p1">**</bpt>App Type<ept id="p1">**</ept>, choose <bpt id="p2">**</bpt>Native app<ept id="p2">**</ept>.
5. Enter a <bpt id="p1">**</bpt>Redirect URL<ept id="p1">**</ept>, such as <bpt id="p2">**</bpt>https://login.live.com/oauth20_desktop.srf<ept id="p2">**</ept>. For a <bpt id="p1">**</bpt>Native client app<ept id="p1">**</ept>, a redirect uri gives <bpt id="p2">**</bpt>Azure AD<ept id="p2">**</ept> more details on the specific application that it will authenticate. The standard Uri for a client app is https://login.live.com/oauth20_desktop.srf.
6. For <bpt id="p1">**</bpt>Choose APIs to access<ept id="p1">**</ept>, choose <bpt id="p2">**</bpt>Read and Write All Datasets<ept id="p2">**</ept>. For all Power BI app permissions, see <bpt id="p1">[</bpt>Power BI Permissions<ept id="p1">](powerbi-developer-power-bi-permissions.md)</ept>.
7. Click <bpt id="p1">**</bpt>Register app<ept id="p1">**</ept>, and save the <bpt id="p2">**</bpt>Client ID<ept id="p2">**</ept> that was generated. A <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> identifies the app in Azure AD.

Here's how your <bpt id="p1">**</bpt>Register an Application for Power BI<ept id="p1">**</ept> page should look:

![](media\powerbi-developer-walkthrough-push-data\powerbi-developer-sample-register-app.png)

The next step shows you how to <bpt id="p1">[</bpt>get an authentication access token<ept id="p1">](powerbi-developer-walkthrough-push-data-get-token.md)</ept>.

[Next Step &gt;](powerbi-developer-walkthrough-push-data-get-token.md)

## 請參閱

[Sign up for Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Get an authentication access token](powerbi-developer-walkthrough-push-data-get-token.md)  
[Walkthrough: Push data into a dashboard](powerbi-developer-walkthrough-push-data.md)  
[Register a client app](powerbi-developer-register-a-client-app.md)  
[Overview of Power BI REST API](powerbi-developer-overview-of-power-bi-rest-api.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
