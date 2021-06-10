---
title: 開始使用 Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Microsoft 中使用小組範本Graph不同主題的頻道建立共同合作空間，並預先安裝應用程式以提供內容和服務。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0208b8c6ad16cc42611768a25237a6e48bf60401
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717824"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>開始使用 Microsoft Graph

> [!NOTE]
> 小組範本目前不支援建立私人頻道。 範本定義中不包含私人頻道建立功能。

小組範本是專為業務需求或專案所設計的小組結構預先建立的定義。 您可以在系統 [管理主控台中建立自己的範本](get-started-with-teams-templates-in-the-admin-console.md)。 使用 Microsoft Graph，您可以使用預先建建的範本。 您可以使用小組範本，以不同主題的頻道快速建立豐富的共同合作空間，並預先安裝 App 以提取任務關鍵型內容和服務。 小組範本提供預先定義的小組結構，可協助您輕鬆建立整個組織的一致團隊。

本文將說明可在範本中定義的屬性、什麼是基本範本類型，以及如何使用一些範例要求從範本建立團隊。

如果您是：

- 負責規劃、部署及管理貴組織的多個團隊<br>
- 開發人員想要以程式化方式建立具有預先定義的頻道和應用程式的團隊

## <a name="team-template-capabilities"></a>小組範本功能

範本會包含及支援小組中的大部分屬性。 但目前不支援一些屬性和功能。 下表提供小組範本中不包含的內容的快速摘要。

| **小組範本支援的小組屬性** | **小組範本尚未支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 範本類型 | 團隊成員資格 |
| 團隊名稱 | 小組圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可見度 (公開或私人)  | 連接器 |
| 團隊設定 (例如成員、來賓、@ 提及)  | 檔案和內容 |
| 自動最愛的頻道 | |
| 已安裝的應用程式 | |
| 釘上定位點 | |

> [!NOTE]
> 我們會在未來版本中新增更多範本功能Microsoft Teams，因此請回來查看支援屬性上最新的資訊。

## <a name="what-are-base-template-types"></a>什麼是基本範本類型

基本範本類型是 Microsoft 針對特定產業所建立的特殊範本。 這些基本範本通常包含市售中無法提供的專屬應用程式。 此外，基本範本通常包含小組範本中尚未個別支援的團隊屬性。 瞭解如何在 Microsoft Graph 中[Graph。](get-started-with-teams-templates.md)

定義基本範本類型之後，您可以使用要指定的其他屬性來延伸或覆蓋這些特殊範本。 某些基本範本類型包含無法重寫的屬性。

根據預設，基本範本會設定為 **標準**，其中不包含任何其他專屬應用程式或特殊屬性。 以下是目前可用的基本範本類型清單。

| 範本類型 | baseTemplateId | 此基本範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 標準 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 沒有額外的應用程式和屬性 |
| 教育 -<br>課程小組 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 應用程式：<ul><li>OneNote課程筆記本 (釘到一般 **)** </li><li>作業應用程式 (釘到的一般 **)**</li></ul> 小組屬性：<ul><li>小組可見度設定為 **HiddenMembership (** 無法) </li></ul> |
| 教育 -<br>教職員團隊 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 應用程式：<ul><li>OneNote已釘 (到一 **般卷)**</li></ul> |
|教育 -<br>PLC 小組 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 應用程式：<ul><li>OneNotePLC 筆記本 (釘到一般 **)**</ul></li>|
| 零售業 -<br>商店 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailStore')` | 頻道：<ul><li>班次交班</li><li>學習</li></ul>團隊屬性<ul><li>團隊可見度設定為公開</li></ul>成員權限<ul><li>防止成員建立、更新或移除頻道</li><li>防止成員新增或移除應用程式</li><li>防止成員建立、更新或移除連接器</li></ul> |
| 零售業 -<br>管理員共同合作 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailManagerCollaboration')` | 頻道：<ul><li>學習</li><li>營運</li></ul>小組屬性：<ul><li>團隊可見度設定為私人</li></ul>成員許可權：<ul><li>防止成員建立、更新或移除頻道</li><li>防止成員新增或移除應用程式</li><li>防止成員建立、更新或移除連接器</li></ul>|
| 醫療保健 -<br>病房 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareWard')` |頻道： <ul><li>公告\*</li><li>過程中討論\*</li><li>輪次</li><li>人員\*</li><li>訓練\*</li></ul>\*自動將頻道加入我的最愛 |
|醫療保健 -<br>醫院 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareHospital')` |頻道：<ul><li>公告\*</li><li>合規性\*</li><li>監管</li><li>人力資源</li></li><li>藥品部</li></ul>\*自動最愛的頻道|
|||


使用下列範本在用戶端和 Microsoft Teams中建立Graph。


| 範本類型 | baseTemplateId | 此基本範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 採用Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  頻道： <ul><li>一般</li> <li>公告</li> <li>冠軍角</li> <li>小組表單</li></ul> 應用程式： <ul><li>Wiki</li>  <li>行事曆</li> |
| 管理專案 |`com.microsoft.teams.template.`<br>`ManageAProject`| 頻道： <ul><li>一般</li> <li>公告</li> <li>資源</li> <li>規劃</li></ul> 應用程式：<ul><li>Wiki</li><li>OneNote</li></ul> |
| 管理活動|`com.microsoft.teams.template.`<br>`ManageAnEvent` | 頻道： <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷與公關</li></ul> 應用程式：<ul><li>Wiki</li><li>網站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|員工上機|`com.microsoft.teams.template.`<br>`OnboardEmployees` | 頻道： <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用程式：<ul><li>Wiki</li><li>社區</li></ul>|
|組織服務台| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|頻道：<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用程式：<ul><li>Wiki</li><li>OneNote</li></ul> |
| 在病患照護上共同作業| `healthcareWard `| 頻道：<ul><li>一般</li><li>公告</li><li>過程中討論</li><li>輪次</li><li>人員</li><li>訓練</li></ul> 應用程式： <ul><li>Wiki</li>|
| 在全球危機或事件上共同合作 |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| 頻道： <ul><li>一般<li>公告</li><li>世界新訊</li><li>業務連續性</li><li>遠端工作</li><li>內部通訊</li><li>外部通訊</li><li>客戶抱怨</li><li>榮譽</li><li>主管更新</li></ul>應用程式： <ul><li>稱讚</li><li>Wiki</li><li>網站</li></ul>|
|在銀行分行內共同合作| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|頻道： <ul><li>一般<li>公告</li><li>過程中討論</li><li>客戶會議</li><li>教練</li><li>技能開發</li><li>貸款處理</li><li>客戶抱怨</li><li>榮譽</li><li>有趣的專案</li><li>合規性</li></ul>|
|協調事件回應| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|頻道： <ul><li>一般<li>公告</li><li>物流</li><li>規劃</li><li>恢復</li><li>緊急</li></ul> 應用程式： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|醫院| `healthcareHospita`我 |頻道： <ul><li>一般<li>公告</li><li>合規性</li><li>監管</li><li>人力資源</li><li>藥品部</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
|組織商店| `retailStore` |頻道： <ul><li>一般<li>班次交班</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
|品質和安全性 |`com.microsoft.teams.`<br>`template.QualitySafety`|頻道： <ul><li>一般<li>公告</li><li>第 1 行</li><li>第 2 行</li><li>第 3 行</li><li>安全</li><li>訓練</li><li>維護</li><li>有趣的專案</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
|零售 - 主管共同作業| `retailManagerCollaboration` |頻道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
||||

請參閱 [在系統管理中心開始使用小組](get-started-with-teams-templates-in-the-admin-console.md) 範本以取得詳細資料。

## <a name="related-topics"></a>相關主題

- [在系統管理主控台中開始使用小組範本](get-started-with-teams-templates-in-the-admin-console.md)
- [在預覽 (](/graph/api/team-post?view=graph-rest-beta) 中建立) 
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
- [系統管理訓練Microsoft Teams](itadmin-readiness.md)
