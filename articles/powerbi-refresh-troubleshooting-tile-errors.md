<properties
pageTitle="並排顯示錯誤的疑難排解"
description="磚會嘗試重新整理時可能遇到的常見錯誤"
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="mblythe"
backup=""
editor=""
tags=""
qualityFocus="monitoring"
qualityDate="06/13/2016"/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="08/15/2016"
ms.author="asaxton"/>
# 並排顯示錯誤的疑難排解

以下是常見的錯誤，您可能會遇到，磚，以及相關說明。

> [AZURE.NOTE] 如果您遇到錯誤，未列出，而且它會造成問題，您可以尋求進一步協助上 [社群網站](http://community.powerbi.com/), ，或者您可以建立 [支援票證](https://powerbi.microsoft.com/support/)。

## 錯誤

**Power BI 載入模型時發生未預期的錯誤。 請稍後再試。**
或 **無法擷取資料模型。請連絡儀表板擁有者，以確定資料來源與模型存在且可存取。**

我們無法存取您的資料，因為資料來源不可以連線。 如果資料來源已移除、 重新命名、 移動、 離線，或變更權限，則會發生此狀況。 請檢查來源仍處於我們所指向的位置，但仍有存取權限。 如果這樣還不問題時，來源可能會變慢。 請稍後再期間在來源上的負載較小。 如果是在內部部署來源，資料來源擁有者可以取得更多資訊。 

**您沒有檢視此磚，或開啟的活頁簿的權限。**

請確定資料來源與模型存在且可存取您帳戶的儀表板擁有者。

**資料圖形必須包含至少一個群組或輸出資料的計算。 請連絡儀表板擁有者。**

我們沒有任何要顯示，因為查詢是空的資料。 請嘗試將某些欄位從欄位清單加入至 visual studio 並重新釘選它。

**無法顯示資料，因為 Power BI 無法判斷兩個或多個欄位之間的關聯性。**

您嘗試使用不相關的資料表中的兩個或多個欄位。 您需要從視覺效果中移除不相關的欄位，然後再建立資料表之間的關聯性。 一旦您已這麼做，您可以將欄位加入至視覺效果。 這可以完成在 Power BI Desktop 或 Power Pivot for Excel。 [進一步了解](powerbi-desktop-create-and-manage-relationships.md)

**主座標軸與副座標軸中的群組重疊。 主座標軸中的群組不能有副座標軸中的群組相同的索引鍵。**

這通常是暫時性的問題。 將通常會發生此移動群組資料列的資料行。 在此情況下，當您完成移動的所有群組，應該都會消失錯誤。 如果您仍然會看到此訊息，請嘗試切換欄位之間的資料列和資料行或軸圖例或移除欄位，從視覺效果。  

**此視覺效果已超出可用資源。 請嘗試篩選以減少顯示的資料量。**

Visual studio 已嘗試查詢太多資料，為我們完成結果與可用的資源。 請試著篩選視覺效果，以減少結果中的資料量。

**無法識別下列欄位︰ {0}。 請以存在於資料集中的欄位更新視覺效果。**

可能已刪除或重新命名此欄位。 您可以從視覺效果，移除中斷的欄位加入不同的欄位，並要重新固定它。

**無法擷取此視覺效果的資料。 請稍後再試。**

這通常是暫時性的問題。 如果您稍後再試，而且您仍然可以看到此訊息，請連絡支援。

## 請連絡支援部門

如果您仍然有問題，請 [連絡支援人員](https://support.powerbi.com) 進一步調查。

## 請參閱

[疑難排解內部部署資料閘道](powerbi-gateway-onprem-tshoot.md)  
[疑難排解 Power BI 個人閘道](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)