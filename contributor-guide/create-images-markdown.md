<properties
    pageTitle="Create images in markdown"
    description="Explains how to create images in markdown according to guidelines set for the Power BI repositories."
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

# Create images in markdown

## 影像資料夾建立和連結語法

For a new article, you'll need to create a folder in the following location on your local file system:

    /articles/media/<article-name>/

例如：

    /articles/media/powerbi-analysis-services-connector/

當您建立資料夾並將影像加入其中之後，請使用下列語法來建立文章中的影像︰

```
![Alt image text](./media/article-name/your-image-filename.png)
```

Then use the standard sync and pull request process so that your new images are merged into the master repo.

範例：

See <bpt id="p1">[</bpt>the markdown template<ept id="p1">](https://raw.githubusercontent.com/Azure/powerbi-content-pr/master/examples/_markdown-template.md)</ept> for an example.  The image call references in this markdown template are designed so the calls are made to image references at the bottom of the template.

## Guidelines specific to powerbi.microsoft.com

> [AZURE.NOTE] We will revise this section based on art guidelines specific to Power BI.

Screenshots are currently encouraged if it's not possible to include repro steps. 如有必要，請撰寫您的內容，讓內容可以獨立，而不需使用螢幕擷取畫面。

建立並包含美工檔案時，使用下列指導方針︰
- Do not share art files across documents. Copy the file you need and add it to the media folder for your specific topic. Sharing between files is discouraged because it is easier to remove deprecated content and images which keeps the repo clean.

- .png files are highly preferred over other formats.

-   When possible, create your screengrabs uisng the Retail Analysis sample that is included with Power BI. If that sample doesn't work for what you're trying to demonstrate, use one of the other official sanctioned Power BI samples (to see the samples, in Power BI service, Get data &gt; Samples).

- Use pink squares of the default width provided in Paint (5 px) or SnagIt to call attention to particular elements in screenshots.  

    範例：
    
    ![這是使用紅色方塊做為圖說文字的範例。](./media/create-images-markdown/gs13noauth.png)
    
-   Use blue arrows (default size and shape in SnagIt!) to call attention to particular elements in screenshots...when a pink box is not enough, or to show a particular order of steps, or to point out something small.

    範例：
    
    ![This is an example of a blue arrow used as a callout.](./media/create-images-markdown/power-bi-see-data.png)

- Avoid whitespace on edges of screenshots. 如果您利用讓邊緣保留白色背景的方式來裁剪螢幕擷取畫面，請在影像周圍加入單一像素的灰色框線。  If using Paint, use the lighter gray in the default color pallete (0xC3C3C3). If using some other graphic app, the RGB color is R195, G195, 195. You can easily add a gray border around an image in Visio--to do this, select the image, select Line, and ensure the the correct color is set, and then change the line weight to 1 1/2 pt.  Screenshots should have a 1-pixel-wide gray border so that white areas of the screenshot do not blur into the web page.

    範例：

    ![這是在空格周圍加上灰色框線的範例。](./media/create-images-markdown/agent.png)

- Conceptual images with whitespace are allowed to not have a gray boder.  
    
    範例：
    
    ![這是包含空格且沒有灰色框線的概念性影像範例。](./media/create-images-markdown/ic727360.png)

- 試著不要製作太寬的影像。  如果影像太寬，即會自動重新調整大小。 However, the resizing sometimes causes fuzziness, so we recommend that you limit the width of your images to a maximum of 780 px, and manually resize images before submission if necessary.

-   We recommend the following sizes: 780 pixels wide as a maximum.  5 inches wide at 120dpi for large screenshots.  4 inches wide at 120dpi for others.  Smaller than 4 inches is fine as long as the screenshot conveys what it needs at the smaller size. And, as mentioned above, try to capture what is needed at the pixel width and size that you need so that no resizing is necessary.

-   For inline icons, size to be at least 30 pixels x 30 pixels.  

    範例：
    
    ![This is an example of max size for an inline image](./media/create-images-markdown/power-bi-vertical-icon.png)

- 在螢幕擷取畫面中顯示命令輸出。  如果您的文章包含使用者在殼層內使用的步驟，最好是在螢幕擷取畫面中顯示命令輸出。 In this case, restricting your shell width to about 72 characters generally ensures that your image will remain within the 780 px width guideline. 取得輸出的螢幕擷取畫面之前，重新調整視窗大小，如此就只會顯示相關的命令和輸出 (可選擇性地在另一端含有一個空白行)。

- Maximum size of screenshots: Take whole screenshots of windows when possible. When taking a screenshot of a browser window, resize your browser window to 780 px wide or less, and keep the height of the browser window as short as possible such that your application fits within the window.  

    範例：

    ![這是瀏覽器視窗螢幕擷取畫面的範例。](./media/create-images-markdown/helloworldlocal.png)

- 請謹慎使用螢幕擷取畫面中所顯示的資訊。  Do not reveal internal company information or personal information.  If you can't avoid including personal information, use the blur tool to obscure it or cut it out and replace with matching color.

- 在概念性美工圖案或圖表中，使用雲端和企業符號與圖示集中的官方圖示。 A public set is available at http://aka.ms/CnESymbols.

###Contributors' Guide Links

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)
