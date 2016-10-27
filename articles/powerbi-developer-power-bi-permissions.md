<properties
   pageTitle="Power BI permissions"
   description="Power BI permissions"
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
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Power BI permissions

## 權限範圍
Power BI permissions give an application the ability to take certain actions on a user's behalf. All permissions must be approved by a user in order to be valid.

|顯示名稱|描述|Scope Value|
|---|---|---|
|View all Datasets|The app can view all datasets for the signed in user and datasets that the user has access to.|Dataset.Read.All|
|Read and Write all Datasets|The app can view and write to all datasets for the signed in user and datasets that the user has access to.|Dataset.ReadWrite.All|
|View users Groups|The app can view all groups that the signed in user belongs to.|Group.Read.All|
|View all Dashboards (preview)|The app can view all dashboards for the signed in user and dashboards that the user has access to.|Dashboard.Read.All|
|View all Reports (preview)|The app can view all reports for the signed in user and reports that the user has access to. The app can also see the data within the reports as well as its structure.|Report.Read.All|

An application can request permissions when it first attempts to log in to a user's page by passing in the requested permissions in the scope parameter of the call. If the permissions are granted, an access token will be returned to the app which can be used on future API calls. The access can only be used by a specific application.

## Requesting Permissions
While you can call the API to authenticate with a username and password, in order to take actions on behalf of another user, they will need to request permissions that the user then approves and then send the resulting access token on all future calls. For this process, we will follow the standard <bpt id="p1">[</bpt>OAuth 2.0<ept id="p1">](http://oauth.net/2/)</ept> protocol. While the actual implementation may vary, the OAuth flow for Power BI has the following elements:

- <bpt id="p1">**</bpt>Login UI<ept id="p1">**</ept> - This is a UI that the developer can evoke to request permissions. It would require the user to log in if not already. The user would also need to approve the permissions that the application is requesting. The login window will post back either an access code or an error message to a redirect URL that is supplied.
    - A standard redirect URL should be supplied by Power BI for use by native applications.
- <bpt id="p1">**</bpt>Authorization Code<ept id="p1">**</ept> - Authorization Codes are returned to web applications after login via URL parameters in the redirect URL. Since they are in parameters there is some security risk. Web applications will have to exchange the authorization code for an Authorization Token
- <bpt id="p1">**</bpt>Authorization Token<ept id="p1">**</ept> - Are used to authenticate API calls on another user's behalf. They will be scoped to a specific application. Tokens have a set lifespan and when they expire they will need to be refreshed.
- <bpt id="p1">**</bpt>Refresh Token<ept id="p1">**</ept> - When tokens expire there will be a process of refreshing them.

More questions? [Try the Power BI Community](http://community.powerbi.com/)
