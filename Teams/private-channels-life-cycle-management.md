---
title: 使用 API 管理Microsoft Teams中的Graph頻道
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何使用 API 管理貴Graph頻道。
ms.openlocfilehash: b0b915529d9d4bc780215afceead61ebf31e5259
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2022
ms.locfileid: "62064869"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>管理私人頻道在 Microsoft Teams

您可以在這裡找到使用 Graph API 管理Teams[私人](./private-channels.md)通道所需的指引。

## <a name="set-whether-team-members-can-create-private-channels"></a>設定小組成員是否可以建立私人頻道

做為系統管理員，您可以使用 Graph API 來控制成員是否可以在特定的團隊中建立私人頻道。 以下是範例。

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>代表團隊擁有者建立私人頻道

做為系統管理員，您可以使用 Graph API 代表團隊擁有者建立私人頻道。 例如，如果您的組織想要集中建立私人頻道，您可能會想要這麼做。

```Graph API
POST /teams/{id}/channels
{
    "membershipType": "Private",
    "displayName": "<Channel_Name>",
    "members": [
        {
            "@odata.type": "#microsoft.graph.aadUserConversationMember",
            "user@odata.bind": "https://graph.microsoft.com/v1.0/users('<user_id>')",
            "roles": [
                "owner"
            ]
        }
    ]
}
            
```

## <a name="get-a-list-of-all-private-channel-messages"></a>取得所有私人頻道訊息的清單

您可能會想要取得張貼在私人頻道中所有郵件和回復的清單，以便進行存檔和稽核。  以下是使用 API Graph執行此操作的方法。

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>尋找SharePoint中所有私人頻道的 URL

無論您是想要在私人頻道中執行 eDiscovery 或合法保留檔案，或想要建立將檔案放在特定私人頻道中的自訂應用程式，您都想要查詢每個私人頻道所建立的唯一 SharePoint 網站集合。

系統管理員可以使用 API 命令Graph查詢這些 URL。

您可以透過您的 Explorer 嘗試Graph[命令](https://developer.microsoft.com/graph/graph-explorer)。

1. 使用下列專案取得給定團隊的私人頻道識別碼清單，其中<group_id>為團隊的群組識別碼。 在後續通話中，您需要這項功能。  (您可以在小組連結中輕鬆找到群組識別碼) 。

    **請求**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **回應**

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

2. 針對您想要取得該 URL 的每個私人SharePoint，請提出下列要求，channel_id &lt; &gt; 為頻道識別碼。

    **請求**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **回應**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>在私人頻道中列出及更新擁有者和成員的角色

您可能會想要列出私人頻道的擁有者和成員，以決定是否需要將私人頻道的某些成員升級為擁有者。 當您有私人頻道的擁有者已離開組織，而私人頻道需要系統管理員協助以要求該頻道的擁有權時，可能會發生此情況。

做為系統管理員，您可以使用 Graph API 來執行這些動作。

您可以透過您的 Explorer 嘗試Graph[命令](https://developer.microsoft.com/graph/graph-explorer)。

1. 請使用下列專案，group_id是團隊的群組識別碼，channel_id &lt; &gt; &lt; &gt; 為頻道識別碼。

    **請求**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members
    ```

    **回應**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/$metadata#teams({group_id}')/channels('{channel_id}')/members",
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

2. 使用下列功能將成員升級為擁有者，其中group_id 、channel_id 和 id 會從上一個 &lt; &gt; &lt; &gt; &lt; &gt; 通話中返回。 請注意，從前一個通話中返回的識別碼和 userId 並不相同， &lt; &gt; &lt; &gt; 無法交換。 請確定您用 &lt; 的是識別碼 &gt; 。

    **請求**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **回應**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>相關主題

[使用 Microsoft 圖形 API 搭配 Teams](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[清單頻道](/graph/api/channel-list)

[建立頻道](/graph/api/channel-post)

[新增成員至頻道](/graph/api/conversationmember-add)

[更新頻道中的成員](/graph/api/conversationmember-update)

[從頻道移除成員](/graph/api/conversationmember-delete)
