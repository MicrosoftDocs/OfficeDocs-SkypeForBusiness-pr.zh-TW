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
ms.openlocfilehash: 527e6421160eefa72b2a9c21e8e8f25303534320
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837323"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>在 Microsoft 團隊中管理私人頻道的生命週期

您可以在這裡找到在組織中管理[私人頻道](private-channels.md)生命週期所需的指導方針。

> [!IMPORTANT]
> 如果您使用本文中的 PowerShell 步驟來管理私人通道，您必須從 PowerShell 測試庫安裝並使用最新版本的團隊 PowerShell 模組。 如需如何執行此動作的步驟，請參閱[從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。 最新的現有團隊 PowerShell 模組版本（目前為[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)）不支援管理私人頻道。

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

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

使用團隊原則設定貴組織中的哪些使用者可以建立私人頻道。 若要深入瞭解，請參閱[管理團隊中的團隊原則](teams-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell

使用**CsTeamsChannelsPolicy**設定您組織中的哪些使用者可以建立私人頻道。 將**AllowPrivateChannelCreation**參數設定為**true** ，以允許獲指派原則的使用者建立私人頻道。 如果將參數設定為**false** ，就會關閉為指派了原則的使用者建立私有通道的功能。

若要深入瞭解，請參閱[新-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>代表團隊擁有者建立私人頻道

做為管理員，您可以使用 PowerShell 或 Graph API 代表團隊擁有者建立私人頻道。 例如，如果您的組織想要集中建立私人頻道，您可能會想要執行此動作。

### <a name="using-powershell"></a>使用 PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
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

無論您是要針對私人頻道中的檔案執行 eDiscovery 或法律封存，或是想要建立在特定專用通道中放入檔案的一系列商務用應用程式，您都想要查詢建立的唯一 SharePoint 網站集合。每個專用通道。

以管理員身分，您可以使用 PowerShell 或圖形 Api 命令來查詢這些 Url。

### <a name="using-powershell"></a>使用 PowerShell

1. 使用您的系統管理員帳戶安裝並[連線至 SharePoint Online 管理命令](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)介面。
2. 執行下列動作，其中&lt;group_id&gt;是團隊的群組識別碼。 （您可以輕鬆地在小組連結中找到群組識別碼）。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
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

2. 針對您想要取得 SharePoint URL 的每個專用通道，請進行下列要求，其中&lt;channel_id&gt;是頻道 id。

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

以管理員身分，您可以使用 PowerShell 或圖形 Api 命令來查詢這些 Url。

### <a name="using-powershell"></a>使用 PowerShell

1. 使用您的系統管理員帳戶安裝並連接至[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。
2. 執行下列操作，其中&lt;group_id&gt;是團隊的群組識別碼，而&lt;channel_id&gt;是通道 id。

    **徵求**

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    **應對**

    ```PowerShell
    HTTP/1.1 200 OK Content-type: application/json
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

3. 將成員升級為擁有者。

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>使用圖形 API

您可以透過[圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。

1. 使用下列專案，其中&lt;group_id&gt;是團隊的群組識別碼，而&lt;channel_id&gt;是通道 id。

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
2.  使用下列專案將成員升級為擁有者&lt;，其中 group_id&gt;、 &lt;channel_id&gt;和&lt;識別碼&gt;都是從先前的呼叫傳回的。 請注意&lt;，&gt;從&lt;先前&gt;的呼叫傳回的識別碼和 userId 不一樣且無法互換。 請確定您使用&lt;的&gt;是 id。

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

## <a name="teams-powershell-module"></a>團隊 Powershell 模組

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組

最新的現有團隊 PowerShell 模組版本（目前為[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)）不支援管理私人頻道。 使用這些步驟，從 PowerShell 測試圖庫中安裝含私用通道支援（目前為1.0.18）的最新版本團隊 PowerShell 模組。

> [!NOTE]
> 請勿從 PowerShell 測試圖庫並排安裝團隊 PowerShell 模組與公用 PowerShell 庫中的模組版本。 請依照下列步驟，先從公用 PowerShell 庫中卸載團隊 PowerShell 模組，然後從 PowerShell 測試圖庫安裝最新版本的模組。

1. 關閉所有現有的 PowerShell 會話。
2. 啟動新的 Windows PowerShell 模組實例。
3. 執行下列動作，從公用 PowerShell 庫中卸載團隊 PowerShell 模組：

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 關閉所有現有的 PowerShell 會話。
5. 再次啟動 Windows PowerShell 模組，然後執行下列動作，以將 PowerShell 測試圖庫註冊為受信任的來源：

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. 執行下列動作，從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組：

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>從 PowerShell 測試圖庫更新到最新版本的團隊 PowerShell 模組

如果您已經從 PowerShell 測試庫安裝團隊 PowerShell 模組，請使用下列步驟更新到最新版本。

1. 關閉所有現有的 PowerShell 會話。
2. 啟動新的 Windows PowerShell 模組實例。
3. 執行下列操作以從 PowerShell 測試圖庫更新目前已安裝的團隊 PowerShell 模組版本：

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)
- [使用 Microsoft Graph API 與團隊搭配運作](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [清單頻道](https://docs.microsoft.com/graph/api/channel-list)
    - [建立頻道](https://docs.microsoft.com/graph/api/channel-post)
    - [將成員新增到頻道](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [更新頻道中的成員](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [移除頻道中的成員](https://docs.microsoft.com/graph/api/conversationmember-delete)
