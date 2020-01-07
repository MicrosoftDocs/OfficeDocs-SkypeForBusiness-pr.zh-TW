---
title: 快速開始使用中小型企業的團隊範本
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: 快速開始使用中小型企業的團隊範本
ms.openlocfilehash: 3ca5e78f3a61f1e272960dc1d7338bd06f81d4c6
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952766"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a>快速開始使用中小型企業的團隊範本

Microsoft 團隊範本可讓您透過提供預先定義的設定、頻道及預先安裝應用程式範本，快速且輕鬆地建立小組。

在中小型企業中，範本特別強大，因為它們可協助管理員快速地在組織中部署團隊。 範本也可協助使用者，並快速開始使用團隊。 如果您負責規劃、部署及管理整個組織中的多個小組，本文適用于您。

我們目前提供了三個第一方的 SMB 範本，您可以在各種情況下利用。 所有範本都會建立*私人*團隊。 在您建立好團隊並準備好要向您的組織中推出後，您就可以視需要將隱私權設定為「*組織內*」或「*公開*」。 若要深入瞭解小組範本的整體資訊，請參閱[開始使用團隊範本](get-started-with-teams-templates.md)。

## <a name="company-wide-template"></a>整個公司的範本
公司範圍的範本適用于與整個公司相關的溝通與共同作業。 您可以在全公司的宣告、行業新聞或主管文章中使用 [一般] 頻道。 人力資源通道是合併所有 HR 相關活動（例如作業文章、新員工加入、訓練及開發）的絕佳位置。 [有趣的內容] 頻道可為所有的隨機及趣味文章提供社交平臺。

| 基底範本類型  | baseTemplateId | 此基礎範本隨附的屬性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>整個公司 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 頻道 <ul><li>一般\*</li><li>人力資源\*</li><li>有趣的內容\*</li></ul><br> 應用程式<ul><li>公司入口網站（已固定至**人力資源**頻道的網站） </li> </UL><br>團隊屬性 <ul><li>[團隊可見度] 設定為 [私人]</li></ul> |

* 自動將通道 

若要從預先定義的範本中取得預設值來建立公司範圍的小組，請在要求內提供小組物件的 JSON 表示。 若要進一步瞭解如何部署團隊範本，請參閱[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的 Microsoft Graph 文章。

#### <a name="request"></a>徵求 
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

## <a name="executive-team-template"></a>總經理小組範本

總經理小組範本適用于建立公司主管的小組，以便在年度優先順序、會計預算、戰略計畫、主要用戶端等公司方案中進行溝通與共同作業。此範本隨附*私人*頻道，以邀請選取使用者取得特定主題。

| 基底範本類型  | baseTemplateId | 此基礎範本隨附的屬性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>主管小組 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 頻道 <ul><li>一般\*</li><li>私有\*</li></ul> 應用程式<ul><li>OneNote （已釘選到**私人**頻道）</li> <li>Planner （釘選到**私人**頻道） </li></ul><br>團隊屬性 <ul><li>[團隊可見度] 設定為 [私人]</li></ul> | 

* 自動將通道<br>

若要從預先定義的範本中取得預設值來建立主管小組，請在要求內提供小組物件的 JSON 表示。 若要進一步瞭解如何部署團隊範本，請參閱[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的 Microsoft Graph 文章。

#### <a name="request"></a>徵求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>部門小組範本

部門小組範本可用於為個別部門或專案建立小組。 [財務小組] 範本適用于財務小組成員中的所有文章、宣告及每日共同作業和通訊，以及適當的管理小組成員。 範本隨附*私人*頻道，以邀請選取使用者提供特定主題。 我們也提供下列適用于財務小組的腳本，透過新增、刪除或編輯您的喜好，就能將範本延伸到其他部門或特定專案。 例如，如果您有*行銷*部門，您可以將團隊從*財務*版重新命名為 [*行銷*]，以建立新的行銷團隊，以調整腳本的改編方式。

| 基底範本類型 | baseTemplateId | 此基礎範本隨附的屬性 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>財務  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 頻道 <ul><li>一般\*</li><li>私有\*</li></ul><br> 應用程式<ul><li>OneNote （已釘選到**私人**頻道）</li> <li>Planner （釘選到**私人**頻道） </li> </ul><br>團隊屬性 <ul><li>[團隊可見度] 設定為 [私人]</li></ul> | 

* 自動將通道

若要從預先定義的範本提取預設值來建立財務小組，請在要求內提供小組物件的 JSON 表示。 若要進一步瞭解如何部署團隊範本，請參閱[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的 Microsoft Graph 文章。

#### <a name="request"></a>徵求 
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

### <a name="example-finance-team-template-extension-script"></a>範例：財務小組範本延伸腳本

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

- [開始使用 Teams 範本](get-started-with-teams-templates.md)
- [建立小組](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)（在預覽中）

