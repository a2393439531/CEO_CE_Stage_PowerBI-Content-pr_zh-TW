<properties pageTitle="文件範例-內嵌程式碼" metaKeywords="" description="這是範例文件" services="" documentationCenter="" title="Documentation Example - Inline code" authors="jamescon" solutions="" videoId="" scriptId="" />

# 程式碼範例 #
這是用來測試及驗證的 Azure.com 發佈系統的範例文件文件。  

下列程式行之間的內容將示範使用程式碼片段反白顯示區段 <mark> 標記。

---

1. 內嵌程式碼片段 `console.log(<mark>"sometext"</mark>)` 

1. 程式碼區塊，以建立  **PRE** 和 **程式碼** 標記

<pre><code>
static private IAsset CreateEmptyAsset(string assetName, AssetCreationOptions assetCreationOptions)
{
    var asset = _context.Assets.Create(assetName, assetCreationOptions);

    Console.WriteLine(<mark>"Asset name: " + asset.Name</mark>);
    Console.WriteLine(<mark>"Time created: " + asset.Created.Date.ToString());
    Console.WriteLine("Time closed: " + asset.Closed.Date.ToString()</mark>);
    
    return asset;
}
</code></pre>

1. 程式碼區塊，以建立  \`\`\`\` (4) 的語法

````C#
static private IAsset CreateEmptyAsset(string assetName, AssetCreationOptions assetCreationOptions)
{
    var asset = _context.Assets.Create(assetName, assetCreationOptions);

    Console.WriteLine(<mark>"Asset name: " + asset.Name</mark>);
    Console.WriteLine(<mark>"Time created: " + asset.Created.Date.ToString());
    Console.WriteLine("Time closed: " + asset.Closed.Date.ToString()</mark>);
    
    return asset;
}
````

1. 程式碼區塊，以建立  \`\`\` (3) 的語法

```C#
static private IAsset CreateEmptyAsset(string assetName, AssetCreationOptions assetCreationOptions)
{
    var asset = _context.Assets.Create(assetName, assetCreationOptions);

    Console.WriteLine(<mark>"Asset name: " + asset.Name</mark>);
    Console.WriteLine(<mark>"Time created: " + asset.Created.Date.ToString());
    Console.WriteLine("Time closed: " + asset.Closed.Date.ToString()</mark>);

    return asset;
}
```

---
