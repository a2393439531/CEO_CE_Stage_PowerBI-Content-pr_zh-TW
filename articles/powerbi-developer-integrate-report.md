<properties
   pageTitle="將 Power BI 報表整合到應用程式"
   description="若要將報告整合到應用程式的逐步解說的範例程式碼"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# 將報告整合到應用程式

## 簡介

在本逐步解說中，整合，或內嵌，請使用 C# 的 web 應用程式的報表和 **Power BI** API、 一些 JavaScript 程式碼和 IFrame。

>
            **請注意**︰ 若要開始使用本逐步解說，您需要 **Power BI** 帳戶。 如果您沒有帳戶，請參閱 [註冊 Power BI]( powerbi-admin-free-with-custom-azure-directory.md)。

若要將報表整合到 web 應用程式，您使用 **Power BI** API 和 Azure Active Directory (AD) 授權 **存取權杖** 以取得報告。 然後，您載入至報表 **IFrame** 使用相同的存取語彙基元。  **Power BI** API 提供以程式設計方式存取特定 **Power BI** 資源。 請參閱 [Power BI REST API 概觀](https://msdn.microsoft.com/library/dn877544.aspx)。 下圖顯示將報告整合的一般流程。

![](media\powerbi-developer-integrate-report\integrate-report-flow.png)

以下是整合，或將內嵌到網頁的報表的步驟。

>
            **請注意**︰ 本文將說明使用中的程式碼 [整合報表範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app) GitHub 上。 若要依照本逐步解說，您應該下載範例。 若要執行範例時，請參閱 [設定整合的報表範例](powerbi-developer-integrate-report-register.md#configure-sample) 中註冊 web 應用程式與 Azure AD 的步驟。

## 若要將報告整合到應用程式的步驟

- 
            [步驟 1︰ 註冊 web 應用程式與 Azure AD](powerbi-developer-integrate-report-register.md)。 您必須註冊您的 web 應用程式與 **Azure Active Directory (AD)** 讓 Azure AD 可以識別您的應用程式，當您需要存取 **Power BI** 報表。
- [步驟 2︰ 取得 Power BI 報表](powerbi-developer-integrate-report-get-report.md)
- [步驟 3︰ 將 IFrame 載入 Power BI 報表](powerbi-developer-integrate-report-load-report-iframe.md)
- [將報告整合到應用程式程式碼清單](powerbi-developer-integrate-report-code.md)

## 下一個步驟

在下一個步驟中，您了解如何 [向 Azure AD 註冊 web 應用程式](powerbi-developer-integrate-report-register.md) 取得 **用戶端識別碼** 和 **用戶端密碼** 來驗證 web 應用程式與 **Azure AD**。 用戶端識別碼和用戶端密碼用來識別您的應用程式在 Azure AD 中。 取得之後 **用戶端識別碼** 和 **用戶端密碼**, ，您可以設定 [整合報表範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)。 請參閱 [設定整合的報表範例](powerbi-developer-integrate-report-register.md#configure-sample)。

[下一步 >](powerbi-developer-integrate-report-register.md)

## 請參閱

[註冊 Power BI]( powerbi-admin-free-with-custom-azure-directory.md)  
[整合的報表範例](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  
[設定整合的報表範例](powerbi-developer-integrate-report-register.md#configure-sample)  
[步驟 1︰ 使用 Azure AD 註冊 web 應用程式](powerbi-developer-integrate-report-register.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)