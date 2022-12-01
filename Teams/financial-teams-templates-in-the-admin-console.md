---
title: 使用金融團隊組範本
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何在 Teams 系統管理中心管理及使用金融團隊範本, 以及使用 Microsoft Graph 快速且輕鬆地為金融服務組織建立團隊。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 096bab4289d5ac9e81c63f83cd73efd41d98e7be
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198686"
---
# <a name="use-financial-team-templates"></a>使用金融團隊組範本

Microsoft Teams 的團隊範本提供預先定義的設定、頻道和預先安裝應用程式的團隊結構, 讓您快速且輕鬆地建立團隊。

對於金融服務組織來說, 團隊範本可能功能特別強大, 因為它們可協助您在整個組織中快速部署一致的團隊。 範本也可以協助職員瞭解如何有效地使用 Teams。

Teams 中包括專為金融服務組織設計的範本。 使用這些預先建立的範本快速建立團隊, 讓職員溝通及共同作業。 本文將介紹各個 Teams 範本, 並建議如何使用範本。

管理及使用團隊範本的方式取決於您是系統管理員或開發人員。

|如果您是: | 那麼, 您: |
| ---- | --------- |
| 系統管理員或 IT 專業人員 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 開發人員 | [使用 Microsoft Graph](#use-team-templates-with-microsoft-graph)從團隊範本建立團隊。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理團隊範本

身為系統管理員, 您可以在 Microsoft Teams 系統管理中心管理團隊範本。 您可以在這裡檢視每個範本的詳細資訊。 您也可以[建立及指派範本原則](templates-policies.md)給職員, 以控制他們在 Teams 中[建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)時看到的範本。

若要深入瞭解一般團隊範本, 請參閱[在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。

我們目前為金融服務組織提供下列預先建立的團隊範本。 若要查看, 請前往 Teams 系統管理中心左側版面配置, 前往 **Teams** > **團隊範本**。

### <a name="collaborate-within-a-bank-branch"></a>在銀行分支機搆內共同作業

集中管理銀行分行員工在小型會議、客戶會議、商務程序 (例如貸款共同作業) 的共同作業，讓每個人都能透過公告和讚美掌握最新狀態。

| 範本類型 |TemplateId| 此範本提供的屬性 |
| ------------------ |--|----------------------------------------------------- |
|銀行分行| `CollaborateWithinABankBranch`|頻道： <ul><li>一般<li>公告</li><li>過程中討論</li><li>客戶會議</li><li>核准要求 </li><li>指導</li><li>技能開發</li><li>借貸處理</li><li>客戶投訴</li><li>讚美</li><li>趣味內容</li><li>合規性</li></ul>應用程式：<ul><li>稱讚 </li><li>問題報告者</li><li>Wiki</li><li>行事曆</li><li>核准</li><li>佈告欄</li><li>構想</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>以 Microsoft Graph 使用團隊範本

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0&preserve-view=true), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0&preserve-view=true).

### <a name="bank-branch"></a>銀行分行

集中管理銀行分行員工在小型會議、客戶會議、商務程序 (例如貸款共同作業) 的共同作業，讓每個人都能透過公告和讚美掌握最新狀態。

| 範本類型 |TemplateId| 範本頻道 |
| ------------------ |--|----------------------------------------------------- |
|銀行分行|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|一般<br>公告<br>過程中討論<br>客戶會議<br>核准要求<br>指導<br>技能開發<br>借貸處理<br>客戶投訴<br>讚美<br>趣味內容<br>合規性|
||||

> [!NOTE]
> 有關適用于金融服務組織的其他團隊範本，請參閱 [Microsoft Graph 中為中小型企業所建的團隊範本](smb-templates.md)。

## <a name="related-articles"></a>相關文章

- [在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)
- [從範本建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [開始用 Microsoft Graph 使用團隊範本](get-started-with-teams-templates.md)