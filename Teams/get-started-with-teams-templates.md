---
title: 開始使用 Microsoft Graph
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
description: 瞭解只有 Microsoft Graph。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991112"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>開始使用 Microsoft Graph

> [!NOTE]
> 小組範本目前不支援建立私人頻道。 範本定義中不包含私人頻道建立功能。

團隊範本Microsoft Teams是圍繞業務需求或專案所設計之團隊結構的定義。 使用小組範本，您可以使用預先定義的設定、頻道和應用程式，快速且輕鬆地建立豐富的共同合作空間。 小組範本可協助您在整個組織中部署一致的團隊。

使用 Microsoft Graph，您可以使用預先建立的團隊範本，這些範本會包含在 Teams中，以建立團隊。 在本文中，您將瞭解可在範本中定義的屬性，以及只有 Microsoft Graph。

如果您是：

- 負責規劃、部署及管理整個組織的多個團隊<br>
- 開發人員想要以程式化方式建立具有預先定義的頻道和應用程式的團隊

## <a name="team-template-capabilities"></a>小組範本功能

範本會包含及支援小組中的大部分屬性。 但目前不支援一些屬性和功能。 以下是小組範本中不包含的內容的快速摘要。

| **小組範本支援的小組屬性** | **小組範本尚未支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 範本類型 | 團隊成員資格 |
| 小組名稱 | 小組圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可見度 (公開或私人)  | 連接 |
| 團隊設定 (例如成員、來賓、@ 提及)  | 檔案和內容 |
| 自動最愛的頻道 | |
| 已安裝的應用程式 | |
| 釘上定位點 | |

> [!NOTE]
> 我們會在未來版本中新增更多範本功能Microsoft Teams，因此請回來查看支援屬性上最新的資訊。

## <a name="pre-built-templates"></a>預先建立範本

預先建立的團隊範本是我們為特定產業所建立範本。 以下是僅適用于 Microsoft Graph 的預先建立Graph。

| 範本類型 | TemplateId | 此範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 標準 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 沒有額外的應用程式和屬性 |
| 教育 -<br>課程小組 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 應用程式：<ul><li>OneNote課程筆記本 (釘到的一般 **)** </li><li>作業應用程式 (釘到的一般 **)**</li></ul> 小組屬性：<ul><li>小組可見度設定為 **HiddenMembership (** 無法) </li></ul> |
| 教育 -<br>教職員團隊 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 應用程式：<ul><li>OneNote已釘 (到一般卷) </li></ul> |
|教育 -<br>PLC 小組 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 應用程式：<ul><li>OneNotePLC 筆記本 (釘到的一般 **)**</ul></li>|

> [!NOTE]
> 有關可在 Teams 用戶端及 Microsoft Graph 中使用的預先建立範本清單，請參閱在系統管理中心Teams[範本](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="related-articles"></a>相關文章

- [在系統管理中心開始使用Teams範本](get-started-with-teams-templates-in-the-admin-console.md)
- [在預覽 (](/graph/api/team-post?view=graph-rest-beta) 中建立) 
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
