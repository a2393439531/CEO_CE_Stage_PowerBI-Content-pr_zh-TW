<properties pageTitle="Documentation Example - Tags" metaKeywords="" description="This is an example document" services="" documentationCenter="" title="Documentation Example - Tags" solutions="" authors="" videoId="" scriptId="" />

<tags ms.service="AzureWebSites" ms.devlang="CSharp" ms.topic="home-page" ms.tgt_pltfrm="Windows" ms.workload="50" ms.date="06/12/2014" ms.author="maurok;v-nabeni@microsoft.com;lito@mail.com" />

# Example - Tags #

This is a sample documentation article that is used to test and validate the publishing system for Azure.com.  

The example <ph id="ph1">`&lt;tags /&gt;`</ph> element can be found right below the <ph id="ph2">`&lt;properties /&gt;`</ph> element at the beginning of the document.

Unless otherwise specified (e.g. for ms.date), values should be restricted to alphanumeric  characters and hyphens and the length of the value should be restricted to 30 characters.

There are 7 required attributes for the tags element: 

- <bpt id="p1">**</bpt>ms.service<ept id="p1">**</ept>: Specifies the Azure service, tool, or feature that the article applies to.

- <bpt id="p1">**</bpt>ms.devlang<ept id="p1">**</ept>: Specifies the programming language that the article applies to.

- <bpt id="p1">**</bpt>ms.topic<ept id="p1">**</ept>: Specifies the topic type.

    > <bpt id="p1">**</bpt>Valid Values<ept id="p1">**</ept>: <bpt id="p2">*</bpt>article, hero-article, reference, index-page, campaign-page, video-page, infographic-page, home-page, service-home-page, dev-center-home-page, site-section-home-page<ept id="p2">*</ept>  

- <bpt id="p1">**</bpt>ms.tgt_pltfrm<ept id="p1">**</ept>: Specifies the target platform, for instance Windows, Linux, Windows Phone, iOS, or Android.

- <bpt id="p1">**</bpt>ms.workload<ept id="p1">**</ept>: Specifies a C&amp;E workload to which the topic applies to.

- <bpt id="p1">**</bpt>ms.date<ept id="p1">**</ept>: Specifies the last updated date for the topic.

    > “04/10/2014”

- <bpt id="p1">**</bpt>ms.author<ept id="p1">**</ept>: Specifies the author(s) associated with the topic. 若要指定多個值，您應該以分號將值分開。

    > <bpt id="p1">**</bpt>Valid Values<ept id="p1">**</ept>: Microsoft aliases and complete email addresses. Length should be no longer than 200 characters.


Here's an example of a valid the tags element:

````XML
<tags ms.service="AzureWebSites" ms.devlang="CSharp" ms.topic="home-page" ms.tgt_pltfrm="Windows" ms.workload="50" ms.date="06/12/2014" ms.author="maurok;v-nabeni@microsoft.com;lito@mail.com" />
````


---