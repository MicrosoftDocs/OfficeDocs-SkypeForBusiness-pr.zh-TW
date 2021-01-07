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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="6e4a4-103">在 Microsoft 團隊中管理私人頻道的生命週期</span><span class="sxs-lookup"><span data-stu-id="6e4a4-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="6e4a4-104">您可以在這裡找到您需要管理的指導方針，以使用圖形 API 管理組織中的 [專用頻道](https://docs.microsoft.com/microsoftteams/private-channels) 。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](https://docs.microsoft.com/microsoftteams/private-channels) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="6e4a4-105">設定小組成員是否可以建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="6e4a4-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="6e4a4-106">做為管理員，您可以使用圖形 API 來控制成員是否可以在特定團隊中建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="6e4a4-107">以下是範例。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="6e4a4-108">代表團隊擁有者建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="6e4a4-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="6e4a4-109">做為管理員，您可以使用圖形 API 代表團隊擁有者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="6e4a4-110">例如，如果您的組織想要集中建立私人頻道，您可能會想要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="6e4a4-111">取得所有私人頻道訊息的清單</span><span class="sxs-lookup"><span data-stu-id="6e4a4-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="6e4a4-112">您可能會想要取得在私人頻道中張貼的所有訊息和回復的清單，以供封存和審核之用。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="6e4a4-113">以下說明如何使用圖形 API 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="6e4a4-114">尋找小組中所有私人頻道的 SharePoint Url</span><span class="sxs-lookup"><span data-stu-id="6e4a4-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="6e4a4-115">無論您是要針對私人頻道中的檔案執行 eDiscovery 或法律封存，或是想要建立將檔案放在特定專用通道中的自訂應用程式，您都會希望能查詢針對每個私人通道建立的唯一 SharePoint 網站集合。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="6e4a4-116">以管理員身分，您可以使用圖形 Api 命令來查詢這些 Url。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="6e4a4-117">您可以透過 [圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6e4a4-118">使用下列程式取得指定團隊的專用通道識別碼清單，其中 <group_id> 是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="6e4a4-119">在後續的通話中，您將需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="6e4a4-120"> (您可以在 [小組]) 的連結中輕鬆找到 [群組識別碼]。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="6e4a4-121">**徵求**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="6e4a4-122">**應對**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-122">**Response**</span></span>

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

2. <span data-ttu-id="6e4a4-123">針對您想要取得 SharePoint URL 的每個專用通道，請進行下列要求，其中 &lt; channel_id &gt; 是頻道 id。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="6e4a4-124">**徵求**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="6e4a4-125">**應對**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="6e4a4-126">在私人頻道中列出並更新擁有者和成員的角色</span><span class="sxs-lookup"><span data-stu-id="6e4a4-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="6e4a4-127">您可能會想要列出私人通道的擁有者和成員，決定是否需要將專用通道的特定成員升級為擁有者。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="6e4a4-128">當您擁有已離開組織的專用頻道擁有者，且專用頻道需要系統管理員協助才能宣告頻道擁有權時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="6e4a4-129">以管理員身分，您可以使用圖形 API 來執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="6e4a4-130">您可以透過 [圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6e4a4-131">使用下列專案，其中 &lt; group_id &gt; 是團隊的群組識別碼，而 &lt; CHANNEL_ID &gt; 是通道 id。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="6e4a4-132">**徵求**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="6e4a4-133">**應對**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-133">**Response**</span></span>

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
2. <span data-ttu-id="6e4a4-134">使用下列專案將成員升級為擁有者，其中 &lt; group_id &gt; 、 &lt; channel_id &gt; 和 &lt; 識別碼 &gt; 都是從先前的呼叫傳回的。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="6e4a4-135">請注意 &lt; ， &gt; &lt; &gt; 從先前的呼叫傳回的識別碼和 userId 不一樣且無法互換。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="6e4a4-136">請確定您使用 &lt; 的是 id &gt; 。</span><span class="sxs-lookup"><span data-stu-id="6e4a4-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="6e4a4-137">**徵求**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="6e4a4-138">**應對**</span><span class="sxs-lookup"><span data-stu-id="6e4a4-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="6e4a4-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="6e4a4-139">Related topics</span></span>

[<span data-ttu-id="6e4a4-140">使用 Microsoft 圖形 API 搭配 Teams</span><span class="sxs-lookup"><span data-stu-id="6e4a4-140">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="6e4a4-141">清單頻道</span><span class="sxs-lookup"><span data-stu-id="6e4a4-141">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)

[<span data-ttu-id="6e4a4-142">建立頻道</span><span class="sxs-lookup"><span data-stu-id="6e4a4-142">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)

[<span data-ttu-id="6e4a4-143">將成員新增到頻道</span><span class="sxs-lookup"><span data-stu-id="6e4a4-143">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)

[<span data-ttu-id="6e4a4-144">更新頻道中的成員</span><span class="sxs-lookup"><span data-stu-id="6e4a4-144">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)

[<span data-ttu-id="6e4a4-145">移除頻道中的成員</span><span class="sxs-lookup"><span data-stu-id="6e4a4-145">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
