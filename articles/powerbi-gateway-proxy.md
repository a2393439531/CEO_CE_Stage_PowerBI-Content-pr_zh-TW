<properties
pageTitle="設定內部部署資料閘道器的 proxy 設定"
description="內部資料閘道的 proxy 設定的相關資訊。"
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
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/01/2016"
ms.author="asaxton"/>
# 設定內部部署資料閘道器的 proxy 設定

您的工作環境可能需要通過 proxy，以存取網際網路。 這可能導致在內部部署資料閘道器連接到服務。

## 您的網路是否使用 proxy？

Superuser.com 上的下列文章討論您可以嘗試判斷是否在網路上有 proxy 的方式。

[如何得知我使用哪些 proxy 伺服器？ (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## 組態檔的位置和預設設定

.NET 組態檔中設定 proxy 資訊。 位置和檔案名稱會隨著您正在使用的閘道而不同。

### 內部資料閘道

有兩個主要的組態檔所涉及的內部資料閘道。

**設定**

第一個是實際設定閘道的組態畫面。 如果您有設定閘道的問題，這是您會想要查看的檔案。

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Windows 服務**

第二個是實際的 windows 服務的互動 Power BI 服務，並且會處理要求。

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

### Power BI 閘道個人

個人閘道可安裝在兩種方式之一。 做為 windows 服務 （管理員） 或使用者模式應用程式。 這是在安裝期間決定。 如此一來，您的組態檔可能在兩個位置視閘道的安裝方式而定。 您會想要查看這兩個位置。

**設定**

第一個是實際設定閘道的組態畫面。 如果您有設定閘道的問題，這是您會想要查看的檔案。

如 *windows 服務*, ，它會。

    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\GWConfig.exe.config
    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

如 *使用者模式應用程式*, ，它會。

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\GWConfig.exe.config
    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

**Windows 服務**

第二個是實際的 windows 服務的互動 Power BI 服務，並且會處理要求。

如 *windows 服務*, ，它會。

    C:\Program Files\Power BI Personal Gateway\1.0\Gateway\diawp.exe.config

如 *使用者模式應用程式*, ，它會。

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Gateway\diawp.exe.config

## 設定 Proxy 設定

預設的 proxy 設定，如下所示。

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

預設組態適用於 windows 驗證。 如果您的 proxy 使用另一種驗證，您將需要變更設定。 如果您不確定，您應該連絡網路系統管理員。

若要深入了解.NET 組態檔的 proxy 元素的設定，請參閱 [defaultProxy 項目 （網路設定）](https://msdn.microsoft.com/library/kd3cf2ex.aspx)

## 將閘道服務帳戶變更為網域使用者

當設定 proxy 設定為使用預設認證，如前文所述，您可能會驗證問題與您的 proxy。 這是因為預設服務帳戶是服務 SID，而且不是已驗證的網域使用者。 您可以變更服務帳戶，以允許適當的驗證用於 proxy 的閘道。

> [AZURE.NOTE] 建議您使用受管理的服務帳戶，以避免重設密碼。 了解如何建立 [受管理的服務帳戶](https://technet.microsoft.com/library/dd548356.aspx) Active Directory 內。

### 將內部部署資料閘道器服務帳戶變更

1. Windows 服務帳戶變更 **內部資料閘道服務**。 

    此服務的預設帳戶是 *NT SERVICE\PBIEgwService*。 您會想將它變更為在 Active Directory 網域的網域使用者帳戶。 或者，您會想要使用受管理的服務帳戶，以避免變更密碼。

    您會想要變更的帳戶上 **登入** 中 Windows 服務的屬性索引標籤。

2. 重新啟動 **內部資料閘道服務**。

    系統管理員命令提示字元中，發出下列命令。

        net stop PBIEgwService

        net start PBIEgwService

3. 啟動 **內部資料閘道設定程式**。 您可以選取 [windows 開始] 按鈕，並搜尋 *內部資料閘道*。

4. 登入 Power BI。

5. 還原使用修復金鑰的閘道。

    這可讓新的服務帳戶能夠解密的資料來源的預存的認證。

## 請參閱

[防火牆資訊](powerbi-gateway-onprem-tshoot.md#firewall-or-proxy)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)