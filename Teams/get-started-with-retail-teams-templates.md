---
title: 在零售中開始使用團隊範本
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用團隊範本來建立專為零售商需求而設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec16f919bad5ed696741664836aa3d7127837c5a
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42892363"
---
# <a name="get-started-with-teams-templates-in-retail"></a>在零售中開始使用團隊範本 

團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。

團隊範本擁有圍繞零售商需求設計之小組結構的預先建立的定義。 您可以使用團隊範本快速建立適用于零售商的團隊類型，並在整個組織中進行部署。 您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。

在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。

如果您負責規劃、部署及管理多個零售組織中的多個小組，本文適用于您。 我們假設您已在貴組織中已部署團隊服務。 如果您還沒有推出小組，請先閱讀[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。

若要深入瞭解小組範本的整體資訊，請參閱[開始使用團隊範本](get-started-with-teams-templates.md)。

## <a name="store-template"></a>商店範本

商店範本非常適合用來建立小組代表個別的零售商店位置。 您可以使用 [商店範本]，為貴組織中的每個零售商店位置建立小組。

| 基底範本類型 | baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 面向 <br>存放 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 頻道 <ul><li>倒班切換\*</li><li>教學\*</li></ul>\*自動將通道<br><br>團隊屬性 <ul><li>將團隊可見度設定為 Public</li></ul> <br>成員許可權 <ul><li>無法建立/更新/刪除頻道 </li><li>無法新增/移除 app </li><li>無法建立/更新/移除索引標籤</li><li>無法建立/更新/移除連接器</li><ul>|
||||

為您的組織自訂商店範本的建議方式：

- 如果您的組織在每個商店中都有部門，請為每個部門新增頻道。 這將有利於在部門內進行通訊與共同作業。

- 如果您的組織有任何內部網站（例如，SharePoint 網站），請考慮將其固定為相關團隊頻道中的索引標籤。 請參閱[開始使用團隊範本](get-started-with-teams-templates.md)取得相關指示。

## <a name="manager-collaboration-template"></a>Manager 共同工作範本

Manager 共同工作範本是根據零售商的需求而設計的另一個團隊範本。 Manager 共同工作範本適用于為一組主管建立小組，以便在商店/地區等共同作業。例如，如果您的組織有地區，您可以為加利福尼亞地區建立經理共同作業小組，並包含該地區的所有書店管理員，以及該地區的地區經理。

| 基底範本類型 | baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 面向 <br>存放 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 頻道 <ul><li>作業\*</li><li>教學\*</li></ul>\*自動將通道<br><br>團隊屬性 <ul><li>[團隊可見度] 設定為 [私人]</li></ul> <br>成員許可權 <ul><li>可以建立/更新/刪除頻道 </li><li>可以新增/移除 app </li><li>可以建立/更新/移除索引標籤</li><li>可以建立/更新/移除連接器</li><ul>|
||||

為您的組織自訂管理員共同工作範本的建議方式：

- 如果您的組織擁有與主管相關的任何內部網站（例如，SharePoint 網站），請考慮將其固定為相關小組頻道中的索引標籤（請參閱[這裡](get-started-with-teams-templates.md)的檔以取得指示）。

## <a name="how-to-use-first-party-templates"></a>如何使用第一方範本

若要使用這些範本，只要將申請主體中的 [template@odata. bind] 屬性從 [標準] 變更為上述 TemplateIDs 即可。  如需如何部署團隊範本的詳細資訊，請參閱 Microsoft Graph 文章，瞭解如何[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 範本中的頻道會自動建立在 [一般] 索引標籤底下。

### <a name="example-store-template-extension-script"></a>範例：儲存範本延伸腳本

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
