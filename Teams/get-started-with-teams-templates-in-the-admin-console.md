---
title: 在 Teams 系統管理中心開始使用團隊範本
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
- highpri
description: 瞭解團隊範本，以及如何在 Microsoft Teams 系統管理中心管理它們。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fc4f5c88e123981ee5224a76c28996306e51ded
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046893"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>在 Teams 系統管理中心開始使用團隊範本

**EDU 客戶尚未支援建立自訂範本的功能。**

> [!NOTE]
> - 團隊範本目前不支援私人和共用頻道。 範本定義中不包含私人和共用頻道建立。
>
> - GCC 環境中的小組範本不支援敏感度標籤。 [從範本建立團隊] 流程中的敏感度標籤選項不會套用至團隊。

## <a name="overview"></a>概觀

Microsoft Teams 中的團隊範本是針對業務需求或專案所設計的團隊結構定義。 身為系統管理員，您可以使用範本，在組織中輕鬆部署一致的團隊。 透過範本，您的使用者可以使用預先定義的設定、頻道和應用程式，快速建立豐富的共同作業空間。

您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 管理團隊範本。 您可以使用我們預先建立的範本，您也可以 [建立自己的自訂範本](#create-your-own-team-templates)。 您也可以 [套用範本原則](#apply-team-template-policies) ，以控制哪些範本可供 Teams 中的使用者使用。

本文提供在 Teams 系統管理中心使用團隊範本的概觀。 您將瞭解範本支援的屬性、我們提供的預先建置範本、範本大小限制、如何建立及管理範本等等。

> [!NOTE]
> 您的使用者可以 [從 Teams 應用程式中預先建立或自訂的團隊範本](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) 建立團隊。 開發人員也可以使用 Microsoft Graph，以程式設計方式從預先建立或自訂的團隊範本建立團隊。 若要深入瞭解，請參閱 [開始使用 Microsoft Graph 的小組範本](get-started-with-teams-templates.md)。

## <a name="team-template-capabilities"></a>團隊範本功能

團隊中大部分的屬性都包含在團隊範本中並受到支援。 但目前不支援一些屬性和功能。 以下是團隊範本中包含的內容和未包含內容的摘要。

| **小組範本支援的團隊屬性** | **小組範本尚未支援小組屬性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 範本類型 | 團隊成員資格 |
| 小組名稱 | 團隊圖片 |
| 團隊描述 | 頻道設定 |
| 公開或私人)  (小組可見度 | 連接器 |
| 團隊設定 (例如成員、來賓、@ 提及)  | 檔案和內容 |
| Autofavorite 通道 | |
| 已安裝的應用程式 | |
| 已釘選的索引標籤 | |

> [!NOTE]
> 我們會在未來的 Microsoft Teams 版本中新增更多範本功能，因此請返回查看支援內容的最新資訊。

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Teams 系統管理中心預先建立的團隊範本

以下是 Teams 系統管理中心中預先建立的團隊範本。 預先建立的範本是我們為特定產業建立的範本。 若要檢視這些範本，請在 Teams 系統管理中心的左側導覽中，移至 **Teams 團隊**  >  **範本**。

您可以複製預先建立的範本，但無法編輯這些範本。 如果您想要變更預先建立的範本中的屬性，您可以從現有的範本建立新的範本，然後新增或移除您要的屬性。 請記住，某些範本中的特定屬性無法變更。

> [!NOTE]
> 星號 (*) 表示範本是 *Microsoft 365 連線的範本*。 當使用者使用範本建立團隊時，連線的 SharePoint 範本會套用至網站和小組。 網頁、清單和 Power Platform 整合等 SharePoint 元件會自動新增並釘選為小組中 [一般] 頻道的索引標籤。 使用者可以直接從 Teams 中編輯這些頁面和清單。
>
> 若要深入瞭解 SharePoint 範本，請參閱 [套用及自訂 SharePoint 網站範本](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)。

>[!div class="mx-tdBreakAll"]
>| 範本類型 | TemplateId | 此範本提供的屬性 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 管理專案* |`com.microsoft.teams.template.ManageAProject`| 頻道： <ul><li>一般</li> <li>公告</li> <li>資源</li> <li>規劃</li></ul> 應用程式：<ul><li>核准</li><li>佈告欄</li><li>清單<ul><li>Project 追蹤器</li><li>問題追蹤器</li></ul></li><li>里程碑</li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>我們的網站</li></ul></li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul> |
| 管理事件*|`com.microsoft.teams.template.ManageAnEvent` | 頻道： <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷和 PR</li></ul> 應用程式：<ul><li>核准</li><li>佈告欄</li> <li>員工想法</li><li>清單<ul><li>內容排程器</li></ul></li><li>里程碑</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint Pages<ul><li>我們的網站</li><li>關於我們的活動</li></ul><li>Planner 和 To Do 的工作</li><li>Wiki</li> |
|入職員工*|`com.microsoft.teams.template.OnboardEmployees` | 頻道： <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用程式：<ul><li>佈告欄</li><li>員工想法</li><li>清單<ul><li>上線檢查清單</li></ul></li><li>里程碑</li><li>Power Automate</li> <li>SharePoint Pages<ul><li>開始使用</li><li>訓練</li></ul><li>Planner 和 To Do 的工作</li><li>Viva Engage</li><li>Wiki</li></ul>|
| 採用Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  頻道： <ul><li>一般</li> <li>公告</li> <li>冠軍專區</li> <li>團隊表單</li><li>行事曆</li></ul> 應用程式： <ul><li>Wiki</li>  <li>頻道行事曆</li> <li>里程碑</li><li>佈告欄</li></ul>
|整理技術支援中心*| `com.microsoft.teams.template.OrganizeHelpDesk`|頻道：<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用程式：<ul><li>問題報告</li><li>清單<ul><li>裝置</li><li>票</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>我們的網站</li><li>常見問題集</li></ul></li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul> |
|事件回應| `com.microsoft.teams.template.CoordinateIncidentResponse`|頻道： <ul><li>一般<li>公告</li><li>物流</li><li>規劃</li><li>恢復</li><li>緊急</li></ul> 應用程式： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>工作</li> <li>核准</li> <li>檢查</li> <li>Power Automate</li><li>佈告欄</li><li>里程碑</li></ul>|
| 嚴重通訊* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 頻道： <ul><li>一般<li>公告</li><li>Executive Update</li><li>規劃</li><li>物流</li></ul>應用程式： <ul><li>核准</li><li>問題報告</li><li>清單<ul><li>內容排程器</li><li>專案計劃</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>我們的網站</li><li>最新更新</li></ul><li>Planner 和 To Do 的工作</li>|
| 管理市集*| `com.microsoft.teams.template.retailStore` |頻道： <ul><li>一般<li>Shift Handoff</li><li>Microsoft Store 整備</li><li>Learning</li></ul> 應用程式： <ul><li>核准</li><li>檢查</li><li>清單<ul><li>庫存清單</li></ul></li><li>SharePoint Pages<ul><li>我們的商店</li></ul></li><li>班次</li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul>|
|銀行分行| `com.microsoft.teams.template.CollaborateWithinABankBranch`|頻道： <ul><li>一般<li>公告</li><li>過程中討論</li><li>客戶會議</li><li>核准要求 </li><li>指導</li><li>技能開發</li><li>貸款處理</li><li>客戶抱怨</li><li>讚美</li><li>有趣的內容</li><li>合規性</li></ul>應用程式：<ul><li>稱讚 </li><li>問題報告者</li><li>Wiki</li><li>行事曆</li><li>核准</li><li>佈告欄</li><li>構想</li></ul>|
| 病患照護| `com.microsoft.teams.template.healthcareWard`| 頻道：<ul><li>一般</li><li>公告</li><li>過程中討論</li><li>輪次</li><li>人員</li><li>訓練</li></ul> 應用程式： <ul><li>Wiki</li><li>清單  </li><li>核准</li><li>佈告欄</li><li>檢查</li></ul>|
|醫院| `com.microsoft.teams.template.healthcareHospital` |頻道： <ul><li>一般</li><li>公告</li><li>合規性</li><li>監管</li><li>人力資源</li><li>藥品部</li></ul> 應用程式： <ul><li>Wiki</li><li>清單</li><li>工作</li><li>核准</li><li>班次</li><li>佈告欄</li><li>檢查</li><li>構想</li></ul>|
|品質與安全 |`com.microsoft.teams.template.QualitySafety`|頻道： <ul><li>一般<li>公告</li><li>領導</li><li>維護</li><li>生產線 1</li><li>生產線 2</li><li>生產線 3</li><li>健康與安全</li><li>訓練</li><li>有趣的內容</li></ul> 應用程式： <ul><li>Wiki</li><li>工作</li> <li>問題報告者</li> <li>檢查</li> </ul>|
|適用于經理的零售*| `com.microsoft.teams.template.retailManagerCollaboration` |頻道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>核准</li><li>檢查</li><li>SharePoint Pages<ul><li>我們的商店</li></ul></li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul>|
|管理自願者| `com.microsoft.teams.template.ManageVolunteers` |頻道： <ul><li>一般<li>公告</li><li>報告</li><li>志願者管理</li><li>預定機會</li><li>志願者上線</li></ul> 應用程式： <ul><li>網站</li><li>YouTube</li><li>Power BI</li><li>Power 應用程式</li><li>工作</li><li>SharePoint</li><li>OneNote</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>依類別和產業分類的小組範本

如需有關如何在您的產業中使用預先建置範本的詳細資訊，請參閱：

- [一般小組範本](general-teams-templates-in-the-admin-console.md)
- [財務小組範本](financial-teams-templates-in-the-admin-console.md)
- [政府小組範本](government-teams-templates-in-the-admin-console.md)
- [醫療保健小組範本](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [製造小組範本](manufacturing-teams-templates-in-the-admin-console.md)
- [非營利組織團隊範本](team-templates-nonprofit.md)
- [零售小組範本](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>團隊範本大小限制

範本僅限於特定數量的頻道、索引標籤和應用程式。

 > [!Note]
 > 您可以在從範本建立之後，將更多頻道、索引標籤和應用程式新增至團隊。

|功能 | 限制|
|-|-|
|每個範本的頻道 | 15 |
|範本中每個頻道的索引標籤 | 20 |
|每個範本的應用程式 | 50|

如需詳細資訊，請參閱 [Teams 的限制和規格](limits-specifications-teams.md)。

## <a name="manage-team-templates"></a>管理小組範本

### <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理團隊範本

#### <a name="view-team-templates"></a>檢視小組範本

若要檢視團隊範本，請在 Teams 系統管理中心的左側導覽中，移至 **Teams 團隊**  >  **範本**。 選取範本以查看更多詳細資料，包括其中包含的頻道和應用程式。

#### <a name="create-your-own-team-templates"></a>建立您自己的團隊範本

您可以從頭開始、從現有的小組，以及從現有的範本建立自己的自訂範本。 若要深入了解，請參閱：

- [建立自訂團隊範本](create-a-team-template.md)
- [從現有團隊建立範本](create-template-from-existing-team.md)
- [從現有的團隊範本建立團隊範本](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>套用團隊範本原則

若要控制使用者在 Teams 中看到的建立 [團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)範本，您可以設定範本原則，並將範本指派給組織中的使用者和群組。 若要深入瞭解，請參閱 [在 Teams 系統管理中心管理團隊範本](templates-policies.md)。

### <a name="manage-team-templates-using-powershell"></a>使用 PowerShell 管理小組範本

使用下列 Cmdlet 來管理 PowerShell 中的範本。

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>相關文章

- [從範本建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [開始用 Microsoft Graph 使用團隊範本](get-started-with-teams-templates.md)
- [複製團隊](/graph/api/team-clone)
- [Teams 與 SharePoint 整合概觀](/sharepoint/teams-connected-sites)
