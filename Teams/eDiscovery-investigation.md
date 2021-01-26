---
title: 對內容進行 eDiscovery 調查
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解當您需要執行 eDiscovery 時要採取的動作，例如當您需要提交所有以電子形式儲存的法律訴訟資訊時。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980457"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="84085-103">在 Microsoft 團隊中進行 eDiscovery 調查內容</span><span class="sxs-lookup"><span data-stu-id="84085-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="84085-104">大型企業通常會面臨大量的法律訴訟，要求提交所有以電子方式儲存的資訊 (ESI) 。</span><span class="sxs-lookup"><span data-stu-id="84085-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="84085-105">Microsoft 團隊內容可以在 eDiscovery 調查期間進行搜尋和使用。</span><span class="sxs-lookup"><span data-stu-id="84085-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="84085-106">概觀</span><span class="sxs-lookup"><span data-stu-id="84085-106">Overview</span></span>

<span data-ttu-id="84085-107">所有 Microsoft 團隊1:1 或群組聊天都會在各個使用者的信箱中進行日記。</span><span class="sxs-lookup"><span data-stu-id="84085-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="84085-108">所有標準通道訊息都會在代表小組的群組信箱中進行歸檔。</span><span class="sxs-lookup"><span data-stu-id="84085-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="84085-109">在標準頻道中上傳的檔案涵蓋在 SharePoint Online 和商務用 OneDrive 的 eDiscovery 功能底下。</span><span class="sxs-lookup"><span data-stu-id="84085-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="84085-110">電子檔探索 [私人通道](private-channels.md) 中的訊息和檔案，與在標準通道中的運作方式不同。</span><span class="sxs-lookup"><span data-stu-id="84085-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="84085-111">若要深入瞭解，請參閱電子檔探索（ [私人頻道](#ediscovery-of-private-channels)）。</span><span class="sxs-lookup"><span data-stu-id="84085-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="84085-112">並非所有團隊內容都是 eDiscoverable。</span><span class="sxs-lookup"><span data-stu-id="84085-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="84085-113">下表顯示您可以使用 Microsoft eDiscovery 工具搜尋的內容類型：</span><span class="sxs-lookup"><span data-stu-id="84085-113">The following table shows the content types that you can search for using Microsoft eDiscovery tools:</span></span>

| <span data-ttu-id="84085-114">內容類型</span><span class="sxs-lookup"><span data-stu-id="84085-114">Content type</span></span> | <span data-ttu-id="84085-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="84085-115">eDiscoverable</span></span> | <span data-ttu-id="84085-116">注釋</span><span class="sxs-lookup"><span data-stu-id="84085-116">Notes</span></span> |
|:--- | :--- |:--- |
|<span data-ttu-id="84085-117">音訊錄製</span><span class="sxs-lookup"><span data-stu-id="84085-117">Audio recordings</span></span> | <span data-ttu-id="84085-118">否</span><span class="sxs-lookup"><span data-stu-id="84085-118">No</span></span> | |
|<span data-ttu-id="84085-119">卡片內容</span><span class="sxs-lookup"><span data-stu-id="84085-119">Card content</span></span>|<span data-ttu-id="84085-120">是</span><span class="sxs-lookup"><span data-stu-id="84085-120">Yes</span></span>|<span data-ttu-id="84085-121">如需詳細資訊，請參閱 [搜尋卡片內容](#search-for-card-content) 。</span><span class="sxs-lookup"><span data-stu-id="84085-121">See [Search for card content](#search-for-card-content) for more information.</span></span>|
|<span data-ttu-id="84085-122">聊天連結</span><span class="sxs-lookup"><span data-stu-id="84085-122">Chat links</span></span> | <span data-ttu-id="84085-123">是</span><span class="sxs-lookup"><span data-stu-id="84085-123">Yes</span></span> | |
|<span data-ttu-id="84085-124">聊天訊息</span><span class="sxs-lookup"><span data-stu-id="84085-124">Chat messages</span></span> | <span data-ttu-id="84085-125">是</span><span class="sxs-lookup"><span data-stu-id="84085-125">Yes</span></span> |<span data-ttu-id="84085-126">這包括團隊頻道中的內容、1:1 聊天、1： N 群組聊天，以及與來賓使用者參與者聊天。</span><span class="sxs-lookup"><span data-stu-id="84085-126">This includes content in Teams channels, 1:1 chats, 1:N group chats, and chats with guest user participants.</span></span>  |
|<span data-ttu-id="84085-127">程式碼片段</span><span class="sxs-lookup"><span data-stu-id="84085-127">Code snippets</span></span> | <span data-ttu-id="84085-128">否</span><span class="sxs-lookup"><span data-stu-id="84085-128">No</span></span> | |
|<span data-ttu-id="84085-129">已編輯的郵件</span><span class="sxs-lookup"><span data-stu-id="84085-129">Edited messages</span></span> | <span data-ttu-id="84085-130">是</span><span class="sxs-lookup"><span data-stu-id="84085-130">Yes</span></span> | <span data-ttu-id="84085-131">如果使用者已保留，則會保留先前版本的已編輯郵件。</span><span class="sxs-lookup"><span data-stu-id="84085-131">If the user is on hold, previous versions of edited messages are also preserved.</span></span> |
|<span data-ttu-id="84085-132">Emoji、Gif 及貼紙</span><span class="sxs-lookup"><span data-stu-id="84085-132">Emojis, GIFs, and stickers</span></span> | <span data-ttu-id="84085-133">是</span><span class="sxs-lookup"><span data-stu-id="84085-133">Yes</span></span> | |
|<span data-ttu-id="84085-134">內嵌圖像</span><span class="sxs-lookup"><span data-stu-id="84085-134">Inline images</span></span> | <span data-ttu-id="84085-135">是</span><span class="sxs-lookup"><span data-stu-id="84085-135">Yes</span></span> | |
|<span data-ttu-id="84085-136">會議 IM 交談</span><span class="sxs-lookup"><span data-stu-id="84085-136">Meeting IM conversations</span></span> | <span data-ttu-id="84085-137">是</span><span class="sxs-lookup"><span data-stu-id="84085-137">Yes</span></span> | |
|<span data-ttu-id="84085-138">會議中繼資料<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="84085-138">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="84085-139">是</span><span class="sxs-lookup"><span data-stu-id="84085-139">Yes</span></span> |  |
|<span data-ttu-id="84085-140">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="84085-140">Name of channel</span></span> | <span data-ttu-id="84085-141">否</span><span class="sxs-lookup"><span data-stu-id="84085-141">No</span></span> | |
|<span data-ttu-id="84085-142">私人通道訊息</span><span class="sxs-lookup"><span data-stu-id="84085-142">Private channel messages</span></span> | <span data-ttu-id="84085-143">是</span><span class="sxs-lookup"><span data-stu-id="84085-143">Yes</span></span> | |
|<span data-ttu-id="84085-144">引述</span><span class="sxs-lookup"><span data-stu-id="84085-144">Quotes</span></span> | <span data-ttu-id="84085-145">是</span><span class="sxs-lookup"><span data-stu-id="84085-145">Yes</span></span> | <span data-ttu-id="84085-146">已報價的內容可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="84085-146">Quoted content is searchable.</span></span> <span data-ttu-id="84085-147">不過，搜尋結果不會指出內容已加上引號。</span><span class="sxs-lookup"><span data-stu-id="84085-147">However, search results don't indicate that the content was quoted.</span></span> |
|<span data-ttu-id="84085-148">反應 (例如贊、心形及其他反應) </span><span class="sxs-lookup"><span data-stu-id="84085-148">Reactions (such as likes, hearts, and other reactions)</span></span> | <span data-ttu-id="84085-149">否</span><span class="sxs-lookup"><span data-stu-id="84085-149">No</span></span> | |
|<span data-ttu-id="84085-150">主題</span><span class="sxs-lookup"><span data-stu-id="84085-150">Subject</span></span> | <span data-ttu-id="84085-151">是</span><span class="sxs-lookup"><span data-stu-id="84085-151">Yes</span></span> | |
|<span data-ttu-id="84085-152">該表</span><span class="sxs-lookup"><span data-stu-id="84085-152">Tables</span></span> | <span data-ttu-id="84085-153">是</span><span class="sxs-lookup"><span data-stu-id="84085-153">Yes</span></span> | |
|||

<span data-ttu-id="84085-154"><sup>1</sup> 會議 (並呼叫) 中繼資料包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="84085-154"><sup>1</sup> Meeting (and call) metadata includes the following:</span></span>

- <span data-ttu-id="84085-155">會議開始和結束時間，以及持續時間</span><span class="sxs-lookup"><span data-stu-id="84085-155">Meeting start and end time, and duration</span></span>
- <span data-ttu-id="84085-156">會議加入與離開每位參與者的活動</span><span class="sxs-lookup"><span data-stu-id="84085-156">Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="84085-157">VOIP 連接/通話</span><span class="sxs-lookup"><span data-stu-id="84085-157">VOIP join/calls</span></span>
- <span data-ttu-id="84085-158">匿名加入</span><span class="sxs-lookup"><span data-stu-id="84085-158">Anonymous join</span></span>
- <span data-ttu-id="84085-159">聯盟使用者加入</span><span class="sxs-lookup"><span data-stu-id="84085-159">Federated user join</span></span>
- <span data-ttu-id="84085-160">來賓使用者加入</span><span class="sxs-lookup"><span data-stu-id="84085-160">Guest user join</span></span>

  <span data-ttu-id="84085-161">影像顯示會議中繼資料的範例。</span><span class="sxs-lookup"><span data-stu-id="84085-161">The image shows an example of meeting metadata.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="84085-162">![Image 是 CVR 記錄會議中繼資料。](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="84085-162">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="84085-163">以下是會議期間參與者之間的 IM 交談範例。</span><span class="sxs-lookup"><span data-stu-id="84085-163">Here's an example of an IM conversation between participants during the meeting.</span></span>

![團隊參與者之間的交談。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84085-165">![EDiscovery 搜尋結果中的參與者之間的交談。](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="84085-165">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="84085-166">如需有關進行 eDiscovery 調查的詳細資訊，請參閱 [核心 EDiscovery 快速](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)入門。</span><span class="sxs-lookup"><span data-stu-id="84085-166">For more information about conducting an eDiscovery investigation, see [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="84085-167">Microsoft 團隊資料將在 Excel eDiscovery 匯出輸出中顯示為 IM 或交談。</span><span class="sxs-lookup"><span data-stu-id="84085-167">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="84085-168">您可以在 [Outlook] 中開啟檔案， `.pst` 以便在您匯出郵件後加以查看。</span><span class="sxs-lookup"><span data-stu-id="84085-168">You can open the `.pst` file in Outlook to view those messages after you export them.</span></span>

<span data-ttu-id="84085-169">針對小組查看 .pst 檔案時，所有交談都會保留在 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="84085-169">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="84085-170">郵件標題包含團隊名稱和頻道名稱。</span><span class="sxs-lookup"><span data-stu-id="84085-170">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="84085-171">例如，下圖顯示的是來自王俊元的訊息，其中 messaged 製造規範小組的專案7標準頻道。</span><span class="sxs-lookup"><span data-stu-id="84085-171">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook 中使用者信箱的小組聊天資料夾螢幕擷取畫面](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="84085-173">使用者信箱中的私人聊天儲存在 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="84085-173">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="84085-174">電子檔探索（私人頻道）</span><span class="sxs-lookup"><span data-stu-id="84085-174">eDiscovery of private channels</span></span>

<span data-ttu-id="84085-175">在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。</span><span class="sxs-lookup"><span data-stu-id="84085-175">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="84085-176">記錄的標題會有格式設定，指出寄自哪一個私人頻道。</span><span class="sxs-lookup"><span data-stu-id="84085-176">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="84085-177">因為每個私人通道都有自己的 SharePoint 網站，與父小組網站分開，所以專用通道中的檔案會獨立于父團隊進行管理。</span><span class="sxs-lookup"><span data-stu-id="84085-177">Because each private channel has its own SharePoint site that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="84085-178">小組不支援小組內單一頻道的 eDiscovery 搜尋，所以必須搜尋整個小組。</span><span class="sxs-lookup"><span data-stu-id="84085-178">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="84085-179">若要在私人頻道中執行電子檔探索搜尋，請在整個小組中搜尋與私人頻道 (相關聯的網站集合，以包含) 的檔案，以及私人頻道成員的信箱 (，以包含) 的郵件。</span><span class="sxs-lookup"><span data-stu-id="84085-179">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="84085-180">使用下列步驟來識別您在 eDiscovery 搜尋中包含的私人頻道中的檔案和訊息。</span><span class="sxs-lookup"><span data-stu-id="84085-180">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="84085-181">在 eDiscovery 搜尋中包含私人通道檔案</span><span class="sxs-lookup"><span data-stu-id="84085-181">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="84085-182">在執行這些步驟之前，請先安裝 [Sharepoint Online 管理命令介面並聯機至 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="84085-182">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="84085-183">執行下列動作，以取得與團隊中的私人頻道相關聯的所有 SharePoint 網站集合的清單。</span><span class="sxs-lookup"><span data-stu-id="84085-183">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="84085-184">執行下列 PowerShell 腳本，以取得與團隊中的私人頻道與父團隊群組識別碼相關聯的所有 SharePoint 網站集合 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="84085-184">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="84085-185">針對每個團隊或群組識別碼，請執行下列 PowerShell 腳本來找出所有相關的專用通道網站，其中 $groupID 是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="84085-185">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="84085-186">在 eDiscovery 搜尋中包含私人通道訊息</span><span class="sxs-lookup"><span data-stu-id="84085-186">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="84085-187">在執行這些步驟之前，請確定您已安裝 [最新版本的團隊 PowerShell 模組](teams-powershell-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="84085-187">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="84085-188">執行下列命令，以取得小組中的私人頻道清單。</span><span class="sxs-lookup"><span data-stu-id="84085-188">Run the following command to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="84085-189">執行下列命令以取得私人頻道成員的清單。</span><span class="sxs-lookup"><span data-stu-id="84085-189">Run the following command to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="84085-190">從小組中的每個私人頻道包含所有成員的信箱，成為 [eDiscovery 搜尋查詢](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)的一部分。</span><span class="sxs-lookup"><span data-stu-id="84085-190">Include the mailboxes of all members from each private channel in the team as part of your [eDiscovery search query](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery).</span></span>

## <a name="search-for-content-for-guest-users"></a><span data-ttu-id="84085-191">搜尋來賓使用者的內容</span><span class="sxs-lookup"><span data-stu-id="84085-191">Search for content for guest users</span></span>

<span data-ttu-id="84085-192">您可以使用 eDiscovery 工具來搜尋與您組織中的來賓使用者相關的小組內容。</span><span class="sxs-lookup"><span data-stu-id="84085-192">You can use eDiscovery tools to search for Teams content related to guest users in your organization.</span></span> <span data-ttu-id="84085-193">團隊聊天與來賓使用者相關聯的內容會保留在雲端式儲存位置，而且可以使用 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="84085-193">Teams chat content that's associated with a guest user is preserved in a cloud-based storage location and can be searched for using eDiscovery.</span></span> <span data-ttu-id="84085-194">這包括搜尋1:1 和1： N 聊天交談中的內容，來賓使用者是您組織中其他使用者的參與者。</span><span class="sxs-lookup"><span data-stu-id="84085-194">This includes searching for content in 1:1 and 1:N chat conversations in which a guest user is a participant with other users in your organization.</span></span> <span data-ttu-id="84085-195">您也可以搜尋來賓使用者是參與者的私人通道訊息，並在來賓中搜尋內容 *：* 只有來賓聊天的參與者是來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="84085-195">You can also search for private channel messages in which a guest user is a participant and search for content in *guest:guest* chat conversations where the only participants are guest users.</span></span>

<span data-ttu-id="84085-196">若要搜尋來賓使用者的內容：</span><span class="sxs-lookup"><span data-stu-id="84085-196">To search for content for guest users:</span></span>

1. <span data-ttu-id="84085-197">[連線至 Azure AD PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="84085-197">Connect to Azure AD PowerShell.</span></span> <span data-ttu-id="84085-198">如需相關指示，請參閱 [使用 PowerShell 連線至 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)中的 [與 Azure Active Directory PowerShell 連線] 區段。</span><span class="sxs-lookup"><span data-stu-id="84085-198">For instructions, see the "Connect with the Azure Active Directory PowerShell" section in [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="84085-199">請務必完成上一個主題中的步驟1和步驟2。</span><span class="sxs-lookup"><span data-stu-id="84085-199">Be sure to complete Step 1 and Step 2 in the previous topic.</span></span>

2. <span data-ttu-id="84085-200">成功連線至 Azure AD PowerShell 之後，請執行下列命令，以顯示貴組織中所有來賓使用者的使用者主要名稱 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="84085-200">After you successfully connect to Azure AD PowerShell, run the following command to display the user principal name (UPN) for all guest users in your organization.</span></span> <span data-ttu-id="84085-201">當您在步驟4中建立搜尋時，您必須使用來賓使用者的 UPN。</span><span class="sxs-lookup"><span data-stu-id="84085-201">You have to use the UPN of the guest user when you create the search in step 4.</span></span>

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > <span data-ttu-id="84085-202">您可以將命令的輸出重新導向到文字檔，而不是在電腦螢幕上顯示使用者主要名稱清單。</span><span class="sxs-lookup"><span data-stu-id="84085-202">Instead of displaying a list of user principal names on the computer screen, you can redirect the output of the command to a text file.</span></span> <span data-ttu-id="84085-203">您可以透過附加 `> filename.txt` 至前一個命令來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="84085-203">You can do this by appending `> filename.txt` to the previous command.</span></span> <span data-ttu-id="84085-204">含有使用者主要名稱的文字檔會儲存至目前的資料夾。</span><span class="sxs-lookup"><span data-stu-id="84085-204">The text file with the user principal names will be saved to the current folder.</span></span>

3. <span data-ttu-id="84085-205">在不同的 Windows PowerShell 視窗中，連線至安全性 & 合規性中心 PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="84085-205">In a different Windows PowerShell window, connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="84085-206">如需相關指示，請參閱連線 [到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="84085-206">For instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="84085-207">您可以使用或不使用多重要素驗證來連接。</span><span class="sxs-lookup"><span data-stu-id="84085-207">You can connect with or without using multi-factor authentication.</span></span>

4. <span data-ttu-id="84085-208">您可以執行下列命令，來建立搜尋內容搜尋，以搜尋所有內容 (例如交談訊息和電子郵件訊息) 。</span><span class="sxs-lookup"><span data-stu-id="84085-208">Create a content search that searches for all content (such as chat messages and email messages) in which the specified guest user was a participant by running the following command.</span></span>

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   <span data-ttu-id="84085-209">例如，若要搜尋與來賓使用者 Sara Davis 相關聯的內容，您可以執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="84085-209">For example, to search for content associated with the guest user Sara Davis, you would run the following command.</span></span>

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    <span data-ttu-id="84085-210">如需使用 PowerShell 建立內容搜尋的詳細資訊，請參閱 [新 ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)。</span><span class="sxs-lookup"><span data-stu-id="84085-210">For more information about using PowerShell to create content searches, see [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch).</span></span>

5. <span data-ttu-id="84085-211">執行下列命令以啟動您在步驟4中建立的內容搜尋：</span><span class="sxs-lookup"><span data-stu-id="84085-211">Run the following command to start the content search that you created in step 4:</span></span>

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. <span data-ttu-id="84085-212">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [**顯示所有**  >  **內容搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="84085-212">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Show all** > **Content search**.</span></span>

7. <span data-ttu-id="84085-213">在搜尋清單中，選取您在步驟4中建立的搜尋，以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="84085-213">In the list of searches, select the search that you created in step 4 to display the flyout page.</span></span>

8. <span data-ttu-id="84085-214">在飛出頁面上，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="84085-214">On the flyout page, you can do the following things:</span></span>

   - <span data-ttu-id="84085-215">按一下 [ **查看結果** ]，查看搜尋結果並預覽內容。</span><span class="sxs-lookup"><span data-stu-id="84085-215">Click **View results** to view the search results and preview the content.</span></span>

   - <span data-ttu-id="84085-216">在 **查詢** 欄位旁邊，按一下 [ **編輯** ] 以編輯，然後重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="84085-216">Next to the **Query** field, click **Edit** to edit and then rerun the search.</span></span> <span data-ttu-id="84085-217">例如，您可以新增搜尋查詢來縮小結果範圍。</span><span class="sxs-lookup"><span data-stu-id="84085-217">For example, you can add a search query to narrow the results.</span></span>

   - <span data-ttu-id="84085-218">按一下 [ **匯出結果** ]，匯出並下載搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="84085-218">Click **Export results** to export and download the search results.</span></span>

## <a name="search-for-card-content"></a><span data-ttu-id="84085-219">搜尋卡片內容</span><span class="sxs-lookup"><span data-stu-id="84085-219">Search for card content</span></span>

<span data-ttu-id="84085-220">在團隊頻道、1:1 聊天及1xN 聊天中，由應用程式所產生的卡片內容會儲存在信箱中，而且可以搜尋。</span><span class="sxs-lookup"><span data-stu-id="84085-220">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="84085-221">*卡片* 是簡短內容片段的 UI 容器。</span><span class="sxs-lookup"><span data-stu-id="84085-221">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="84085-222">卡片可以有多個屬性和附件，而且可以包含可觸發卡片動作的按鈕。</span><span class="sxs-lookup"><span data-stu-id="84085-222">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="84085-223">如需詳細資訊，請參閱 [卡片](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span><span class="sxs-lookup"><span data-stu-id="84085-223">For more information, see [Cards](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

<span data-ttu-id="84085-224">與其他團隊內容一樣，儲存卡片內容的位置是以信用卡使用的位置為基礎。</span><span class="sxs-lookup"><span data-stu-id="84085-224">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="84085-225">在團隊頻道中使用的卡片內容會儲存在 [團隊] 群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="84085-225">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="84085-226">1:1 和1xN 聊天的卡片內容會儲存在聊天參與者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="84085-226">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

<span data-ttu-id="84085-227">若要搜尋卡片內容，您可以使用 `kind:microsoftteams` 或 `itemclass:IPM.SkypeTeams.Message` 搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="84085-227">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="84085-228">當您查看搜尋結果時，由 bot 在團隊頻道中產生的卡片內容是 **寄件者/作者** 電子郵件屬性 `<appname>@teams.microsoft.com` ，其中 `appname` 是產生卡片內容的 app 名稱。</span><span class="sxs-lookup"><span data-stu-id="84085-228">When reviewing search results, card content generated by bots in a Teams channel has the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="84085-229">如果使用者已產生卡片內容，則 **寄件者/作者** 的值會識別使用者。</span><span class="sxs-lookup"><span data-stu-id="84085-229">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

<span data-ttu-id="84085-230">在內容搜尋結果中查看卡片內容時，內容會以附件的形式顯示在郵件中。</span><span class="sxs-lookup"><span data-stu-id="84085-230">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="84085-231">附件已命名 `appname.html` ，其中 `appname` 是產生卡片內容之應用程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="84085-231">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="84085-232">下列螢幕擷取畫面顯示名為 Asana 之 app 的卡片內容 () 會出現在 [團隊] 和 [搜尋] 的結果中。</span><span class="sxs-lookup"><span data-stu-id="84085-232">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

<span data-ttu-id="84085-233">**小組中的卡片內容**</span><span class="sxs-lookup"><span data-stu-id="84085-233">**Card content in Teams**</span></span>

![小組頻道訊息中的卡片內容](media/CardContentTeams.png)

<span data-ttu-id="84085-235">**搜尋結果中的卡片內容**</span><span class="sxs-lookup"><span data-stu-id="84085-235">**Card content in search results**</span></span>
  
![內容搜尋結果中的相同卡片內容](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> <span data-ttu-id="84085-237">若要在搜尋結果中顯示卡片內容的影像， (例如先前螢幕擷取畫面中的核取記號) ，您必須登入團隊 (在 https://teams.microsoft.com) 您用來查看搜尋結果的同一個瀏覽器會話中的另一個索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="84085-237">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="84085-238">否則，就會顯示圖像預留位置。</span><span class="sxs-lookup"><span data-stu-id="84085-238">Otherwise, image placeholders are displayed.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="84085-239">高級 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="84085-239">Advanced eDiscovery</span></span>

<span data-ttu-id="84085-240">您也可以使用 [ [高級 eDiscovery 工作流程](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)] 來搜尋及保留部分 Microsoft 團隊內容。</span><span class="sxs-lookup"><span data-stu-id="84085-240">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="84085-241">雖然 eDiscovery 提供一系列的搜尋、保留和匯出功能，但高級 eDiscovery 則提供合規性管理員更多工具來識別資料來源並分析其內容。</span><span class="sxs-lookup"><span data-stu-id="84085-241">While eDiscovery provides a range of search, hold, and export functionality, Advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="84085-242">小組內容的高級 eDiscovery 保管人工作流程</span><span class="sxs-lookup"><span data-stu-id="84085-242">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="84085-243">保管人可能是各種團隊的成員。</span><span class="sxs-lookup"><span data-stu-id="84085-243">Custodians might be a member of various teams.</span></span> <span data-ttu-id="84085-244">您可以捕獲與這些保管人相關的小組內容。</span><span class="sxs-lookup"><span data-stu-id="84085-244">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="84085-245">如需保管人工作流程的指示，請參閱 [將保管人新增至高級 eDiscovery 案例](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="84085-245">For instructions on the custodian workflow, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

<span data-ttu-id="84085-246">在新增保管人之後，按一下 [ **下一步]** 按鈕，然後按一下 [ **新增** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="84085-246">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="84085-247">接著會顯示一個視窗，提示您選取其他位置，這會顯示所有保管人的成員資格以及其資料對應的 SharePoint 網站位置。</span><span class="sxs-lookup"><span data-stu-id="84085-247">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="84085-248">從所有這些資料來源和小組中，您可以選擇您想要用於 eDiscovery 的內容，然後將該使用者及您已識別的所有資料來源保留。</span><span class="sxs-lookup"><span data-stu-id="84085-248">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="84085-249">您可以選取是否要包括其 Exchange 內容、其 OneDrive 內容，或同時包含兩者。</span><span class="sxs-lookup"><span data-stu-id="84085-249">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="84085-250">Exchange 內容包括使用者信箱中的所有應用程式內容，例如他們的電子郵件、儲存在其信箱中的小組內容等。</span><span class="sxs-lookup"><span data-stu-id="84085-250">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="84085-251">OneDrive 內容不僅包括使用者的內容，還包含儲存在 OneDrive 中的所有小組內容，例如1:1 聊天、1： N 聊天，以及在聊天中共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="84085-251">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="84085-252">您也可以選擇將保管人中的任何小組相關聯，讓保管人擁有存取權的通道交談訊息和檔案都包含在其中。</span><span class="sxs-lookup"><span data-stu-id="84085-252">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="84085-253">此外，任何其他團隊都可以與保管人建立關聯。</span><span class="sxs-lookup"><span data-stu-id="84085-253">Additionally, any other team can be associated with a custodian.</span></span>

> [!NOTE]
> <span data-ttu-id="84085-254">電子檔探索 [私人通道](private-channels.md) 中的訊息和檔案，與在標準通道中的運作方式不同。</span><span class="sxs-lookup"><span data-stu-id="84085-254">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="84085-255">若要深入瞭解，請參閱電子檔探索（ [私人頻道](#ediscovery-of-private-channels)）。</span><span class="sxs-lookup"><span data-stu-id="84085-255">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="84085-256">保留資料來源</span><span class="sxs-lookup"><span data-stu-id="84085-256">Placing a data source on hold</span></span>

<span data-ttu-id="84085-257">如果沒有指派給保管人的特定使用者，您可以保留整個資料來源。</span><span class="sxs-lookup"><span data-stu-id="84085-257">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="84085-258">如需保留的詳細資訊，請參閱 [在高級 eDiscovery 中管理保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="84085-258">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="84085-259">建立小組內容的保留時間時，您可以選擇要在保留中包含的所有位置。</span><span class="sxs-lookup"><span data-stu-id="84085-259">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="84085-260">即使使用者正在刪除或變更內容，保留也會維持該內容所有先前版本的複本。</span><span class="sxs-lookup"><span data-stu-id="84085-260">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="84085-261">您也可以使用選擇性查詢，根據關鍵字、日期範圍、作者及許多其他準則來設定保留條件。</span><span class="sxs-lookup"><span data-stu-id="84085-261">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="84085-262">如果您沒有指定關鍵字，則來自該資料來源的所有內容都會受到保留。</span><span class="sxs-lookup"><span data-stu-id="84085-262">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="84085-263">[高級 eDiscovery 搜尋]</span><span class="sxs-lookup"><span data-stu-id="84085-263">Advanced eDiscovery searches</span></span>

<span data-ttu-id="84085-264">您也可以搜尋小組內容。</span><span class="sxs-lookup"><span data-stu-id="84085-264">Teams content can also be searched.</span></span> <span data-ttu-id="84085-265">如需搜尋的詳細資訊，請參閱 [在 [高級 eDiscovery] 中收集案例的資料](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="84085-265">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="84085-266">如果即使一封郵件符合搜尋查詢，搜尋將會傳回整個交談。</span><span class="sxs-lookup"><span data-stu-id="84085-266">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="84085-267">建立搜尋查詢時，您可以選擇 [保管人]，讓您已選取的所有來源都經過搜尋。</span><span class="sxs-lookup"><span data-stu-id="84085-267">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="84085-268">您也可以搜尋非 custodial 來源，例如未對應至使用者的小組網站。</span><span class="sxs-lookup"><span data-stu-id="84085-268">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="84085-269">您也可以在小組內容中縮小搜尋範圍，提供選用的查詢。</span><span class="sxs-lookup"><span data-stu-id="84085-269">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="84085-270">在您建立並選取搜尋後，會顯示一個視窗，其中包含您可以在選取的搜尋上執行的其他詳細資料和動作。</span><span class="sxs-lookup"><span data-stu-id="84085-270">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="84085-271">如果您按一下 [ **統計資料]** 按鈕，您可以查看有關搜尋的統計資料，包括根據位置類型、內容的原始來源，以及內容是否位於群組信箱、個別使用者信箱或 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="84085-271">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="84085-272">因此，您可以在搜尋結果中看到哪些來源的明細。</span><span class="sxs-lookup"><span data-stu-id="84085-272">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="84085-273">您也可以使用 [ **查詢** ] 視圖，查看哪些個別關鍵字對您的結果有影響。</span><span class="sxs-lookup"><span data-stu-id="84085-273">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="84085-274">完成搜尋之後，您可以按一下 [ **新增結果至審閱設定** ] 按鈕，然後將其新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="84085-274">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="84085-275">如需有關審閱集的詳細資訊，請參閱本文稍後的管理高級 eDiscovery 和[審閱集合工作流程](#review-sets-workflow)[中的審閱集合](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="84085-275">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="84085-276">標準的審閱集和交談審查集合</span><span class="sxs-lookup"><span data-stu-id="84085-276">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="84085-277">在將搜尋新增至審閱集合時，您可以從一般的審閱集或交談審查集合中進行選擇。</span><span class="sxs-lookup"><span data-stu-id="84085-277">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="84085-278">標準的審閱集與匯出類似;它提供小組內容的個別檔案 `.msg` ，並在 [基本視圖] 中呈現內容。</span><span class="sxs-lookup"><span data-stu-id="84085-278">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="84085-279">您通常會在規劃使用其他軟體工具以稍後重新處理檔案時，使用一般的審閱集。</span><span class="sxs-lookup"><span data-stu-id="84085-279">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="84085-280">交談審查集合提供更直觀、更具執行緒的交談視圖;它會以正確的順序來顯示相關的郵件。</span><span class="sxs-lookup"><span data-stu-id="84085-280">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84085-281">![交談審查設定的螢幕擷取畫面](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="84085-281">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="84085-282">在兩種類型的審閱集中都提供密文等功能。</span><span class="sxs-lookup"><span data-stu-id="84085-282">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="84085-283">如需有關審閱集的詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="84085-283">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="84085-284">收集選項</span><span class="sxs-lookup"><span data-stu-id="84085-284">Collection options</span></span>

<span data-ttu-id="84085-285">新增至審閱集合時，視窗的 [ **收集選項** ] 區段下有幾個選項可供使用，包括 **交談檢索選項** 和 **團隊交談**。</span><span class="sxs-lookup"><span data-stu-id="84085-285">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="84085-286">如果您啟用這些選項，任何屬於您的審閱集中的個別團隊訊息，也會顯示在其周圍有其他訊息，以供內容使用。</span><span class="sxs-lookup"><span data-stu-id="84085-286">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="84085-287">例如，如果您的查詢是特定的，且只傳回一封郵件，則啟用這些選項也會傳回數個郵件，並追蹤符合您查詢的訊息。</span><span class="sxs-lookup"><span data-stu-id="84085-287">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="84085-288">許多邏輯準則是用來判斷其他訊息是否提供與您查詢相符之訊息的內容。</span><span class="sxs-lookup"><span data-stu-id="84085-288">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="84085-289">例如，針對小組內容，啟用這些選項將會因郵件進行執行緒化的方式來檢索上層訊息和所有子郵件。</span><span class="sxs-lookup"><span data-stu-id="84085-289">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="84085-290">也會檢查郵件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="84085-290">Message time stamps are also checked.</span></span> <span data-ttu-id="84085-291">如果郵件符合您的查詢，在4小時內，或在4個小時內追蹤的相鄰訊息，就會被視為交談的一部分，也會包含在結果中。</span><span class="sxs-lookup"><span data-stu-id="84085-291">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="84085-292">如果您必須確定哪些上下文訊息會傳回與您的搜尋查詢相符的內容，您就不需要使用這些選項。</span><span class="sxs-lookup"><span data-stu-id="84085-292">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="84085-293">您可以收集所有內容，或者您可以放寬搜尋的日期範圍，以便讓您查詢的結果傳回更多的郵件。</span><span class="sxs-lookup"><span data-stu-id="84085-293">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="84085-294">審閱集合工作流程</span><span class="sxs-lookup"><span data-stu-id="84085-294">Review sets workflow</span></span>

<span data-ttu-id="84085-295">您可以按一下 [ **審閱集** ] 索引標籤，查看現有的審閱集或建立新的評論。如需有關審閱集的詳細資訊，請參閱 [在高級 eDiscovery 中管理審閱集合](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="84085-295">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="84085-296">除了檔之外，您還可以將電子郵件、團隊訊息、Yammer 郵件及其他內容新增到您的審閱集中。</span><span class="sxs-lookup"><span data-stu-id="84085-296">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="84085-297">在審閱集中，您也可以執行許多您可以在其他上下文中執行的相同作業，例如搜尋內容和建立自訂查詢。</span><span class="sxs-lookup"><span data-stu-id="84085-297">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="84085-298">這些操作只適用于已新增至審閱集的專案。</span><span class="sxs-lookup"><span data-stu-id="84085-298">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="84085-299">[ **管理審閱設定** ] 按鈕可提供其他選項，例如 [分析]、[摘要報告]、已新增多少個載入組等等。</span><span class="sxs-lookup"><span data-stu-id="84085-299">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="84085-300">若要存取資料的視覺效果與圖表，請按一下右上角的 [ **個別結果** \> **搜尋設定檔] 視圖** 。</span><span class="sxs-lookup"><span data-stu-id="84085-300">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="84085-301">您可以按一下這些圖表中的 [楔形]，以互動方式選取您要查詢的內容類型。</span><span class="sxs-lookup"><span data-stu-id="84085-301">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="84085-302">例如，您可以選擇只查詢團隊內容。</span><span class="sxs-lookup"><span data-stu-id="84085-302">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="84085-303">您也可以儲存這些查詢，就像儲存您手動撰寫的查詢一樣。</span><span class="sxs-lookup"><span data-stu-id="84085-303">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="84085-304">[摘要] 視圖、[文字視圖] 和 [批註] 視圖</span><span class="sxs-lookup"><span data-stu-id="84085-304">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="84085-305">如果您按一下 [審查] 集中的 [小組交談]，就會顯示 [ **摘要] 視圖**，將整個小組交談顯示為您可以個別互動的訊息清單。</span><span class="sxs-lookup"><span data-stu-id="84085-305">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="84085-306">按一下訊息右邊的向下箭號，以顯示操作功能表，可讓您查看訊息詳細資料或下載個別檔案 `.msg` 。</span><span class="sxs-lookup"><span data-stu-id="84085-306">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="84085-307">按一下 [郵件詳細資料]，就會顯示該郵件的中繼資料或完整中繼資料摘要。</span><span class="sxs-lookup"><span data-stu-id="84085-307">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="84085-308">若要下載 PDF，請按一下 [摘要] 視圖右上方的 [下載] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="84085-308">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="84085-309">按一下 [ **文字視圖** ] 索引標籤，以顯示已提取的小組交談文字的純文字視圖。</span><span class="sxs-lookup"><span data-stu-id="84085-309">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="84085-310">此純文字內容適合匯出，您可以使用其他軟體工具輕鬆處理。</span><span class="sxs-lookup"><span data-stu-id="84085-310">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="84085-311">按一下 [批註] [ **查看** ] 索引標籤，即可存取 [批註] 功能。</span><span class="sxs-lookup"><span data-stu-id="84085-311">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="84085-312">這個索引標籤會以類似團隊交談的格式來顯示內容，但是還有其他編輯選項。</span><span class="sxs-lookup"><span data-stu-id="84085-312">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="84085-313">您可以使用鉛筆工具來製作筆記、在郵件上繪圖，或進行精細的 scratching 以進行密文。</span><span class="sxs-lookup"><span data-stu-id="84085-313">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="84085-314">您也可以使用「 **區域密文** 」工具來繪製黑色外框，並將它標示為「Redacted」的矩形。</span><span class="sxs-lookup"><span data-stu-id="84085-314">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="84085-315">以下是在使用者之間進行執行緒交談的 redacted 檔案範例。</span><span class="sxs-lookup"><span data-stu-id="84085-315">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84085-316">![Redacted 檔案的螢幕擷取畫面](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="84085-316">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="84085-317">[ **批註視圖** ] 索引標籤底部是 [ **標記檔** ] 按鈕，會顯示 [標記] 面板。</span><span class="sxs-lookup"><span data-stu-id="84085-317">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="84085-318">在此面板中，您可以將標記套用至團隊交談中的所有訊息。</span><span class="sxs-lookup"><span data-stu-id="84085-318">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="84085-319">您可以將交談標記為「回應」或「無回應」、[無論是否包含有趣的專案] （無論是否應包含在匯出中），以及是否需要進一步審查。</span><span class="sxs-lookup"><span data-stu-id="84085-319">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="84085-320">您也可以管理並套用其他可自訂的標記。</span><span class="sxs-lookup"><span data-stu-id="84085-320">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="84085-321">[動作] 功能表</span><span class="sxs-lookup"><span data-stu-id="84085-321">Action menu</span></span>

<span data-ttu-id="84085-322">您可以在 [審閱集合] 視窗中按一下 [ **動作** 匯出] 來匯出內容 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84085-322">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="84085-323">匯出時有許多選項可供使用。</span><span class="sxs-lookup"><span data-stu-id="84085-323">There are many options available when exporting.</span></span>

<span data-ttu-id="84085-324">若要匯出包含所有小組郵件之所有中繼資料的檔案，請按一下以選取 [ **載入** 檔案] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="84085-324">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="84085-325">若要在檔案中包含任何您已套用至內容的標記，請按一下以選取 **[卷** 標] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="84085-325">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="84085-326">使用 [ **原生** 檔案] 選項，以其原生格式匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="84085-326">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="84085-327">您可以選擇將交談匯出為單一檔案，或是將所有個別聊天訊息匯出為自己的個別檔案。</span><span class="sxs-lookup"><span data-stu-id="84085-327">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="84085-328">[ **文字檔** ] 選項可讓您儲存純文字版本的內容。</span><span class="sxs-lookup"><span data-stu-id="84085-328">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="84085-329">如需如何在審閱集中取得小組交談的純文字視圖的詳細資訊，請參閱上方的 [ [摘要視圖]、[文字視圖] 和 [批註] 視圖](#summary-view-text-view-and-annotate-view) 。</span><span class="sxs-lookup"><span data-stu-id="84085-329">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="84085-330">如果您對內容套用任何密文，如上面的 [ [摘要視圖]、[文字視圖] 和 [批註](#summary-view-text-view-and-annotate-view) ] 區段所述，您可以選取 [ **使用轉換過的 pdf 取代 redacted natives** ] 選項，以 PDF 中的已轉換複本來取代原生檔案。</span><span class="sxs-lookup"><span data-stu-id="84085-330">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="84085-331">您可以選擇匯出至 Microsoft 提供的 Azure blob 儲存體容器，或提供您自己的 Azure Blob 儲存體容器。</span><span class="sxs-lookup"><span data-stu-id="84085-331">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="84085-332">當您準備好要開始匯出程式時，請按一下 [ **匯出** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="84085-332">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="84085-333">如需如何存取 Azure blob 儲存體容器，以及在匯出完成後下載匯出內容的詳細資訊，請參閱 [下載匯出作業](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 。</span><span class="sxs-lookup"><span data-stu-id="84085-333">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="84085-334">匯出可能需要較長的時間。</span><span class="sxs-lookup"><span data-stu-id="84085-334">Exporting can take an extended period of time.</span></span> <span data-ttu-id="84085-335">若要追蹤匯出程式的狀態，請結束 [ **審閱集** ] 索引標籤，然後按一下 [ **匯出** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="84085-335">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84085-336">相關主題</span><span class="sxs-lookup"><span data-stu-id="84085-336">Related topics</span></span>

- [<span data-ttu-id="84085-337">Microsoft 365 中的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="84085-337">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="84085-338">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="84085-338">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
