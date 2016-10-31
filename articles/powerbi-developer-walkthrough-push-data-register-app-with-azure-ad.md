<properties
   pageTitle="使用 Azure AD 註冊應用程式"
   description="逐步解說-將資料發送到儀表板-使用 Azure AD 註冊應用程式"
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

# 步驟 1︰ 使用 Azure AD 註冊應用程式

逐步解說的這篇文章屬於 [資料推送至儀表板](powerbi-developer-walkthrough-push-data.md)。

資料發送到 Power BI 儀表板的第一個步驟是在 Azure AD 中註冊您的應用程式。 您必須先執行此作業，因此您必須 **用戶端識別碼** ，Azure AD 中識別您的應用程式。 不含 **用戶端識別碼**, ，Azure AD 無法驗證您的應用程式。

>
            **請注意**︰ 在 Power bi 註冊應用程式之前，您需要 [註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)。

以下是 Azure AD 中註冊應用程式的步驟。

## 在 Azure AD 中註冊應用程式

1. 請移至 dev.powerbi.com/apps。
2. 按一下 [ **使用現有的帳戶登入**, ，然後登入 Power BI 帳戶。
3. 輸入 **應用程式名稱** 例如 「 範例發送資料應用程式 」。
4. 如 **應用程式類型**, ，選擇 [ **原生應用程式**。
5. 輸入 **重新導向 URL**, ，例如 **https://login.live.com/oauth20_desktop.srf**。 如 **原生用戶端應用程式**, ，重新導向 uri 會提供 **Azure AD** 更多詳細資料，就會進行驗證之特定應用程式。 用戶端應用程式的標準 Uri 是 https://login.live.com/oauth20_desktop.srf。
6. 如 **選擇 Api 來存取**, ，選擇 [ **讀取和寫入所有資料集**。 所有的 Power BI 應用程式權限，請參閱 [Power BI 權限](powerbi-developer-power-bi-permissions.md)。
7. 按一下 [ **註冊應用程式**, ，並儲存 **用戶端識別碼** 產生。 A **用戶端識別碼** 識別 Azure AD 中的應用程式。

以下是如何您 **註冊 Power bi 應用程式** 頁面應該看起來︰

![](media\powerbi-developer-walkthrough-push-data\powerbi-developer-sample-register-app.png)

下一個步驟顯示如何以 [取得驗證存取權杖](powerbi-developer-walkthrough-push-data-get-token.md)。

[下一步 >](powerbi-developer-walkthrough-push-data-get-token.md)

## 請參閱

[註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[取得驗證存取權杖](powerbi-developer-walkthrough-push-data-get-token.md)  
[逐步解說︰ 將資料推送至儀表板](powerbi-developer-walkthrough-push-data.md)  
[註冊用戶端應用程式](powerbi-developer-register-a-client-app.md)  
[Power BI REST API 概觀](powerbi-developer-overview-of-power-bi-rest-api.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
