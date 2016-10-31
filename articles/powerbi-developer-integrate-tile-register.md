<properties
   pageTitle="向 Azure AD 註冊 web 應用程式"
   description="向 Azure AD 註冊 web 應用程式"
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

# 步驟 1︰ 使用 Azure AD 註冊 web 應用程式

## 簡介

在此步驟的 [磚整合應用程式逐步解說](powerbi-developer-integrate-tile.md), ，註冊您的應用程式中 **Azure Active Directory (AD)**。 您必須先執行此作業，因此您必須 **用戶端識別碼** 和 **用戶端密碼** ，Azure AD 中識別您的 web 應用程式。 不含 **用戶端識別碼** 和 **用戶端密碼**, ，Azure AD 無法驗證您的 web 應用程式。 如果您已經下載 [整合並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), ，您使用 **用戶端識別碼** 和 **用戶端密碼** 您註冊之後，若要設定的範例，範例可以向 Azure AD 取得。

![](media\powerbi-developer-integrate-tile\integrate-tile-step1a.png)

>
            **請注意**︰ 您註冊的 web 應用程式之前 **Power BI**, ，您需要 [註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)。

以下是 Azure AD 中註冊的 web 應用程式的步驟。

## 在 Azure AD 中註冊的 web 應用程式

1. 請移至 dev.powerbi.com/apps。
2. 按一下 [ **使用現有的帳戶登入**, ，然後登入 Power BI 帳戶。
3. 輸入 **應用程式名稱**。 此逐步解說中，輸入 **整合並排顯示範例**。
4. 如 **應用程式類型**, ，選擇 [ **伺服器端 Web 應用程式**。
5. 輸入 **重新導向 URL**。 此逐步解說中，Azure AD 的重新導向回到 [預設] 頁面中，因此輸入 http://localhost:13526。 Azure Active Directory (AD) 會重新導向至與此頁面 **授權碼**。 若要了解如何取得 **存取權杖** 存取 **Power BI** 並排使用 **授權碼**, ，請參閱 [取得驗證存取權杖](powerbi-developer-integrate-tile-get-dashboard.md#get-token)。
6. 輸入 **首頁**。 此逐步解說中，輸入 http://localhost:13526 即首頁上的範例。
7. 如 **選擇 Api 來存取**, ，選擇 [ **讀取所有儀表板 （預覽）**。 所有的 Power BI 應用程式權限，請參閱 [應用程式權限](powerbi-developer-power-bi-permissions.md)。
7. 按一下 [ **註冊應用程式**, ，並儲存 **用戶端識別碼** 和 **用戶端密碼** 產生。 A **用戶端識別碼** 和 **用戶端密碼** 識別 Azure AD 中的應用程式。 若要設定 [整合並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app) 使用 **用戶端識別碼** 和 **用戶端密碼** 進行驗證，請參閱 [設定整合的並排顯示範例](powerbi-developer-integrate-tile-register.md#configure-sample)。

以下是如何您 **註冊 Power bi 應用程式** 頁面應該看起來︰

![](media\powerbi-developer-integrate-tile\register-app.png)

既然您已經註冊您的 web 應用程式與 **Azure AD**, ，您可以取得授權存取權杖，從 **Azure AD** 存取 **Power BI** 儀表板和並排顯示。

![](media\powerbi-developer-integrate-tile\integrate-tile-step1b.png)

之後 **用戶端識別碼** 和 **用戶端密碼**, ，您可以設定您的 web 應用程式，例如 [整合並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), ，使其能夠存取 **Power BI** 磚。 下一節將說明如何設定範例。

<a name="configure-sample"/>
## 設定整合的並排顯示範例
如果您已經下載 [整合並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), ，您使用 **用戶端識別碼** 和 **用戶端密碼** 範例可以向 Azure AD 註冊之後取得。 若要設定範例，請變更 **用戶端識別碼** 和 **用戶端密碼** web.config 中。 若要深入了解如何向 Azure AD 驗證，請參閱 [步驟 2︰ 取得 Power BI 儀表板](powerbi-developer-integrate-tile-get-dashboard.md)。

## 下一個步驟

若要整合應用程式磚，您需要取得儀表板中的並排顯示。 在下一個步驟中，您了解如何 [取得 Power BI 儀表板](powerbi-developer-integrate-tile-get-dashboard.md)。 在步驟 3 中，您會了解如何從儀表板取得並排顯示。

[下一步 >](powerbi-developer-integrate-tile-get-dashboard.md)

## 請參閱

[註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[將磚整合到應用程式逐步解說](powerbi-developer-integrate-tile.md)  
[整合的並排顯示範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[設定整合的並排顯示範例](powerbi-developer-integrate-tile-register.md#configure-sample)  
[取得驗證存取權杖](powerbi-developer-integrate-tile-get-dashboard.md#get-token)  
[應用程式權限](powerbi-developer-power-bi-permissions.md)  
[步驟 2︰ 取得 Power BI 儀表板](powerbi-developer-integrate-tile-get-dashboard.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)