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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19c6676bb742deacf97afae54f29b369d551b9ae
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007763"
---
# <a name="use-financial-team-templates"></a>使用金融團隊組範本

Microsoft Teams 的團隊範本提供預先定義的設定、頻道和預先安裝應用程式的團隊結構, 讓您快速且輕鬆地建立團隊。

對於金融服務組織來說, 團隊範本可能功能特別強大, 因為它們可協助您在整個組織中快速部署一致的團隊。 範本也可以協助職員瞭解如何有效地使用 Teams。

Teams 中包括專為金融服務組織設計的範本。 使用這些預先建立的範本快速建立團隊, 讓職員溝通及共同作業。 本文將介紹各個 Teams 範本, 並建議如何使用範本。

管理及使用團隊範本的方式取決於您是系統管理員或開發人員。

|如果您是: | 那麼, 您: |
| ---- | --------- |
| 系統管理員或 IT 專業人員 |[在 Teams 系統管理中心管理團隊範本](#manage-team-templates-in-the-teams-admin-center)。 查看團隊範本並申請範本原則, 以控制職員在 Teams 中建立團隊時可使用的範本。 |
| 開發人員 | [使用 Microsoft Graph](#use-team-templates-with-microsoft-graph)從團隊範本建立團隊。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理團隊範本

身為系統管理員, 您可以在 Microsoft Teams 系統管理中心管理團隊範本。 您可以在這裡檢視每個範本的詳細資訊。 您也可以[建立及指派範本原則](templates-policies.md)給職員, 以控制他們在 Teams 中[建立團隊](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)時看到的範本。

若要深入了解一般團隊範本, 請參閱[在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。

我們目前為金融服務組織提供下列預先建立的團隊範本。 若要查看, 請前往 Teams 系統管理中心左側版面配置, 前往 **Teams** > **團隊範本**。

### <a name="collaborate-within-a-bank-branch"></a>在銀行分支機搆內共同作業

集中管理銀行分行員工在小型會議、客戶會議、商務程序 (例如貸款共同作業) 的共同作業，讓每個人都能透過公告和讚美掌握最新狀態。

| 範本類型 |TemplateId| 此範本提供的屬性 |
| ------------------ |--|----------------------------------------------------- |
|銀行分行| `CollaborateWithinABankBranch`|頻道： <ul><li>一般<li>公告</li><li>過程中討論</li><li>客戶會議</li><li>核准要求 </li><li>指導</li><li>技能開發</li><li>借貸處理</li><li>客戶投訴</li><li>讚美</li><li>趣味內容</li><li>合規性</li></ul>應用程式：<ul><li>稱讚 </li><li>問題報告者</li><li>Wiki</li><li>行事曆</li><li>核准</li><li>佈告欄</li><li>構想</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>以 Microsoft Graph 使用團隊範本

開發人員可以使用 Microsoft Graph 從預先建立的團隊範本建立團隊。 若要深入了解以 Microsoft Graph 使用團隊範本, 請參閱[開始用 Microsoft Graph 使用團隊範本](get-started-with-teams-templates.md), [Microsoft Teams API 概觀](/graph/teams-concept-overview?view=graph-rest-1.0), 和 [teamsTemplate 資源類型](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

### <a name="bank-branch"></a>銀行分行

集中管理銀行分行員工在小型會議、客戶會議、商務程序 (例如貸款共同作業) 的共同作業，讓每個人都能透過公告和讚美掌握最新狀態。

| 範本類型 |TemplateId| 範本頻道 |
| ------------------ |--|----------------------------------------------------- |
|銀行分行|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|一般<br>公告<br>過程中討論<br>客戶會議<br>核准要求<br>指導<br>技能開發<br>借貸處理<br>客戶投訴<br>讚美<br>趣味內容<br>合規性|
||||

> [!NOTE]
> 有關適用于金融服務組織的其他團隊範本，請參閱 [Microsoft Graph 中為中小型企業所建的團隊範本](smb-templates.md)。