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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在您的組織中管理私人頻道的生命週期。
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969411"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="e174e-103">在 Microsoft 團隊中管理私人頻道的生命週期</span><span class="sxs-lookup"><span data-stu-id="e174e-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="e174e-104">您可以在這裡找到在組織中管理[私人頻道](private-channels.md)生命週期所需的指導方針。</span><span class="sxs-lookup"><span data-stu-id="e174e-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="e174e-105">設定小組成員是否可以建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="e174e-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="e174e-106">小組擁有者可以關閉或開啟成員在小組設定中建立私人頻道的能力。</span><span class="sxs-lookup"><span data-stu-id="e174e-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="e174e-107">若要這樣做，請在團隊的 [**設定**] 索引標籤上，關閉或開啟 [**允許成員建立私人頻道**]。</span><span class="sxs-lookup"><span data-stu-id="e174e-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="e174e-108">做為管理員，您可以使用圖形 API 來控制成員是否可以在特定團隊中建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="e174e-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="e174e-109">以下是範例。</span><span class="sxs-lookup"><span data-stu-id="e174e-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="e174e-110">設定貴組織中的使用者是否可以建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="e174e-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="e174e-111">身為管理員，您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則，以控制貴組織中的哪些使用者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="e174e-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e174e-112">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e174e-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e174e-113">使用團隊原則設定貴組織中的哪些使用者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="e174e-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="e174e-114">若要深入瞭解，請參閱[管理團隊中的團隊原則](teams-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e174e-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e174e-115">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e174e-115">Using PowerShell</span></span>

<span data-ttu-id="e174e-116">使用**CsTeamsChannelsPolicy**設定您組織中的哪些使用者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="e174e-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="e174e-117">將**AllowPrivateChannelCreation**參數設定為**true** ，以允許獲指派原則的使用者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="e174e-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="e174e-118">如果將參數設定為**false** ，就會關閉為指派了原則的使用者建立私有通道的功能。</span><span class="sxs-lookup"><span data-stu-id="e174e-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="e174e-119">若要深入瞭解，請參閱[新-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e174e-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="e174e-120">代表團隊擁有者建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="e174e-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="e174e-121">做為管理員，您可以使用 PowerShell 或 Graph API 代表團隊擁有者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="e174e-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="e174e-122">例如，如果您的組織想要集中建立私人頻道，您可能會想要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e174e-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e174e-123">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e174e-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="e174e-124">使用圖形 API</span><span class="sxs-lookup"><span data-stu-id="e174e-124">Using Graph API</span></span>

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="e174e-125">取得所有私人頻道訊息的清單</span><span class="sxs-lookup"><span data-stu-id="e174e-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="e174e-126">您可能會想要取得在私人頻道中張貼的所有訊息和回復的清單，以供封存和審核之用。</span><span class="sxs-lookup"><span data-stu-id="e174e-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="e174e-127">以下說明如何使用圖形 API 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="e174e-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="e174e-128">尋找小組中所有私人頻道的 SharePoint Url</span><span class="sxs-lookup"><span data-stu-id="e174e-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="e174e-129">無論您是要針對私人頻道中的檔案執行 eDiscovery 或法律封存，或是想要建立在特定專用通道中放入檔案的一系列商務用應用程式，您都想要查詢建立的唯一 SharePoint 網站集合。每個專用通道。</span><span class="sxs-lookup"><span data-stu-id="e174e-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="e174e-130">以管理員身分，您可以使用 PowerShell 或圖形 Api 命令來查詢這些 Url。</span><span class="sxs-lookup"><span data-stu-id="e174e-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e174e-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e174e-131">Using PowerShell</span></span>

1. <span data-ttu-id="e174e-132">使用您的系統管理員帳戶安裝並[連線至 SharePoint Online 管理命令](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)介面。</span><span class="sxs-lookup"><span data-stu-id="e174e-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="e174e-133">執行下列動作，其中&lt;group_id&gt;是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="e174e-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="e174e-134">（您可以輕鬆地在小組連結中找到群組識別碼）。</span><span class="sxs-lookup"><span data-stu-id="e174e-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="e174e-135">使用圖形 API</span><span class="sxs-lookup"><span data-stu-id="e174e-135">Using Graph API</span></span>

<span data-ttu-id="e174e-136">您可以透過[圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。</span><span class="sxs-lookup"><span data-stu-id="e174e-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="e174e-137">使用下列程式取得指定團隊的專用通道識別碼清單，其中 <group_id> 是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="e174e-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="e174e-138">在後續的通話中，您將需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="e174e-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="e174e-139">（您可以在小組連結中輕鬆找到群組識別碼）。</span><span class="sxs-lookup"><span data-stu-id="e174e-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="e174e-140">**徵求**</span><span class="sxs-lookup"><span data-stu-id="e174e-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="e174e-141">**應對**</span><span class="sxs-lookup"><span data-stu-id="e174e-141">**Response**</span></span>

    ```
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

2. <span data-ttu-id="e174e-142">針對您想要取得 SharePoint URL 的每個專用通道，請進行下列要求，其中&lt;channel_id&gt;是頻道 id。</span><span class="sxs-lookup"><span data-stu-id="e174e-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="e174e-143">**徵求**</span><span class="sxs-lookup"><span data-stu-id="e174e-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="e174e-144">**應對**</span><span class="sxs-lookup"><span data-stu-id="e174e-144">**Response**</span></span>

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="e174e-145">在私人頻道中列出並更新擁有者和成員的角色</span><span class="sxs-lookup"><span data-stu-id="e174e-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="e174e-146">您可能會想要列出私人通道的擁有者和成員，決定是否需要將專用通道的特定成員升級為擁有者。</span><span class="sxs-lookup"><span data-stu-id="e174e-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="e174e-147">當您擁有已離開組織的專用頻道擁有者，且專用頻道需要系統管理員協助才能宣告頻道擁有權時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="e174e-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="e174e-148">以管理員身分，您可以使用 PowerShell 或圖形 Api 命令來查詢這些 Url。</span><span class="sxs-lookup"><span data-stu-id="e174e-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e174e-149">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e174e-149">Using PowerShell</span></span>

1. <span data-ttu-id="e174e-150">使用您的系統管理員帳戶安裝並連接至[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="e174e-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="e174e-151">執行下列操作，其中&lt;group_id&gt;是團隊的群組識別碼，而&lt;channel_id&gt;是通道 id。</span><span class="sxs-lookup"><span data-stu-id="e174e-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="e174e-152">**徵求**</span><span class="sxs-lookup"><span data-stu-id="e174e-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="e174e-153">**應對**</span><span class="sxs-lookup"><span data-stu-id="e174e-153">**Response**</span></span>

    ```
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

3. <span data-ttu-id="e174e-154">將成員升級為擁有者。</span><span class="sxs-lookup"><span data-stu-id="e174e-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="e174e-155">使用圖形 API</span><span class="sxs-lookup"><span data-stu-id="e174e-155">Using Graph API</span></span>

<span data-ttu-id="e174e-156">您可以透過[圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。</span><span class="sxs-lookup"><span data-stu-id="e174e-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="e174e-157">使用下列專案，其中&lt;group_id&gt;是團隊的群組識別碼，而&lt;channel_id&gt;是通道 id。</span><span class="sxs-lookup"><span data-stu-id="e174e-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="e174e-158">**徵求**</span><span class="sxs-lookup"><span data-stu-id="e174e-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="e174e-159">**應對**</span><span class="sxs-lookup"><span data-stu-id="e174e-159">**Response**</span></span>

    ```
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
2.  <span data-ttu-id="e174e-160">使用下列專案將成員升級為擁有者&lt;，其中 group_id&gt;、 &lt;channel_id&gt;和&lt;識別碼&gt;都是從先前的呼叫傳回的。</span><span class="sxs-lookup"><span data-stu-id="e174e-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="e174e-161">請注意&lt;，&gt;從&lt;先前&gt;的呼叫傳回的識別碼和 userId 不一樣且無法互換。</span><span class="sxs-lookup"><span data-stu-id="e174e-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="e174e-162">請確定您使用&lt;的&gt;是 id。</span><span class="sxs-lookup"><span data-stu-id="e174e-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="e174e-163">**徵求**</span><span class="sxs-lookup"><span data-stu-id="e174e-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="e174e-164">**應對**</span><span class="sxs-lookup"><span data-stu-id="e174e-164">**Response**</span></span>

    ```
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

## <a name="related-topics"></a><span data-ttu-id="e174e-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="e174e-165">Related topics</span></span>

- [<span data-ttu-id="e174e-166">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="e174e-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="e174e-167">使用 Microsoft Graph API 與團隊搭配運作</span><span class="sxs-lookup"><span data-stu-id="e174e-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="e174e-168">清單頻道</span><span class="sxs-lookup"><span data-stu-id="e174e-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="e174e-169">建立頻道</span><span class="sxs-lookup"><span data-stu-id="e174e-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="e174e-170">將成員新增到頻道</span><span class="sxs-lookup"><span data-stu-id="e174e-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="e174e-171">更新頻道中的成員</span><span class="sxs-lookup"><span data-stu-id="e174e-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="e174e-172">移除頻道中的成員</span><span class="sxs-lookup"><span data-stu-id="e174e-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)