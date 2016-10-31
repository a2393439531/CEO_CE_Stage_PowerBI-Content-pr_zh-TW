<properties linkid="nested-include-in-ordered-list" urlDisplayName="List with Nested Include Example" pageTitle="巢狀清單中包含的範例" title="List with Nested Include Example" metaKeywords="southworks" description="包含功能測試。" metaCanonical="" disqusComments="1" umbracoNaviHide="0" writer="f2bo" services="" solutions="" documentationCenter="" authors="" videoId="" scriptId="" />

# 巢狀的已排序的清單中包含的範例

*語法*

**主要文件**

```
1. Item ONE
    [AZURE.INCLUDE [innerlist](../includes/inner-list.md)]
2. Item FOUR
```

**Include**

```
1. Item TWO
2. Item THREE
```

<hr />

## 我的項目

1. 其中一個項目

    [AZURE.INCLUDE [innerlist](../includes/inner-list.md)]

1. 四個項目
