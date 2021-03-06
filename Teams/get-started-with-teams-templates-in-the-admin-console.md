---
title: 在系統管理中心使用 Teams 範本
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用預先安裝範本，使用 Teams 範本建立不同主題的頻道共同合作空間。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62bee9c494cc6155a84b30d75ae71528656133be
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508006"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>在系統管理中心開始使用 Teams 範本

**尚未支援 EDU 客戶建立自訂範本的能力。**

> [!NOTE]
> Teams 範本目前不支援建立私人頻道。 私人頻道的建立不會包含在範本定義中。

Teams 範本是專為業務需求或專案設計的小組結構預先建立的定義。 使用預先建立的範本或建立您自己的範本。 Teams 範本讓您利用不同主題的頻道快速建立豐富的共同合作空間，並預先安裝應用程式，以拉出任務關鍵性的內容和服務。 Teams 範本提供預先定義的小組結構，可協助貴組織輕鬆建立一致的團隊。 目前，您可以在 Teams 中的範本或 [Microsoft Graph](get-started-with-teams-templates.md)中建立團隊。

本文將說明可在範本中定義的屬性、什麼是基本範本類型，以及如何使用幾個範例要求從範本建立小組。

如果您負責規劃、部署和管理整個組織的多個小組，本文適合您

## <a name="teams-template-capabilities"></a>Teams 範本功能

範本會包含及支援小組中的大部分屬性。 但目前不支援一些屬性和功能。 下表提供 Teams 範本中未包含之內容的快速摘要。

| **Teams 範本支援的小組屬性** | **Teams 範本尚未支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本範本類型 | 團隊成員資格 |
| 團隊名稱 | 團隊圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可見度 (公開或私人)  | 連接器 |
| 團隊設定 (例如成員、來賓、@ 提及)  | 檔案和內容 |
| Autofavorite 頻道 | |
| 已安裝的應用程式 | |
| 釘住的定位點 | |

> [!NOTE]
> 我們會在未來 Microsoft Teams 版本中新增更多範本功能，因此請回來查看支援屬性上最新的資訊。

## <a name="what-are-base-template-types"></a>什麼是基本範本類型

基本範本類型是 Microsoft 為特定產業所建立的特殊範本。 這些基本範本通常包含 App Store 中無法提供的專屬應用程式。

定義基本範本類型後，您可以使用要指定的其他屬性來延伸或覆蓋這些特殊範本。 某些基本範本類型包含無法覆蓋的屬性。

> [!NOTE]
> Microsoft Teams 中預先定義的基準範本可以複製，但無法編輯。

| 基本範本類型 | baseTemplateId | 此基本範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 採用 Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  管道： <ul><li>一般</li> <li>公告</li> <li>歐洲強人角</li> <li>小組表單</li></ul> 應用程式： <ul><li>維琪</li>  <li>行事曆</li> |
| 管理專案 |`com.microsoft.teams.template.ManageAProject`| 管道： <ul><li>一般</li> <li>公告</li> <li>資源</li> <li>規劃</li></ul> 應用程式：<ul><li>維琪</li><li>OneNote</li><li>Planner</li><li>清單</li>  </ul> |
| 管理事件|`com.microsoft.teams.template.ManageAnEvent` | 管道： <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷與 PR</li></ul> 應用程式：<ul><li>維琪</li><li>網站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|讓員工上機|`com.microsoft.teams.template.OnboardEmployees` | 管道： <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用程式：<ul><li>維琪</li><li>社區</li><li>Planner</li></ul>|
|組織技術支援人員| `com.microsoft.teams.template.OrganizeHelpDesk`|管道：<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用程式：<ul><li>維琪</li><li>OneNote</li><li>Planner </li><li>讚美</li></ul> |
| 在病患照護上共同合作| `healthcareWard`| 管道：<ul><li>一般</li><li>公告</li><li>Huddles</li><li>輪</li><li>人手</li><li>訓練</li></ul> 應用程式： <ul><li>維琪</li><li>清單  </li></ul>|
| 在全域事件或事件上共同合作 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 管道： <ul><li>一般<li>公告</li><li>世界新訊</li><li>業務持續性</li><li>遠端工作</li><li>內部通訊</li><li>外部通訊</li><li>核准要求</li><li>客戶抱怨</li><li>榮譽</li><li>執行更新</li></ul>應用程式： <ul><li>讚美</li><li>維琪</li><li>網站</li><li>Planner</li></ul>|
|在銀行分行內共同合作| `com.microsoft.teams.template.CollaborateWithinABankBranch`|管道： <ul><li>一般<li>公告</li><li>Huddles</li><li>客戶會議</li><li>核准要求 </li><li>教練</li><li>技能開發</li><li>貸款處理</li><li>客戶抱怨</li><li>榮譽</li><li>有趣的內容</li><li>合規性</li></ul>應用程式：<ul><li>讚美 </li></ul>|
|協調事件回應| `com.microsoft.teams.template.CoordinateIncidentResponse`|管道： <ul><li>一般<li>公告</li><li>物流</li><li>規劃</li><li>恢復</li><li>緊急</li></ul> 應用程式： <ul><li>維琪</li><li>Excel</li><li>OneNote</li><li>Sharepoint</li><li>Planner</li></ul>|
|醫院| `healthcareHospital` |管道： <ul><li>一般</li><li>公告</li><li>合規性</li><li>保管</li><li>人力資源</li><li>藥學</li></ul> 應用程式： <ul><li>維琪</li><li>清單  </li></ul>|
|組織商店| `retailStore` |管道： <ul><li>一般<li>Shift handoff</li><li>學習</li></ul> 應用程式： <ul><li>維琪</li><li>Planner</li></ul>|
|品質與安全 |`com.microsoft.teams.template.QualitySafety`|管道： <ul><li>一般<li>公告</li><li>行 1</li><li>行 2</li><li>行 3</li><li>安全</li><li>訓練</li><li>維護</li><li>有趣的內容</li></ul> 應用程式： <ul><li>維琪</li><li>Planner</li></ul>|
|零售 - 主管共同合作| `retailManagerCollaboration` |管道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>維琪</li><li>Planner</li></ul>|
||||

有關範本類別的資訊，請參閱下列類別：

- [財務範本](financial-teams-templates-in-the-admin-console.md)
- [一般範本](general-teams-templates-in-the-admin-console.md)
- [政府範本](government-teams-templates-in-the-admin-console.md)
- [醫療保健範本](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造範本](manufacturing-teams-templates-in-the-admin-console.md)
- [零售範本](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>範本大小限制

範本僅限於特定數量的頻道、定位字元和應用程式。

 > [!Note]
 > 從範本建立團隊之後，您可以新增更多頻道、定位停駐點和應用程式至團隊。

|功能 | 限制|
|-|-|
|每個範本的頻道 | 15 |
|範本中每個頻道的定位停駐點 | 20 |
|每個範本的應用程式 | 50|
|||

請參閱 [Teams 的限制](limits-specifications-teams.md) 和規格以瞭解更多資訊。

## <a name="related-topics"></a>相關主題

- [建立自訂小組範本](create-a-team-template.md)
- [從現有的小組範本建立小組範本](create-template-from-existing-template.md)
- [從現有小組建立範本](create-template-from-existing-team.md)
