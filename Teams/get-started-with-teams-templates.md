---
title: 使用 Microsoft Graph 快速開始使用團隊範本
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
description: 瞭解如何使用 Microsoft Graph 中的團隊範本建立共同作業空間，並提供不同主題的頻道與預先安裝應用程式，以提供內容和服務。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772194"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>使用 Microsoft Graph 快速開始使用團隊範本

> [!NOTE]
> 團隊範本目前不支援建立專用頻道。 範本定義中不包含專用通道建立。

團隊範本是預先建立的小組結構定義，它是圍繞業務需求或專案設計的。 您可以 [在系統管理主控台中建立您自己的範本](get-started-with-teams-templates-in-the-admin-console.md)。 透過 Microsoft Graph，您可以使用預先建立的範本。 您可以使用團隊範本快速建立豐富的共同作業空間，並提供不同主題和預先安裝應用程式的頻道，以納入重要的內容和服務。 團隊範本提供預先定義的小組結構，可協助您在組織中輕鬆建立一致的團隊。

在本文中，我們將說明可在範本中定義的屬性、基底範本類型，以及如何使用幾個範例要求來從範本建立小組。

本文適用于您（如果您是：

- 負責規劃、部署及管理整個組織中的多個團隊<br>
- 開發人員想要以程式設計方式使用預先定義的頻道和應用程式建立小組

## <a name="teams-template-capabilities"></a>團隊範本功能

小組中的大部分屬性都包含在範本中並受到支援。 但目前尚不支援一些屬性和功能。 下表提供 [摘要]，簡要說明團隊範本中包含的內容和不包含的內容。

| **團隊範本支援的團隊屬性** | **團隊範本尚不支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基底範本類型 | 團隊成員資格 |
| 團隊名稱 | 小組圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可視性 (公開或私人)  | 連接器 |
| 小組設定 (例如 [成員]、[來賓]、[@ 提及])  | 檔案和內容 |
| 自動常用頻道 | |
| 已安裝的應用程式 | |
| 釘選索引標籤 | |

> [!NOTE]
> 我們將在未來版本的 Microsoft 團隊中新增更多範本功能，因此請返回支援屬性的最新資訊。

## <a name="what-are-base-template-types"></a>什麼是基本範本類型

基底範本類型是 Microsoft 針對特定行業建立的特殊範本。 這些基本範本通常包含無法在市集中使用的專有 app。 此外，基本範本通常包含小組範本中尚不支援的團隊屬性。 瞭解如何 [在 Microsoft Graph 中使用團隊範本](get-started-with-teams-templates.md)。

一旦定義基底範本類型之後，您就可以使用您想要指定的其他屬性來延伸或覆寫這些特殊範本。 某些基底範本類型包含無法重寫的屬性。

根據預設，基本範本會設定為 [ **標準** ]，不會包含任何其他專屬 app 或特殊屬性。 以下是可用的基本範本類型的目前清單。

| 基底範本類型 | baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 標準 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 沒有其他 app 和屬性 |
| 學習<br>課程小組 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | 應用<ul><li>OneNote 課程筆記本 (釘選到 [ **一般** ] 索引標籤)  </li><li>[作業] app (釘選到 [ **一般** ] 索引標籤) </li></ul> 團隊屬性：<ul><li>無法重寫 [團隊可見度] 設定為 **HiddenMembership** () </li></ul> |
| 學習<br>員工小組 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | 應用<ul><li>OneNote 員工筆記本 (釘選到 [ **一般** ] 索引標籤) </li></ul> |
|學習<br>PLC 小組 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 應用<ul><li>OneNote PLC 筆記本 (釘選到 [ **一般** ] 索引標籤) </ul></li>|
| 面向<br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | 管道<ul><li>倒班切換</li><li>教學</li></ul>團隊屬性<ul><li>將團隊可見度設定為 Public</li></ul>成員許可權<ul><li>避免成員建立、更新或移除頻道</li><li>防止成員新增或移除應用程式</li><li>防止成員建立、更新或移除連接器</li></ul> |
| 面向<br>Manager 共同作業 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | 管道<ul><li>教學</li><li>營運</li></ul>團隊屬性：<ul><li>[團隊可見度] 設定為 [私人]</li></ul>成員許可權：<ul><li>避免成員建立、更新或移除頻道</li><li>防止成員新增或移除應用程式</li><li>防止成員建立、更新或移除連接器</li></ul>|
| 健康<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |管道 <ul><li>公告\*</li><li>Huddles\*</li><li>輪</li><li>人員\*</li><li>訓練\*</li></ul>\*自動將通道 |
|健康<br>醫院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |管道<ul><li>公告\*</li><li>合規性\*</li><li>Custodial</li><li>人力資源</li></li><li>藥房</li></ul>\*自動將通道|
|||


使用下列範本，在團隊用戶端及 Microsoft Graph 中建立團隊。


| 基底範本類型 | baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 採納 Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  管道 <ul><li>一般</li> <li>公告</li> <li>擁護方角落</li> <li>小組表單</li></ul> 應用 <ul><li>Wiki</li>  <li>行事曆</li> |
| 管理專案 |`com.microsoft.teams.template.`<br>`ManageAProject`| 管道 <ul><li>一般</li> <li>公告</li> <li>資源清單</li> <li>規劃</li></ul> 應用<ul><li>Wiki</li><li>OneNote</li></ul> |
| 管理活動|`com.microsoft.teams.template.`<br>`ManageAnEvent` | 管道 <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷與 PR</li></ul> 應用<ul><li>Wiki</li><li>Web</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|板載員工|`com.microsoft.teams.template.`<br>`OnboardEmployees` | 管道 <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用<ul><li>Wiki</li><li>社區</li></ul>|
|組織技術支援中心| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|管道<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用<ul><li>Wiki</li><li>OneNote</li></ul> |
| 在患者治療上共同作業| `healthcareWard `| 管道<ul><li>一般</li><li>公告</li><li>Huddles</li><li>輪</li><li>人員</li><li>訓練</li></ul> 應用 <ul><li>Wiki</li>|
| 在全球危機或活動上共同作業 |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| 管道 <ul><li>一般<li>公告</li><li>世界新聞</li><li>業務連續性</li><li>遠端作業</li><li>內部 comms</li><li>外部 comms</li><li>客戶投訴</li><li>Kudos</li><li>主管更新</li></ul>應用 <ul><li>稱讚</li><li>Wiki</li><li>Web</li></ul>|
|在銀行分支機搆內共同作業| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|管道 <ul><li>一般<li>公告</li><li>Huddles</li><li>客戶會議</li><li>警告</li><li>技能開發</li><li>貸款處理</li><li>客戶投訴</li><li>Kudos</li><li>有趣的內容</li><li>合規性</li></ul>|
|協調事件回應| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|管道 <ul><li>一般<li>公告</li><li>物流</li><li>規劃</li><li>修復</li><li>非常</li></ul> 應用 <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|醫院| `healthcareHospita`左 |管道 <ul><li>一般<li>公告</li><li>合規性</li><li>Custodial</li><li>人力資源</li><li>藥房</li></ul> 應用 <ul><li>Wiki</li></ul>|
|整理商店| `retailStore` |管道 <ul><li>一般<li>倒班切換</li><li>教學</li></ul> 應用 <ul><li>Wiki</li></ul>|
|品質與安全性 |`com.microsoft.teams.`<br>`template.QualitySafety`|管道 <ul><li>一般<li>公告</li><li>行1</li><li>第2行</li><li>第3行</li><li>安全</li><li>訓練</li><li>保養</li><li>有趣的內容</li></ul> 應用 <ul><li>Wiki</li></ul>|
|零售經理共同作業| `retailManagerCollaboration` |管道 <ul><li>一般<li>營運</li><li>教學</li></ul> 應用 <ul><li>Wiki</li></ul>|
||||

如需詳細資訊，請參閱 [管理中心的團隊範本快速](get-started-with-teams-templates-in-the-admin-console.md) 入門。

## <a name="related-topics"></a>相關主題

- [管理主控台中的團隊範本快速入門](get-started-with-teams-templates-in-the-admin-console.md)
- 在預覽中[建立小組](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) () 
- [新團隊](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft 團隊的系統管理訓練](itadmin-readiness.md)