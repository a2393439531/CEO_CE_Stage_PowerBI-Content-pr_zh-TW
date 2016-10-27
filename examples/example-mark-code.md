<properties pageTitle="Documentation Example - Inline code" metaKeywords="" description="This is an example document" services="" documentationCenter="" title="Documentation Example - Inline code" authors="jamescon" solutions="" videoId="" scriptId="" />

# Example - Code #
This is a sample documentation article that is used to test and validate the publishing system for Azure.com.  

The content between the lines below demonstrates the highlight sections inside a code snippet using the <ph id="ph1">&lt;mark&gt;</ph> tag.

---

1. Inline code snippet `console.log(<mark>"sometext"</mark>)` 

1. Code block created with  <bpt id="p1">**</bpt>PRE<ept id="p1">**</ept> and <bpt id="p2">**</bpt>CODE<ept id="p2">**</ept> tags

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

1. Code block created with  <ph id="ph1">\`\`\`\`</ph> (4) syntax

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

1. Code block created with  <ph id="ph1">\`\`\`</ph> (3) syntax

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
