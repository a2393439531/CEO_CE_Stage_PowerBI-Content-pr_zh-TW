<properties pageTitle="文件範例-標記" metaKeywords="" description="這是範例文件" services="" documentationCenter="" title="Documentation Example - Tags" solutions="" authors="" videoId="" scriptId="" />

<tags ms.service="AzureWebSites" ms.devlang="CSharp" ms.topic="home-page" ms.tgt_pltfrm="Windows" ms.workload="50" ms.date="06/12/2014" ms.author="maurok;v-nabeni@microsoft.com;lito@mail.com" />

# 範例-標記 #

這是用來測試及驗證的 Azure.com 發佈系統的範例文件文件。  

此範例 `<tags />` 可以找到項目下方 `<properties />` 從文件開頭的項目。

除非另外指定 （例如，對於 ms.date)，值限制為英數字元和連字號和值的長度應該限制為 30 個字元。

有的標記項目 7 必要的屬性︰ 

- 
            **ms.service**︰ 指定 Azure 服務、 工具或適用於文件的功能。

- 
            **ms.devlang**︰ 指定適用於文件的程式語言。

- 
            **ms.topic**︰ 指定主題型別。

    > 
            **有效的值**: *文章、 英雄文章、 參考、 索引頁、 行銷頁面、 影片頁面、 資訊圖分頁、 首頁上，服務首頁、 開發人員中心-首頁上、 站台] 區段的首頁上*  

- 
            **ms.tgt_pltfrm**︰ 指定目標平台，例如 Windows、 Linux、 Windows Phone、 iOS 或 Android。

- 
            **ms.workload**︰ 指定主題適用於 C （& E） 工作負載。

- 
            **ms.date**︰ 指定上次更新的日期相關的主題。

    > 
            **有效的值**︰ 日期格式 mm/dd/yyyy，例如︰“04/10/2014”

- 
            **ms.author**︰ 指定與主題相關聯的作者。 若要指定多個值，您應該以分號將值分開。

    > 
            **有效的值**: Microsoft 別名和完整的電子郵件地址。 長度應為長度不超過 200 個字元。


以下是範例是有效的標記項目︰

````XML
<tags ms.service="AzureWebSites" ms.devlang="CSharp" ms.topic="home-page" ms.tgt_pltfrm="Windows" ms.workload="50" ms.date="06/12/2014" ms.author="maurok;v-nabeni@microsoft.com;lito@mail.com" />
````


---