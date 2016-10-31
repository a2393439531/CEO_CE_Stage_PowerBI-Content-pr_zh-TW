<properties
   pageTitle="建立 Azure Active Directory 租用戶"
   description="建立 Azure Active Directory 租用戶"
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

# 建立 Azure Active Directory 租用戶

使用 Power BI REST API，您可以在任何平台上支援呼叫 REST 作業建立 Power BI 應用程式。 不過，開始建立 Power BI 應用程式之前，您需要 **Azure Active Directory**, ，組織的使用者，和 [Power BI 服務帳戶](powerbi-admin-free-with-custom-azure-directory.md)。

## 建立 Azure Active Directory 租用戶的 Power BI 應用程式

Power BI 應用程式整合在一起 **Azure Active Directory** (Azure AD) 以提供安全登入和授權您的應用程式。 若要使用 Azure AD 整合 Power BI 應用程式，您註冊詳細資料與 Azure AD 的應用程式的相關使用 Azure 管理入口網站。


            **重要** 註冊 **Power BI 服務**, ， **Azure Active Directory** 必須至少一個組織使用者。 使用您的組織使用者 [註冊 Power BI 服務](powerbi-admin-free-with-custom-azure-directory.md)。

<a name="setup"></a>
### 建立 Azure Active Directory 租用戶
開始建立 Power BI 應用程式之前，您需要 **Azure Active Directory** 和組織使用者。 以下是如何設定 **Azure Active Directory**:

 1. 巡覽至 https://manage.windowsazure.com，並具有 Azure 訂用帳戶的帳戶登入。
 2. 按一下 [ **ACTIVE DIRECTORY** 的左窗格中的 [管理] 圖示。

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/active-directory.png)

 3. 按一下 [ **新增** 在頁面底部的按鈕。
 4. 選擇 **應用程式服務** > **ACTIVE DIRECTORY** > **目錄** > **自訂建立**

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/new-ad.png)

 5. 在 **加入目錄** 頁面上，輸入名稱和網域名稱。 國家或地區，選擇美國或國家/地區所 Power BI 使用。

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-directory.png)

 6. 選擇 [確定] 圖示。 建立 Azure Active Directory。

<a name="newuser"></a>
### 將使用者加入您的 Azure Active Directory 租用戶
您需要從您的 Azure AD 註冊的組織使用者 **Power BI 服務**。 一旦您登入 **Power BI 服務** 第一次，您會看到 **Power BI 服務** 加入至您的 Azure AD 可讓您使用正確的權限建立 Power BI 應用程式。 以下是如何將使用者新增至您的 Azure Active Directory:

1. 巡覽至 https://manage.windowsazure.com，並具有 Azure 訂用帳戶的帳戶登入。
2. 按一下 [ **ACTIVE DIRECTORY** 的左窗格中的 [管理] 圖示。
3. 在您 **Azure Active Directory**, ，按一下 [ **使用者**。

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-ad-user.png)
4. 在頁面底部，按一下 [ **新增使用者**。 使用者帳戶用來註冊 Power BI 應用程式。
5. 在 **告訴我們使用者本頁**:

    1. 如 **使用者類型**, ，選擇 [ **貴組織中的新使用者**。
    2. 輸入您 **使用者名稱**。
    3. 按一下 [下一步] ****。

        ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-ad-user2.png)

6. 在 **使用者設定檔** 頁面上，輸入您 **顯示名稱**。 顯示名稱是必要的欄位。

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/user-profile.png)

7. 按一下 [下一步] ****。 如 **角色**, ，您可以使用 **使用者**。
8. 按一下 [ **建立** 建立暫時密碼。 在第一次登入時必須變更暫時密碼是指派給新使用者。
9. 在 **取得暫時密碼** 頁面複製暫時密碼，然後按一下 **完成** 圖示。 使用的暫時密碼當您第一次登入您的 AAD。
10. 按一下之後 **完成** 圖示、 新建立 Azure AD 使用者。

一旦 **Azure Active Directory** 租用戶和組織使用者，您 [註冊 Power BI](powerbi-admin-free-with-custom-azure-directory.md)。


            **請注意** 當您註冊 Power BI 服務 」 時，使用您的組織使用者。 一旦您登入 **Power BI 服務** 第一次，您會看到 **Power BI 服務** 加入至您的 Azure AD。

## 另請參閱

[什麼是 Azure AD 目錄？](https://msdn.microsoft.com/library/azure/jj573650.aspx)  
[如何取得 Azure Active Directory 租用戶](https://azure.microsoft.com/documentation/articles/active-directory-howto-tenant/)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)