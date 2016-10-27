<properties pageTitle="Documentation Example - AZURE.NOTE Markdown Extension" metaKeywords="" description="This is an example document" services="" documentationCenter="" title="Documentation Example - Inline code" solutions="" authors="" videoId="" scriptId="" />

# Example - AZURE.NOTE Markdown Extension #

This is a sample documentation article that is used to test and validate the publishing system for azure.microsoft.com.  

The content between the lines below demonstrates the use of the AZURE.NOTE Markdown extension.  For more information about the AZURE.NOTE Markdown extension please see the WIKI   <bpt id="p1">[</bpt>here<ept id="p1">](https://github.com/Azure/azure-content-test/wiki/markdown-extensions-notes)</ept>.

---
## AZURE.NOTE ##

Here is an example of a AZURE.NOTE:

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE.NOTE with custom heading##

Here is an example of a AZURE.NOTE:

````lang-html
> [AZURE.NOTE (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> <bpt id="p1">[AZURE.NOTE (</bpt>some heading<ept id="p1">)]</ept> To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE.NOTE with multiple paragraphs ##

Here is an example of a AZURE.NOTE with multiple paragraphs:

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. 
> 
> If you don't have an account, you can [create a free trial account](https://azure.microsoft.com/pricing/free-trial/) in just a couple of minutes. 
````

> [AZURE.NOTE] To complete this tutorial, you must have an Microsoft Azure account. 
> 
> If you don't have an account, you can <bpt id="p1">[</bpt>create a free trial account<ept id="p1">](https://azure.microsoft.com/pricing/free-trial/)</ept> in just a couple of minutes. 

---
## AZURE.NOTE with inline links and formatting ##

Here is an example of a AZURE.NOTE with an inline link and inline formatting for bold and italics:

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an _active_ **Microsoft Azure account**. If you don't have an account, you can [create a free trial account](https://azure.microsoft.com/pricing/free-trial/) in just a couple of minutes. 
````

> [AZURE.NOTE] To complete this tutorial, you must have an <bpt id="p1">_</bpt>active<ept id="p1">_</ept> <bpt id="p2">**</bpt>Microsoft Azure account<ept id="p2">**</ept>. If you don't have an account, you can <bpt id="p1">[</bpt>create a free trial account<ept id="p1">](https://azure.microsoft.com/pricing/free-trial/)</ept> in just a couple of minutes. 

---

## AZURE.NOTE with inline code ##

Here is an example of a AZURE.NOTE with an inline code:

````lang-html
> [AZURE.NOTE] When deploying to a Microsoft Azure Web Site, if your package.json file references a native module you will see an error similar to the following when publishing the application using Git:
````
npm ERR! module-name@0.6.0 install: <ph id="ph1">`node-gyp configure build`</ph> npm ERR! `cmd "/c" "node-gyp configure build"` failed with 1
````
````

> [AZURE.NOTE] When deploying to a Microsoft Azure Web Site, if your package.json file references a native module you will see an error similar to the following when publishing the application using Git:
````
npm ERR! module-name@0.6.0 install: `node-gyp configure build`
npm ERR! `cmd "/c" "node-gyp configure build"` failed with 1
````

---
## AZURE.NOTE With multiple paragraphs, lists and images ##


Here is an example of a AZURE.NOTE with custom heading:

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

> <bpt id="p1">[AZURE.NOTE (</bpt>some heading<ept id="p1">)]</ept> To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

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



---

## AZURE.WARNING##

Here is an example of a AZURE.WARNING:

````lang-html
> [AZURE.WARNING] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.WARNING] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---

## AZURE.WARNING With custom title ##


Here is an example of a AZURE.WARNING with custom heading:

````lang-html
> [AZURE.WARNING (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.WARNING (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE.WARNING With multiple paragraphs, lists and images ##


Here is an example of a AZURE.WARNING with custom heading:

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

> [AZURE.WARNING (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

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


---
## AZURE.INFORMATION ##


Here is an example of a AZURE.INFORMATION with custom heading:

````lang-html
> [AZURE.INFORMATION] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.INFORMATION] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE.INFORMATION With custom title ##


Here is an example of a AZURE.INFORMATION with custom heading:

````lang-html
> [AZURE.INFORMATION (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.INFORMATION (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE.INFORMATION With multiple paragraphs, lists and images ##


Here is an example of a AZURE.INFORMATION with custom heading:

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

> [AZURE.INFORMATION (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

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



---
## AZURE.TIP ##


Here is an example of a AZURE.TIP with custom heading:

````lang-html
> [AZURE.TIP ] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.TIP] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE.TIP With custom title ##


Here is an example of a AZURE.TIP with custom heading:

````lang-html
> [AZURE.TIP (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.TIP (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

---
## AZURE.TIP With multiple paragraphs, lists and images ##


Here is an example of a AZURE.TIP with custom heading:

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

> [AZURE.TIP (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

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



---
## AZURE.IMPORTANT ##


Here is an example of a AZURE.IMPORTANT with custom heading:

````lang-html
> [AZURE.IMPORTANT] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.IMPORTANT] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE.IMPORTANT With custom title ##


Here is an example of a AZURE.TIP with custom heading:

````lang-html
> [AZURE.IMPORTANT (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 
````

> [AZURE.IMPORTANT (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 


---
## AZURE.IMPORTANT With multiple paragraphs, lists and images ##


Here is an example of a AZURE.IMPORTANT with custom heading:

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

> [AZURE.IMPORTANT (some heading)] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

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

---
## AZURE.NOTE Example ##

Here is an example of a AZURE.NOTE with custom heading:

````lang-html
> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. If you don't have an account, you can create a free trial account in just a couple of minutes. 

>
````

> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 

<br />

> [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Azure account. 如果您沒有帳戶，只需要幾分鐘的時間就可以建立免費試用帳戶。 
