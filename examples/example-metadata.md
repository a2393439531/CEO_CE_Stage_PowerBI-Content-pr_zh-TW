<properties pageTitle="文件範例-中繼資料屬性" description="這是範例文件" services="" documentationCenter="" authors="" tags="tag1,tag2" />

# 範例-中繼資料屬性 #

本文件是屬性設定的所有文件必須具備才能發佈的示範。  

---
## 中繼資料屬性 ##

中繼資料屬性應放在來源 Markdown 文件的開頭。 有強制必要和選擇性屬性。 如果需要中繼資料，然後在文件發行服務會產生錯誤驗證內容和發佈已修正之中繼資料之前的區塊。  如果不需要中繼資料則會發行服務產生警告。


它們應遵循此語法︰

`<properties pageTitle="page-title" description="description" services="services" documentationCenter="documentation-center"  authors="authors" tags="tag1,tag2" />`

下表顯示每一個屬性設定的詳細資訊︰

|  屬性      |    強制    | 說明 |
|--------|--------|--------|
| pageTitle       | 是       | HTML/頭/標題所使用的頁面標題。  請注意，這可能是不同於文件標題。 |
| 描述       | 是       | 指派給 HTML 中的中繼描述項目，並使用站台內的簡短文字描述。  |
| 服務       | 否       | 以逗號分隔清單中的服務名稱，例如 「 網站 」、 「 儲存體 」 等等。 |
| documentationCenter       | 否       | 單一開發人員中心 / 語言，會套用至文件。  |
| 作者       | 否       | 作者名稱以逗號分隔清單。   |
| 標記       | 否       | 索引標籤來識別文件的文件。 |
