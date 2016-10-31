<properties
   pageTitle="從檔案取得資料"
   description="了解如何從 Excel、 Power BI Desktop 及 CSV 檔案將資料送入 Power BI"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="04/01/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/29/2016"
   ms.author="davidi"/>

# 從檔案取得資料
![](media/powerbi-service-get-data-from-files/file_icons.png)

您可在 Power BI 連接到，或從三種類型的檔案匯入資料和報表。

-   Microsoft Excel （.xlsx 或.xlsm）
-   Power BI Desktop (.pbix)
-   以逗號分隔值 (.csv)

## 什麼會從檔案取得資料平均真的？

在 Power BI 中您瀏覽的資料來自資料集。 但若要有一個資料集，您必須先取得一些資料。 在本文中，我們把重點放在從檔案取得資料。

若要進一步了解資料集，以及我們如何為其取得資料的重要性，讓我們看看汽車。 需要在您的車子的基座，並查看 [儀表板。 很像看看 Power BI 儀表板在電腦前一般。 儀表板會顯示賽車這項作業的項目速度引擎開始運轉，溫度、 哪些齒輪，您已位於您速度等。

在 Power BI 中的資料集是像是在車上引擎。 資料集提供資料、 度量和 Power BI 儀表板中顯示的資訊。 當然需要燃料，您的引擎或資料集，並在 Power BI 的燃料就是資料。 您的車子有提供引擎天然氣油箱。 變 Power BI 中，您需要油箱，您可以逐一將加入資料集的資料。 在本例中，該油箱是 Power BI Desktop 檔案，Excel 活頁簿檔案，或。CSV 檔案。

我們可以更進一步它其中一個步驟。 在車上油箱有天然氣填滿。 我們的 Power BI Desktop，Excel 的天然氣或。CSV 檔是從其他資料來源的資料。 我們從其他資料來源取得資料，並將它放入 Excel 中，Power BI Desktop 或。CSV 檔案。 如果是 Excel 活頁簿或。CSV 檔案中，我們可以手動輸入資料的列。 或者，我們就可以連接至外部資料來源，以查詢和載入資料到我們的檔案。 一旦我們有一些資料檔案，我們也找得到到 Power BI 做為資料集。

## 儲存您的檔案差異


            **本機** -如果您將檔案儲存到本機磁碟機上您的電腦或另一個位置在組織中，您可以從 Power BI *匯入* 到 Power BI 檔案。 讓整個檔案不真的匯入 Power BI，您的檔案實際上會保留在本機磁碟機。 真正發生的情況是新的資料集建立在您的 Power BI 網站和資料，而且在某些情況下資料模型，會載入至資料集。 如果您的檔案會有任何報表，這些會出現在 [報表] 下的 Power BI 網站。


            **OneDrive-商務** – 如果您有商務用 OneDrive 使用相同的帳戶登入 Power BI 與登入，這是由遠方最有效的方式在 Excel 的 Power BI Desktop，保留您的工作或。CSV 檔案您資料集、 報表和儀表板中 Power BI 中同步處理。 因為 Power BI 和 OneDrive 位於定域機組，Power BI 可連接至您放在 OneDrive 上的檔案大約每小時。 如果找不到任何變更，您的資料集、 報表和儀表板會自動更新，Power BI。


            **OneDrive-個人** – 如果您將檔案儲存到您自己的 OneDrive 帳戶，就會顯示許多相同的優點就與商務用 OneDrive。 最大的差異是當您第一次連接到您的檔案 (使用取得資料 > 檔案 > OneDrive-個人) 需要您的 OneDrive 與您通常不同於您用於登入 Power BI 的 Microsoft 帳戶登入。 當登入您的 OneDrive 與您的 Microsoft 帳戶，請務必在選項中選取 [讓我保持登。 如此一來，Power BI 都能夠連接到每個小時的相關檔案，並確定您在 Power BI 中的資料集是在同步處理。


            **SharePoint 小組網站** – 將 Power BI Desktop 檔案儲存到 SharePoint – 小組網站時，就如同儲存至商務用 OneDrive。 最大的差別是如何連接至檔從 Power BI。 您可以指定 URL，或連線至根資料夾。

## 準備好開始了嗎？
請參閱下列文件，若要深入了解您的檔案放入 Power BI。

-   [從 Excel 活頁簿檔案取得資料](articles/powerbi-service-excel-workbook-files.md)
-   [從 Power BI Desktop 檔案取得資料](articles/powerbi-service-powerbi-desktop-files.md)
-   [從逗號分隔值檔案取得資料](articles/powerbi-service-comma-separated-value-files.md)
