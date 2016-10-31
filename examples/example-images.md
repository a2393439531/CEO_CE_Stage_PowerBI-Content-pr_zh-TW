<properties pageTitle="文件範例-映像" metaKeywords="" description="這是範例文件" services="" documentationCenter="" title="Documentation Example - Images" solutions="" authors="" videoId="" scriptId="" />

# 範例-映像 #

這是用來測試及驗證 azure.microsoft.com 的發佈系統的範例文件文件。  

下列程式行之間的內容將示範不同支援的影像語法。  


---
## 映像內嵌語法 ##

使用這個語法時必須開頭放置一個驚嘆號。 然後，之間的識別項的映像的方括號。 之後，括號內的資料夾結構的影像的相對路徑之間。

**映像的語法︰**  `![windows-azure-logo](./media/example-images/windows-azure.png) `

**產生的映像︰** 

![windows azure 標誌](./media/example-images/windows-azure.png)

---

## 參考的影像語法 ##

此語法很類似，但參照映像路徑，在本文中的運作方式。 它會使用一個驚嘆號開頭，與一組包含文件中的映像的參考 id 的方括號。 影像參考則必須包含資料夾結構中的影像的相對路徑。

**映像的語法︰** 
`![][windows-azure-logo]`

**影像參考︰** `[windows-azure-logo]: ./media/example-images/windows-azure.png `

**產生的映像︰** 

![][windows-azure-logo]

[windows azure 標誌]: ./media/example-images/windows-azure.png


參照映像的另一種方式︰

`![windows-azure-logo][] `

![windows azure 標誌][]

`![windows-azure-logo][windows-azure-logo] `

![windows azure 標誌][windows-azure-logo]
