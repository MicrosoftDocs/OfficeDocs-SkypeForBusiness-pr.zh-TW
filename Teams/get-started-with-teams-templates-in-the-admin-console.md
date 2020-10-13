---
title: 使用團隊範本建立新團隊
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
description: 瞭解如何使用預先安裝的範本，在不同主題的頻道中使用團隊範本建立共同作業空間。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 618c1a2949dc00e1257e3fef56c41b3bf2be567c
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424653"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>在系統管理中心快速開始使用團隊範本

[!INCLUDE [preview-feature](includes/preview-feature.md)]

**EDU 客戶尚不支援自訂範本。**

> [!NOTE]
> 團隊範本目前不支援建立專用頻道。 範本定義中不包含專用通道建立。

團隊範本是預先建立的小組結構定義，它是圍繞業務需求或專案設計的。 使用預先建立的範本或建立您自己的範本。 團隊範本可讓您使用不同主題的頻道快速建立豐富的共同作業空間，並預先安裝 app 來拉入重要的內容和服務。 團隊範本提供預先定義的小組結構，可協助您在組織中輕鬆建立一致的團隊。 目前您可以從小組中的範本或使用 [Microsoft Graph](get-started-with-teams-templates.md)來建立小組。

本文將說明可在範本中定義的屬性、基底範本類型，以及如何使用幾個範例要求來從範本建立小組。

如果您負責規劃、部署及管理多個組織中的多個小組，本文適用于您。

## <a name="teams-template-capabilities"></a>團隊範本功能

小組中的大部分屬性都包含在範本中並受到支援。 但目前尚不支援一些屬性和功能。 下表提供 [摘要]，簡要說明團隊範本中包含的內容和不包含的內容。

| **團隊範本支援的團隊屬性** | **團隊範本尚不支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基底範本類型 | 團隊成員資格 |
| 團隊名稱 | 小組圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可視性 (公開或私人)  | 連接器 |
| 小組設定 (例如 [成員]、[來賓]、[@ 提及])  | 檔案和內容 |
| Autofavorite 通道 | |
| 已安裝的應用程式 | |
| 釘選索引標籤 | |

> [!NOTE]
> 我們將在未來版本的 Microsoft 團隊中新增更多範本功能，因此請返回支援屬性的最新資訊。

## <a name="what-are-base-template-types"></a>什麼是基本範本類型

基底範本類型是 Microsoft 針對特定行業建立的特殊範本。 這些基本範本通常包含無法在 [應用程式] 存放區中使用的專有 app。

一旦定義基底範本類型之後，您就可以使用您想要指定的其他屬性來延伸或覆寫這些特殊範本。 某些基底範本類型包含無法重寫的屬性。

> [!NOTE]
> 您可以複製 Microsoft 團隊中提供的預先定義基礎範本，但無法進行編輯。

| 基底範本類型 | baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------ |----|----------------------------------------------------- |
| 採納 Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  管道 <ul><li>一般</li> <li>公告</li> <li>擁護方角落</li> <li>小組表單</li></ul> 應用 <ul><li>Wiki</li>  <li>行事曆</li> |
| 管理專案 |`com.microsoft.teams.template.ManageAProject`| 管道 <ul><li>一般</li> <li>公告</li> <li>資源清單</li> <li>規劃</li></ul> 應用<ul><li>Wiki</li><li>OneNote</li></ul> |
| 管理活動|`com.microsoft.teams.template.ManageAnEvent` | 管道 <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷與 PR</li></ul> 應用<ul><li>Wiki</li><li>Web</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|板載員工|`com.microsoft.teams.template.OnboardEmployees` | 管道 <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用<ul><li>Wiki</li><li>社區</li></ul>|
|組織技術支援中心| `com.microsoft.teams.template.OrganizeHelpDesk`|管道<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用<ul><li>Wiki</li><li>OneNote</li></ul> |
| 在患者治療上共同作業| `healthcareWard `| 管道<ul><li>一般</li><li>公告</li><li>Huddles</li><li>輪</li><li>人員</li><li>訓練</li></ul> 應用 <ul><li>Wiki</li>|
| 在全球危機或活動上共同作業 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 管道 <ul><li>一般<li>公告</li><li>世界新聞</li><li>業務連續性</li><li>遠端作業</li><li>內部 comms</li><li>外部 comms</li><li>客戶投訴</li><li>Kudos</li><li>主管更新</li></ul>應用 <ul><li>稱讚</li><li>Wiki</li><li>Web</li></ul>|
|在銀行分支機搆內共同作業| `com.microsoft.teams.template.CollaborateWithinABankBranch `|管道 <ul><li>一般<li>公告</li><li>Huddles</li><li>客戶會議</li><li>警告</li><li>技能開發</li><li>貸款處理</li><li>客戶投訴</li><li>Kudos</li><li>有趣的內容</li><li>合規性</li></ul>|
|協調事件回應| `com.microsoft.teams.template.CoordinateIncidentResponse`|管道 <ul><li>一般<li>公告</li><li>物流</li><li>規劃</li><li>修復</li><li>非常</li></ul> 應用 <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|醫院| `healthcareHospita`左 |管道 <ul><li>一般<li>公告</li><li>合規性</li><li>Custodial</li><li>人力資源</li><li>藥房</li></ul> 應用 <ul><li>Wiki</li></ul>|
|整理商店| `retailStore` |管道 <ul><li>一般<li>倒班切換</li><li>教學</li></ul> 應用 <ul><li>Wiki</li></ul>|
|品質與安全性 |`com.microsoft.teams.template.QualitySafety`|管道 <ul><li>一般<li>公告</li><li>行1</li><li>第2行</li><li>第3行</li><li>安全</li><li>訓練</li><li>保養</li><li>有趣的內容</li></ul> 應用 <ul><li>Wiki</li></ul>|
|零售經理共同作業| `retailManagerCollaboration` |管道 <ul><li>一般<li>營運</li><li>教學</li></ul> 應用 <ul><li>Wiki</li></ul>|
||||

如需範本類別的詳細資訊，請參閱下列類別：

- [財務範本](financial-teams-templates-in-the-admin-console.md)
- [一般範本](general-teams-templates-in-the-admin-console.md)
- [政府範本](government-teams-templates-in-the-admin-console.md)
- [醫療保健範本](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造範本](manufacturing-teams-templates-in-the-admin-console.md)
- [零售範本](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>範本大小限制

範本僅限特定數量的頻道、索引標籤和應用程式。

 > [!Note]
 > 從範本建立之後，您可以在小組中新增更多頻道、索引標籤和應用程式。

|功能 | 期限|
|-|-|
|每個範本的頻道 | 工資 |
|範本中的每個頻道索引標籤 | 20 |
|每個範本的 app | 50|
|||

如需詳細資訊，請參閱 [小組的限制與規格](limits-specifications-teams.md) 。

## <a name="related-topics"></a>相關主題

- [建立自訂團隊範本](create-a-team-template.md)
- [從現有的小組範本建立小組範本](create-template-from-existing-template.md)
- [從現有團隊建立範本](create-template-from-existing-team.md)
