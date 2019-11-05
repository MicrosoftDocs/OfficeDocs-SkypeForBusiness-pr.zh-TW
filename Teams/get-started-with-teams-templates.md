---
title: 開始使用 Teams 範本
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用團隊範本來建立擁有預先定義頻道的小組。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 378977e86854f3c4b2192017fa10ce19aeb4990e
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968314"
---
# <a name="get-started-with-teams-templates"></a>開始使用 Teams 範本

> [!NOTE]
> 團隊範本目前不支援建立專用頻道。 範本定義中不包含專用通道建立。 

團隊範本是預先建立的小組結構定義，它是圍繞業務需求或專案設計的。 您可以使用團隊範本快速建立豐富的共同作業空間，並提供不同主題和預先安裝應用程式的頻道，以納入重要的內容和服務。 團隊範本提供預先定義的小組結構，可協助您在組織中輕鬆建立一致的團隊。 

在本文中，我們將說明可在範本中定義的屬性、基底範本類型，以及如何使用幾個範例要求來從範本建立小組。
 
本文適用于您（如果您是：

- 負責規劃、部署及管理整個組織中的多個團隊<br>
- 開發人員想要以程式設計方式使用預先定義的頻道和應用程式建立小組

## <a name="teams-template-capabilities"></a>團隊範本功能

小組中的大部分屬性都包含在範本中並受到支援。 但目前不支援某些屬性和功能。 下表提供 [摘要]，簡要說明團隊範本中包含的內容和不包含的內容。

| **團隊範本支援的團隊屬性** | **團隊範本尚不支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基底範本類型 | 小組成員資格 |
| 團隊名稱 | 小組圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可見度（公開或私人） | 連接線 |
| 團隊設定（例如 [成員]、[來賓]、[@ 提及]） | 檔案和內容 |
| 自動常用頻道 | |
| 已安裝的應用程式 | |
| 釘選索引標籤 | |

> [!NOTE]
> 我們將在未來版本的 Microsoft 團隊中新增更多範本功能，因此請返回支援屬性的最新資訊。

## <a name="what-are-base-template-types"></a>什麼是基本範本類型？

基底範本類型是 Microsoft 針對特定行業建立的特殊範本。 這些基本範本通常包含無法在 [書店] 和 [小組] 範本中個別不支援的 [店鋪] 和 [團隊屬性] 中提供的專有 app。

一旦定義基底範本類型之後，您就可以使用您想要指定的其他屬性來延伸或覆寫這些特殊範本。 但某些基底範本類型包含無法重寫的屬性。

根據預設，基本範本會設定為**標準**，不包含任何其他專屬 app 或特殊屬性。 以下是可用的基本範本類型的目前清單。

| 基底範本類型 | baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 標準 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 沒有其他 app 和屬性 |
| 學習<br>課程小組 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | 應用<ul><li>OneNote 課程筆記本（已固定至 **[一般**] 索引標籤） </li><li>作業應用程式（釘選到 [**一般**] 索引標籤）</li></ul> 團隊屬性：<ul><li>團隊可見度設定為**HiddenMembership** （不能重寫）</li></ul> |
| 學習<br>員工小組 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | 應用<ul><li>OneNote 教職員筆記本（已固定至 **[一般**] 索引標籤）</li></ul> |
|學習<br>PLC 小組 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 應用<ul><li>OneNote PLC 筆記本（已固定至 **[一般**] 索引標籤）</ul></li>|
| 面向<br>存放 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | 管道<ul><li>倒班切換</li><li>教學</li></ul>團隊屬性<ul><li>將團隊可見度設定為 Public</li></ul>成員許可權<ul><li>避免成員建立、更新或移除頻道</li><li>防止成員新增或移除應用程式</li><li>防止成員建立、更新或移除連接器</li></ul> |
| 面向<br>Manager 共同作業 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | 管道<ul><li>倒班切換</li><li>教學</li></ul>團隊屬性：<ul><li>[團隊可見度] 設定為 [私人]</li></ul>成員許可權：<ul><li>避免成員建立、更新或移除頻道</li><li>防止成員新增或移除應用程式</li><li>防止成員建立、更新或移除連接器</li></ul>|
| 健康<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |管道 <ul><li>公告\*</li><li>Huddles\*</li><li>輪</li><li>人員\*</li><li>訓練\*</li></ul>\*自動將通道 |
|健康<br>醫院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |管道<ul><li>公告\*</li><li>從屬\*</li><li>Custodial</li><li>人力資源</li></li><li>藥房</li></ul>\*自動將通道|
|||

> [!NOTE]
> 我們將在未來版本的 Microsoft 團隊中新增更多基本範本類型，因此請返回支援屬性的最新資訊。

## <a name="related-topics"></a>相關主題

- [建立小組](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)（在預覽中）
- [新團隊](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft 團隊的系統管理訓練](itadmin-readiness.md)
- [開始使用適用於零售業的 Teams 範本](get-started-with-retail-teams-templates.md)
- [開始使用適用於醫療保健組織的 Teams 範本](expand-teams-across-your-org/healthcare/healthcare-templates.md)
