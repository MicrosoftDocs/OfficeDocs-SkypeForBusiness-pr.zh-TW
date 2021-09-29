---
title: Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: 使用Microsoft Teams Microsoft Graph內建的預先定義範本，以快速且輕鬆地為中小型企業建立團隊。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0855e7a61b52582b283a5c1f7c4c4f966045d743
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991212"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Microsoft 中為中小型企業Graph小組範本

小組範本Microsoft Teams提供預先定義的團隊結構，包括設定、頻道和預先安裝的應用程式，讓您快速且輕鬆地建立團隊。

對於中小型企業而言，範本可能特別強大，因為它們可協助您快速Teams整個組織。 範本也可以協助使用者瞭解如何有效地使用Teams。 如果您負責規劃、部署及管理整個組織的多個團隊，本文適合您閱讀。

我們目前為中小型企業提供三個預先建建的範本，您可以用於各種情況。 所有範本都建立 *私人* 團隊。 建立團隊並準備好要推出至貴組織之後，您可以設定隱私權為 *組織* 範圍或 *公用*，並在適當時設定。

若要深入瞭解一般小組範本，請參閱開始使用[Microsoft](get-started-with-teams-templates.md)Graph。

## <a name="company-wide-template"></a>Company-Wide範本

Company-Wide範本適用于整個公司的通訊和共同合作。 您可以使用一般頻道來發佈全公司的公告、產業新聞或主管文章。 人力資源頻道是整合所有人力資源相關活動的地方，例如職位、新員工入職、訓練及發展。 Fun Stuff 頻道提供所有隨機且有趣的文章的社交平臺。

| 範本類型  | TemplateId | 此範本提供的屬性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>全公司 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 頻道 <ul><li>一般\*</li><li>人力資源\*</li><li>有趣的專案\*</li></ul><br> 應用程式<ul><li>公司入口網站 (釘到人力資源頻道連結)  </li> </UL><br>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> |

*自動最愛的頻道 

若要從Company-Wide範本中採用預設設定來建立團隊，請提供要求內文中團隊物件的 JSON 標記法。 若要深入瞭解如何部署小組範本，請參閱 Microsoft Graph[建立小組一文](/graph/api/team-post?view=graph-rest-beta)。

#### <a name="request"></a>請求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>主管小組範本

執行小組範本是建立一個團隊，讓公司高主管在年度優先順序、財務預算、策略計畫及主要客戶等公司計畫上溝通和共同合作的理想範本。 此範本隨附私人 *頻道* ，可邀請特定主題的選取使用者。

| 範本類型  | TemplateId | 此範本提供的屬性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>高主管小組 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 頻道 <ul><li>一般\*</li><li>私人 \*</li></ul> 應用程式<ul><li>OneNote (釘到私人 **頻道**) </li> <li>Planner (釘到私人 **頻道**)  </li></ul><br>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> | 

*自動最愛的頻道<br>

若要從預先定義的範本中採用預設設定來建立主管團隊，請提供要求內文中團隊物件的 JSON 標記法。 若要深入瞭解如何部署小組範本，請參閱 Microsoft Graph[建立小組一文](/graph/api/team-post?view=graph-rest-beta)。

#### <a name="request"></a>請求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>部門小組範本

部門小組範本可用於為個別部門或專案建立團隊。 財務小組範本適用于財務小組成員和主管小組成員內的所有文章、公告，以及每日共同合作及溝通。 範本隨附私人 *頻道* ，可邀請特定主題的選取使用者。

我們也提供以下腳本給財務小組，可用來將範本新增、刪除或編輯至您的喜好，以將範本延伸到其他部門或特定專案。 例如，如果您有行銷部門，可以將團隊從財務重新命名為行銷，以建立新的行銷小組，以調整腳本 **

| 範本類型 | TemplateId | 此範本提供的屬性 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>財務  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 頻道 <ul><li>一般\*</li><li>私人 \*</li></ul><br> 應用程式<ul><li>OneNote (釘到私人 **頻道**) </li> <li>Planner (釘到私人 **頻道**)  </li> </ul><br>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> | 

*自動最愛的頻道

若要從預先定義的範本中採用預設設定來建立財務小組，請提供要求內文中小組物件的 JSON 標記法。 若要深入瞭解如何部署小組範本，請參閱 Microsoft Graph[建立小組一文](/graph/api/team-post?view=graph-rest-beta)。

#### <a name="request"></a>請求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a>範例：財務小組範本擴充腳本

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>相關主題

- [在系統管理Teams中開始使用範本](get-started-with-teams-templates-in-the-admin-console.md)
- [開始使用 Teams 範本](get-started-with-teams-templates.md)
- [在預覽 (](/graph/api/team-post?view=graph-rest-beta) 中建立) 