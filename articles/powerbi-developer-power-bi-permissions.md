<properties
   pageTitle="Power BI 權限"
   description="Power BI 權限"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Power BI 權限

## 權限範圍
Power BI 權限給應用程式代表使用者採取某些動作的能力。 所有的權限必須經由使用者核准，才會有效。

|顯示名稱|描述|範圍值|
|---|---|---|
|檢視所有資料集|應用程式可以檢視已登入使用者的所有資料集和資料集的使用者具有存取權。|Dataset.Read.All|
|讀取和寫入所有資料集|可以檢視應用程式，並將它寫入使用者具有存取權的登入的使用者和資料集的所有資料集。|Dataset.ReadWrite.All|
|檢視使用者群組|應用程式可以檢視所有已登入使用者所屬的群組。|Group.Read.All|
|檢視所有儀表板 （預覽）|應用程式可以檢視已登入使用者的所有儀表板和儀表板使用者具有存取權。|Dashboard.Read.All|
|檢視所有報告 （預覽）|應用程式可以檢視已登入使用者的所有報表和報表以及使用者所擁有的存取權。 應用程式也可以查看報表，以及其結構內的資料。|Report.Read.All|

第一次嘗試透過傳入要求的權限的範圍參數中呼叫的登入使用者的頁面時，應用程式可以要求權限。 如果授與權限，存取權杖會傳回可用來在後續的 API 呼叫的應用程式。 存取只用於特定應用程式。

## 要求權限
雖然您可以呼叫 API 來驗證使用者名稱和密碼，以便採取動作代表其他使用者，他們必須要求使用者再核准的權限，然後將產生的存取權杖傳送的所有後續的呼叫。 此程序，我們會遵循標準 [OAuth 2.0](http://oauth.net/2/) 通訊協定。 實際的實作可能有所不同，Power BI 的 OAuth 流程包含下列項目︰

- 
            **登入 UI** -這是開發人員可呼叫以要求權限的 UI。 這需要使用者在沒有已登。 使用者也必須核准應用程式所要求的權限。 登入視窗會回傳存取程式碼或錯誤訊息會提供重新導向 url。
    - 標準的重新導向 URL 應該提供由 Power BI 使用原生應用程式。
- 
            **授權碼** -授權碼會傳回至 web 應用程式登入後透過 URL 重新導向 URL 中的參數。 因為它們都在參數會有些安全性風險。 Web 應用程式必須交換授權權杖的授權碼
- 
            **授權權杖** -用來驗證使用者代表的 API 呼叫。 它們將限於特定的應用程式。 權杖有設定期限和到期時就會需要重新整理。
- 
            **重新整理權杖** -權杖到期時將會有加以重新整理的程序。

更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)
