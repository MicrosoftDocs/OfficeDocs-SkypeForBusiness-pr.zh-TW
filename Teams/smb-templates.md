---
title: 使用 Microsoft Graph 建置的中小型企業團隊範本
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
description: 使用 microsoft Graph 中內建Microsoft Teams預先定義的範本，輕鬆快速地建立中小型企業的小組。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5317b989bd7fe77f34743b6554cd356c226c2fa8
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646302"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>內建于 Microsoft Graph 中小型企業的小組範本

Microsoft Teams 的團隊範本提供預先定義的設定、頻道和預先安裝應用程式的團隊結構, 讓您快速且輕鬆地建立團隊。

對於中小型企業來說，範本功能特別強大，因為它們可協助您在組織中快速部署Teams。 範本也可協助使用者熟悉如何有效地使用Teams。 如果您負責在組織中規劃、部署和管理多個小組，本文適合供您使用。

我們目前為中小型企業提供三個預先建立的範本，供您用於各種情況。 所有範本都會建立 *私人* 團隊。 在您建立團隊並準備好要推行到您的組織之後，您可以視需要將隱私權設定為 [ *組織全* 局] 或 [ *公開*]。

若要深入瞭解一般團隊範本，請參閱[使用 Microsoft Graph 使用團隊範本開始](get-started-with-teams-templates.md)。

## <a name="company-wide-template"></a>Company-Wide範本

Company-Wide範本適用于整個公司的通訊和共同作業。 您可以使用 [一般] 頻道來發佈全公司公告、產業新聞或高階主管文章。 人力資源通道是整合所有人力資源相關活動的好地方，例如職文、新進員工入職、訓練及開發。 [有趣小玩意] 頻道為所有隨機和有趣的貼文提供社交平臺。

| 範本類型  | TemplateId | 此範本提供的屬性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>全公司 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 頻道 <ul><li>一般\*</li><li>人力資源\*</li><li>有趣的內容\*</li></ul><br> 應用程式<ul><li>釘選到人力資源頻道) 公司入口網站 (網站 </li> </UL><br>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> |

*自動加入我的最愛的頻道 

若要從預先定義的範本中使用預設設定來建立Company-Wide團隊，請在要求內文中提供團隊物件的 JSON 表示。 若要深入瞭解如何部署團隊範本，請參閱 Microsoft Graph[建立團隊一文](/graph/api/team-post?view=graph-rest-beta)。

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

## <a name="executive-team-template"></a>高階主管團隊範本

高階主管小組範本很適合用來建立一個團隊，讓公司高階主管在公司計畫上溝通及共同作業，例如年度優先順序、會計預算、策略計畫及主要用戶端。 此範本隨附 *私人* 頻道，可邀請特定主題的選取使用者。

| 範本類型  | TemplateId | 此範本提供的屬性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>高階主管團隊 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 頻道 <ul><li>一般\*</li><li>私人 \*</li></ul> 應用程式<ul><li>釘選到 **私人** 頻道) OneNote (</li> <li>Planner (釘選到 **私人** 頻道)  </li></ul><br>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> | 

*自動加入我的最愛的頻道<br>

若要從預先定義的範本中使用預設設定來建立高階主管團隊，請在要求內文中提供團隊物件的 JSON 表示。 若要深入瞭解如何部署團隊範本，請參閱 Microsoft Graph[建立團隊一文](/graph/api/team-post?view=graph-rest-beta)。

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

部門小組範本可用於為個別部門或專案建立小組。 財務小組範本適用于財務小組成員和執行小組成員中的所有文章、公告，以及每日共同作業和溝通。 範本隨附 *私人* 頻道，可邀請特定主題的選取使用者。

我們也提供下列適用于財務小組的腳本，可用來將範本延伸至其他部門或特定專案，方法是根據您的喜好新增、刪除或編輯。 例如，如果您 *有行銷部門* ，則可以將小組從 *財務* 重新 *命名為行銷* 來調整腳本，以建立新的行銷團隊

| 範本類型 | TemplateId | 此範本提供的屬性 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>財務  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 頻道 <ul><li>一般\*</li><li>私人 \*</li></ul><br> 應用程式<ul><li>釘選到 **私人** 頻道) OneNote (</li> <li>Planner (釘選到 **私人** 頻道)  </li> </ul><br>團隊屬性 <ul><li>團隊可見度設定為私人</li></ul> | 

*自動加入我的最愛的頻道

若要從預先定義的範本中使用預設設定來建立財務小組，請在要求內文中提供團隊物件的 JSON 表示。 若要深入瞭解如何部署團隊範本，請參閱 Microsoft Graph[建立團隊一文](/graph/api/team-post?view=graph-rest-beta)。

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

### <a name="example-finance-team-template-extension-script"></a>範例：Finance Team 範本擴充功能腳本

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

- [在 Teams 系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)
- [開始用 Microsoft Graph 使用團隊範本](get-started-with-teams-templates.md)
- [在](/graph/api/team-post?view=graph-rest-beta) 預覽) 中建立團隊 (
