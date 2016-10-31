<properties 
   pageTitle="疑難排解 Azure SQL 資料庫的排程重新整理"
   description="疑難排解排定的重新整理 Power BI 中的 Azure SQL 資料庫"
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
   ms.date="09/21/2016"
   ms.author="asaxton"/>

# 疑難排解排定的重新整理 Power BI 中的 Azure SQL 資料庫  

如需設定排定的重新整理的詳細步驟，務必參閱 [Power BI 中的資料重新整理](powerbi-refresh-data.md)。

而設定排定重新整理 Azure SQL 資料庫，如果您收到錯誤，錯誤碼為 400 期間編輯的認證，請嘗試下列動作以設定適當的防火牆規則︰

1.  登入 Azure 管理入口網站

2.  請移至您要設定的重新整理的 Azure SQL 伺服器

3.  開啟 [允許的服務區段中的 [Windows Azure 服務]

![](media/powerbi-admin-troubleshooting-scheduled-refresh-azure-sql-databases/Azurerefresh.png)  

更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)