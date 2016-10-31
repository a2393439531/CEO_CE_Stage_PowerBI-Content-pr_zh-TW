<properties
pageTitle="深入的內部資料閘道"
description="這篇文章探討深入的內部部署閘道。 這會查看服務的運作方式與 Azure Active Directory 和本機 Active Directory 使用 Analysis Services 時"
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
# 深入的內部資料閘道

您組織中的使用者可以看到您的內部資料，但內部資料閘道器使用者可以連線到內部部署資料來源之前，必須安裝和設定。 閘道可以讓幕後通訊定域機組中的使用者從內部部署資料來源，再回到定域機組快速且安全。

安裝和設定閘道通常是由系統管理員。 它可能需要特殊知識的內部部署伺服器，並在某些情況下可能需要伺服器系統管理員權限。

這篇文章並未提供如何安裝和設定閘道的逐步指引。 為此，請務必查看 [內部資料閘道](powerbi-gateway-onprem.md)。 本文旨在提供您深入了解閘道的運作方式。 我們將也進入有詳盡的使用者名稱和 Azure Active Directory 和 Analysis Services 中的安全性和雲端服務如何使用電子郵件地址的使用者登入、 閘道和 Active Directory 來安全地連接及查詢您的內部資料。

<!-- Shared Requirements Include -->
[AZURE.INCLUDE [gateway-onprem-requirements-include](../includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[AZURE.INCLUDE [gateway-onprem-datasources-include](../includes/gateway-onprem-datasources-include.md)]

## 登入帳戶

使用者將會使用工作或學校帳戶。 這是您的組織帳戶。 如果您註冊 Office 365 供應項目，而且未提供實際的公司電子郵件，看起來像 nancy@contoso.onmicrosoft.com。 您的帳戶，在雲端服務中，會儲存在 Azure Active Directory (AAD) 租用戶中。 在大部分情況下，AAD 帳戶的 UPN 會比對電子郵件地址。

## 內部資料來源的驗證

預存的認證將用來從 Analysis Services 以外的閘道連線到內部部署資料來源。 不論個別使用者，閘道會使用預存的認證來連線。 

## 驗證即時 Analysis Services 資料來源 

每次使用者與 Analysis Services 互動的有效使用者名稱會傳遞到閘道，然後拖曳至您的內部部署 Analysis Services 伺服器。 使用者主要名稱 (UPN)，通常您登入，定域機組電子郵件地址是我們會將傳遞至 Analysis Services 做為有效的使用者。 連接屬性 EffectiveUserName 傳遞 UPN。 此電子郵件地址應該符合本機 Active Directory 網域中定義的 UPN。 UPN 是 Active Directory 帳戶的屬性。 然後該 Windows 帳戶必須已經存在於 Analysis Services 角色具有到伺服器的存取權。 登入不會成功，如果沒有找到符合的 Active Directory 中。

Analysis Services 也可以提供根據此帳戶進行篩選。 篩選可能會發生角色型安全性或資料列層級安全性。

## 以角色為基礎的安全性

模型會提供根據使用者角色的安全性。 角色定義在 SQL Server Data Tools – Business Intelligence (SSDT-BI)，或是在部署模型時，使用 SQL Server Management Studio (SSMS) 之後撰寫期間針對特定模型專案。 角色不包含 Windows 使用者名稱或 Windows 群組成員。 角色會定義要查詢或模型上執行動作的使用者具有權限。 大部分的使用者將屬於讀取權限的角色。 其他角色的用意在於，具有處理項目之權限的系統管理員，管理資料庫函式，以及管理其他角色。

## 資料列層級安全性

Analysis Services 資料列層級安全性的特定資料列層級安全性。 模型可提供動態、 資料列層級安全性。 不同於具有使用者隸屬於至少一個角色，不需要任何表格式模型動態安全性。 在高階、 動態安全性使用者的讀取權限定義特定資料表中特定的資料列向右的資料。 類似角色，動態資料列層級安全性依賴使用者的 Windows 使用者名稱。

查詢和檢視表的模型資料的使用者的能力決定先由其 Windows 使用者帳戶所隸屬的角色和第二，動態資料列層級安全性，如果設定。

實作的角色和模型中的動態資料列層級安全性已超出本文的範圍。  您可以進一步在 [角色 （SSAS 表格式）](https://msdn.microsoft.com/library/hh213165.aspx) 和 [安全性角色 (Analysis Services-多維度資料)](https://msdn.microsoft.com/library/ms174840.aspx) MSDN 上。 如表格式模型安全性最深入的瞭解，請下載並閱讀安全 [表格式 BI 語意模型 （英文） 白皮書](https://msdn.microsoft.com/library/jj127437.aspx)。 

## Azure Active Directory 呢？

Microsoft 雲端服務會使用 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) 來驗證使用者的處理。 Azure Active Directory 是租用戶包含使用者名稱和安全性的群組。 一般而言，使用者登入電子郵件地址是帳戶的 UPN 相同。

什麼是我的本機 Active Directory 的角色？

若要判斷是否連接到它的使用者讀取資料的權限的角色所屬的 Analysis services，伺服器必須轉換到閘道，並在 Analysis Services 伺服器上，從 AAD 傳遞有效的使用者名稱。 Analysis Services 伺服器會將有效的使用者名稱傳遞至 Windows Active Directory 網域控制站 (DC)。 然後 Active Directory DC 驗證的有效使用者名稱是有效的 UPN，本機帳戶，並且該使用者的 Windows 使用者名稱傳回 Analysis Services 伺服器。

EffectiveUserName 不能在非網域聯結 Analysis Services 伺服器上。 Analysis Services 伺服器必須加入網域，以避免任何登入錯誤。

## 如何知道我 UPN 為何？

您可能不知道您 UPN 為何，以及您可能不是網域系統管理員。 您可以使用下列命令從您的工作站，以查明您帳戶的 UPN。

    whoami /upn

結果看起來類似電子郵件地址，但這是用來在本機網域帳戶的 UPN。 如果您使用即時連接的 Analysis Services 資料來源，這必須符合從閘道傳遞給 EffectiveUserName 什麼。

## 對應 [Analysis Services 資料來源的使用者名稱

Power BI 可讓您對應 Analysis Services 資料來源的使用者名稱。 您可以設定規則，將對應的使用者名稱登入 Power BI Analysis Services 連接傳遞的 EffectiveUserName 的名稱。 使用者名稱對應] 功能是解決當您在 AAD 中的使用者名稱不符合您的本機 Active Directory 中的 UPN 的好方法。 比方說，如果 nancy@contoso.onmicrsoft.com 電子郵件地址，您可以將它對應至 nancy@contoso.com，，這個值會傳遞至閘道。 您可以進一步了解如何 [將使用者名稱對應](powerbi-gateway-enterprise-manage-ssas.md#map-user-names)。

## 與 Azure Active Directory 同步處理內部部署 Active Directory

您會想要比對 Azure Active Directory，如果您打算使用 Analysis Services 即時連接您本機 Active Directory 帳戶。 為符合帳戶之間的 UPN。

雲端服務只知道 Azure Active Directory 內的帳戶。 如果您新增至您的本機 Active Directory 帳戶並不重要在 AAD 中不存在，如果無法使用。 有不同的方式可以比對與 Azure Active Directory 您本機 Active Directory 帳戶。

1.  您可以手動新增帳戶至 Azure Active Directory。

    在 Azure 網站或 Office 365 系統管理入口網站中，您可以建立帳戶，帳戶名稱必須符合本機 Active Directory 帳戶的 UPN。

2.  您可以使用 [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) 工具來同步處理至 Azure Active Directory 租用戶的本機帳戶。

    Azure AD Connect 工具提供目錄和密碼同步處理的選項。 如果您不是租用戶管理員或本機網域系統管理員，您必須連絡您的 IT 管理員，來開始這項設定。

3.  您可以設定 Active Directory Federation Services (ADFS)。

    您可以將 ADFS 伺服器關聯至 AAD 租用戶與 [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) 工具。 ADFS 進行目錄同步作業使用上面所討論，但允許單一登入 (SSO) 體驗。 例如，如果您是在您的公司網路，當您的雲端服務，並移至 [登入，您可能不提示您輸入使用者名稱或密碼。 您必須與您的 IT 管理員討論，如果這是適用於您的組織。

使用 Azure AD Connect 可確保 UPN 會比對 AAD 與本機 Active Directory 之間。

> [AZURE.NOTE] 同步處理帳戶與 Azure AD Connect 工具會建立 AAD 租用戶內的新帳戶。

## 現在，這時候就需要在閘道

閘道可做為雲端和內部部署伺服器之間的橋樑。 雲端和閘道間的資料傳輸透過安全 [Azure 服務匯流排](https://azure.microsoft.com/documentation/services/service-bus/)。 服務匯流排閘道上建立定域機組和輸出連線透過內部部署伺服器之間的安全通道。  沒有您需要在內部防火牆開啟任何輸入的連線。

如果您有 Analysis Services 資料來源，您必須加入相同樹系/網域做為 Analysis Services 伺服器的電腦上安裝閘道。

閘道越接近到伺服器時，此連接將會越快。 您可以取得閘道做為資料來源相同的伺服器上，如果，最好避免閘道與伺服器之間的網路延遲。

## 有可能發生錯誤

有時安裝閘道器就會失敗。 或者，可能是閘道似乎安裝好了，但服務是仍然無法使用它。 在許多情況下，是一些簡單項目，例如閘道用來登入資料來源認證的密碼。

在其他情況下，可能會發生問題的使用者登入的電子郵件地址或 Analysis Services 無法有效的使用者名稱解析的型別。 如果您有多個網域具有信任關係，而且您的閘道是其中一種和 Analysis Services 中，這有時可能會造成一些問題。

而非進入這裡閘道問題的疑難排解，我們將一系列的疑難排解步驟到另一篇文章。 [疑難排解內部部署資料閘道](powerbi-gateway-onprem-tshoot.md)。 順利的話，您將不會有任何問題。 但如果您這樣做，了解此運作方式以及疑難排解文件的所有應該如何協助。

<!-- Account and Port information -->
[AZURE.INCLUDE [gateway-onprem-accounts-ports-more](../includes/gateway-onprem-accounts-ports-more.md)]

## 請參閱

[疑難排解內部部署資料閘道](powerbi-gateway-onprem-tshoot.md)  
[Azure 服務匯流排](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)