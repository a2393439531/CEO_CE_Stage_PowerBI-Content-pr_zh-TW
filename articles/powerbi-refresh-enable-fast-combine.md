<properties
pageTitle="Disable privacy settings"
description="How to enable Fast Combine within the Personal Gateway to disable privacy settings for refresh."
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
# Disable privacy setting in Power BI Gateway - Personal

You may receive the following error based on the privacy settings for your data sources when used with the personal gateway.

> *An error occurred while processing the data in the dataset.*
>
> *[Unable to combine data] <ph id="ph1">&amp;lt;</ph>query part<ph id="ph2">&amp;gt;/&amp;lt;</ph>…<ph id="ph3">&amp;gt;/&amp;lt;</ph>…&gt; is accessing data sources that have privacy levels which cannot be used together. Please rebuild this data combination.*

To work around this error, you can turn on <bpt id="p1">**</bpt>Fast Combine<ept id="p1">**</ept>. <bpt id="p1">**</bpt>Fast Combine<ept id="p1">**</ept> will ignore the privacy settings allowing the different data sources to be combined. 

> [AZURE.NOTE] Privacy levels are not considered when combining data. This could expose sensitive or confidential data to another data source when combining data.

## What is Fast Combine?

To learn more about privacy levels and Fast Combine, you can look at <bpt id="p1">[</bpt>Privacy Levels<ept id="p1">](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)</ept>. By default, the privacy level will be set to private which could result in the error mentioned above. This is because a setting of private will isolate the data source from other sources. An example of where this would be a problem would be a parameterized query getting inputs from another data source. 

Turning Fast Combine on will ignore the private setting and allow the execution to occur.

## Turn on Fast Combine

You can use the following steps to enable Fast Combine for your personal gateway. The On-Premises Data Gateway does not have this setting.

1. Open <bpt id="p1">**</bpt>ConnectorConfig.xml<ept id="p1">**</ept>.  This may be in one of two locations on your machine.  If you are an administrator on the computer, it will be the following.

    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

    If you are not an administrator, the location will be the following.

    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2.  Add the <bpt id="p1">**</bpt><ph id="ph1">&amp;lt;</ph>EnableFastCombine<ph id="ph2">&amp;gt;</ph><ept id="p1">**</ept> element with a value of true to the config file. Adding this element will turn <bpt id="p1">**</bpt>Fast Combine<ept id="p1">**</ept> on.

    <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
    
    ![](media/powerbi-refresh-enable-fast-combine/configfile.png)

3.  Exit and re-launch the gateway configuration screen.

4.  You will see a status letting you know that Fast Combine is enabled.

    ![](media/powerbi-refresh-enable-fast-combine/fastcombineenabled.png)

## Turn off Fast Combine

1. Open <bpt id="p1">**</bpt>ConnectorConfig.xml<ept id="p1">**</ept>.  This may be in one of two locations on your machine.  If you are an administrator on the computer, it will be the following.

    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

    If you are not an administrator, the location will be the following.

    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2.  Remove the <bpt id="p1">**</bpt><ph id="ph1">&amp;lt;</ph>EnableFastCombine<ph id="ph2">&amp;gt;</ph><ept id="p1">**</ept> element from the config file. Removing this element will turn <bpt id="p1">**</bpt>Fast Combine<ept id="p1">**</ept> off.

3.  Exit and re-launch the gateway configuration screen.

4.  You will no longer see a status telling you know that <bpt id="p1">**</bpt>Fast Combine<ept id="p1">**</ept> is enabled.


## 請參閱

[Privacy Levels](https://support.office.com/en-us/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Common query tasks in Power BI Desktop](powerbi-desktop-common-query-tasks.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
