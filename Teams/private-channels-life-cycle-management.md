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
ms.openlocfilehash: 7cd7701a66c03dfc71d89f007eae4addaed0c89a
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403742"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="0266d-103">在 Microsoft 團隊中管理私人頻道的生命週期</span><span class="sxs-lookup"><span data-stu-id="0266d-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="0266d-104">您可以在這裡找到在組織中管理[私人頻道](private-channels.md)生命週期所需的指導方針。</span><span class="sxs-lookup"><span data-stu-id="0266d-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0266d-105">如果您使用本文中的 PowerShell 步驟來管理私人通道，您必須從 PowerShell 測試庫安裝並使用最新版本的團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="0266d-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="0266d-106">如需如何執行此動作的步驟，請參閱[從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。</span><span class="sxs-lookup"><span data-stu-id="0266d-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="0266d-107">最新的現有團隊 PowerShell 模組版本（目前為[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)）不支援管理私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="0266d-108">設定小組成員是否可以建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="0266d-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="0266d-109">小組擁有者可以關閉或開啟成員在小組設定中建立私人頻道的能力。</span><span class="sxs-lookup"><span data-stu-id="0266d-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="0266d-110">若要這樣做，請在團隊的 [**設定**] 索引標籤上，關閉或開啟 [**允許成員建立私人頻道**]。</span><span class="sxs-lookup"><span data-stu-id="0266d-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="0266d-111">做為管理員，您可以使用圖形 API 來控制成員是否可以在特定團隊中建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="0266d-112">以下是範例。</span><span class="sxs-lookup"><span data-stu-id="0266d-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="0266d-113">設定貴組織中的使用者是否可以建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="0266d-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="0266d-114">身為管理員，您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則，以控制貴組織中的哪些使用者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0266d-115">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="0266d-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="0266d-116">使用團隊原則設定貴組織中的哪些使用者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="0266d-117">若要深入瞭解，請參閱[管理團隊中的團隊原則](teams-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0266d-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0266d-118">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0266d-118">Using PowerShell</span></span>

<span data-ttu-id="0266d-119">使用**CsTeamsChannelsPolicy**設定您組織中的哪些使用者可以建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="0266d-120">將**AllowPrivateChannelCreation**參數設定為**true** ，以允許獲指派原則的使用者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="0266d-121">如果將參數設定為**false** ，就會關閉為指派了原則的使用者建立私有通道的功能。</span><span class="sxs-lookup"><span data-stu-id="0266d-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="0266d-122">若要深入瞭解，請參閱[新-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0266d-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="0266d-123">代表團隊擁有者建立私人頻道</span><span class="sxs-lookup"><span data-stu-id="0266d-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="0266d-124">做為管理員，您可以使用 PowerShell 或 Graph API 代表團隊擁有者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="0266d-125">例如，如果您的組織想要集中建立私人頻道，您可能會想要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0266d-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0266d-126">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0266d-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="0266d-127">使用圖形 API</span><span class="sxs-lookup"><span data-stu-id="0266d-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="0266d-128">取得所有私人頻道訊息的清單</span><span class="sxs-lookup"><span data-stu-id="0266d-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="0266d-129">您可能會想要取得在私人頻道中張貼的所有訊息和回復的清單，以供封存和審核之用。</span><span class="sxs-lookup"><span data-stu-id="0266d-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="0266d-130">以下說明如何使用圖形 API 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="0266d-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="0266d-131">尋找小組中所有私人頻道的 SharePoint Url</span><span class="sxs-lookup"><span data-stu-id="0266d-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="0266d-132">無論您是要針對私人頻道中的檔案執行 eDiscovery 或法律封存，或是想要建立在特定專用通道中放入檔案的一系列商務用應用程式，您都想要查詢建立的唯一 SharePoint 網站集合。每個專用通道。</span><span class="sxs-lookup"><span data-stu-id="0266d-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="0266d-133">以管理員身分，您可以使用 PowerShell 或圖形 Api 命令來查詢這些 Url。</span><span class="sxs-lookup"><span data-stu-id="0266d-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0266d-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0266d-134">Using PowerShell</span></span>

1. <span data-ttu-id="0266d-135">使用您的系統管理員帳戶安裝並[連線至 SharePoint Online 管理命令](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)介面。</span><span class="sxs-lookup"><span data-stu-id="0266d-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="0266d-136">執行下列動作，其中&lt;group_id&gt;是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="0266d-136">Run the following, where &lt;group_id&gt; is the group ID of the team.</span></span> <span data-ttu-id="0266d-137">（您可以輕鬆地在小組連結中找到群組識別碼）。</span><span class="sxs-lookup"><span data-stu-id="0266d-137">(You can easily find the group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="0266d-138">使用圖形 API</span><span class="sxs-lookup"><span data-stu-id="0266d-138">Using Graph API</span></span>

<span data-ttu-id="0266d-139">您可以透過[圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。</span><span class="sxs-lookup"><span data-stu-id="0266d-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="0266d-140">使用下列程式取得指定團隊的專用通道識別碼清單，其中 <group_id> 是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="0266d-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="0266d-141">在後續的通話中，您將需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="0266d-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="0266d-142">（您可以在小組連結中輕鬆找到群組識別碼）。</span><span class="sxs-lookup"><span data-stu-id="0266d-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="0266d-143">**徵求**</span><span class="sxs-lookup"><span data-stu-id="0266d-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="0266d-144">**應對**</span><span class="sxs-lookup"><span data-stu-id="0266d-144">**Response**</span></span>

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

2. <span data-ttu-id="0266d-145">針對您想要取得 SharePoint URL 的每個專用通道，請進行下列要求，其中&lt;channel_id&gt;是頻道 id。</span><span class="sxs-lookup"><span data-stu-id="0266d-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="0266d-146">**徵求**</span><span class="sxs-lookup"><span data-stu-id="0266d-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="0266d-147">**應對**</span><span class="sxs-lookup"><span data-stu-id="0266d-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="0266d-148">在私人頻道中列出並更新擁有者和成員的角色</span><span class="sxs-lookup"><span data-stu-id="0266d-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="0266d-149">您可能會想要列出私人通道的擁有者和成員，決定是否需要將專用通道的特定成員升級為擁有者。</span><span class="sxs-lookup"><span data-stu-id="0266d-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="0266d-150">當您擁有已離開組織的專用頻道擁有者，且專用頻道需要系統管理員協助才能宣告頻道擁有權時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="0266d-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="0266d-151">以管理員身分，您可以使用 PowerShell 或圖形 Api 命令來查詢這些 Url。</span><span class="sxs-lookup"><span data-stu-id="0266d-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0266d-152">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0266d-152">Using PowerShell</span></span>

1. <span data-ttu-id="0266d-153">執行下列動作，其中&lt;group_id&gt;是團隊的群組識別碼，而&lt;channel_name&gt;是頻道名稱。</span><span class="sxs-lookup"><span data-stu-id="0266d-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> –MembershipType Private -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="0266d-154">將成員升級為擁有者。</span><span class="sxs-lookup"><span data-stu-id="0266d-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> –MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="0266d-155">使用圖形 API</span><span class="sxs-lookup"><span data-stu-id="0266d-155">Using Graph API</span></span>

<span data-ttu-id="0266d-156">您可以透過[圖表資源管理器](https://developer.microsoft.com/graph/graph-explorer)來嘗試這些命令。</span><span class="sxs-lookup"><span data-stu-id="0266d-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="0266d-157">使用下列專案，其中&lt;group_id&gt;是團隊的群組識別碼，而&lt;channel_id&gt;是通道 id。</span><span class="sxs-lookup"><span data-stu-id="0266d-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="0266d-158">**徵求**</span><span class="sxs-lookup"><span data-stu-id="0266d-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="0266d-159">**應對**</span><span class="sxs-lookup"><span data-stu-id="0266d-159">**Response**</span></span>

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
2.  <span data-ttu-id="0266d-160">使用下列專案將成員升級為擁有者&lt;，其中 group_id&gt;、 &lt;channel_id&gt;和&lt;識別碼&gt;都是從先前的呼叫傳回的。</span><span class="sxs-lookup"><span data-stu-id="0266d-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="0266d-161">請注意&lt;，&gt;從&lt;先前&gt;的呼叫傳回的識別碼和 userId 不一樣且無法互換。</span><span class="sxs-lookup"><span data-stu-id="0266d-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="0266d-162">請確定您使用&lt;的&gt;是 id。</span><span class="sxs-lookup"><span data-stu-id="0266d-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="0266d-163">**徵求**</span><span class="sxs-lookup"><span data-stu-id="0266d-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="0266d-164">**應對**</span><span class="sxs-lookup"><span data-stu-id="0266d-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="0266d-165">團隊 Powershell 模組</span><span class="sxs-lookup"><span data-stu-id="0266d-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="0266d-166">從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="0266d-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="0266d-167">最新的現有團隊 PowerShell 模組版本（目前為[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)）不支援管理私人頻道。</span><span class="sxs-lookup"><span data-stu-id="0266d-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span> <span data-ttu-id="0266d-168">使用這些步驟，從 PowerShell 測試圖庫中安裝含私用通道支援（目前為1.0.18）的最新版本團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="0266d-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="0266d-169">請勿從 PowerShell 測試圖庫並排安裝團隊 PowerShell 模組與公用 PowerShell 庫中的模組版本。</span><span class="sxs-lookup"><span data-stu-id="0266d-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="0266d-170">請依照下列步驟，先從公用 PowerShell 庫中卸載團隊 PowerShell 模組，然後從 PowerShell 測試圖庫安裝最新版本的模組。</span><span class="sxs-lookup"><span data-stu-id="0266d-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="0266d-171">關閉所有現有的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="0266d-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="0266d-172">啟動新的 Windows PowerShell 模組實例。</span><span class="sxs-lookup"><span data-stu-id="0266d-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="0266d-173">執行下列動作，從公用 PowerShell 庫中卸載團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="0266d-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="0266d-174">關閉所有現有的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="0266d-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="0266d-175">再次啟動 Windows PowerShell 模組，然後執行下列動作，以將 PowerShell 測試圖庫註冊為受信任的來源：</span><span class="sxs-lookup"><span data-stu-id="0266d-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="0266d-176">執行下列動作，從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="0266d-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="0266d-177">執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="0266d-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="0266d-178">從 PowerShell 測試圖庫更新到最新版本的團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="0266d-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="0266d-179">如果您已經從 PowerShell 測試庫安裝團隊 PowerShell 模組，請使用下列步驟更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="0266d-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="0266d-180">關閉所有現有的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="0266d-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="0266d-181">啟動新的 Windows PowerShell 模組實例。</span><span class="sxs-lookup"><span data-stu-id="0266d-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="0266d-182">執行下列操作以從 PowerShell 測試圖庫更新目前已安裝的團隊 PowerShell 模組版本：</span><span class="sxs-lookup"><span data-stu-id="0266d-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="0266d-183">執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="0266d-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="0266d-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="0266d-184">Related topics</span></span>

- [<span data-ttu-id="0266d-185">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="0266d-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="0266d-186">使用 Microsoft Graph API 與團隊搭配運作</span><span class="sxs-lookup"><span data-stu-id="0266d-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="0266d-187">清單頻道</span><span class="sxs-lookup"><span data-stu-id="0266d-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="0266d-188">建立頻道</span><span class="sxs-lookup"><span data-stu-id="0266d-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="0266d-189">將成員新增到頻道</span><span class="sxs-lookup"><span data-stu-id="0266d-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="0266d-190">更新頻道中的成員</span><span class="sxs-lookup"><span data-stu-id="0266d-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="0266d-191">移除頻道中的成員</span><span class="sxs-lookup"><span data-stu-id="0266d-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
