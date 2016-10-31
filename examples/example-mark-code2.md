<properties pageTitle="文件範例-標記程式碼" metaKeywords="" description="這是範例文件" services="" documentationCenter="" title="Documentation Example - Inline code" solutions="" authors="" videoId="" scriptId="" />

# 範例-標記程式碼 #

這個範例已經從 http://www.asp.net/mvc/tutorials/mvc-5/introduction/adding-a-view 採取以顯示如何新增程式碼片段內的標記標籤

---
...

我們先建立 Views\HelloWorld\Index.cshtml 檔案，它會包含下列程式碼︰

````
@{
    Layout = "~/Views/Shared/_Layout.cshtml";
}
````
    
上面的 Razor 程式碼是 explicted 設定版面配置頁。 請檢查檢視\_ViewStart.cshtml 檔，它包含相同的 Razor 標記。 TheViews\_ViewStart.cshtml 檔定義將使用的所有檢視的一般配置，因此您可以標記為註解或移除該程式碼從 Views\HelloWorld\Index.cshtml 檔。

````
<mark>@*@{
    Layout = "~/Views/Shared/_Layout.cshtml";
}*@</mark>

@{
    ViewBag.Title = "Index";
}

<h2>Index</h2>

<p>Hello from our View Template!</p>
````

您可以使用版面配置] 屬性設定不同的版面配置檢視，或將它設定為 null，所以會使用未配置的檔案。

現在，讓我們來變更 [索引] 檢視的標題。

開啟 MvcMovie\Views\HelloWorld\Index.cshtml。 若要變更的兩個地方︰ 第一次，文字會出現標題的瀏覽器中，並在第二個標頭 ( &lt;h2&gt; 項目)。 您要進行這些稍有不同，您所見的位元的程式碼變更的部分應用程式。

````
@{
    ViewBag.Title = "<mark>Movie List</mark>";
}

<h2><mark>My Movie List</mark></h2>

<p>Hello from our View Template!</p>
````

若要指出要顯示的 HTML 標題，上面的程式碼會設定 ViewBag 物件 （這是 Index.cshtml 檢視範本中） 的 Title 屬性。 請注意，版面配置範本 (Views\Shared\_Layout.cshtml) 會使用此值在 &lt;標題&gt; 一部分的項目 &lt;head&gt; 一節我們先前已修改的 html。

````
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><mark>@ViewBag.Title</mark> - Movie App</title>
    @Styles.Render("~/Content/css")
    @Scripts.Render("~/bundles/modernizr")
</head>
````

使用這個 ViewBag 方法，可以檢視範本和版面配置檔之間輕鬆地傳遞其他參數。

執行應用程式。 請注意，瀏覽器標題、 主要的標題和第二個標題已變更。 （如果您沒有看到瀏覽器中的變更，您可能要檢視快取的內容。 按 Ctrl + F5 在瀏覽器中強制載入伺服器的回應。）瀏覽器標題會透過我們在 Index.cshtml 檢視範本和其他設定 ViewBag.Title 」-電影應用程式 」 在版面配置檔中加入。

也請注意如何在 Index.cshtml 檢視範本內容已合併至 _Layout.cshtml 檢視範本和單一 HTML 回應已傳送至瀏覽器。 版面配置範本讓您很容易變更套用於所有應用程式中的頁面。

...

---
