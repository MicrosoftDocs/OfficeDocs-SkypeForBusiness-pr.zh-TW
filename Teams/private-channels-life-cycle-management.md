---
title: 在 Microsoft 團隊中管理私人頻道的生命週期
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在您的組織中管理私人頻道的生命週期。
ms.openlocfilehash: 45d9591eed2bd3a880d3ca3e2ceb2252bf6f8898
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326690"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>在 Microsoft 團隊中管理私人頻道的生命週期

您可以在這裡找到在組織中管理[私人頻道](private-channels.md)生命週期所需的指導方針。

> [!IMPORTANT]
> 如果您使用本文中的 PowerShell 步驟來管理私人通道，您必須從[PowerShell 測試庫](https://www.poshtestgallery.com/packages/MicrosoftTeams/)安裝並使用最新的「團隊 PowerShell」模組的預發行版本本。 如需如何安裝模組的步驟，請參閱[安裝團隊 PowerShell 模組的預發行版本本](install-prerelease-teams-powershell-module.md)。 最新公開提供的團隊 PowerShell 模組版本不支援管理專用通道。

## <a name="set-whether-team-members-can-create-private-channels"></a>設定小組成員是否可以建立私人頻道

小組擁有者可以關閉或開啟成員在小組設定中建立私人頻道的能力。 若要這樣做，請在團隊的 [**設定**] 索引標籤上，關閉或開啟 [**允許成員建立私人頻道**]。

做為管理員，您可以使用圖形 API 來控制成員是否可以在特定團隊中建立私人頻道。 以下是範例。

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>設定貴組織中的使用者是否可以建立私人頻道

身為管理員，您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則，以控制貴組織中的哪些使用者可以建立私人頻道。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

使用團隊原則設定貴組織中的哪些使用者可以建立私人頻道。 若要深入瞭解，請參閱[管理團隊中的團隊原則](teams-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell

使用**CsTeamsChannelsPolicy**設定您組織中的哪些使用者可以建立私人頻道。 將**AllowPrivateChannelCreation**參數設定為**true** ，以允許獲指派原則的使用者建立私人頻道。 如果將參數設定為**false** ，就會關閉為指派了原則的使用者建立私有通道的功能。

若要深入瞭解，請參閱[新-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>代表團隊擁有者建立私人頻道

做為管理員，您可以使用 PowerShell 或 Graph API 代表團隊擁有者建立私人頻道。 例如，如果您的組織想要集中建立私人頻道，您可能會想要執行此動作。

### <a name="using-powershell"></a>使用 PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>使用圖形 API

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>取得所有私人頻道訊息的清單

您可能會想要取得在私人頻道中張貼的所有訊息和回復的清單，以供封存和審核之用。  以下說明如何使用圖形 API 來執行這項作業。

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>尋找小組中所有私人頻道的 SharePoint Url

無論您是要針對私人頻道中的檔案執行 eDiscovery 或法律封存，或是想要建立將檔案放在特定專用通道中的自訂應用程式，您都會希望能查詢針對每個私人通道建立的唯一 SharePoint 網站集合。

以管理員身分，您可以使用 PowerShell 或圖形 Api 命令來查詢這些 Url。

### <a name="using-powershell"></a>使用 PowerShell

1. 使用您的系統管理員帳戶安裝並[連線至 SharePoint Online 管理命令](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)介面。
2. 執行下列動作，其中 &lt; group_id &gt; 是團隊的群組識別碼。 （您可以輕鬆地在小組連結中找到群組識別碼）。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>使用圖形 API

您可以透過[圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。

1. 使用下列程式取得指定團隊的專用通道識別碼清單，其中 <group_id> 是團隊的群組識別碼。 在後續的通話中，您將需要這麼做。 （您可以在小組連結中輕鬆找到群組識別碼）。

    **徵求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **應對**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. 針對您想要取得 SharePoint URL 的每個專用通道，請進行下列要求，其中 &lt; channel_id &gt; 是頻道 id。

    **徵求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **應對**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>在私人頻道中列出並更新擁有者和成員的角色

您可能會想要列出私人通道的擁有者和成員，決定是否需要將專用通道的特定成員升級為擁有者。 當您擁有已離開組織的專用頻道擁有者，且專用頻道需要系統管理員協助才能宣告頻道擁有權時，就會發生這種情況。

以管理員身分，您可以使用 Microsoft 團隊系統管理中心、PowerShell 或圖形 API 來執行這些動作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

若要瞭解如何使用 Microsoft 團隊系統管理中心管理團隊成員，請參閱在[Microsoft 團隊系統管理中心管理團隊](manage-teams-in-modern-portal.md)。

### <a name="using-powershell"></a>使用 PowerShell

1. 執行下列動作，其中 &lt; group_id &gt; 是團隊的群組識別碼，而 &lt; channel_name &gt; 是頻道名稱。

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. 將成員升級為擁有者。

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>使用圖形 API

您可以透過[圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。

1. 使用下列專案，其中 &lt; group_id &gt; 是團隊的群組識別碼，而 &lt; CHANNEL_ID &gt; 是通道 id。

    **徵求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **應對**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. 使用下列專案將成員升級為擁有者，其中 &lt; group_id &gt; 、 &lt; channel_id &gt; 和 &lt; 識別碼 &gt; 都是從先前的呼叫傳回的。 請注意 &lt; ， &gt; &lt; &gt; 從先前的呼叫傳回的識別碼和 userId 不一樣且無法互換。 請確定您使用 &lt; 的是 id &gt; 。

    **徵求**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **應對**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [使用 Microsoft 圖形 API 搭配 Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [清單頻道](https://docs.microsoft.com/graph/api/channel-list)
    - [建立頻道](https://docs.microsoft.com/graph/api/channel-post)
    - [將成員新增到頻道](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [更新頻道中的成員](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [移除頻道中的成員](https://docs.microsoft.com/graph/api/conversationmember-delete)
