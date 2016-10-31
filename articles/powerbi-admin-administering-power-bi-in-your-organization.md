<properties
   pageTitle="管理組織中的 Power BI"
   description="管理組織中的 Power BI"
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
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/16/2016"
   ms.author="asaxton"/>

# 管理組織中的 Power BI

Microsoft Power BI 可讓使用者將資料視覺化、 共用探索及共同作業以直覺化的新方式。 若要深入了解，請參閱 [開始使用 Power BI](powerbi-service-get-started.md)。

Power BI 的管理可能會發生在多個位置。 以下是兩個常見的位置。

> [AZURE.NOTE] 您的帳戶必須標示為 **全域管理員**, 、 Office 365 或 Azure Active Directory，才能存取 Power BI 系統管理員入口網站內。

- [Power BI 系統管理員入口網站](https://app.powerbi.com/admin-portal)
- [Office 365 系統管理中心](https://portal.office.com/adminportal/home)

## 什麼是在這篇文章

**註冊 Power BI**

- [如何使用者註冊 Power BI？](#how-do-users-sign-up-for-power-bi)

- [如何在我的組織中的個別使用者註冊？](#how-do-individual-users-in-my-organization-sign-up)

- [如何防止使用者加入我現有的 Office 365 租用戶？](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)

- [我要如何讓使用者加入我現有的 Office 365 租用戶？](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)

- [如何確認上是否有在區塊中的租用戶？](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)

- [如何防止我現有的使用者開始使用 Power BI？](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)

- [我要如何讓我現有的使用者註冊 Power BI？](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Power BI 的系統管理**

- [這將會如何變更我今天我組織中管理的使用者身分識別的方式？](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)

- [我們要如何管理 Power BI？](#how-do-we-manage-power-bi)

- [什麼是管理租用戶的程序由 Microsoft 建立的 [我的使用者？](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
   
- [如果我有多個網域時，會將使用者加入 Office 365 租用戶可以控制？](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)

- [如何移除已註冊的使用者的 Power BI？](#how-do-i-remove-power-bi-for-users-that-already-signed-up)

- [如何知道當新的使用者已加入我的租用戶？](#how-do-i-know-when-new-users-have-joined-my-tenant)

- [你有沒有任何其他我應該做好嗎？](#are-there-any-additional-things-i-should-be-prepared-for)

- [沒有此嗎？ 我必須支付這些授權？](#is-this-free-will-i-be-charged-for-these-licenses)

- [我的 Power BI 租用戶位於何處？](#where-is-my-power-bi-tenant-located)

**在 Power BI 中的安全性**

- [Power BI 是否符合國家、 區域和業界特定的相容性需求？](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)

- [在 Power BI 中如何運作的安全性？](#how-does-security-work-in-power-bi?)

## 註冊 Power BI

### 如何使用者註冊 Power BI？

您可以透過 Power bi 註冊 [Power BI 網站](https://powerbi.microsoft.com)。 您也可以註冊透過 Office 365 系統管理中心購買服務 」 頁面。 當系統管理員可註冊 Power bi 時，他們可以指派使用者授權都應該能夠存取的使用者。

此外，您組織中的個別使用者可能可以透過 Power bi 註冊 [Power BI 網站](https://powerbi.microsoft.com)。 當您的組織中的使用者註冊 Power bi 時，該使用者就會自動指派 Power BI 授權。 [進一步了解](powerbi-service-self-service-signup-for-power-bi.md)

### 如何在我的組織中的個別使用者註冊？

有三種案例可能適用於您組織中使用者︰

案例 1︰ 您的組織已經有現有的 Office 365 環境和使用者登入 Power BI 已經有 Office 365 帳戶。
在此案例中，如果使用者已經擁有工作或學校帳戶 (例如，contoso.com) 的租用戶中但並不會但有 Power BI、 Microsoft 只會啟用該帳戶，規劃以及如何使用 Power BI 服務，會自動通知使用者。

案例 2︰ 您的組織有現有的 Office 365 環境，並註冊 Power BI 使用者沒有 Office 365 帳戶。
在此案例中，使用者會在貴組織的網域 (例如，contoso.com) 中有電子郵件地址，但還沒有 Office 365 帳戶。 在此情況下，使用者可以註冊 Power bi，並自動將指定的帳戶。 這可讓使用者存取 Power BI 服務。 比方說，如果名為 Nancy 員工登入，以使用她的工作電子郵件地址 (例如，Nancy@contoso.com)，Microsoft 會自動加入 Nancy Contoso Office 365 環境中的使用者身分，並為該帳戶啟用 Power BI。

案例 3︰ 組織沒有 Office 365 環境連接到您的電子郵件網域。
沒有您的組織需要採取來充分利用 Power BI 系統管理動作。 使用者將會新增至新，僅限雲端的使用者目錄中，而且您必須選擇接管，成為租用戶系統管理員與管理方式的選項。

> [AZURE.IMPORTANT] 如果您的組織有多個電子郵件網域，而且您想要在相同的租用戶中所有電子郵件位址擴充功能，加入電子郵件地址的所有網域的 Azure Active Directory 租用戶前的任何使用者登入。 沒有租用戶之間移動使用者之後已建立, 自動化的機制。 如需此程序的詳細資訊，請參閱 [如果我有多個網域，我可以控制使用者加入至 Office 365 租用戶？](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) 在本文稍後和 [新增網域至 Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) 線上。

### 如何防止使用者加入我現有的 Office 365 租用戶？

幾個的步驟，您可以採取身為管理員，以防止使用者加入現有的 Office 365 租用戶。 如果您封鎖這，使用者嘗試登入，將會失敗，並指示它們連絡組織的管理員。 您不需要重複此程序，如果您已停用自動授權發佈 (例如教育學生、 教職人員和人員的 Office 365)。

這些步驟需要使用 Windows PowerShell。 若要開始使用 Windows PowerShell，請參閱 [PowerShell 入門指南](http://go.microsoft.com/fwlink/p/?LinkID=286814)。

若要執行下列步驟，您必須安裝最新的 64 位元版本的 [Azure Active Directory 的 Windows PowerShell 模組](http://go.microsoft.com/fwlink/p/?LinkID=236297)。

您選取的連結之後，請選取 **執行** 執行安裝程式套件。


            **停用自動租用戶聯結**︰ 若要防止新使用者加入受管理的租用戶使用此 Windows PowerShell 命令︰

- 若要停用自動租用戶加入新使用者︰

    Set-msolcompanysettings-AllowEmailVerifiedUsers $false

- 若要啟用自動的租用戶加入新使用者︰

    Set-msolcompanysettings-AllowEmailVerifiedUsers $true

> [AZURE.NOTE] 此封鎖可防止註冊 Power BI 組織中的新使用者。 註冊 Power BI 之前停用組織的新註冊的使用者仍然會保留使用者的授權。 請參閱 [如何移除授權？] 區段，如需如何移除有先前已註冊的服務的使用者存取 Power BI 的指示。

### 我要如何讓使用者加入我現有的 Office 365 租用戶？

若要允許使用者加入您的租用戶，請執行相反的命令，以上問題中所述︰

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### 如何確認上是否有在區塊中的租用戶？

使用下列 PowerShell 指令碼︰

    Get-MsolCompanyInformation | fl allow*

### 如何防止我現有的使用者開始使用 Power BI？

幾個的步驟，您可以採取身為管理員，以防止使用者註冊 Power BI。 如果您封鎖這，使用者嘗試登入，將會失敗，並指示它們連絡組織的管理員。 您不需要重複此程序，如果您已停用自動授權發佈 (例如教育學生、 教職人員和人員的 Office 365)。 [進一步了解](powerbi-admin-powerbi-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-Azure-Active-Directory)

> [AZURE.NOTE] AllowAdHocSubscriptions 旗標用來控制數個使用者功能，在您組織中，包括使用者登入 Azure 版權管理服務的能力。 變更這個旗標會影響所有這些功能。

### 我要如何讓我現有的使用者註冊 Power BI？

若要讓您註冊 Power BI 的現有使用者，執行命令列上的一個問題，但傳遞而不是 false，則為 true。 [進一步了解](powerbi-admin-powerbi-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-Azure-Active-Directory)

## Power BI 的系統管理

### 這將會如何變更我今天我組織中管理的使用者身分識別的方式？

如果您的組織已經有現有的 Office 365 環境，而且您組織中的所有使用者都擁有 Office 365 帳戶，不會變更身分識別管理。

如果您的組織已經有現有的 Office 365 環境，但並非所有使用者在組織中的都擁有 Office 365 帳戶，我們將租用戶中建立使用者並指派使用者的公司或學校，電子郵件地址為基礎的授權。 這表示您在特定時間所管理的使用者數目會成長為組織中的使用者註冊服務。

如果您要管理目錄在內部，並使用 Active Directory 同盟服務 (AD FS) 時，Microsoft 不會將使用者加入至您的租用戶，並嘗試加入您的租用戶的使用者會收到訊息，以連絡組織的管理員。

如果您的組織沒有 Office 365 環境連接到您的電子郵件網域，則會不會變更您要如何管理身分識別。 使用者將會新增至新，僅限雲端的使用者目錄中，而且您必須選擇接管，成為租用戶系統管理員與管理方式的選項。

### 我們要如何管理 Power BI？

Power BI 提供系統管理員入口網站，可讓您檢視使用量統計資料，可連結到 Office 365 系統管理中心來管理使用者和群組，以及控制租用戶各種設定的能力。 

> [AZURE.NOTE] 您的帳戶必須標示為 **全域管理員**, 、 Office 365 或 Azure Active Directory，才能存取 Power BI 系統管理員入口網站內。

如需詳細資訊，請參閱 [Power BI 系統管理員入口網站](powerbi-admin-portal.md)。

### 什麼是管理租用戶的程序由 Microsoft 建立的 [我的使用者？

如果租用戶由 Microsoft 建立的您可以宣告並遵循下列步驟來管理該租用戶︰

1. 註冊 Power BI，使用符合您想要管理的租用戶網域的電子郵件地址網域加入租用戶。 例如，如果 Microsoft 建立 contoso.com 租用戶，您需要加入租用戶結尾 @contoso.com 電子郵件地址。

2. 管理員可以控制宣告驗證網域擁有權︰ 一旦租用戶中，您可以將自己升級 *全域管理員* 藉由驗證網域擁有權的角色。 若要這樣做，請依照下列步驟執行：

    1. 移至 [https://portal.office.com](https://portal.office.com)。

    2. 在左上角中選取應用程式啟動器圖示，然後選擇 [ **管理員**。

    3. 閱讀 **成為系統管理員** 頁面，然後選擇 **是，我想要管理**。

    > [AZURE.NOTE] 如果沒有出現此選項，已經有 Office 365 系統管理員中的位置。
    
### 如果我有多個網域時，會將使用者加入 Office 365 租用戶可以控制？

如果您執行任何動作，將會建立租用戶，針對每個使用者的電子郵件網域和子網域。

如果您想要在相同的租用，不論其電子郵件地址擴充功能的所有使用者︰

- 建立目標租用戶工作量，或使用現有的租用戶，並新增所有現有網域與您想要彙總該租用戶內的子網域。 然後當他們註冊電子郵件地址那些網域與子網域中的所有使用者會自動都加入目標租用戶。

> [AZURE.IMPORTANT] 沒有任何支援的自動化的機制租用戶之間移動使用者，一旦已建立。 若要深入了解將網域加入至單一的 Office 365 租用戶，請參閱 [將您的使用者和網域加入至 Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。

### 如何移除已註冊的使用者的 Power BI？

如果使用者已註冊的 Power BI，但您不想再它們存取 Power bi，您可以移除該使用者的 Power BI 授權。

1. 瀏覽至 Office 365 系統管理中心。

2. 在左側的導覽列中，選取 **使用者** > **作用中使用者**。

3. 尋找您想要移除的授權的使用者，然後選取其名稱 > **編輯**。

4. 在 [使用者詳細資料] 頁面上，選取 [ **授權** 左側的導覽列中。

5. 取消核取 **（免費） 的 Power BI**, ，或 **Power BI Pro**, ，取決於套用哪些授權其帳戶。

6. 選取 **儲存**。

> [AZURE.NOTE] 您可以執行到使用者，以及大量授權管理。 若要這樣做，請選取多個使用者，選取 **編輯**。

### 如何知道當新的使用者已加入我的租用戶？

此程式的一部分加入您的租用戶的使用者會指派唯一的授權，您可以篩選在您管理儀表板中的作用中使用者] 窗格內。

若要在 Office 365 系統管理中心建立這個新的檢視，請移至 **使用者** > **作用中使用者**, ，然後在 **選取檢視** 功能表中，選取 **新檢視**。 將新的檢視，然後在 **指派的授權**, ，請選取 **（免費） 的 Power BI** 或 **Power BI Pro**。 您只能有一個每一次檢視選取的授權。 如果兩者都 **（免費） 的 Power BI** 和 **Power BI Pro** 組織中的授權，您必須建立兩個檢視。 一旦建立新的檢視，您會看到所有使用者在您的租用戶中註冊此程式中。

### 你有沒有任何其他我應該做好嗎？

您可能會遇到增加密碼重設要求。 此程序的詳細資訊，請參閱 [重設使用者密碼](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)。

您可以從您的租用戶透過標準的程序中的 Office 365 系統管理中心移除使用者。 不過，如果使用者仍然可以從您的組織使用中的電子郵件地址，他們將能夠重新加入，除非您封鎖所有使用者加入。

### 沒有此嗎？ 我必須支付這些授權？

 **（免費） 的 Power BI** 授權是免費的 Power BI 版本。 如果您有興趣的其他功能，看看 [Power BI Pro 版本](powerbi-power-bi-pro-content-what-is-it.md)。

### 我的 Power BI 租用戶位於何處？

若要了解如何尋找您的 Power BI 租用戶所在的位置，也稱為資料區域中，請參閱 [我的 Power BI 租用戶位於何處？](powerbi-admin-where-is-my-tenant-located.md)

## 在 Power BI 中的安全性

### Power BI 是否符合國家、 區域和業界特定的相容性需求？

若要深入了解 Power BI 相容性，請參閱 [Microsoft 信任中心](http://go.microsoft.com/fwlink/?LinkId=785324)。

### 在 Power BI 中如何運作的安全性？

Power BI 是建置在 Office 365，接著是根據 Azure 服務，例如 Azure Active Directory 的基礎。 如需 Power BI 架構的概觀，請參閱 [Power BI 安全性](powerbi-admin-power-bi-security.md)。 

## 請參閱

[Power BI 系統管理員入口網站](powerbi-admin-portal.md)  
[自助式註冊 Power bi](powerbi-service-self-service-signup-for-power-bi.md)  
[Power BI 組織中的 （免費）](powerbi-admin-powerbi-free-in-your-organization.md)  
[採購 Power BI Pro](powerbi-admin-purchasing-power-bi-pro.md)  
[Office 365 使用者帳戶管理](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Office 365 群組管理](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  

            [管理您的群組，在 Power BI 和 Office 365](powerbi-service-manage-your-group-in-power-bi-and-office-365.md) 更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)