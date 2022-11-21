---
title: 使用零售團隊範本
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何在 Teams 系統管理中心管理及使用零售團隊範本, 以及使用 Microsoft Graph 快速且輕鬆地為零售組織建立團隊。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e32430990450fbe72cf80efd5eb960a28e3315a1
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131322"
---
# <a name="use-retail-team-templates"></a>使用零售團隊範本

## <a name="overview"></a>概觀

Microsoft Teams 的團隊範本提供預先定義的設定、頻道和預先安裝應用程式的團隊結構, 讓您快速且輕鬆地建立團隊。

對於零售商來說, 團隊範本可能功能特別強大, 因為它們可協助您在整個組織中快速部署一致的團隊。 範本也可以協助職員瞭解如何有效地使用 Teams。

Teams 中包括專為零售商需求設計的範本。 使用這些預先建立的範本快速建立團隊, 讓職員溝通及共同作業。 本文將介紹各個 Teams 範本, 並建議如何使用範本。

管理及使用團隊範本的方式取決於您是系統管理員或開發人員。

|如果您是: | 那麼, 您: |
| ---- | --------- |
| 系統管理員或 IT 專業人員 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 開發人員 | [使用 Microsoft Graph](#use-team-templates-with-microsoft-graph)從團隊範本建立團隊。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理團隊範本

身為系統管理員, 您可以在 Microsoft Teams 系統管理中心管理團隊範本。 您可以在這裡檢視每個範本的詳細資訊。 您也可以[建立及指派範本原則](templates-policies.md)給職員, 以控制他們在 Teams 中[建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)時看到的範本。

若要深入瞭解一般團隊範本, 請參閱[在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。

我們目前提供下列預先建立的零售團隊範本。 若要查看, 請前往 Teams 系統管理中心左側版面配置, 前往 **Teams** > **團隊範本**。

> [!NOTE]
> 星號 (*) 表示範本是 *Microsoft 365 連線的範本*。 當使用者使用範本建立團隊時，連線的 SharePoint 範本會套用至網站和小組。 網頁、清單和 Power Platform 整合等 SharePoint 元件會自動新增並釘選為小組中 [一般] 頻道的索引標籤。 使用者可以直接從 Teams 中編輯這些頁面和清單。
>
> 若要深入瞭解 SharePoint 範本，請參閱 [套用及自訂 SharePoint 網站範本](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)。

### <a name="manage-a-store"></a>管理市集*

將零售員工彙集在集中的體驗，以管理工作、共用文件及解決客戶問題。 整合其他應用程式以簡化班次開始和結束程式。

> [!div class="mx-tdBreakAll"]
>| 範本類型 |TemplateId | 此範本提供的屬性 |
>| ------------------|-- |----------------------------------------------------- |
>| 管理市集| `retailStore` |頻道： <ul><li>一般<li>Shift Handoff</li><li>Microsoft Store 整備</li><li>Learning</li></ul> 應用程式： <ul><li>核准</li><li>檢查</li><li>清單<ul><li>庫存清單</li></ul></li><li>SharePoint Pages<ul><li>我們的商店</li></ul></li><li>班次</li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>適用于經理的零售*

為一組主管建立一個團隊，以便跨商店或地區共同作業。 例如，如果您的組織有地區，您可以為加州地區建立一個小組，並包含該區域的所有店面管理員，以及該地區的地區經理。

> [!div class="mx-tdBreakAll"]
>| 範本類型| TemplateId | 此範本提供的屬性 |
>| ------------------|- |----------------------------------------------------- |
>| 適用于經理的零售| `retailManagerCollaboration` |頻道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>核准</li><li>檢查</li><li>SharePoint Pages<ul><li>我們的商店</li></ul></li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>以 Microsoft Graph 使用團隊範本

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

以下是預先建立的零售團隊範本。

> [!NOTE]
> 星號 (*) 表示範本是 *Microsoft 365 連線的範本*。 當使用者使用範本建立團隊時，連線的 SharePoint 範本會套用至網站和小組。 網頁、清單和 Power Platform 整合等 SharePoint 元件會自動新增並釘選為小組中 [一般] 頻道的索引標籤。 使用者可以直接從 Teams 中編輯這些頁面和清單。
>
> 若要深入瞭解 SharePoint 範本，請參閱 [套用及自訂 SharePoint 網站範本](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)。

### <a name="manage-a-store"></a>管理市集*

使用此範本為貴組織中的每個零售商店位置建立小組。

> [!div class="mx-tdBreakAll"]
>| 範本類型 | TemplateId | 範本頻道 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 零售業 - <br>商店 | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| 頻道 <ul><li>一般</li><li>Shift Handoff</li><li>Microsoft Store 整備</li><li>Learning</li></ul>團隊屬性 <ul><li>團隊可見度設定為公開</li></ul> <br>成員權限 <ul><li>無法建立、更新或刪除頻道 </li><li>無法新增或移除應用程式 </li><li>無法建立、更新或移除索引標籤</li><li>無法建立、更新或移除連接器</li><ul>|

為貴組織自訂商店範本的建議方法：

- 如果貴組織在每個商店中都有部門，請為每個部門新增頻道。 新增頻道有助於在部門內進行通訊和共同作業。

- 如果貴組織有任何內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。

### <a name="retail-for-managers"></a>適用于經理的零售*

使用此範本建立團隊，讓一組管理員跨商店或地區共同作業。 例如，如果您的組織有地區，您可以為加州地區建立一個小組，並包含該區域的所有店面管理員，以及該地區的地區經理。

> [!div class="mx-tdBreakAll"]
>| 範本類型 | TemplateId | 範本頻道 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 零售業 - <br>主管共同作業 | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| 頻道 <ul><li>一般</li><li>營運</li><li>學習</li></ul>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> <br>成員權限 <ul><li>可以建立、更新或刪除頻道 </li><li>可以新增和移除應用程式 </li><li>可以建立、更新和移除索引標籤</li><li>可以建立、更新和移除連接器</li><ul>|

為貴組織自訂主管共同作業範本的建議方法：

- 如果貴組織有任何與主管相關的內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>如何用 Microsoft Graph 使用團隊範本

若要使用這些範本, 請將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateIds。  若要瞭解如何部署團隊範本, 請參閱 Microsoft Graph 如何[建立團隊](/graph/api/team-post?view=graph-rest-beta)一文。

> [!NOTE]
> 範本中的頻道會自動在 **[一般]** 索引標籤下建立。

### <a name="example-store-template-extension-script"></a>範例：商店範本延伸模組指令碼

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```

> [!NOTE]
> 如果您使用 Microsoft Graph，使用 Microsoft 365 連線的範本從現有的 Microsoft 365 群組或小組建立團隊，連線的 SharePoint 範本不會自動套用至網站或小組。 建立小組之後，您必須手動套用 SharePoint 網站範本。 在 Teams 中，移至團隊，選取右上角的 [ **更多選項** ] > **[在 SharePoint 中開啟]**。 然後選擇 **[設定] 套用**  >  **網站範本**，然後選取對應的網站範本。

## <a name="related-articles"></a>相關文章

- [在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)
- [從範本建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [開始用 Microsoft Graph 使用團隊範本](get-started-with-teams-templates.md)