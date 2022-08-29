---
title: 開始用 Microsoft Graph 使用團隊範本
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
description: 瞭解只有 Microsoft Graph 才能使用的團隊範本。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4251aa0293665b6fd41c66e352ca9c595378259
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397234"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>開始用 Microsoft Graph 使用團隊範本

> [!NOTE]
> 團隊範本目前不支援建立私人頻道。 範本定義中不包含私人頻道建立。

Microsoft Teams 中的團隊範本是針對業務需求或專案所設計的團隊結構定義。 使用團隊範本，您可以使用預先定義的設定、頻道和應用程式，快速且輕鬆地建立豐富的共同作業空間。 團隊範本可協助您在整個組織中部署一致的團隊。

您可以使用 Microsoft Graph [建立自己的範本](/graph/api/resources/teamtemplate?view=graph-rest-beta) ，或使用 Teams 隨附的預先建置團隊範本來建立團隊。 在本文中，您將瞭解可以在範本中定義的屬性，以及只有 Microsoft Graph 才能使用的預先建立範本。

如果您有下列情況，請參閱這篇文章：

- 負責在整個組織中規劃、部署和管理多個小組<br>
- 想要以程式設計方式建立具有預先定義通道和應用程式之團隊的開發人員

## <a name="team-template-capabilities"></a>團隊範本功能

範本會包含並支援小組中的大部分屬性。 但目前不支援一些屬性和功能。 以下是團隊範本中包含的內容和未包含內容的快速摘要。

| **小組範本支援的團隊屬性** | **小組範本尚未支援小組屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 範本類型 | 團隊成員資格 |
| 小組名稱 | 團隊圖片 |
| 團隊描述 | 頻道設定 |
| 公開或私人)  (小組可見度 | 連接器 |
| 團隊設定 (例如成員、來賓、@ 提及)  | 檔案和內容 |
| 自動加入我的最愛頻道 | |
| 已安裝的應用程式 | |
| 已釘選的索引標籤 | |

> [!NOTE]
> 我們會在未來的 Microsoft Teams 版本中新增更多範本功能，因此請返回查看支援內容的最新資訊。

## <a name="pre-built-templates"></a>預先建立的範本

預先建立的小組範本是我們為特定產業建立的範本。 以下是僅適用于 Microsoft Graph 的預先建立範本。

| 範本類型 | TemplateId | 此範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 標準 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 沒有其他應用程式和屬性 |
| 教育版 -<br>班級團隊 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 應用程式：<ul><li>OneNote 課程筆記本 (釘選到 [ **一般** ] 索引標籤)  </li><li>[作業] 應用程式 (釘選到 [ **一般** ] 索引標籤) </li></ul> 小組內容：<ul><li>將團隊可見度設定為 **HiddenMembership** (無法覆寫) </li></ul> |
| 教育版 -<br>教職員小組 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 應用程式：<ul><li>OneNote 教職員筆記本 (釘選到 [ **一般** ] 索引標籤) </li></ul> |
|教育版 -<br>PLC 小組 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 應用程式：<ul><li>OneNote PLC 筆記本 (釘選到 [ **一般** ] 索引標籤) </ul></li>|

> [!NOTE]
> 如需您可以在 Teams 用戶端和 Microsoft Graph 中使用的預先建置範本清單，請參閱開始使用 Teams 系統管理 [中心的團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="related-articles"></a>相關文章

- [在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)
- [在](/graph/api/team-post?view=graph-rest-beta) 預覽) 中建立團隊 (
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
