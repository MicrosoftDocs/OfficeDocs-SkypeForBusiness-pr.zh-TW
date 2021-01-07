---
title: 在 Microsoft 團隊中使用圖形 API 管理私人頻道
author: MikePlumleyMSFT
ms.author: mikeplum
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
description: 瞭解如何使用圖形 API 管理貴組織中的私人頻道。
ms.openlocfilehash: 854e8721dac7d49e258db42845b84480955bfec7
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772036"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>在 Microsoft 團隊中管理私人頻道的生命週期

您可以在這裡找到您需要管理的指導方針，以使用圖形 API 管理組織中的 [專用頻道](https://docs.microsoft.com/microsoftteams/private-channels) 。

## <a name="set-whether-team-members-can-create-private-channels"></a>設定小組成員是否可以建立私人頻道

做為管理員，您可以使用圖形 API 來控制成員是否可以在特定團隊中建立私人頻道。 以下是範例。

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>代表團隊擁有者建立私人頻道

做為管理員，您可以使用圖形 API 代表團隊擁有者建立私人頻道。 例如，如果您的組織想要集中建立私人頻道，您可能會想要執行此動作。

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

以管理員身分，您可以使用圖形 Api 命令來查詢這些 Url。

您可以透過 [圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。

1. 使用下列程式取得指定團隊的專用通道識別碼清單，其中 <group_id> 是團隊的群組識別碼。 在後續的通話中，您將需要這麼做。  (您可以在 [小組]) 的連結中輕鬆找到 [群組識別碼]。

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

以管理員身分，您可以使用圖形 API 來執行這些動作。

您可以透過 [圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。

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

[使用 Microsoft 圖形 API 搭配 Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[清單頻道](https://docs.microsoft.com/graph/api/channel-list)

[建立頻道](https://docs.microsoft.com/graph/api/channel-post)

[將成員新增到頻道](https://docs.microsoft.com/graph/api/conversationmember-add)

[更新頻道中的成員](https://docs.microsoft.com/graph/api/conversationmember-update)

[移除頻道中的成員](https://docs.microsoft.com/graph/api/conversationmember-delete)
