---
title: 使用零售團隊範本
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
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
ms.openlocfilehash: f3cf6d2e7eb23517477572775e7d18571463957b
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046339"
---
# <a name="use-retail-team-templates"></a>使用零售團隊範本

Microsoft Teams 的團隊範本提供預先定義的設定、頻道和預先安裝應用程式的團隊結構, 讓您快速且輕鬆地建立團隊。

對於零售商來說, 團隊範本可能功能特別強大, 因為它們可協助您在整個組織中快速部署一致的團隊。 範本也可以協助職員瞭解如何有效地使用 Teams。

Teams 中包括專為零售商需求設計的範本。 使用這些預先建立的範本快速建立團隊, 讓職員溝通及共同作業。 本文將介紹各個 Teams 範本, 並建議如何使用範本。

管理及使用團隊範本的方式取決於您是系統管理員或開發人員。

|如果您是: | 那麼, 您: |
| ---- | --------- |
| 系統管理員或 IT 專業人員 |[Teams 系統管理中心管理團隊範本](#manage-team-templates-in-the-teams-admin-center)。檢視團隊範本並申請範本原則, 以控制職員在 Teams 中建立團隊時可使用的範本。 |
| 開發人員 | [使用 Microsoft Graph](#use-team-templates-with-microsoft-graph)從團隊範本建立團隊。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理團隊範本

身為系統管理員, 您可以在 Microsoft Teams 系統管理中心管理團隊範本。 您可以在這裡檢視每個範本的詳細資訊。 您也可以[建立及指派範本原則](templates-policies.md)給職員, 以控制他們在 Teams 中[建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)時看到的範本。

若要深入了解一般團隊範本, 請參閱[在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。

我們目前提供下列預先建立的零售團隊範本。 若要查看, 請前往 Teams 系統管理中心左側版面配置, 前往 **Teams** > **團隊範本**。

### <a name="organize-a-store"></a>組織商店

將零售員工彙集在集中的體驗，以管理工作、共用文件及解決客戶問題。 整合其他應用程式，以簡化班次的開始與結束程序。

| 範本類型 |TemplateId | 此範本提供的屬性 |
| ------------------|-- |----------------------------------------------------- |
|組織商店| `retailStore` |頻道： <ul><li>一般<li>班次交班</li><li>存放區整備<ul><li>檢查&sup1;</li></ul></li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li><li>工作</li><li>班次</li><li>檢查</li></ul>|

&sup1;應用程式已做為索引標籤新增到頻道

### <a name="manager-collaboration"></a>主管共同作業

管理員共同作業範本適合用來建立團隊，以讓一組主管跨商店及區域等進行共同作業。例如，如果您的組織有不同地區，您可以為加州地區建立主管共同作業團隊，並包含該區域的所有商店主管，以及該地區的地區主管。

| 範本類型| TemplateId | 此範本提供的屬性 |
| ------------------|- |----------------------------------------------------- |
|零售管理員|`retailManagerCollaboration` |頻道： <ul><li>一般<li>營運<ul><li>工作 (作業工作)&sup1;</li><li>檢查&sup1;</li></ul></li><li>Learning<ul><li>工作 (Learning 工作)&sup1;</li></ul></li></ul> 應用程式： <ul><li>Wiki</li><li>工作</li><li>檢查</li></ul>|
||||

&sup1;應用程式已做為索引標籤新增到頻道

## <a name="use-team-templates-with-microsoft-graph"></a>以 Microsoft Graph 使用團隊範本

開發人員可以使用 Microsoft Graph 從預先組建的團隊範本建立團隊。若要深入了解在 Microsoft Graph 中使用團隊範本, 請參閱[開始在 Microsoft Graph 中使用團隊範本](get-started-with-teams-templates.md), [Microsoft Teams API 概觀](/graph/teams-concept-overview?view=graph-rest-1.0), 和 [teamsTemplate 資源類型](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

以下是預先建立的零售團隊範本。

### <a name="store"></a>商店

商店範本很適合用來建立團隊，以代表個體零售商店位置。 使用商店範本，您可以為組織的每個零售商店位置建立團隊。

| 範本類型 | TemplateId | 範本頻道 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售業 - <br>商店 | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| 頻道 <ul><li>一般</li><li>交班&sup2;</li><li>存放區整備</li><li>Learning&sup2;</li></ul>團隊屬性 <ul><li>團隊可見度設定為公開</li></ul> <br>成員權限 <ul><li>無法建立、更新或刪除頻道 </li><li>無法新增或移除應用程式 </li><li>無法建立、更新或移除索引標籤</li><li>無法建立、更新或移除連接器</li><ul>|
||||

&sup2;自動將頻道加入我的最愛

為貴組織自訂商店範本的建議方法：

- 如果貴組織在每個商店中都有部門，請為每個部門新增頻道。 新增頻道有助於在部門內進行通訊和共同作業。

- 如果貴組織有任何內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。

### <a name="manager-collaboration"></a>主管共同作業

管理員共同作業範本適合用來建立團隊，以讓一組主管跨商店及區域等進行共同作業。例如，如果您的組織有不同地區，您可以為加州地區建立主管共同作業團隊，並包含該區域的所有商店主管，以及該地區的地區主管。

| 範本類型 | TemplateId | 範本頻道 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售業 - <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 頻道 <ul><li>一般</li><li>作業&sup2;</li><li>Learning&sup2;</li></ul>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> <br>成員權限 <ul><li>可以建立、更新或刪除頻道 </li><li>可以新增和移除應用程式 </li><li>可以建立、更新和移除索引標籤</li><li>可以建立、更新和移除連接器</li><ul>|
||||

&sup2;自動將頻道加入我的最愛

為貴組織自訂主管共同作業範本的建議方法：

- 如果貴組織有任何與主管相關的內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>如何用 Microsoft Graph 使用團隊範本

若要使用這些範本, 請將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateIds。  若要了解如何部署團隊範本, 請參閱 Microsoft Graph 如何[建立團隊](/graph/api/team-post?view=graph-rest-beta)一文。

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

## <a name="related-articles"></a>相關文章

- [在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)
- [從範本建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [開始用 Microsoft Graph 使用團隊範本](get-started-with-teams-templates.md)