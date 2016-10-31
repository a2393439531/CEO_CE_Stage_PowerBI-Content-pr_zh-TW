<properties
pageTitle="停用隱私權設定"
description="如何啟用 [快速合併在個人閘道，以停用重新整理的隱私權設定中。"
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="mblythe"
backup=""
editor=""
tags=""
qualityFocus="complete"
qualityDate="04/01/2016"/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="08/15/2016"
ms.author="asaxton"/>
# 停用在 Power BI 閘道個人隱私權設定

您可能會收到下列錯誤取決於資料來源與個人閘道搭配使用時的隱私權設定。

> *處理資料集中的資料時發生錯誤。*
>
> *[無法結合資料] &lt;查詢部分&gt;/&lt;...&gt;/&lt;…&gt; 存取的資料來源的隱私權等級無法一起使用。 請重建這個資料組合。*

若要解決此錯誤，您可以開啟 **快速合併**。 
            **快速合併** 將會忽略允許結合不同資料來源的隱私權設定。 

> [AZURE.NOTE] 聯結的資料時，不會視為隱私權等級。 聯結的資料時，這無法公開敏感或機密資料到其他資料來源。

## 什麼是快速合併？

若要深入了解隱私權等級 」 和 「 快速合併，您可以查看 [隱私權等級](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)。 根據預設，隱私權層級會設私用，因而造成上述錯誤。 這是因為私用的設定會隔離其他來源的資料來源。 情況範例問題會從另一個資料來源取得輸入的參數型的查詢。 

開啟快速合併會忽略私用設定，並允許發生執行。

## 開啟 [快速合併

您可以使用下列步驟以啟用您的個人閘道的 [快速合併。 內部部署資料閘道器並沒有這項設定。

1. 開啟 **ConnectorConfig.xml**。  這可能是在您的電腦上的兩個位置。  如果您是電腦的系統管理員，它會如下。

    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

    如果您不是系統管理員，此位置會是以下。

    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2.  新增 **&lt;EnableFastCombine&gt;** 值為 true 的組態檔項目。 加入這個項目將會關閉 **快速合併** 上。

    <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
    
    ![](media/powerbi-refresh-enable-fast-combine/configfile.png)

3.  結束並重新啟動閘道器組態畫面。

4.  您會看到狀態，告訴您已啟用 [快速合併。

    ![](media/powerbi-refresh-enable-fast-combine/fastcombineenabled.png)

## 關閉 [快速合併

1. 開啟 **ConnectorConfig.xml**。  這可能是在您的電腦上的兩個位置。  如果您是電腦的系統管理員，它會如下。

    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

    如果您不是系統管理員，此位置會是以下。

    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2.  移除 **&lt;EnableFastCombine&gt;** 組態檔中的項目。 移除這個項目將會關閉 **快速合併** 關閉。

3.  結束並重新啟動閘道器組態畫面。

4.  您不會再看到狀態，告訴您知道 **快速合併** 已啟用。


## 請參閱

[隱私權等級](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[在 Power BI Desktop 常見查詢工作](powerbi-desktop-common-query-tasks.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
