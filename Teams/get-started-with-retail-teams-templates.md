---
title: 開始使用零售業 Teams 範本
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Teams 範本，透過提供預先定義的設定、頻道和預先安裝的應用程式，以建立專為零售商需求設計的團隊結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d72f88bb33dca16254ec09a2ea89ac90a0e7aca
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995141"
---
# <a name="create-a-team-using-teams-retail-templates"></a>使用 Teams 零售範本建立團隊

Microsoft Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。

Teams 範本具有專為零售商需求設計的團隊結構預先建立的定義。 您可以使用 Teams 範本快速建立適合零售商的團隊類型，並在整個組織中部署。 您也可以擴充 Teams 範本，以建立專為您特定組織需求量身打造的團隊。

本文將介紹各個 Teams 範本，並建議如何使用範本。

如果您負責規劃、部署和管理整個零售組織的多個團隊，本文適合您。 您已在組織中部署 Teams 服務。 如果您尚未推出 Teams，請先閱讀[如何推出 Microsoft Teams](./deploy-overview.md)。

如需深入了解一般 Teams 範本，請參閱 [Teams 範本入門](get-started-with-teams-templates.md)。

| 誰 | 使用方法： |
| ---- | --------- |
| 系統管理員和 IT 專業人員 | [使用 Teams 系統管理中心](#use-the-teams-templates-in-the-teams-admin-center) ，根據零售 Teams 範本建立團隊。|
| 開發人員和系統整合者 | [使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) 根據零售 Teams 範本建立團隊。 |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>使用 Teams 系統管理中心的 Teams 範本

### <a name="organize-a-store"></a>組織商店

將零售員工彙集在集中的體驗，以管理工作、共用文件及解決客戶問題。 整合其他應用程式，以簡化班次的開始與結束程序。

| 基本範本類型 |baseTemplateId | 此基本範本提供的屬性 |
| ------------------|-- |----------------------------------------------------- |
|組織商店|`retailStore`|頻道： <ul><li>一般<li>班次交班</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>主管共同作業

管理員共同合作範本非常適合建立團隊，讓一組主管跨市/地區共同合作。例如，如果貴組織有地區，您可以為加州地區建立管理員共同合作小組，並包含該區域的所有商店管理員，以及該地區的地區管理員。

| 基本範本類型| baseTemplateId | 此基本範本提供的屬性 |
| ------------------|- |----------------------------------------------------- |
|零售 - 主管共同作業|`retailManagerCollaboration` |頻道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>使用 Teams 範本與 Microsoft Graph

### <a name="store-template"></a>商店範本

商店範本很適合用來建立團隊，以代表個體零售商店位置。 使用商店範本，您可以為組織的每個零售商店位置建立團隊。

| 基礎範本類型 | baseTemplateId | 此基礎範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售業 - <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 頻道 <ul><li>班次交班\*</li><li>學習\*</li></ul>\*自動將頻道加入我的最愛<br><br>團隊屬性 <ul><li>團隊可見度設定為公開</li></ul> <br>成員權限 <ul><li>無法建立/更新/刪除頻道 </li><li>無法新增/移除應用程式 </li><li>無法建立/更新/移除索引標籤</li><li>無法建立/更新/移除連接器</li><ul>|
||||

為貴組織自訂商店範本的建議方法：

- 如果貴組織在每個商店中都有部門，請為每個部門新增頻道。 新增頻道有助於在部門內進行通訊和共同作業。

- 如果貴組織有任何內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。 請參閱 [Teams 範本入門](get-started-with-teams-templates.md) 以取得指示。

### <a name="manager-collaboration-template"></a>主管共同作業範本

主管共同作業範本是專為零售商需求設計的另一個 Teams 範本。 主管共同作業範本很適合建立團隊，讓一組主管跨商店/地區共同作業等等。 例如，如果您的組織有不同地區，您可以為加州地區建立主管共同作業團隊，並包含該區域的所有商店主管，以及該地區的地區主管。

| 基礎範本類型 | baseTemplateId | 此基礎範本提供的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售業 - <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 頻道 <ul><li>作業\*</li><li>學習\*</li></ul>\*自動將頻道加入我的最愛<br><br>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> <br>成員權限 <ul><li>可以建立/更新/刪除頻道 </li><li>可以新增/移除應用程式 </li><li>可以建立/更新/移除定位字元</li><li>可以建立/更新/移除連接器</li><ul>|
||||

為貴組織自訂主管共同作業範本的建議方法：

- 如果貴組織有任何與主管相關的內部網站 (例如 SharePoint 網站)，請考慮將它們釘選為相關團隊頻道中的索引標籤。 您可以查看 [Microsoft Teams 範本文件](get-started-with-teams-templates.md)的指示。

## <a name="how-to-use-first-party-templates"></a>如何使用第一方範本

若要使用這些範本，請將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateDs。  若要了解如何部署 Teams 範本，請參閱 Microsoft Graph 文章，以了解如何[建立團隊](/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 範本中的頻道會自動在 [一般] 索引標籤下建立。

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
