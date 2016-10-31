<properties
   pageTitle="秘訣和訣竅 Power BI 地圖視覺效果"
   description="秘訣和訣竅 Power BI 地圖視覺效果"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="ajTPGNpthcg"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/22/2016"
   ms.author="mihart"/>

# 秘訣和訣竅 Power BI 地圖視覺效果  

Power BI 整合 Bing，以提供預設地圖座標 （稱為地理編碼的程序），以便於為您建立的對應。 Bing 使用某些演算法和提示來嘗試取得正確的位置，但它是最佳的猜測。 若要增加正確的地理編碼的可能性，您可以使用下列秘訣︰

**1.使用地理位置詞彙**

根據指定的地理命名資料行，最好 Bing 猜出您想要顯示。 例如，如果您有一個人的欄位狀態名稱如 *加州* 和 *華盛頓*, ，Bing 如果資料行不是根據地理指定 （在此情況下狀態），可能會傳回的位置 *華盛頓特區* 而不是華盛頓州 word *華盛頓*。 命名該資料行 *狀態* 將可改善地理編碼。 同樣適用於資料行名稱為 *國家/地區*, ，*狀態*, ，和 *城市*。   

**2.使用逗號將多個內容新增至地理區域欄位**

某些指定是當多個國家 （地區） 的內容中被視為模稜兩可。 您可以藉由建置一起附加多個欄位，並使用這些來繪製資料位置的資料行增加地理編碼的精確度。 例如，而不是只傳遞 *Wiltshire*, ，您可以傳遞 *Wiltshire 英國* 以取得更精確的地理編碼結果。 

**3.使用特定的緯度和經度**

您永遠可以提供特定的經度和緯度位置。 當您這樣做時，您也需要填滿 *位置* 欄位建立視覺效果時。 否則，根據預設，比方說，緯度彙總的資料，並會在狀態層級，而不是縣 （市） 層級成對的經度。 經度和緯度欄位必須是 *十進位數字* 格式，您可以在資料模型中設定。

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>


## 分類地理提示 Bing 的地理編碼的欄位  
在 Power BI Desktop，您可以確定欄位設定是正確進行地理編碼 *資料類別* 上的資料欄位。 在 Power BI Desktop，選取所需的資料表，請移至 **進階** 功能區，然後設定 **資料類別** 至 **位址**, ，**縣 （市)**, ，**大陸**, ，**國家/地區**, ，**國家/地區**, ，**郵遞區號**, ，**狀態** 或 **州/省**。 這些資料類別有助於將 Bing 正確編碼的日期。 若要深入了解，請參閱 [Power BI Desktop 中的資料分類](powerbi-desktop-data-categorization.md)。

## 更好的地理編碼為更特定的位置  
有時候，即使設定對應的資料分類不夠 Bing 正確猜出您的意圖。 在查詢中，您可以建置更特定的位置，例如街道地址，使用 **查詢編輯器** Power BI Desktop 中。  使用 **加入資料行** 功能來建置自訂的資料行，然後建置所需的位置，如下所示︰ 


    = [Field1] & " " & [Field2]

然後使用地圖視覺效果中產生的欄位。 這種方法是非常適合建置街道地址，從資料集中常見的送貨地址欄位。 請注意，串連僅適用於文字欄位。 如有必要，將轉換的街道號碼 *文字* 資料型別，再使用它來建置一個地址。  

## 請參閱

[Power Bi 視覺效果](powerbi-service-visualizations-for-reports.md)

更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
