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
description: 瞭解如何使用 Teams 範本，使用預先安裝範本建立不同主題的頻道共同合作空間。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad7b25a645948bae404a890f88ab29a14150f4d5
ms.sourcegitcommit: 29646ef386f693ecb9b740a473fba4365b187210
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51188315"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>在系統管理中心開始使用 Teams 範本

**尚未支援 EDU 客戶建立自訂範本的能力。**

> [!NOTE]
> Teams 範本目前不支援私人頻道和敏感度標籤。 範本定義中不包含私人頻道建立功能。 從範本流程 **建立團隊** 中的敏感度標籤選項將不會適用于該團隊。

Teams 範本是專為業務需求或專案所設計的小組結構預先建立的定義。 使用預先建建的範本或建立您自己的範本。 Teams 範本讓您能利用不同主題的頻道，快速建立豐富的共同合作空間，並預先安裝 App 以利於任務關鍵型內容和服務。 Teams 範本提供預先定義的小組結構，可協助您輕鬆建立整個組織的一致團隊。 目前，您可以在 Teams 中的範本或 [Microsoft Graph](get-started-with-teams-templates.md)中建立團隊。

本文將說明下列功能：

- 可在範本中定義的屬性。
- 基本範本類型。
- 如何使用一些範例要求，從範本建立團隊。

如果您負責規劃、部署及管理整個組織的多個團隊，本文適合您閱讀

## <a name="teams-template-capabilities"></a>Teams 範本功能

範本會包含及支援小組中的大部分屬性。 但目前不支援一些屬性和功能。 下表提供 Teams 範本中不包含的內容的快速摘要。

| **Teams 範本支援的小組屬性** | **Teams 範本尚未支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本範本類型 | 團隊成員資格 |
| 團隊名稱 | 小組圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可見度 (公開或私人)  | 連接器 |
| 團隊設定 (例如成員、來賓、@ 提及)  | 檔案和內容 |
| Autofavorite 頻道 | |
| 已安裝的應用程式 | |
| 釘上定位點 | |

> [!NOTE]
> 我們會在未來 Microsoft Teams 版本中新增更多範本功能，因此請回來查看支援屬性的最新版本資訊。

## <a name="what-are-base-template-types"></a>什麼是基本範本類型

基本範本類型是 Microsoft 針對特定產業所建立的特殊範本。 這些基本範本通常包含在 App Store 中無法提供的專屬應用程式。

定義基本範本類型之後，您可以使用更多要指定的屬性來延伸或覆蓋這些特殊範本。 某些基本範本類型包含無法重寫的屬性。

> [!NOTE]
> Microsoft Teams 中預先定義的基礎範本可以複製，但無法編輯。

| 基本範本類型 | baseTemplateId | 此基本範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 採用 Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  頻道： <ul><li>一般</li> <li>公告</li> <li>冠軍角</li> <li>小組表單</li></ul> 應用程式： <ul><li>Wiki</li>  <li>行事曆</li> |
| 管理專案 |`com.microsoft.teams.template.ManageAProject`| 頻道： <ul><li>一般</li> <li>公告</li> <li>資源</li> <li>規劃</li></ul> 應用程式：<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>清單</li>  </ul> |
| 管理活動|`com.microsoft.teams.template.ManageAnEvent` | 頻道： <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷與公關</li></ul> 應用程式：<ul><li>Wiki</li><li>網站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|上載員工|`com.microsoft.teams.template.OnboardEmployees` | 頻道： <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用程式：<ul><li>Wiki</li><li>社區</li><li>Planner</li></ul>|
|組織服務台| `com.microsoft.teams.template.OrganizeHelpDesk`|頻道：<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用程式：<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>讚美</li></ul> |
| 在病患照護上共同作業| `healthcareWard`| 頻道：<ul><li>一般</li><li>公告</li><li>過程中討論</li><li>輪次</li><li>人員</li><li>訓練</li></ul> 應用程式： <ul><li>Wiki</li><li>清單  </li></ul>|
| 在全球危機或事件上共同合作 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 頻道： <ul><li>一般<li>公告</li><li>世界新訊</li><li>業務連續性</li><li>遠端工作</li><li>內部通訊</li><li>外部通訊</li><li>核准要求</li><li>客戶抱怨</li><li>榮譽</li><li>主管更新</li></ul>應用程式： <ul><li>讚美</li><li>Wiki</li><li>網站</li><li>Planner</li></ul>|
|在銀行分行內共同合作| `com.microsoft.teams.template.CollaborateWithinABankBranch`|頻道： <ul><li>一般<li>公告</li><li>過程中討論</li><li>客戶會議</li><li>核准要求 </li><li>教練</li><li>技能開發</li><li>貸款處理</li><li>客戶抱怨</li><li>榮譽</li><li>有趣的專案</li><li>合規性</li></ul>應用程式：<ul><li>讚美 </li></ul>|
|協調事件回應| `com.microsoft.teams.template.CoordinateIncidentResponse`|頻道： <ul><li>一般<li>公告</li><li>物流</li><li>規劃</li><li>恢復</li><li>緊急</li></ul> 應用程式： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>Sharepoint</li><li>Planner</li></ul>|
|醫院| `healthcareHospital` |頻道： <ul><li>一般</li><li>公告</li><li>合規性</li><li>監管</li><li>人力資源</li><li>藥品部</li></ul> 應用程式： <ul><li>Wiki</li><li>清單  </li></ul>|
|組織商店| `retailStore` |頻道： <ul><li>一般<li>班次交班</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li><li>Planner</li></ul>|
|品質和安全性 |`com.microsoft.teams.template.QualitySafety`|頻道： <ul><li>一般<li>公告</li><li>第 1 行</li><li>第 2 行</li><li>第 3 行</li><li>安全</li><li>訓練課程</li><li>維護</li><li>有趣的專案</li></ul> 應用程式： <ul><li>Wiki</li><li>Planner</li></ul>|
|零售 - 主管共同作業| `retailManagerCollaboration` |頻道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li><li>Planner</li></ul>|
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

請參閱 [Teams 的限制和](limits-specifications-teams.md) 規格以瞭解更多資訊。

## <a name="related-topics"></a>相關主題

- [建立自訂小組範本](create-a-team-template.md)
- [從現有的小組範本建立小組範本](create-template-from-existing-template.md)
- [從現有的小組建立範本](create-template-from-existing-team.md)
