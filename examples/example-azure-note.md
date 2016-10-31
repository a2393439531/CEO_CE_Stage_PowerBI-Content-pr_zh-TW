<properties pageTitle="文件範例-AZURE。請注意 Markdown 延伸模組" metaKeywords="" description="這是範例文件" services="" documentationCenter="" title="Documentation Example - Inline code" solutions="" authors="" videoId="" scriptId="" />

# 範例-AZURE。請注意 Markdown 延伸模組 #

這是用來測試及驗證 azure.microsoft.com 的發佈系統的範例文件文件。  

下列程式行之間的內容中，示範如何使用 AZURE。請注意 Markdown 延伸模組。  如需 AZURE 的詳細資訊。請注意 Markdown 延伸模組，請參閱 WIKI   [這裡](https://github.com/Azure/azure-content-test/wiki/markdown-extensions-notes)。

---
## AZURE。附註 ##

以下是在 AZURE 的範例。注意︰

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.NOTE] 若要完成本教學課程，您必須使用中的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE。請注意，自訂標題##

以下是在 AZURE 的範例。注意︰

````lang-html
> [AZURE.NOTE (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> 
            [AZURE.NOTE (某些標題)] 若要完成本教學課程，您必須具有有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE。請注意，使用多個段落 ##

以下是在 AZURE 的範例。請注意，使用多個段落︰

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. 
> 
> If you don't have an account, you can [create a free trial account](https://azure.microsoft.com/pricing/free-trial/) in just a couple of minutes. 
````

> [AZURE.NOTE] 若要完成本教學課程，您必須使用 Microsoft Azure 帳戶。 
> 
> 如果您沒有帳戶，您可以 [建立免費試用帳戶](https://azure.microsoft.com/pricing/free-trial/) 只需要幾分鐘的時間。 

---
## AZURE。請注意，使用內嵌的連結和格式 ##

以下是在 AZURE 的範例。請注意，使用內嵌連結和內嵌格式為粗體和斜體︰

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an _active_ **Microsoft Azure account**. If you don't have an account, you can [create a free trial account](https://azure.microsoft.com/pricing/free-trial/) in just a couple of minutes. 
````

> [AZURE.NOTE] 若要完成本教學課程，您必須擁有 _active_ **Microsoft Azure 帳戶**。 如果您沒有帳戶，您可以 [建立免費試用帳戶](https://azure.microsoft.com/pricing/free-trial/) 只需要幾分鐘的時間。 

---

## AZURE。請注意，使用內嵌程式碼 ##

以下是在 AZURE 的範例。請注意，使用內嵌程式碼︰

````lang-html
> [AZURE.NOTE] When deploying to a Microsoft Azure Web Site, if your package.json file references a native module you will see an error similar to the following when publishing the application using Git:
````
npm ERR ！ 安裝 module-name@0.6.0: `node-gyp configure build` npm ERR ！ `cmd "/c" "node-gyp configure build"` 因 1
````
````

> [AZURE.NOTE] 當部署到 Microsoft Azure 網站，如果您的 package.json 檔案參考原生模組，您會看到類似下列的錯誤，發行使用 Git 的應用程式時︰
````
npm ERR! module-name@0.6.0 install: `node-gyp configure build`
npm ERR! `cmd "/c" "node-gyp configure build"` failed with 1
````

---
## AZURE。請注意，使用多個段落、 清單和影像 ##


以下是在 AZURE 的範例。自訂標題，請注意︰

````lang-html
> [AZURE.NOTE (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 

> * List 1
> * List 2
> * List 3
> * List 4

> ````C#
>   some code   
> ````

> Some text

> ![windows-azure-logo](./media/example-azure-note/windows-azure.png)
        
> Some text
````

> 
            [AZURE.NOTE (某些標題)] 若要完成本教學課程，您必須具有有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

> * 清單 1
> * 清單 2
> * 清單 3
> * 清單 4

> ````C#
>   some code   
> ````

> 一些文字

> ![windows azure 標誌](./media/example-azure-note/windows-azure.png)
        
> 一些文字



---

## AZURE。警告##

以下是在 AZURE 的範例。警告︰

````lang-html
> [AZURE.WARNING] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.WARNING] 若要完成本教學課程，您必須使用中的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---

## AZURE。警告與自訂標題 ##


以下是在 AZURE 的範例。自訂標題警告︰

````lang-html
> [AZURE.WARNING (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE。警告 （某些標題）] 來完成此教學課程，您必須具有有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE。使用多個段落、 清單和影像警告 ##


以下是在 AZURE 的範例。自訂標題警告︰

````lang-html
> [AZURE.WARNING (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 

> * List 1
> * List 2
> * List 3
> * List 4

> ````C#
>   some code   
> ````

> Some text

> ![windows-azure-logo](./media/example-azure-note/windows-azure.png)
        
> Some text
````

> [AZURE。警告 （某些標題）] 來完成此教學課程，您必須具有有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

> * 清單 1
> * 清單 2
> * 清單 3
> * 清單 4

> ````C#
>   some code   
> ````

> 一些文字

> ![windows azure 標誌](./media/example-azure-note/windows-azure.png)
        
> 一些文字


---
## AZURE.INFORMATION ##


自訂標題 AZURE.INFORMATION 的範例如下︰

````lang-html
> [AZURE.INFORMATION] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.INFORMATION] 若要完成此教學課程中，您必須具備有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE.INFORMATION 與自訂標題 ##


自訂標題 AZURE.INFORMATION 的範例如下︰

````lang-html
> [AZURE.INFORMATION (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> 若要完成此教學課程中的 [AZURE.INFORMATION （某些標題）] 您必須具備有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## 使用多個段落、 清單和影像 AZURE.INFORMATION ##


自訂標題 AZURE.INFORMATION 的範例如下︰

````lang-html
> [AZURE.INFORMATION (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 

> * List 1
> * List 2
> * List 3
> * List 4

> ````C#
>   some code   
> ````

> Some text

> ![windows-azure-logo](./media/example-azure-note/windows-azure.png)
        
> Some text
````

> 若要完成此教學課程中的 [AZURE.INFORMATION （某些標題）] 您必須具備有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

> * 清單 1
> * 清單 2
> * 清單 3
> * 清單 4

> ````C#
>   some code   
> ````

> 一些文字

> ![windows azure 標誌](./media/example-azure-note/windows-azure.png)
        
> 一些文字



---
## AZURE。秘訣 ##


以下是在 AZURE 的範例。自訂標題祕訣︰

````lang-html
> [AZURE.TIP ] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.TIP] 若要完成本教學課程，您必須使用中的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE。秘訣與自訂標題 ##


以下是在 AZURE 的範例。自訂標題祕訣︰

````lang-html
> [AZURE.TIP (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE。提示 （某些標題）] 以完成此教學課程中，您必須具備有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE。秘訣與多個段落、 清單和映像 ##


以下是在 AZURE 的範例。自訂標題祕訣︰

````lang-html
> [AZURE.TIP (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 

> * List 1
> * List 2
> * List 3
> * List 4

> ````C#
>   some code   
> ````

> Some text

> ![windows-azure-logo](./media/example-azure-note/windows-azure.png)
        
> Some text
````

> [AZURE。提示 （某些標題）] 以完成此教學課程中，您必須具備有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

> * 清單 1
> * 清單 2
> * 清單 3
> * 清單 4

> ````C#
>   some code   
> ````

> 一些文字

> ![windows azure 標誌](./media/example-azure-note/windows-azure.png)
        
> 一些文字



---
## AZURE。重要 ##


以下是在 AZURE 的範例。自訂標題的重要事項︰

````lang-html
> [AZURE.IMPORTANT] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.IMPORTANT] 若要完成本教學課程，您必須使用中的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE。自訂標題重要 ##


以下是在 AZURE 的範例。自訂標題祕訣︰

````lang-html
> [AZURE.IMPORTANT (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE。重要事項 （某些標題）] 若要完成本教學課程，您必須具有有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE。使用多個段落、 清單和影像的重要事項 ##


以下是在 AZURE 的範例。自訂標題的重要事項︰

````lang-html
> [AZURE.IMPORTANT (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 

> * List 1
> * List 2
> * List 3
> * List 4

> ````C#
>   some code   
> ````

> Some text

> ![windows-azure-logo](./media/example-azure-note/windows-azure.png)
        
> Some text
````

> [AZURE。重要事項 （某些標題）] 若要完成本教學課程，您必須具有有效的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

> * 清單 1
> * 清單 2
> * 清單 3
> * 清單 4

> ````C#
>   some code   
> ````

> 一些文字

> ![windows azure 標誌](./media/example-azure-note/windows-azure.png)
        
> 一些文字

---
## AZURE。請注意範例 ##

以下是在 AZURE 的範例。自訂標題，請注意︰

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 

>
````

> [AZURE.NOTE] 若要完成本教學課程，您必須使用中的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

<br />

> [AZURE.NOTE] 若要完成本教學課程，您必須使用中的 Microsoft Azure 帳戶。 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 
