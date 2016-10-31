<properties
pageTitle="內部資料閘道器常見問題集"
description="這是內部部署資料閘道器常見問題集。 這會收集同一個地方閘道常見問題集。"
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
# 內部資料閘道常見問題集

<!-- Shared FAQ shared Include -->
[AZURE.INCLUDE [gateway-onprem-faq-shared-include](../includes/gateway-onprem-faq-shared-include.md)]

## Analysis Services


            **問題︰** 可以使用 msdmpump.dll Analysis services 建立自訂的有效使用者名稱對應嗎？  

            **答案是︰** [否]。 不支援這一次。


            **問題︰** 可以使用閘道來連接到多維度 (OLAP) 執行個體。  

            **答案是︰** 是 ！ 「 企業閘道支援即時連接到 Analysis Services 表格式和多維度模型。


            **問題︰** 要是我使用 Windows 驗證的內部部署伺服器不同的網域中的電腦上安裝閘道器嗎？  

            **答案是︰** 不保證一定。 所有這取決於兩個網域之間的信任關係。 如果兩個不同網域中受信任的網域模型，然後閘道可能能夠連接到 Analysis Services 伺服器，而且可以解決的有效使用者名稱。 如果沒有，您可能會遇到登入失敗。 


            **問題︰** 我要如何找出何種有效的使用者名稱傳遞至我的內部部署 Analysis Services 伺服器？  

            **答案是︰** 我們回答這在 [疑難排解文件](powerbi-gateway-onprem-tshoot.md)。


            **問題︰** 我有 25 資料庫 Analysis Services 中，有方法可以讓它們全部已啟用閘道嗎？  

            **答案是︰** [否]。 這在藍圖，但還沒時間範圍。

## 系統管理


            **問題︰** 可以有多個閘道的系統管理員嗎？  

            **答案是︰** 是 ！ 當您管理的閘道時，您可以移至系統管理員的索引標籤，以新增其他系統管理員。


            **問題︰** 閘道管理員必須是系統管理員，在電腦上的安裝閘道嗎？  

            **答案是︰** [否]。 閘道管理員用來管理的服務中的閘道。 


            **問題︰** 可以防止使用者在我的組織從建立閘道嗎？  

            **答案是︰** [否]。 這在藍圖，但還沒時間範圍。


            **問題︰** 可以取得使用量和統計資料資訊的閘道在我的組織？  

            **答案是︰** [否]。 這在藍圖，但還沒時間範圍。

## Power BI


            **問題︰** 如果我在企業部署使用目前的 Power BI 閘道，我要升級？

            **答案是︰** 是的但很容易做到，因為它只適用於相同的方式，在升級至最新的企業閘道。 簡易安裝新的內部部署資料閘道，以升級您現有的閘道。


            **問題︰** Do i 需要升級個人閘道嗎？

            **答案是︰** 否，您可以繼續使用個人閘道 Power bi。


            **問題︰** 頻率會並排顯示在儀表板，在 Power BI 中透過 「 企業閘道 」 連線時重新整理嗎？  

            **答案是︰** 約十分鐘。 DirectQuery 連接是指。 這並不表示磚內部部署伺服器，請發出查詢，並顯示新的資料，每十分鐘。


            **問題︰** 可以上傳連接至內部部署資料來源的 Power Pivot 資料模型的 Excel 活頁簿嗎？ 需要針對此案例的閘道嗎？  

            **答案是︰** 是，您可以上傳活頁簿。 並不會，您不需要閘道。 但是，因為資料將位於 Excel 資料模型中，請在 Excel 活頁簿為基礎的 Power BI 中的報表將無法即時。 若要重新整理 Power BI 中的報表，您必須每次重新上傳更新的活頁簿。 或者，使用閘道與排定的重新整理。


            **問題︰** 如果使用者共用儀表板具有 DirectQuery 連線，將這些其他的使用者能夠查看的資料，即使它們沒有相同的權限。  

            **答案是︰** 連接至 Analysis Services 儀表板，使用者只會看到他們擁有存取權的資料。 如果使用者沒有相同的權限，他們將無法看到任何資料。 其他資料來源，所有使用者會都共用該資料來源輸入系統管理員的認證。


            **問題︰** 是 Pro 授權，才能使用閘道嗎？  

            **答案是︰** [是]。


            **問題︰** 是 Pro 授權與儀表板或報表，以便使用閘道的互動時，所需的使用者嗎？  

            **答案是︰** [是]。


            **問題︰** 為何我無法連線到我的 Oracle 伺服器？  

            **答案是︰** 您可能需要安裝 Oracle 用戶端並設定適當的伺服器資訊以連接到 Oracle 伺服器 tnsnames.ora 檔案。 這是外部閘道個別安裝。 如需詳細資訊，請參閱 [安裝 Oracle 用戶端](powerbi-gateway-onprem-manage-oracle.md#installing-the-oracle-client)。


            **問題︰** 將閘道使用 ExpressRoute 嗎？  

            **答案是︰** [是]。 如需 ExpressRoute 和 Power BI 的詳細資訊，請參閱 [Power BI 和 ExpressRoute](powerbi-admin-power-bi-expressroute.md)。

## 請參閱
[內部資料閘道](powerbi-gateway-onprem.md)  
[深入的內部資料閘道](powerbi-gateway-onprem-indepth.md)  
[疑難排解內部部署資料閘道](powerbi-gateway-onprem-tshoot.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)