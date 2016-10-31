<properties
pageTitle="管理您的資料來源-Oracle"
description="如何管理內部部署資料閘道和資料來源屬於該閘道。"
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
ms.date="08/26/2016"
ms.author="asaxton"/>
# 管理您的資料來源-Oracle

當您安裝內部部署資料閘道之後時，您必須加入可以搭配閘道使用的資料來源。 這篇文章將探討如何使用閘道器和資料來源。 排定的重新整理或 DirectQuery，您可以使用 Oracle 資料來源。

## 下載並安裝閘道

您可以從 Power BI 服務的閘道。 選取 **下載** > **資料閘道**, ，或移至 [閘道下載頁面](https://go.microsoft.com/fwlink/?LinkId=698861)。

![](media/powerbi-gateway-onprem/powerbi-download-data-gateway.png)

> [AZURE.WARNING] 為了要能夠連接到 Oracle 伺服器閘道，Oracle 資料提供者.NET (ODP.NET) 必須安裝和設定。 這是 Oracle 資料存取元件 (ODAC)。 如需有關如何下載 Oracle 提供者的詳細資訊，請參閱 [安裝 Oracle 用戶端](#installing-the-oracle-client) 下方。

## 安裝 Oracle 用戶端

如 **32 位元** 版本的 Power BI Desktop，使用下列連結以下載並安裝 **32 位元** Oracle 用戶端︰

-   [32 位元 Oracle 資料存取元件 (ODAC) 與 Oracle Developer Tools for Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

如 **64 位元** 版本的 Power BI Desktop，或做為內部部署資料閘道，使用下列連結以下載並安裝 **64 位元** Oracle 用戶端︰

-   [64 位元 ODAC 12c 版本 4 (12.1.0.2.4) Xcopy 適用於 Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

安裝之後，您必須使用適當的資訊為您的資料庫設定 tnsnames.ora 檔案。 Power BI Desktop 和閘道器將會移開 net_service_name tnsnames.ora 檔案中定義。 如果未設定，您將無法連接。 Tnsnames.ora 的預設路徑如下所示︰ `[Oracle Home Directory]\Network\Admin\tnsnames.ora`。 如需如何設定 tnsnames.ora 檔案的詳細資訊，請參閱 [Oracle︰ 本機命名參數 (tnsnames.ora)](https://docs.oracle.com/cd/B28359_01/network.111/b28317/tnsnames.htm)。

### 範例 tnsnames.ora 檔案項目

Tnsname.ora 中的項目中的基本格式如下所示。

```
net_service_name= 
 (DESCRIPTION= 
   (ADDRESS=(protocol_address_information))
   (CONNECT_DATA= 
     (SERVICE_NAME=service_name))) 
```

以下是伺服器和連接埠資訊填入的範例。

```
CONTOSO =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracleserver.contoso.com)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = CONTOSO)
    )
  )
```

## 新增閘道

若要新增閘道，只要 [下載](https://go.microsoft.com/fwlink/?LinkId=698861) 和您的環境中的伺服器上安裝閘道。 安裝閘道之後，它會顯示在清單中下閘道 **管理閘道**。

> [AZURE.NOTE] 
            **管理閘道** 直到至少一個閘道的系統管理員，就不會顯示。 這種情形是藉由新增為系統管理員，或您安裝和設定閘道。

## 移除閘道

移除閘道也會刪除該閘道] 下的任何資料來源。  這也會中斷任何儀表板和依賴這些資料來源的報表。

1.  選擇齒輪圖示 ![](media/powerbi-gateway-enterprise-manage/pbi_gearicon.png) 右上角 > **管理閘道**。

2.  閘道 > **移除**

    ![](media/powerbi-gateway-enterprise-manage/datasourcesettings7.png)

## 加入資料來源

您可以加入資料來源選取閘道器和按一下 **新增資料來源**, ，或移至閘道 > **新增資料來源**。

![](media/powerbi-gateway-enterprise-manage/datasourcesettings1.png)

然後您可以選取 **資料來源類型** 從清單中。

![](media/powerbi-gateway-enterprise-manage/data-source-oracle.png)

您接著要填入資料來源包含的資訊 **伺服器** 和 **資料庫**。  

您也需要選擇 **驗證方法**。  這可以是 **Windows** 或 **基本**。  您會想要選擇 **基本** 如果您要在 Oracle，而不是 Windows 驗證中使用所建立的帳戶。 然後輸入將用於此資料來源的認證。

> [AZURE.NOTE] 資料來源的所有查詢會使用這些認證來都執行。 如需詳細資訊，請參閱主要內部部署資料閘道文件，以深入了解如何 [認證](powerbi-gateway-onprem.md#credentials) 儲存。

![](media/powerbi-gateway-enterprise-manage/data-source-oracle2.png)

您可以按一下 **新增** 填入的所有項目之後。  您現在可以使用此資料來源為排定的重新整理或 DirectQuery，對 Oracle 伺服器的內部部署上。 您會看到 *連線成功* 如果成功。

![](media/powerbi-gateway-enterprise-manage/datasourcesettings4.png)

### 進階設定

您可以設定您的資料來源的私密性等級。 這會控制如何 mashed 資料，設定。 這只用於排定的重新整理。 它不適用於 DirectQuery。 [進一步了解](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/powerbi-gateway-enterprise-manage/datasourcesettings9.png)

## 移除資料來源

移除資料來源會中斷任何儀表板或仰賴特定的資料來源的報表。  

若要移除資料來源，請移至資料來源 > **移除**。

![](media/powerbi-gateway-enterprise-manage/datasourcesettings6.png)

## 管理系統管理員

在系統管理員] 索引標籤的 [閘道，您可以加上移除，使用者可以管理閘道。 您只可以在此階段中新增使用者。 無法新增安全性群組。

![](media/powerbi-gateway-enterprise-manage/datasourcesettings8.png)

## 管理使用者

在 [使用者] 索引標籤的 [資料來源，您可以加入，並移除使用者或安全性群組，可以使用此資料來源。

> [AZURE.NOTE] 使用者清單只可以發行報表的控制項。 報表擁有者可以建立儀表板或內容的組件，並與其他使用者所共用。 使用報表或儀表板的使用者不需要出現在使用者清單中。

![](media/powerbi-gateway-enterprise-manage/datasourcesettings5.png)

## 使用資料來源

建立資料來源之後，它可使用其中一個 DirectQuery 的連線，或透過排定的重新整理。 

> [AZURE.WARNING] 伺服器和資料庫名稱必須符合 Power BI Desktop 與內部部署資料閘道的閘道器內的資料來源之間 ！

您的資料集與在閘道中的資料來源之間的連結根據您的伺服器名稱和資料庫名稱。 它們有相符 ！ 比方說，如果您提供之 IP 位址的伺服器名稱，在 Power BI Desktop，您必須為資料來源的閘道設定中使用的 IP 位址。 這個名稱也必須符合 tnsnames.ora 檔案中定義的別名。 如需 tnsnames.ora 檔案的詳細資訊，請參閱 [安裝 Oracle 用戶端](#installing-the-oracle-client)。

這是 DirectQuery 和排定的重新整理的狀況。

### 使用 DirectQuery 連接資料來源

您必須確定伺服器和資料庫名稱相符項目 Power BI Desktop 與設定的資料來源之間的閘道。 您也要確定您的使用者列在 **使用者** 為了發佈 DirectQuery 資料集的資料來源] 索引標籤。 當您第一次匯入資料選取範圍，directquery，就會發生在 Power BI Desktop。 [進一步了解](powerbi-desktop-use-directquery.md)

發行之後，從 Power BI Desktop 或 **取得資料**, ，您的報表應該開始工作。 可能需要幾分鐘的時間之後建立的閘道，可連接內的資料來源。

### 使用排定的重新整理資料來源

如果您列出 **的使用者** ] 索引標籤設定閘道，以及伺服器和資料庫名稱比對中的資料來源，您會看到閘道使用排定的重新整理選項。

![](media/powerbi-gateway-enterprise-manage/powerbi-gateway-enterprise-schedule-refresh.png)

## 疑難排解

當命名語法不正確或未設定正確，可能會遇到來自 Oracle 多種錯誤。

- ORA-TUT1-LESSON1-STEP2-12154: TNS︰ 無法解析指定的連接識別項  
- ORA-TUT1-LESSON1-STEP2-12514: TNS 接聽程式目前不知要求的服務中連接描述項  
- ORA-TUT1-LESSON1-STEP2-12541: TNS︰ 沒有任何接聽項  
- ORA-TUT1-LESSON1-STEP2-12170: TNS︰ 連接逾時，發生  
- ORA-TUT1-LESSON1-STEP2-12504: TNS 接聽程式已中未指定 SERVICE_NAME CONNECT_DATA  

如果未安裝 Oracle 用戶端，或如果未正確設定，可能會發生這些錯誤。 如果安裝時，您會想要驗證 tnsnames.ora 檔案已正確設定，並使用適當的 net_service_name。 您也必須確定 net_service_name 是使用 Power BI Desktop 的電腦以及執行閘道的機器之間相同。 如需詳細資訊，請參閱 [安裝 Oracle 用戶端](#installing-the-oracle-client)。

> [AZURE.NOTE] 您也可能遭遇的問題，因為 Oracle 伺服器上的版本與版本的 Oracle 用戶端之間的相容性。 通常您要比對。

取得與閘道相關的其他疑難排解資訊，請參閱 [疑難排解內部部署資料閘道](powerbi-gateway-onprem-tshoot.md)。

## 另請參閱

[內部資料閘道](powerbi-gateway-onprem.md)  
[內部資料閘道-深入](powerbi-gateway-onprem-indepth.md)  
[疑難排解內部部署資料閘道](powerbi-gateway-onprem-tshoot.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)