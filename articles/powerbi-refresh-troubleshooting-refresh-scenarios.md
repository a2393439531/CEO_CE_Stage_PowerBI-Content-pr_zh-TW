<properties 
   pageTitle="重新整理的疑難排解案例"
   description="重新整理的疑難排解案例"
   services="powerbi" 
   documentationCenter="" 
   authors="guyinacube" 
   manager="mblythe" 
   backup=""
   editor=""
   tags=""
   qualityFocus="complete"
   qualityDate="04/04/2016"/>
 
<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/15/2016"
   ms.author="asaxton"/>

# 重新整理的疑難排解案例  

您可以在這裡找到 Power BI 服務內的資料重新整理時，您可能會面臨不同案例的相關資訊。 

> [AZURE.NOTE] 如果您遇到未列出，以下的案例，而且它會造成問題，您可以尋求進一步協助上 [社群網站](http://community.powerbi.com/), ，或者您可以建立 [支援票證](https://powerbi.microsoft.com/support/)。

## 不支援的資料來源重新整理
當設定資料集，您可能會收到錯誤，指出此資料集使用不支援的資料來源重新整理。 如需詳細資訊，請參閱 [疑難排解不支援的資料來源重新整理](powerbi-admin-troubleshoot-unsupported-data-source-for-refresh.md)

## 儀表板並不會反映更新後的變更  
請等候大約 10-15 分鐘重新整理才會反映在 [儀表板] 磚。  如果它仍未顯示，重新釘選到儀表板的視覺效果。

## GatewayNotReachable 時設定認證  
嘗試設定資料來源的認證時，您可能會遇到 GatewayNotReachable。 這可能是閘道的過期的結果。  安裝最新的閘道，並再試一次。

## 處理錯誤:，發生下列系統錯誤︰ 類型不相符  
這可能是您在 Power BI Desktop 檔案或 Excel 活頁簿內的 M 指令碼發生問題。  它也可能是因為過期的 Power BI Desktop 版本。

## 並排顯示重新整理錯誤
如需使用儀表板圖格和說明可能遭遇的錯誤，請參閱 [疑難排解磚錯誤](powerbi-refresh-troubleshooting-tile-errors.md)。

## 另請參閱  

[資料重新整理](powerbi-refresh-data.md)  
[疑難排解內部部署資料閘道](powerbi-gateway-onprem-tshoot.md)  
[疑難排解 Power BI 閘道-個人](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)