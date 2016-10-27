<properties
   pageTitle="Register a client app"
   description="Register a client app"
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

# Register a client app

This article shows you how to register a Power BI client app in <bpt id="p1">**</bpt>Azure Active Directory (Azure AD)<ept id="p1">**</ept>. You register your client app with Azure AD to allow your application access to the Power BI REST API. This will allow you to establish an identity for your application and specify permissions to Power BI REST resources. For a list of Power BI permissions, see <bpt id="p1">[</bpt>Power BI permissions<ept id="p1">](powerbi-developer-power-bi-permissions.md)</ept>.

<bpt id="p1">**</bpt>Important<ept id="p1">**</ept> Before you register a Power BI app you need an <bpt id="p2">[</bpt>Azure Active Directory tenant and an organizational user<ept id="p2">](powerbi-developer-create-an-azure-active-directory-tenant.md)</ept>, and a <bpt id="p3">[</bpt>Power BI service account<ept id="p3">](powerbi-developer-sign-up-for-power-bi-service.md)</ept>.

There are two ways to register your client app: with the Power BI App Registration Tool or on Azure Management Portal. The Power BI App Registration Tool is the easiest option since there are just a few fields to fill in. If you want to make changes to you app, this can be done through the Azure Management Portal.

### 本文內容

- [Register a client app with Power BI App Registration Tool](#clientTool)
- [Register a client app with Azure Management Portal](#client)
- [How to get a client id in Azure Management Portal](#clientID)

<a name="clientTool"></a>
## Register a client app with Power BI App Registration Tool
You need to register your client app in <bpt id="p1">**</bpt>Azure Active Directory<ept id="p1">**</ept> to establish an identity for your application and specify permissions to Power BI REST resources. When you register a client app, such as a console app, you receive a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept>.  The <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> is used by the application to identify themselves to the users that they are requesting permissions from.
Here's how to register your client app with the Power BI App Registration Tool:

1.  Go to dev.powerbi.com/apps.
2.  In the Power BI App Registration Tool, follow these four steps:

<bpt id="p1">**</bpt>Step 1<ept id="p1">**</ept> - Choose <bpt id="p2">**</bpt>Login in<ept id="p2">**</ept> to login to your Azure AD account. You will see your name in the Welcome line.

<bpt id="p1">**</bpt>Step 2<ept id="p1">**</ept> – Enter information about your app.

  * <bpt id="p1">**</bpt>App Name<ept id="p1">**</ept>: The name of your app.
  * <bpt id="p1">**</bpt>App Type<ept id="p1">**</ept>: Choose Native app.
  * <bpt id="p1">**</bpt>Redirect URI<ept id="p1">**</ept>: For a native client app, a redirect uri gives AAD more details on the specific application that it will authenticate. Any valid Uri will work such as https://login.live.com/oauth20_desktop.srf.

<bpt id="p1">**</bpt>Step 3<ept id="p1">**</ept> – Choose APIs to access. For more information about Power BI access permissions, see <bpt id="p1">[</bpt>Power BI Permissions<ept id="p1">](powerbi-developer-power-bi-permissions.md)</ept>.

![](media/powerbi-developer-register-a-client-app/register-app-tool-step-3.png)

<bpt id="p1">**</bpt>Step 4<ept id="p1">**</ept> - To register your app, click <bpt id="p2">**</bpt>Register App<ept id="p2">**</ept>. After the app is registered in Azure AD, you will get a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept>. Make sure you copy the Client ID. You can get the Client ID later in the <bpt id="p1">**</bpt>Azure Management Portal<ept id="p1">**</ept>. See <bpt id="p1">[</bpt>How to get a client id in Azure Management Portal<ept id="p1">](#clientID)</ept>.

You can now use your Client ID for your app. The next section shows how to register a client app with Azure Management Portal.

<a name="client"></a>
## Register a client app with Azure Management Portal
You need to register your client app in <bpt id="p1">**</bpt>Azure Active Directory<ept id="p1">**</ept> to establish an identity for your application and specify permissions to Power BI REST resources. When you register a client app, such as a console app, you receive a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept>.  The <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> is used by the application to identify themselves to the users that they are requesting permissions from.

To learn how to authenticate a client app using an Azure AD <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept>, see <bpt id="p2">[</bpt>Authenticate a client app<ept id="p2">](powerbi-developer-authenticate-a-client-app.md)</ept>.

### Register a client app

Here's how to register a client app:
1. Accept the <bpt id="p1">[</bpt>Microsoft Power BI API Terms<ept id="p1">](https://powerbi.microsoft.com/api-terms)</ept>.
2. Sign into your Microsoft Azure subscription at https://manage.windowsazure.com.
3. In the left service panel, choose <bpt id="p1">**</bpt>ACTIVE DIRECTORY<ept id="p1">**</ept>.
4. Click the active directory that you belong to.

  ![](media/powerbi-developer-register-a-client-app/register-app-ad.png)

5. Click <bpt id="p1">**</bpt>APPLICATIONS<ept id="p1">**</ept>.

    ![](media/powerbi-developer-register-a-client-app/register-app-applications.png)

6. Click <bpt id="p1">**</bpt>ADD<ept id="p1">**</ept>.

    ![](media/powerbi-developer-register-a-client-app/register-app-add.png)

7. In <bpt id="p1">**</bpt>Tell us about your application<ept id="p1">**</ept>, enter a <bpt id="p2">**</bpt>NAME<ept id="p2">**</ept>, and choose <bpt id="p3">**</bpt>NATIVE CLIENT APPLICATION<ept id="p3">**</ept> for the type, and click <bpt id="p4">**</bpt>Next<ept id="p4">**</ept> icon..

    ![](media/powerbi-developer-register-a-client-app/register-app-client-app.png)

8. In <bpt id="p1">**</bpt>Application information<ept id="p1">**</ept>, enter a <bpt id="p2">**</bpt>REDIRECT URI<ept id="p2">**</ept>. For a client app, a redirect uri gives AAD more details on the specific application that it will authenticate. For a client app, you can use any valid Uri such as https://login.live.com/oauth20_desktop.srf.

9.  Click the <bpt id="p1">**</bpt>Complete<ept id="p1">**</ept> icon.
10. In the application page, choose <bpt id="p1">**</bpt>CONFIGURE<ept id="p1">**</ept>. You will see your <bpt id="p1">**</bpt>CLIENT ID<ept id="p1">**</ept>.
11. In the <bpt id="p1">**</bpt>CONFIGURATION<ept id="p1">**</ept> page, under permissions to other applications, click <bpt id="p2">**</bpt>Add Application<ept id="p2">**</ept>.

    ![](media/powerbi-developer-register-a-client-app/register-app-add-application.png)

12. In <bpt id="p1">**</bpt>Permissions to other applications<ept id="p1">**</ept>, choose <bpt id="p2">**</bpt>Power BI Service<ept id="p2">**</ept>.

    ![](media/powerbi-developer-register-a-client-app/register-app-permissions-to-other-applications.png)

      <bpt id="p1">**</bpt>Important<ept id="p1">**</ept> If you do not see <bpt id="p2">**</bpt>Power BI Service<ept id="p2">**</ept> in the <bpt id="p3">**</bpt>Permissions to other applications<ept id="p3">**</ept> list, you need to sign up for the <bpt id="p4">[</bpt>Power BI Service<ept id="p4">](https://www.powerbi.com/)</ept>. To sign up for the Power BI Service, you need at least one organizational user in your Azure Active Directory (AAD) tenant. If you do not have an Azure Active Directory (AAD) tenant, see <bpt id="p1">[</bpt>Create an Azure Active Directory tenant<ept id="p1">](powerbi-developer-create-an-azure-active-directory-tenant.md)</ept> to create an Azure AD tenant and an organizational user in your Azure AD tenant.

13. Click <bpt id="p1">**</bpt>Complete<ept id="p1">**</ept> icon.
14. In the <bpt id="p1">**</bpt>permissions to other applications<ept id="p1">**</ept> group, choose all <bpt id="p2">**</bpt>Delegated Permissions<ept id="p2">**</ept>, and chooses one or more permissions. For more information about Power BI permissions, see <bpt id="p1">[</bpt>Power BI Permissions<ept id="p1">](powerbi-developer-power-bi-permissions.md)</ept>.

    ![](media/powerbi-developer-register-a-client-app/register-app-delegated-permissions.png)

15. 按一下 **[儲存]**。

<a name="clientID"></a>
## How to get a client app id
When you register a client app, such as a console app, you receive a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept>.  The <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> is used by the application to identify themselves to the users that they are requesting permissions from.

Here's how to get a client id:

1. Sign into your Microsoft Azure subscription at https://manage.windowsazure.com.
2. In the left service panel, choose <bpt id="p1">**</bpt>ACTIVE DIRECTORY<ept id="p1">**</ept>.
3. Click the active directory that you belong to.
4. Click <bpt id="p1">**</bpt>APPLICATIONS<ept id="p1">**</ept>.
5. Choose an application.
6. In the application page, choose <bpt id="p1">**</bpt>CONFIGURE<ept id="p1">**</ept>.
7. In the <bpt id="p1">**</bpt>CONFIGURE<ept id="p1">**</ept> page, copy the <bpt id="p2">**</bpt>CLIENT ID<ept id="p2">**</ept>.

    ![](media/powerbi-developer-register-a-client-app/register-app-clientid.png)

## 請參閱

[Power BI permissions](powerbi-developer-power-bi-permissions.md)  
[Azure Active Directory tenant and an organizational user](powerbi-developer-create-an-azure-active-directory-tenant.md)  
[Power BI service account](powerbi-developer-sign-up-for-power-bi-service.md)  
[Authenticate a client app](powerbi-developer-authenticate-a-client-app.md)  
[Overview of Power BI REST API](powerbi-developer-overview-of-power-bi-rest-api.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)