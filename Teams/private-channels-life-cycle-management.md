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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用 API 管理貴Graph頻道。
ms.openlocfilehash: 263c490156a3dc02ddc8f81233a049ff020c72f8
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278526"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="f9ad3-103">管理私人頻道在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9ad3-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="f9ad3-104">您可以在這裡找到管理所需的指南，使用 Graph API 來管理[Teams中的](./private-channels.md)私人頻道。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](./private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="f9ad3-105">設定小組成員是否可以建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="f9ad3-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="f9ad3-106">做為系統管理員，您可以使用 Graph API 來控制成員是否可以在特定的團隊中建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="f9ad3-107">以下是範例。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="f9ad3-108">代表團隊擁有者建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="f9ad3-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="f9ad3-109">做為系統管理員，您可以使用 Graph API 代表團隊擁有者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="f9ad3-110">例如，如果您的組織想要集中建立私人頻道，您可能會想要這麼做。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="f9ad3-111">取得所有私人頻道訊息的清單</span><span class="sxs-lookup"><span data-stu-id="f9ad3-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="f9ad3-112">您可能會想要取得張貼在私人頻道中所有郵件和回復的清單，以便進行存檔和稽核。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="f9ad3-113">以下是使用 API Graph執行此操作的方法。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="f9ad3-114">尋找SharePoint中所有私人頻道的 URL</span><span class="sxs-lookup"><span data-stu-id="f9ad3-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="f9ad3-115">無論您是想要在私人頻道中執行 eDiscovery 或合法保留檔案，或想要建立將檔案放在特定私人頻道中的自訂應用程式，您都想要查詢每個私人頻道所建立的唯一 SharePoint 網站集合。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="f9ad3-116">系統管理員可以使用 API 命令Graph查詢這些 URL。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="f9ad3-117">您可以透過您的 Explorer 嘗試Graph[命令](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="f9ad3-118">使用下列專案取得給定團隊的私人頻道識別碼清單，其中<group_id>為團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="f9ad3-119">在後續通話中，您需要這項功能。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="f9ad3-120"> (您可以在小組連結中輕鬆找到群組識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="f9ad3-121">**請求**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="f9ad3-122">**回應**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-122">**Response**</span></span>

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

2. <span data-ttu-id="f9ad3-123">針對您想要取得該 URL 的每個私人SharePoint，請提出下列要求，channel_id &lt; &gt; 為頻道識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="f9ad3-124">**請求**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="f9ad3-125">**回應**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="f9ad3-126">在私人頻道中列出及更新擁有者和成員的角色</span><span class="sxs-lookup"><span data-stu-id="f9ad3-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="f9ad3-127">您可能會想要列出私人頻道的擁有者和成員，以決定是否需要將私人頻道的某些成員升級為擁有者。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="f9ad3-128">當您有私人頻道的擁有者已離開組織，而私人頻道需要系統管理員協助以要求該頻道的擁有權時，可能會發生此情況。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="f9ad3-129">做為系統管理員，您可以使用 Graph API 來執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="f9ad3-130">您可以透過您的 Explorer 嘗試Graph[命令](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="f9ad3-131">請使用下列專案，group_id是團隊的群組識別碼，channel_id &lt; &gt; 為頻道 &lt; &gt; 識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="f9ad3-132">**請求**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```

    <span data-ttu-id="f9ad3-133">**回應**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-133">**Response**</span></span>

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

2. <span data-ttu-id="f9ad3-134">使用下列專案將成員升級為擁有者，其中group_id 、channel_id 和 id 會從上一個 &lt; &gt; &lt; &gt; &lt; &gt; 通話中返回。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="f9ad3-135">請注意，從前一個通話中返回的識別碼和 userId 並不相同， &lt; &gt; &lt; &gt; 無法交換。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="f9ad3-136">請確定您用 &lt; 的是識別碼 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="f9ad3-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="f9ad3-137">**請求**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="f9ad3-138">**回應**</span><span class="sxs-lookup"><span data-stu-id="f9ad3-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="f9ad3-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="f9ad3-139">Related topics</span></span>

[<span data-ttu-id="f9ad3-140">使用 Microsoft 圖形 API 搭配 Teams</span><span class="sxs-lookup"><span data-stu-id="f9ad3-140">Use the Microsoft Graph API to work with Teams</span></span>](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="f9ad3-141">清單頻道</span><span class="sxs-lookup"><span data-stu-id="f9ad3-141">List channels</span></span>](/graph/api/channel-list)

[<span data-ttu-id="f9ad3-142">建立頻道</span><span class="sxs-lookup"><span data-stu-id="f9ad3-142">Create channel</span></span>](/graph/api/channel-post)

[<span data-ttu-id="f9ad3-143">新增成員至頻道</span><span class="sxs-lookup"><span data-stu-id="f9ad3-143">Add member to channel</span></span>](/graph/api/conversationmember-add)

[<span data-ttu-id="f9ad3-144">更新頻道中的成員</span><span class="sxs-lookup"><span data-stu-id="f9ad3-144">Update member in channel</span></span>](/graph/api/conversationmember-update)

[<span data-ttu-id="f9ad3-145">從頻道移除成員</span><span class="sxs-lookup"><span data-stu-id="f9ad3-145">Remove member from channel</span></span>](/graph/api/conversationmember-delete)