---
title: 在系統管理中心開始使用Teams範本
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
description: 瞭解小組範本，以及如何在系統管理中心Microsoft Teams範本。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19333badf3df580129ab7a805cf27c670748d299
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991142"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>在系統管理中心開始使用Teams範本

**尚未支援 EDU 客戶建立自訂範本的能力。**

> [!NOTE]
> 小組範本目前不支援私人頻道和敏感度標籤。 範本定義中不包含私人頻道建立功能。 從範本流程 **建立團隊** 中的敏感度標籤選項將不會適用于團隊。

## <a name="overview"></a>概觀

團隊範本Microsoft Teams是圍繞業務需求或專案所設計之團隊結構的定義。 做為系統管理員，您可以使用範本，輕鬆在貴組織中部署一致的團隊。 有了範本，您的使用者可以使用預先定義的設定、頻道和應用程式，快速建立豐富的共同合作空間。

您可以在系統管理中心Microsoft Teams或使用 PowerShell 來管理小組範本。 您可以使用我們提供的預先建立範本，您也可以 [建立自己的自訂範本](#create-your-own-team-templates)。 您也可以使用[範本原則](#apply-team-template-policies)來控制哪些範本可供您的使用者在 Teams。

本文提供在系統管理中心使用小組範本Teams概觀。 您將瞭解範本中支援的屬性、我們提供的預先建立範本、範本大小限制、如何建立及管理範本等等。

> [!NOTE]
> 您的使用者可以從應用程式內預先建立或[自訂](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)的團隊範本Teams團隊。 開發人員也可以以程式設計的方式使用 Microsoft Graph 預先建立的團隊範本。 若要深入瞭解[，請參閱開始使用](get-started-with-teams-templates.md)Microsoft Graph。

## <a name="team-template-capabilities"></a>小組範本功能

團隊範本會包含並支援小組中的大部分屬性。 但目前不支援一些屬性和功能。 以下摘要顯示小組範本包含的內容和未包含的內容。

| **小組範本支援的小組屬性** | **小組範本尚未支援的團隊屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 範本類型 | 團隊成員資格 |
| 小組名稱 | 小組圖片 |
| 團隊描述 | 頻道設定 |
| 團隊可見度 (公開或私人)  | 連接 |
| 團隊設定 (例如成員、來賓、@ 提及)  | 檔案和內容 |
| 自動favorite頻道 | |
| 已安裝的應用程式 | |
| 釘上定位點 | |

> [!NOTE]
> 我們會在未來版本中新增更多範本功能Microsoft Teams，因此請回來查看支援屬性上最新的資訊。

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>系統管理中心內預先建立Teams範本

以下是在系統管理中心提供的預先建立Teams範本。 預先建立範本是我們為特定產業所建立範本。 若要查看這些範本，請前往系統管理中心的左側導Teams，前往 Teams ****  >  **範本**。

您可以複製預先建立範本，但無法編輯它們。 如果您想要變更預先建立範本中的屬性，您可以從現有的範本建立新範本，然後新增或移除您想要的屬性。 請記住，某些範本中的某些屬性無法變更。

| 範本類型 | TemplateId | 此範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 採用Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  頻道： <ul><li>一般</li> <li>公告</li> <li>冠軍角</li> <li>小組表單</li><li>行事曆</li></ul> 應用程式： <ul><li>Wiki</li>  <li>頻道日曆</li> <li>里程碑</li><li>公告</li></ul>|
| 管理專案 |`com.microsoft.teams.template.ManageAProject`| 頻道： <ul><li>一般</li> <li>公告</li> <li>資源</li> <li>規劃</li></ul> 應用程式：<ul><li>Wiki</li><li>OneNote</li><li>任務</li><li>清單</li><li>Power Automate</li></ul> |
| 管理活動|`com.microsoft.teams.template.ManageAnEvent` | 頻道： <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷與公關</li></ul> 應用程式：<ul><li>Wiki</li><li>網站</li> <li>YouTube</li> <li>任務</li> <li>OneNote</li> <li>員工的想法</li> <li>問題報訊者</li><li>Power Automate</li><li>公告</li><li>里程碑</li></ul> |
|上載員工|`com.microsoft.teams.template.OnboardEmployees` | 頻道： <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用程式：<ul><li>Wiki</li><li>社區</li><li>任務</li><li>員工的想法</li><li>Power Automate</li><li>公告</li><li>里程碑</li></ul>|
|組織服務台| `com.microsoft.teams.template.OrganizeHelpDesk`|頻道：<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用程式：<ul><li>Wiki</li><li>OneNote</li><li>任務 </li><li>稱讚</li><li>問題報訊者</li><li>Power Automate</li><li>公告</li></ul> |
| 病患照護| `com.microsoft.teams.template.healthcareWard`| 頻道：<ul><li>一般</li><li>公告</li><li>過程中討論</li><li>輪次</li><li>人員</li><li>訓練</li></ul> 應用程式： <ul><li>Wiki</li><li>清單  </li><li>批准</li><li>公告</li><li>檢驗</li></ul>|
| 危機通訊 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 頻道： <ul><li>一般<li>公告</li><li>世界新訊</li><li>內部通訊</li><li>外部通訊</li><li>核准要求</li><li>客戶升級</li><li>主管更新</li><li>規劃</li><li>物流</li></ul>應用程式： <ul><li>網站</li><li>任務</li><li>問題報訊者</li><li>批准</li><li>公告</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|銀行分行| `com.microsoft.teams.template.CollaborateWithinABankBranch`|頻道： <ul><li>一般<li>公告</li><li>過程中討論</li><li>客戶會議</li><li>核准要求 </li><li>教練</li><li>技能開發</li><li>貸款處理</li><li>客戶抱怨</li><li>榮譽</li><li>有趣的專案</li><li>合規性</li></ul>應用程式：<ul><li>稱讚 </li><li>問題報訊者</li><li>Wiki</li><li>行事曆</li><li>批准</li><li>公告</li><li>想法</li></ul>|
|事件回應| `com.microsoft.teams.template.CoordinateIncidentResponse`|頻道： <ul><li>一般<li>公告</li><li>物流</li><li>規劃</li><li>恢復</li><li>緊急</li></ul> 應用程式： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>任務</li> <li>批准</li> <li>檢驗</li> <li>Power Automate</li><li>公告</li><li>里程碑</li></ul>|
|醫院| `com.microsoft.teams.template.healthcareHospital` |頻道： <ul><li>一般</li><li>公告</li><li>合規性</li><li>監管</li><li>人力資源</li><li>藥品部</li></ul> 應用程式： <ul><li>Wiki</li><li>清單</li><li>任務</li><li>批准</li><li>班次</li><li>公告</li><li>檢驗</li><li>想法</li></ul>|
|組織商店| `com.microsoft.teams.template.retailStore` |頻道： <ul><li>一般<li>班次交班</li><li>儲存準備狀態</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li><li>任務</li><li>班次</li><li>檢驗</li></ul>|
|適用于主管的零售| `com.microsoft.teams.template.retailManagerCollaboration` |頻道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li><li>任務</li><li>檢驗</li></ul>|
|品質和安全性 |`com.microsoft.teams.template.QualitySafety`|頻道： <ul><li>一般<li>公告</li><li>領導</li><li>維護</li><li>第 1 條生產線</li><li>第 2 條生產線</li><li>第 3 條生產線</li><li>健康與安全</li><li>訓練</li><li>有趣的專案</li></ul> 應用程式： <ul><li>Wiki</li><li>任務</li> <li>問題報訊者</li> <li>檢驗</li> </ul>|

### <a name="team-templates-by-category-and-industry"></a>按類別和產業分類的團隊範本

若要進一步瞭解在業界使用預先建立範本的方法，請參閱：

- [財務小組範本](financial-teams-templates-in-the-admin-console.md)
- [一般小組範本](general-teams-templates-in-the-admin-console.md)
- [政府小組範本](government-teams-templates-in-the-admin-console.md)
- [醫療保健小組範本](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造小組範本](manufacturing-teams-templates-in-the-admin-console.md)
- [零售小組範本](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>小組範本大小限制

範本僅限於特定數量的頻道、定位字元和應用程式。

 > [!Note]
 > 從範本建立團隊之後，您可以新增更多頻道、定位停駐點和應用程式至團隊。

|功能 | 限制|
|-|-|
|每個範本的頻道 | 15 |
|範本中每個頻道的定位停駐點 | 20 |
|每個範本的應用程式 | 50|
|||

詳細資訊，請參閱限制和[Teams。](limits-specifications-teams.md)

## <a name="manage-team-templates"></a>管理小組範本

### <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理Teams範本

#### <a name="view-team-templates"></a>查看小組範本

若要查看小組範本，在系統管理中心的左側導Teams，請前往 Teams ****  >  **範本**。 選取範本以查看更多詳細資料，包括其中包含的頻道和應用程式。

#### <a name="create-your-own-team-templates"></a>建立您自己的小組範本

您可以從頭開始、從現有的小組和現有的範本建立您自己的自訂範本。 若要深入了解，請參閱：

- [建立自訂小組範本](create-a-team-template.md)
- [從現有小組建立範本](create-template-from-existing-team.md)
- [從現有的小組範本建立小組範本](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>適用小組範本原則

若要控制使用者在建立團隊Teams中所看到的範本，您可以設定範本政策，並將其指派給貴組織的使用者和群組。 若要深入瞭解，請參閱在系統管理中心管理Teams[範本](templates-policies.md)。

### <a name="manage-team-templates-using-powershell"></a>使用 PowerShell 管理小組範本

使用下列 Cmdlet 在 PowerShell 中管理範本。

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps) 
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps) 
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>相關文章

- [從範本建立團隊](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)
- [開始使用 Microsoft Graph](get-started-with-teams-templates.md) 