<properties
pageTitle="使用 Power BI Desktop 的資料列層級安全性 (RLS)"
description="如何設定匯入的資料集和 DirectQuery，Power BI Desktop 中的資料列層級安全性。"
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
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="09/21/2016"
ms.author="asaxton"/>
# 使用 Power BI Desktop 的資料列層級安全性 (RLS)

使用 Power BI Desktop 的資料列層級安全性 (RLS) 可以用來限制資料存取，針對指定的使用者。 篩選器會限制資料列層級的資料。 您可以定義在角色中的篩選器。

> [AZURE.NOTE] RLS 是 Pro 功能。 您可以進一步瞭解 [Pro 內容](powerbi-power-bi-pro-content-what-is-it.md) 是。

您現在可以設定 RLS 匯入 Power BI 使用 Power BI Desktop 資料模型。 您也可以使用 DirectQuery，例如 SQL Server 的資料集上設定 RLS。 之前，您便只能夠在內部部署 Analysis Services 模型在 Power BI 外部實作 RLS。 Analysis Services 即時連接，您可以設定資料列層級安全性之內部模型上。 [安全性] 選項不會顯示即時連接的資料集。

> [AZURE.IMPORTANT] 如果您定義角色/規則 Power BI 服務中，您必須重新建立這些 Power BI Desktop 中的角色，並將報表發行至服務。

深入了解選項 [Power BI 服務內的 RLS](powerbi-admin-rls.md)。

[AZURE.INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-limitations.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-faq.md)]

## 請參閱

[Power BI 服務的資料列層級安全性 (RLS)](powerbi-admin-rls.md)  
更多的問題嗎？ [試用 Power BI 社群](http://community.powerbi.com/)