<properties
    pageTitle="在 markdown 中建立映像"
    description="說明如何根據設定的 Power BI 儲存機制的指導方針的 markdown 中建立映像。"
    services=""
    solutions=""
    documentationCenter=""
    authors="mblythe"
    manager="dongill"
    editor="NA"/>

<tags
    ms.service="contributor-guide"
    ms.devlang=""
    ms.topic="article"
    ms.tgt_pltfrm=""
    ms.workload=""
    ms.date="05/19/2016"
    ms.author="mblythe" />

# 在 markdown 中建立映像

## 影像資料夾建立和連結語法

針對新發行項，您將需要在您的本機檔案系統上的下列位置建立資料夾︰

    /articles/media/<article-name>/

例如：

    /articles/media/powerbi-analysis-services-connector/

當您建立資料夾並將影像加入其中之後，請使用下列語法來建立文章中的影像︰

```
![Alt image text](./media/article-name/your-image-filename.png)
```

然後使用標準的 sync 或提取要求程序，所以新的映像會合併到主要的儲存機制。

範例：

請參閱 [markdown 範本](https://raw.githubusercontent.com/Azure/powerbi-content-pr/master/examples/_markdown-template.md) 範例。  映像呼叫範本中的參考此 markdown 呼叫底部的範本映像參考的設計。

## Powerbi.microsoft.com 特有的指導方針

> [AZURE.NOTE] 我們會修訂本節根據特定 Power bi 的藝術指導方針。

如果您不可以包含重新產生步驟目前建議的螢幕擷取畫面。 如有必要，請撰寫您的內容，讓內容可以獨立，而不需使用螢幕擷取畫面。

建立並包含美工檔案時，使用下列指導方針︰
- 請勿在文件共用圖片檔。 將複製的檔案，您需要並將它新增至媒體資料夾中，您的特定主題。 由於很容易移除過時內容與映像，會清除儲存機制，否則不建議在檔案間共用。

- .png 檔案它具有較高於其他格式。

-   可能的話，請建立 screengrabs 使用隨附於 Power BI 零售分析範例。 如果該範例不適用於您正嘗試示範，使用其中一個其他正式保障 Power BI 範例 (若要查看範例，在 Power BI 服務取得資料 > 範例)。

- 使用 [小畫家] 中提供的預設寬度的粉紅色平方 (5 像素) 或 SnagIt 以醒目提示特定項目在螢幕擷取畫面。  

    範例：
    
    ![這是使用紅色方塊做為圖說文字的範例。](./media/create-images-markdown/gs13noauth.png)
    
-   使用藍色箭頭 （預設大小和形狀中 SnagIt ！） 醒目提示特定項目在螢幕擷取畫面...粉紅色方塊不足夠時, 顯示的步驟，以特定順序或點小一點。

    範例：
    
    ![這是藍色箭號做為圖說文字的範例。](./media/create-images-markdown/power-bi-see-data.png)

- 請避免空白字元的螢幕擷取畫面邊緣上。 如果您利用讓邊緣保留白色背景的方式來裁剪螢幕擷取畫面，請在影像周圍加入單一像素的灰色框線。  如果使用 [小畫家]，使用淡灰色預設色盤 (0xC3C3C3) 中。 如果使用其他圖形應用程式，RGB 色彩會是 R195，G195，195。 您可以輕鬆加入影像周圍的灰色框線 visio-執行這項操作，選取的映像、 選取行，並確保正確的色彩設定，並變更線條的寬度為 1 1/2 pt。  螢幕擷取畫面應該有 1 像素寬的灰色框線，讓螢幕擷取畫面的白色區域不執行模糊到網頁。

    範例：

    ![這是在空格周圍加上灰色框線的範例。](./media/create-images-markdown/agent.png)

- 允許空白的概念影像沒有灰色 boder。  
    
    範例：
    
    ![這是包含空格且沒有灰色框線的概念性影像範例。](./media/create-images-markdown/ic727360.png)

- 試著不要製作太寬的影像。  如果影像太寬，即會自動重新調整大小。 不過，有時使用調整大小會導致 fuzziness，因此我們建議您最多個 780 影像的寬度限制像素，並手動調整大小如有必要進行提交之前的映像。

-   我們建議下列大小︰ 780 像素寬的最大值。  5 英吋 120 dpi 的大型螢幕擷取畫面。  4 英吋寬 120 dpi 供其他人。  小於 4 英吋，沒關係，只要螢幕擷取畫面傳達它需要在較小的大小。 然後，如上所述，嘗試擷取所需的像素寬度和您需要調整大小不是必要的大小。

-   內嵌圖示，為至少 30 個像素 x 30 像素的大小。  

    範例：
    
    ![這是大小的範例的內嵌影像上限](./media/create-images-markdown/power-bi-vertical-icon.png)

- 在螢幕擷取畫面中顯示命令輸出。  如果您的文章包含使用者在殼層內使用的步驟，最好是在螢幕擷取畫面中顯示命令輸出。 在此情況下，通常需要大約 72 個字元限制殼層寬度可確保您的映像將會保留在 780 像素寬度指導方針。 取得輸出的螢幕擷取畫面之前，重新調整視窗大小，如此就只會顯示相關的命令和輸出 (可選擇性地在另一端含有一個空白行)。

- 螢幕擷取畫面的大小上限︰ 拍攝的 windows 盡可能整個螢幕擷取畫面。 進行瀏覽器視窗的螢幕擷取畫面，調整瀏覽器視窗的 780 像素寬或較少，並保留為瀏覽器視窗的高度短越好讓您的應用程式配合視窗。  

    範例：

    ![這是瀏覽器視窗螢幕擷取畫面的範例。](./media/create-images-markdown/helloworldlocal.png)

- 請謹慎使用螢幕擷取畫面中所顯示的資訊。  不要顯露內部的公司資訊或個人資訊。  如果您不能避免包括個人資訊，請使用模糊工具模糊或剪下它，並取代相符的色彩。

- 在概念性美工圖案或圖表中，使用雲端和企業符號與圖示集中的官方圖示。 Http://aka.ms/CnESymbols 的公用集合。

###著作指南的連結

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)
