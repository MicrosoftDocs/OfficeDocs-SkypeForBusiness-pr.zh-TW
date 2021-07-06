---
title: 對內容進行電子檔探索調查
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
description: 瞭解執行電子檔探索時該做什麼，例如當您需要提交所有電子檔儲存的資訊進行訴訟時。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ebc1bb12b8a864e65cf6cb26b3d2022ae2e1563b
ms.sourcegitcommit: e023c3023f49e196315e176ce346f0dc5825fa56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53275682"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="d67bc-103">在電子郵件中對內容進行電子檔探索Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d67bc-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="d67bc-104">大型企業通常會受到高罰訴訟，要求提交所有電子 (ESI) 。</span><span class="sxs-lookup"><span data-stu-id="d67bc-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="d67bc-105">Microsoft Teams內容可在電子檔探索調查期間搜尋及使用。</span><span class="sxs-lookup"><span data-stu-id="d67bc-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="d67bc-106">概觀</span><span class="sxs-lookup"><span data-stu-id="d67bc-106">Overview</span></span>

<span data-ttu-id="d67bc-107">所有Microsoft Teams 1：1 或群組聊天會記錄到各個使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="d67bc-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="d67bc-108">所有標準頻道訊息會記錄到代表團隊的群組信箱。</span><span class="sxs-lookup"><span data-stu-id="d67bc-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="d67bc-109">在標準頻道上傳的檔案會涵蓋在 SharePoint Online 和 商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="d67bc-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="d67bc-110">私人頻道中郵件和檔案的 [eDiscovery](private-channels.md) 運作方式與標準頻道不同。</span><span class="sxs-lookup"><span data-stu-id="d67bc-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="d67bc-111">若要深入瞭解，請參閱 [私人頻道的 eDiscovery](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="d67bc-112">並非所有Teams都是可電子檔探索的。</span><span class="sxs-lookup"><span data-stu-id="d67bc-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="d67bc-113">下表顯示您可以使用 Microsoft 電子檔探索工具搜尋的內容類型：</span><span class="sxs-lookup"><span data-stu-id="d67bc-113">The following table shows the content types that you can search for using Microsoft eDiscovery tools:</span></span>

| <span data-ttu-id="d67bc-114">內容類型</span><span class="sxs-lookup"><span data-stu-id="d67bc-114">Content type</span></span> | <span data-ttu-id="d67bc-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="d67bc-115">eDiscoverable</span></span> | <span data-ttu-id="d67bc-116">注釋</span><span class="sxs-lookup"><span data-stu-id="d67bc-116">Notes</span></span> |
|:--- | :--- |:--- |
|<span data-ttu-id="d67bc-117">音訊錄製</span><span class="sxs-lookup"><span data-stu-id="d67bc-117">Audio recordings</span></span> | <span data-ttu-id="d67bc-118">否</span><span class="sxs-lookup"><span data-stu-id="d67bc-118">No</span></span> | |
|<span data-ttu-id="d67bc-119">卡片內容</span><span class="sxs-lookup"><span data-stu-id="d67bc-119">Card content</span></span>|<span data-ttu-id="d67bc-120">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-120">Yes</span></span>|<span data-ttu-id="d67bc-121">請參閱 [搜尋卡片內容](#search-for-card-content) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="d67bc-121">See [Search for card content](#search-for-card-content) for more information.</span></span>|
|<span data-ttu-id="d67bc-122">聊天連結</span><span class="sxs-lookup"><span data-stu-id="d67bc-122">Chat links</span></span> | <span data-ttu-id="d67bc-123">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-123">Yes</span></span> | |
|<span data-ttu-id="d67bc-124">聊天訊息</span><span class="sxs-lookup"><span data-stu-id="d67bc-124">Chat messages</span></span> | <span data-ttu-id="d67bc-125">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-125">Yes</span></span> |<span data-ttu-id="d67bc-126">這包括在 Teams頻道中的內容、1：1 聊天、1：N 群組聊天，以及與來賓使用者參與者的聊天。</span><span class="sxs-lookup"><span data-stu-id="d67bc-126">This includes content in Teams channels, 1:1 chats, 1:N group chats, and chats with guest user participants.</span></span>  |
|<span data-ttu-id="d67bc-127">程式碼段</span><span class="sxs-lookup"><span data-stu-id="d67bc-127">Code snippets</span></span> | <span data-ttu-id="d67bc-128">否</span><span class="sxs-lookup"><span data-stu-id="d67bc-128">No</span></span> | |
|<span data-ttu-id="d67bc-129">編輯的郵件</span><span class="sxs-lookup"><span data-stu-id="d67bc-129">Edited messages</span></span> | <span data-ttu-id="d67bc-130">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-130">Yes</span></span> | <span data-ttu-id="d67bc-131">如果使用者保持保留狀態，也會保留先前版本的已編輯郵件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-131">If the user is on hold, previous versions of edited messages are also preserved.</span></span> |
|<span data-ttu-id="d67bc-132">圖釋、GIF 和貼圖</span><span class="sxs-lookup"><span data-stu-id="d67bc-132">Emojis, GIFs, and stickers</span></span> | <span data-ttu-id="d67bc-133">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-133">Yes</span></span> | |
|<span data-ttu-id="d67bc-134">內嵌圖像</span><span class="sxs-lookup"><span data-stu-id="d67bc-134">Inline images</span></span> | <span data-ttu-id="d67bc-135">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-135">Yes</span></span> | |
|<span data-ttu-id="d67bc-136">會議 IM 交談</span><span class="sxs-lookup"><span data-stu-id="d67bc-136">Meeting IM conversations</span></span> | <span data-ttu-id="d67bc-137">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-137">Yes</span></span> | |
|<span data-ttu-id="d67bc-138">會議中繼資料<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d67bc-138">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="d67bc-139">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-139">Yes</span></span> |  |
|<span data-ttu-id="d67bc-140">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="d67bc-140">Name of channel</span></span> | <span data-ttu-id="d67bc-141">否</span><span class="sxs-lookup"><span data-stu-id="d67bc-141">No</span></span> | |
|<span data-ttu-id="d67bc-142">私人頻道訊息</span><span class="sxs-lookup"><span data-stu-id="d67bc-142">Private channel messages</span></span> | <span data-ttu-id="d67bc-143">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-143">Yes</span></span> | |
|<span data-ttu-id="d67bc-144">報價</span><span class="sxs-lookup"><span data-stu-id="d67bc-144">Quotes</span></span> | <span data-ttu-id="d67bc-145">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-145">Yes</span></span> | <span data-ttu-id="d67bc-146">可搜尋引用的內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-146">Quoted content is searchable.</span></span> <span data-ttu-id="d67bc-147">不過，搜尋結果不會指出已引用內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-147">However, search results don't indicate that the content was quoted.</span></span> |
|<span data-ttu-id="d67bc-148">對 (反應，例如喜歡、心和其他反應) </span><span class="sxs-lookup"><span data-stu-id="d67bc-148">Reactions (such as likes, hearts, and other reactions)</span></span> | <span data-ttu-id="d67bc-149">否</span><span class="sxs-lookup"><span data-stu-id="d67bc-149">No</span></span> | |
|<span data-ttu-id="d67bc-150">主題</span><span class="sxs-lookup"><span data-stu-id="d67bc-150">Subject</span></span> | <span data-ttu-id="d67bc-151">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-151">Yes</span></span> | |
|<span data-ttu-id="d67bc-152">表</span><span class="sxs-lookup"><span data-stu-id="d67bc-152">Tables</span></span> | <span data-ttu-id="d67bc-153">是</span><span class="sxs-lookup"><span data-stu-id="d67bc-153">Yes</span></span> | |
|<span data-ttu-id="d67bc-154">提要通知</span><span class="sxs-lookup"><span data-stu-id="d67bc-154">Feed notifications</span></span> | <span data-ttu-id="d67bc-155">否</span><span class="sxs-lookup"><span data-stu-id="d67bc-155">No</span></span> | |
|||

<span data-ttu-id="d67bc-156"><sup>1</sup> 會議 (和) 中繼資料包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="d67bc-156"><sup>1</sup> Meeting (and call) metadata includes the following:</span></span>

- <span data-ttu-id="d67bc-157">會議開始時間和結束時間，以及持續時間</span><span class="sxs-lookup"><span data-stu-id="d67bc-157">Meeting start and end time, and duration</span></span>
- <span data-ttu-id="d67bc-158">每個參與者的會議加入和離開活動</span><span class="sxs-lookup"><span data-stu-id="d67bc-158">Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="d67bc-159">VOIP 加入/通話</span><span class="sxs-lookup"><span data-stu-id="d67bc-159">VOIP join/calls</span></span>
- <span data-ttu-id="d67bc-160">匿名加入</span><span class="sxs-lookup"><span data-stu-id="d67bc-160">Anonymous join</span></span>
- <span data-ttu-id="d67bc-161">聯合使用者加入</span><span class="sxs-lookup"><span data-stu-id="d67bc-161">Federated user join</span></span>
- <span data-ttu-id="d67bc-162">來賓使用者加入</span><span class="sxs-lookup"><span data-stu-id="d67bc-162">Guest user join</span></span>

  <span data-ttu-id="d67bc-163">影像顯示會議中繼資料的範例。</span><span class="sxs-lookup"><span data-stu-id="d67bc-163">The image shows an example of meeting metadata.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d67bc-164">![影像是 CVR 記錄會議中繼資料的影像。](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="d67bc-164">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="d67bc-165">以下是參與者在會議期間進行 IM 交談的範例。</span><span class="sxs-lookup"><span data-stu-id="d67bc-165">Here's an example of an IM conversation between participants during the meeting.</span></span>

![在 Teams 參與者Teams。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d67bc-167">![eDiscovery 搜尋結果中參與者之間的交談。](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="d67bc-167">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="d67bc-168">有關執行 eDiscovery 調查的資訊，請參閱開始使用 [Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-168">For more information about conducting an eDiscovery investigation, see [Get started with Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="d67bc-169">Microsoft Teams電子檔探索匯出輸出中，Excel會顯示為 IM 或交談。</span><span class="sxs-lookup"><span data-stu-id="d67bc-169">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="d67bc-170">您可以在檔案中 `.pst` 開啟Outlook以在匯出郵件後查看這些郵件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-170">You can open the `.pst` file in Outlook to view those messages after you export them.</span></span>

<span data-ttu-id="d67bc-171">檢視團隊的 .pst 檔案時，所有交談都位於 [交談記錄> 下的 [小組聊天> 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="d67bc-171">When viewing the .pst file for the team, all conversations are located in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="d67bc-172">郵件的標題包含團隊名稱和頻道名稱。</span><span class="sxs-lookup"><span data-stu-id="d67bc-172">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="d67bc-173">例如，下圖顯示來自 Bob 的訊息，該訊息Project製造規格小組的 7 個標準通道。</span><span class="sxs-lookup"><span data-stu-id="d67bc-173">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![使用者信箱中的小組聊天資料夾螢幕擷取畫面Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="d67bc-175">使用者信箱中的私人聊天會儲存在交談記錄下的小組聊天資料夾中。</span><span class="sxs-lookup"><span data-stu-id="d67bc-175">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="d67bc-176">私人頻道的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d67bc-176">eDiscovery of private channels</span></span>

<span data-ttu-id="d67bc-177">在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。</span><span class="sxs-lookup"><span data-stu-id="d67bc-177">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="d67bc-178">記錄的標題會有格式設定，指出寄自哪一個私人頻道。</span><span class="sxs-lookup"><span data-stu-id="d67bc-178">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="d67bc-179">由於每個私人頻道都有自己的SharePoint與父小組網站分開的網站，因此私人頻道中的檔案會獨立于父團隊管理。</span><span class="sxs-lookup"><span data-stu-id="d67bc-179">Because each private channel has its own SharePoint site that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="d67bc-180">Teams不支援小組內單一頻道的 eDiscovery 搜尋，因此必須搜尋整個團隊。</span><span class="sxs-lookup"><span data-stu-id="d67bc-180">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="d67bc-181">若要在私人頻道中執行 eDiscovery 內容搜尋，請搜尋整個小組、與私人頻道關聯的網站集合 (以包含檔案) ，以及私人頻道成員的信箱 (以包含郵件) 。</span><span class="sxs-lookup"><span data-stu-id="d67bc-181">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="d67bc-182">請使用下列步驟來識別私人頻道中的檔案和訊息，以納入您的電子檔探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="d67bc-182">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="d67bc-183">在電子檔探索搜尋中納入私人頻道檔案</span><span class="sxs-lookup"><span data-stu-id="d67bc-183">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="d67bc-184">執行這些步驟之前，請安裝 SharePoint[管理命令殼，然後連線至 SharePoint Online。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="d67bc-184">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="d67bc-185">執行下列操作，以取得與小組中私人SharePoint相關聯的所有網站集合清單。</span><span class="sxs-lookup"><span data-stu-id="d67bc-185">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="d67bc-186">執行下列 PowerShell 腳本，以取得SharePoint中與私人頻道相關聯的所有網站集合 URL 清單，以及父團隊群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="d67bc-186">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="d67bc-187">針對每個小組或群組識別碼，執行下列 PowerShell 腳本，以識別所有相關的私人頻道網站，$groupID是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="d67bc-187">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="d67bc-188">在 eDiscovery 搜尋中納入私人頻道訊息</span><span class="sxs-lookup"><span data-stu-id="d67bc-188">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="d67bc-189">執行這些步驟之前，請確定已安裝最新版本的 PowerShell 模組Teams [PowerShell 模組](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-189">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="d67bc-190">執行下列命令以取得團隊中的私人頻道清單。</span><span class="sxs-lookup"><span data-stu-id="d67bc-190">Run the following command to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="d67bc-191">執行下列命令以取得私人頻道成員的清單。</span><span class="sxs-lookup"><span data-stu-id="d67bc-191">Run the following command to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="d67bc-192">在 [eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery)搜尋查詢中，包含團隊中每個私人頻道中所有成員的信箱。</span><span class="sxs-lookup"><span data-stu-id="d67bc-192">Include the mailboxes of all members from each private channel in the team as part of your [eDiscovery search query](/microsoft-365/compliance/search-for-content-in-core-ediscovery).</span></span>

## <a name="search-for-content-for-guest-users"></a><span data-ttu-id="d67bc-193">搜尋來賓使用者的內容</span><span class="sxs-lookup"><span data-stu-id="d67bc-193">Search for content for guest users</span></span>

<span data-ttu-id="d67bc-194">您可以使用 eDiscovery 工具搜尋Teams來賓使用者的相關內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-194">You can use eDiscovery tools to search for Teams content related to guest users in your organization.</span></span> <span data-ttu-id="d67bc-195">Teams與來賓使用者相關聯的聊天內容會保留在雲端儲存位置，而且可以使用 eDiscovery 搜尋。</span><span class="sxs-lookup"><span data-stu-id="d67bc-195">Teams chat content that's associated with a guest user is preserved in a cloud-based storage location and can be searched for using eDiscovery.</span></span> <span data-ttu-id="d67bc-196">這包括在 1：1 和 1：N 聊天交談中搜尋內容，其中來賓使用者是貴組織中其他使用者的參與者。</span><span class="sxs-lookup"><span data-stu-id="d67bc-196">This includes searching for content in 1:1 and 1:N chat conversations in which a guest user is a participant with other users in your organization.</span></span> <span data-ttu-id="d67bc-197">您也可以搜尋來賓使用者為參與者的私人頻道訊息，並搜尋來賓 *：來賓* 聊天交談中只有參與者為來賓使用者的內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-197">You can also search for private channel messages in which a guest user is a participant and search for content in *guest:guest* chat conversations where the only participants are guest users.</span></span>

<span data-ttu-id="d67bc-198">若要搜尋來賓使用者的內容：</span><span class="sxs-lookup"><span data-stu-id="d67bc-198">To search for content for guest users:</span></span>

1. <span data-ttu-id="d67bc-199">連線 Azure AD PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d67bc-199">Connect to Azure AD PowerShell.</span></span> <span data-ttu-id="d67bc-200">有關指示，請參閱使用 PowerShell 連線 PowerShell Azure Active Directory>一[連線Microsoft 365>一節](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-200">For instructions, see the "Connect with the Azure Active Directory PowerShell" section in [Connect to Microsoft 365 with PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="d67bc-201">請務必完成上一個主題中的步驟 1 和步驟 2。</span><span class="sxs-lookup"><span data-stu-id="d67bc-201">Be sure to complete Step 1 and Step 2 in the previous topic.</span></span>

2. <span data-ttu-id="d67bc-202">成功連接到 Azure AD PowerShell 之後，請執行下列命令，為貴組織的所有來賓使用者 (UPN) 使用者主體名稱。</span><span class="sxs-lookup"><span data-stu-id="d67bc-202">After you successfully connect to Azure AD PowerShell, run the following command to display the user principal name (UPN) for all guest users in your organization.</span></span> <span data-ttu-id="d67bc-203">當您在步驟 4 建立搜尋時，您必須使用來賓使用者的 UPN。</span><span class="sxs-lookup"><span data-stu-id="d67bc-203">You have to use the UPN of the guest user when you create the search in step 4.</span></span>

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > <span data-ttu-id="d67bc-204">您可以重新導向命令的輸出至文字檔，而不是在電腦畫面上顯示使用者主體名稱清單。</span><span class="sxs-lookup"><span data-stu-id="d67bc-204">Instead of displaying a list of user principal names on the computer screen, you can redirect the output of the command to a text file.</span></span> <span data-ttu-id="d67bc-205">您可以附加至上一個命令 `> filename.txt` ，以執行此操作。</span><span class="sxs-lookup"><span data-stu-id="d67bc-205">You can do this by appending `> filename.txt` to the previous command.</span></span> <span data-ttu-id="d67bc-206">具有使用者主體名稱的文字檔會儲存到目前的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d67bc-206">The text file with the user principal names will be saved to the current folder.</span></span>

3. <span data-ttu-id="d67bc-207">在不同的安全Windows PowerShell，請連接到安全性與合規性& PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d67bc-207">In a different Windows PowerShell window, connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d67bc-208">有關指示，[請參閱連線安全&中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="d67bc-208">For instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="d67bc-209">您可以使用多重要素驗證進行連接，也可以不使用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="d67bc-209">You can connect with or without using multi-factor authentication.</span></span>

4. <span data-ttu-id="d67bc-210">建立內容搜尋，以執行下列命令 (搜尋所有內容，例如聊天訊息) 電子郵件訊息。其中指定的來賓使用者是參與者。</span><span class="sxs-lookup"><span data-stu-id="d67bc-210">Create a content search that searches for all content (such as chat messages and email messages) in which the specified guest user was a participant by running the following command.</span></span>

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   <span data-ttu-id="d67bc-211">例如，若要搜尋與來賓使用者 Sara Davis 相關聯的內容，您可以執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="d67bc-211">For example, to search for content associated with the guest user Sara Davis, you would run the following command.</span></span>

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    <span data-ttu-id="d67bc-212">有關使用 PowerShell 建立內容搜尋的資訊，請參閱 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-212">For more information about using PowerShell to create content searches, see [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).</span></span>

5. <span data-ttu-id="d67bc-213">執行下列命令以開始在步驟 4 中建立的內容搜尋：</span><span class="sxs-lookup"><span data-stu-id="d67bc-213">Run the following command to start the content search that you created in step 4:</span></span>

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. <span data-ttu-id="d67bc-214">前往 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然後按一下 [**顯示所有**  >  **內容搜尋**> 。</span><span class="sxs-lookup"><span data-stu-id="d67bc-214">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Show all** > **Content search**.</span></span>

7. <span data-ttu-id="d67bc-215">在搜尋清單中，選取您于步驟 4 中建立搜尋以顯示飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="d67bc-215">In the list of searches, select the search that you created in step 4 to display the flyout page.</span></span>

8. <span data-ttu-id="d67bc-216">在飛出頁面上，您可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d67bc-216">On the flyout page, you can do the following things:</span></span>

   - <span data-ttu-id="d67bc-217">按一下 **[查看結果** 以查看搜尋結果並預覽內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-217">Click **View results** to view the search results and preview the content.</span></span>

   - <span data-ttu-id="d67bc-218">按一下 [ **查詢欄位** 的旁邊 **編輯** 以編輯，然後重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="d67bc-218">Next to the **Query** field, click **Edit** to edit and then rerun the search.</span></span> <span data-ttu-id="d67bc-219">例如，您可以新增搜尋查詢來縮小結果範圍。</span><span class="sxs-lookup"><span data-stu-id="d67bc-219">For example, you can add a search query to narrow the results.</span></span>

   - <span data-ttu-id="d67bc-220">按一下 **[匯出結果** 以匯出並下載搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d67bc-220">Click **Export results** to export and download the search results.</span></span>

## <a name="search-for-card-content"></a><span data-ttu-id="d67bc-221">搜尋卡片內容</span><span class="sxs-lookup"><span data-stu-id="d67bc-221">Search for card content</span></span>

<span data-ttu-id="d67bc-222">由應用程式在 Teams、1：1 聊天和 1xN 聊天中產生的卡片內容會儲存在信箱中，而且可以搜尋。</span><span class="sxs-lookup"><span data-stu-id="d67bc-222">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="d67bc-223">卡片 *是* 包含簡短內容的 UI 容器。</span><span class="sxs-lookup"><span data-stu-id="d67bc-223">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="d67bc-224">卡片可以有多個屬性和附件，而且可以包含可觸發卡片動作的按鈕。</span><span class="sxs-lookup"><span data-stu-id="d67bc-224">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="d67bc-225">詳細資訊，請參閱 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span><span class="sxs-lookup"><span data-stu-id="d67bc-225">For more information, see [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

<span data-ttu-id="d67bc-226">與其他Teams內容一樣，卡片內容的儲存位置會依據卡片的使用位置。</span><span class="sxs-lookup"><span data-stu-id="d67bc-226">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="d67bc-227">在頻道中使用的卡片Teams內容會儲存在Teams信箱中。</span><span class="sxs-lookup"><span data-stu-id="d67bc-227">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="d67bc-228">1：1 和 1xN 聊天的卡片內容會儲存在聊天參與者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="d67bc-228">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

<span data-ttu-id="d67bc-229">若要搜尋卡片內容，您可以使用 或 `kind:microsoftteams` `itemclass:IPM.SkypeTeams.Message` 搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-229">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="d67bc-230">在審查搜尋結果時，Teams頻道中的 Bot 產生的卡片內容具有寄件者 **/作者** 電子郵件屬性，其中產生卡片內容的應用程式名稱在哪裡 `<appname>@teams.microsoft.com` `appname` 。</span><span class="sxs-lookup"><span data-stu-id="d67bc-230">When reviewing search results, card content generated by bots in a Teams channel has the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="d67bc-231">如果卡片內容是由使用者產生，寄件者 **/作者的值會** 識別使用者。</span><span class="sxs-lookup"><span data-stu-id="d67bc-231">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

<span data-ttu-id="d67bc-232">在內容搜尋結果中檢視卡片內容時，內容會顯示為郵件的附件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-232">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="d67bc-233">附件會命名為 `appname.html` ，其中就是產生卡片 `appname` 內容的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="d67bc-233">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="d67bc-234">下列螢幕擷取畫面顯示 (Asana) 應用程式卡片內容Teams顯示在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="d67bc-234">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

<span data-ttu-id="d67bc-235">**卡片內容Teams**</span><span class="sxs-lookup"><span data-stu-id="d67bc-235">**Card content in Teams**</span></span>

![頻道訊息Teams卡片內容](media/CardContentTeams.png)

<span data-ttu-id="d67bc-237">**搜尋結果中的卡片內容**</span><span class="sxs-lookup"><span data-stu-id="d67bc-237">**Card content in search results**</span></span>
  
![內容搜尋結果中的卡片內容相同](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> <span data-ttu-id="d67bc-239">若要在搜尋結果中顯示來自卡片內容的影像 (例如上一個螢幕擷取畫面) 中的核取方塊，您必須在您用於查看搜尋結果的同一個瀏覽器會話的不同索引點，在 Teams (上登錄。 https://teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d67bc-239">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="d67bc-240">否則會顯示影像預留位置。</span><span class="sxs-lookup"><span data-stu-id="d67bc-240">Otherwise, image placeholders are displayed.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="d67bc-241">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d67bc-241">Advanced eDiscovery</span></span>

<span data-ttu-id="d67bc-242">您也可以Microsoft Teams工作流程來搜尋及保留部分Advanced eDiscovery[內容](/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-242">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="d67bc-243">雖然 eDiscovery 提供一系列的搜尋、保留和匯出功能，Advanced eDiscovery提供合規性系統管理員更多工具來識別資料來源及分析其內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-243">While eDiscovery provides a range of search, hold, and export functionality, Advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="d67bc-244">Advanced eDiscovery內容管理Teams工作流程</span><span class="sxs-lookup"><span data-stu-id="d67bc-244">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="d67bc-245">監護者可能是各種團隊的成員。</span><span class="sxs-lookup"><span data-stu-id="d67bc-245">Custodians might be a member of various teams.</span></span> <span data-ttu-id="d67bc-246">您可以Teams與這些監護者相關的內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-246">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="d67bc-247">有關監護工作流程的指示，請參閱新增監護者[至Advanced eDiscovery案例](/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-247">For instructions on the custodian workflow, see [Add custodians to an Advanced eDiscovery case](/microsoft-365/compliance/add-custodians-to-case).</span></span>

<span data-ttu-id="d67bc-248">新增保管人之後，按一下 **[下** 一步> 按鈕，然後按一下 [ **新增>** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d67bc-248">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="d67bc-249">隨後會顯示一個視窗，提示您選取其他位置，這會顯示保管人的所有成員資格，以及其SharePoint網站的對應位置。</span><span class="sxs-lookup"><span data-stu-id="d67bc-249">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="d67bc-250">您可以從所有這些資料來源和團隊中，選擇您想要用於 eDiscovery 的內容，然後將該使用者和您識別的所有資料來源保留。</span><span class="sxs-lookup"><span data-stu-id="d67bc-250">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="d67bc-251">您可以選取是否要包含其Exchange內容、OneDrive或兩者。</span><span class="sxs-lookup"><span data-stu-id="d67bc-251">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="d67bc-252">Exchange包含使用者信箱中所有的應用程式內容，例如其電子郵件、Teams信箱中儲存的 Teams 內容等等。</span><span class="sxs-lookup"><span data-stu-id="d67bc-252">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="d67bc-253">OneDrive內容不僅包括使用者的內容，也包含 OneDrive 中儲存的所有 Teams 內容，例如 1：1 聊天、1：N 聊天，以及聊天中共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="d67bc-253">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="d67bc-254">您也可以選擇將監護者是其中一員的任何團隊進行關聯，以便包含監護者可存取的頻道聊天訊息和檔案。</span><span class="sxs-lookup"><span data-stu-id="d67bc-254">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="d67bc-255">此外，任何其他團隊都可以與監護者相關聯。</span><span class="sxs-lookup"><span data-stu-id="d67bc-255">Additionally, any other team can be associated with a custodian.</span></span>

> [!NOTE]
> <span data-ttu-id="d67bc-256">私人頻道中郵件和檔案的 [eDiscovery](private-channels.md) 運作方式與標準頻道不同。</span><span class="sxs-lookup"><span data-stu-id="d67bc-256">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="d67bc-257">若要深入瞭解，請參閱 [私人頻道的 eDiscovery](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-257">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="d67bc-258">保留資料來源</span><span class="sxs-lookup"><span data-stu-id="d67bc-258">Placing a data source on hold</span></span>

<span data-ttu-id="d67bc-259">如果沒有任何特定使用者要指定為監管人，您可以將整個資料來源保留。</span><span class="sxs-lookup"><span data-stu-id="d67bc-259">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="d67bc-260">有關保留詳細資訊，請參閱在 Advanced eDiscovery[中管理Advanced eDiscovery。](/microsoft-365/compliance/managing-holds)</span><span class="sxs-lookup"><span data-stu-id="d67bc-260">For more information on holds, see [Manage holds in Advanced eDiscovery](/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="d67bc-261">建立保留Teams內容時，您可以選擇要納入保留的所有位置。</span><span class="sxs-lookup"><span data-stu-id="d67bc-261">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="d67bc-262">即使使用者刪除或變更內容，保留也會保留該內容的所有先前版本複本。</span><span class="sxs-lookup"><span data-stu-id="d67bc-262">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="d67bc-263">您也可以使用選擇性查詢，根據關鍵字、日期範圍、作者和許多其他準則來設定保留的條件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-263">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="d67bc-264">如果您未指定關鍵字，則來自該資料來源的所有專案都會受到保留。</span><span class="sxs-lookup"><span data-stu-id="d67bc-264">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="d67bc-265">Advanced eDiscovery搜尋</span><span class="sxs-lookup"><span data-stu-id="d67bc-265">Advanced eDiscovery searches</span></span>

<span data-ttu-id="d67bc-266">Teams搜尋內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-266">Teams content can also be searched.</span></span> <span data-ttu-id="d67bc-267">有關搜尋詳細資訊，請參閱在 Advanced eDiscovery[中收集案例Advanced eDiscovery。](/microsoft-365/compliance/collecting-data-for-ediscovery)</span><span class="sxs-lookup"><span data-stu-id="d67bc-267">For more information on searches, see [Collect data for a case in Advanced eDiscovery](/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="d67bc-268">即使有一封郵件符合搜尋查詢，搜尋也會返回整個交談。</span><span class="sxs-lookup"><span data-stu-id="d67bc-268">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="d67bc-269">建立搜尋查詢時，您可以選擇監護者，以便搜尋所有已選取的來源。</span><span class="sxs-lookup"><span data-stu-id="d67bc-269">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="d67bc-270">您也可以搜尋非監護來源，例如Teams未對應給使用者的網站。</span><span class="sxs-lookup"><span data-stu-id="d67bc-270">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="d67bc-271">選擇性查詢也可以縮小搜尋範圍，以縮小Teams範圍。</span><span class="sxs-lookup"><span data-stu-id="d67bc-271">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="d67bc-272">建立並選取搜尋之後，視窗會顯示其他詳細資料，以及您可以在選取的搜尋上執行的動作。</span><span class="sxs-lookup"><span data-stu-id="d67bc-272">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="d67bc-273">如果您按一下 [統計資料> 按鈕，就可以查看搜尋的統計資料，包括根據位置類型細分、內容的原始來源，以及內容是否位於群組信箱、個別使用者信箱或 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="d67bc-273">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="d67bc-274">因此，您可以查看哪些來源對搜尋結果有説明。</span><span class="sxs-lookup"><span data-stu-id="d67bc-274">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="d67bc-275">您也可以使用 **[查詢** 視圖>，以便查看哪些個別關鍵字對結果有影響。</span><span class="sxs-lookup"><span data-stu-id="d67bc-275">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="d67bc-276">完成搜尋之後，您可以按一下 [新增結果 **以審查設定** 按鈕並新增到評論集。</span><span class="sxs-lookup"><span data-stu-id="d67bc-276">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="d67bc-277">有關審查集詳細資訊，請參閱本文稍後[Advanced eDiscovery管理檢查](/microsoft-365/compliance/managing-review-sets)集和[檢查](#review-sets-workflow)集工作流程。</span><span class="sxs-lookup"><span data-stu-id="d67bc-277">For more information about review sets, see [Manage review sets in Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="d67bc-278">一般評論集和交談評論集</span><span class="sxs-lookup"><span data-stu-id="d67bc-278">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="d67bc-279">新增搜尋至評論集時，您可以選擇一般評論集或交談評論集。</span><span class="sxs-lookup"><span data-stu-id="d67bc-279">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="d67bc-280">一般評論集與匯出類似;它提供個別檔案Teams內容，並且以基本視圖 `.msg` 呈現內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-280">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="d67bc-281">當您打算稍後使用其他軟體工具重新處理檔案時，通常會使用一般評論集。</span><span class="sxs-lookup"><span data-stu-id="d67bc-281">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="d67bc-282">交談評論集提供交談的更直覺、討論執行緒的視圖;它會以適當的順序一起顯示相關郵件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-282">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d67bc-283">![交談評論集的螢幕擷取畫面](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="d67bc-283">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="d67bc-284">兩種類型的校閱集都提供編校等功能。</span><span class="sxs-lookup"><span data-stu-id="d67bc-284">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="d67bc-285">有關評論集詳細資訊，請參閱在進一版 [eDiscovery 中審查交談](/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="d67bc-285">For more information about review sets, see [Review conversations in advanced eDiscovery](/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="d67bc-286">集合選項</span><span class="sxs-lookup"><span data-stu-id="d67bc-286">Collection options</span></span>

<span data-ttu-id="d67bc-287">新增到評論集時，視窗的收藏選項區段下有數個選項可用做為核取方塊，包括交談Teams **選項**。 </span><span class="sxs-lookup"><span data-stu-id="d67bc-287">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="d67bc-288">如果您啟用這些選項，任何屬於您Teams之個別的郵件也會顯示周圍其他訊息以做為上下文。</span><span class="sxs-lookup"><span data-stu-id="d67bc-288">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="d67bc-289">例如，如果您的查詢是特定的，因此只會返回一封郵件，啟用這些選項也會在符合查詢的郵件前和之後，返回數封郵件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-289">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="d67bc-290">許多邏輯準則會用來判斷其他郵件是否提供符合您查詢的郵件內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-290">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="d67bc-291">例如，針對Teams，啟用這些選項會因為郵件的執行緒方式，來取回父郵件和所有子郵件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-291">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="d67bc-292">也會檢查郵件時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d67bc-292">Message time stamps are also checked.</span></span> <span data-ttu-id="d67bc-293">如果郵件符合您的查詢，則 4 小時內或 4 小時內追蹤該郵件的相鄰郵件會視為交談的一部分，也會包含在結果中。</span><span class="sxs-lookup"><span data-stu-id="d67bc-293">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="d67bc-294">如果您必須確定哪些上下文相關郵件會與搜尋查詢的符合專案一起返回，則不需要使用這些選項。</span><span class="sxs-lookup"><span data-stu-id="d67bc-294">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="d67bc-295">您可以收集所有內容，也可以擴大搜尋的日期範圍，讓查詢的結果會退回更多郵件。</span><span class="sxs-lookup"><span data-stu-id="d67bc-295">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="d67bc-296">審查集工作流程</span><span class="sxs-lookup"><span data-stu-id="d67bc-296">Review sets workflow</span></span>

<span data-ttu-id="d67bc-297">您可以按一下檢查集，來查看現有的評論集或 **建立** 新評論集。有關評閱集的資訊，請參閱在 Advanced eDiscovery [中管理Advanced eDiscovery。](/microsoft-365/compliance/managing-review-sets)</span><span class="sxs-lookup"><span data-stu-id="d67bc-297">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="d67bc-298">除了檔之外，您還可以在評論集Teams電子郵件、Yammer郵件及其他內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-298">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="d67bc-299">您也可以在評論集內執行許多可在其他上下文執行相同的作業，例如搜尋內容和建立自訂查詢。</span><span class="sxs-lookup"><span data-stu-id="d67bc-299">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="d67bc-300">這些作業僅適用于已新加入審查集的專案。</span><span class="sxs-lookup"><span data-stu-id="d67bc-300">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="d67bc-301">管理 **審查集** 按鈕提供其他選項，例如分析、摘要報告、新增的載入集數等等。</span><span class="sxs-lookup"><span data-stu-id="d67bc-301">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="d67bc-302">若要存取資料的視覺效果和圖表，請按一下右上角的 [個別 **結果** 搜尋 \> 設定檔視圖。</span><span class="sxs-lookup"><span data-stu-id="d67bc-302">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="d67bc-303">您可以按一下這些圖表中的圓形圖，以互動式方式選取您想要查詢的內容類型。</span><span class="sxs-lookup"><span data-stu-id="d67bc-303">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="d67bc-304">例如，您可以選擇只查詢Teams內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-304">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="d67bc-305">您也可以儲存這些查詢，就像儲存手動撰寫的查詢一樣。</span><span class="sxs-lookup"><span data-stu-id="d67bc-305">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="d67bc-306">摘要視圖、文字視圖和批註視圖</span><span class="sxs-lookup"><span data-stu-id="d67bc-306">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="d67bc-307">如果您按一下評論Teams中的交談，它會顯示 [摘要視圖Teams整個交談，作為您可以個別互動的郵寄清單。</span><span class="sxs-lookup"><span data-stu-id="d67bc-307">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="d67bc-308">按一下郵件右邊的向下箭鍵，以顯示操作功能表，可讓您查看郵件詳細資料或下載個別 `.msg` 檔案。</span><span class="sxs-lookup"><span data-stu-id="d67bc-308">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="d67bc-309">按一下郵件詳細資料會顯示中繼資料摘要或郵件的完整中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d67bc-309">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="d67bc-310">若要下載 PDF，請按一下摘要視圖右上角的下載按鈕。</span><span class="sxs-lookup"><span data-stu-id="d67bc-310">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="d67bc-311">按一下 [**文字視圖>** 選項卡，以顯示交談中摘要文字的純文字Teams視圖。</span><span class="sxs-lookup"><span data-stu-id="d67bc-311">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="d67bc-312">此純文字內容適合匯出，而且您可以使用其他軟體工具輕鬆處理。</span><span class="sxs-lookup"><span data-stu-id="d67bc-312">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="d67bc-313">按一下 [ **批註視圖>** 選項卡以存取注釋功能。</span><span class="sxs-lookup"><span data-stu-id="d67bc-313">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="d67bc-314">此選項卡會以類似交談Teams格式顯示內容，但還有其他編輯選項。</span><span class="sxs-lookup"><span data-stu-id="d67bc-314">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="d67bc-315">您可以使用鉛筆工具做筆記、在郵件上繪圖，或執行細細微性的刮擦，以用於編校用途。</span><span class="sxs-lookup"><span data-stu-id="d67bc-315">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="d67bc-316">您也可以使用 **區域密** 文工具來繪製一個矩形，將區域黑色化，並標記為「已重新編輯」。</span><span class="sxs-lookup"><span data-stu-id="d67bc-316">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="d67bc-317">以下是使用者之間對話對話的已修訂檔案範例。</span><span class="sxs-lookup"><span data-stu-id="d67bc-317">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d67bc-318">![已修訂檔案的螢幕擷取畫面](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="d67bc-318">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="d67bc-319">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span><span class="sxs-lookup"><span data-stu-id="d67bc-319">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="d67bc-320">您可以在此面板中，將標記Teams交談。</span><span class="sxs-lookup"><span data-stu-id="d67bc-320">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="d67bc-321">您可以將交談標示為回應性或非回應式、有許可權或不具有許可權、是否包含「有趣專案」、是否要包含在匯出中，以及是否需要進一步審查。</span><span class="sxs-lookup"><span data-stu-id="d67bc-321">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="d67bc-322">您也可以管理並應用其他可自訂的標記。</span><span class="sxs-lookup"><span data-stu-id="d67bc-322">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="d67bc-323">動作功能表</span><span class="sxs-lookup"><span data-stu-id="d67bc-323">Action menu</span></span>

<span data-ttu-id="d67bc-324">在評論集視窗中，您可以按一下動作匯出來匯出 \> **內容**。</span><span class="sxs-lookup"><span data-stu-id="d67bc-324">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="d67bc-325">匯出時有許多可用的選項。</span><span class="sxs-lookup"><span data-stu-id="d67bc-325">There are many options available when exporting.</span></span>

<span data-ttu-id="d67bc-326">若要匯出包含所有郵件之所有中繼資料Teams，請按一下以選取 [載入 **檔案>** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d67bc-326">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="d67bc-327">若要在檔案中納入任何您已對內容所申請的標記，請按一下以選取 [ **標記>** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d67bc-327">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="d67bc-328">使用 **原生檔案** 選項以原生格式匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="d67bc-328">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="d67bc-329">您可以選擇將交談匯出為個別檔案中的一個檔案或所有個別聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="d67bc-329">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="d67bc-330">文字檔 **選項** 可讓您儲存純文字版本的內容。</span><span class="sxs-lookup"><span data-stu-id="d67bc-330">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="d67bc-331">若要瞭解如何取得評論集內交談的純文字Teams，請參閱上方的摘要視圖、文字視圖和[批註視圖。](#summary-view-text-view-and-annotate-view)</span><span class="sxs-lookup"><span data-stu-id="d67bc-331">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="d67bc-332">如果您按照上述的摘要視圖、文字視圖和批註視圖區段 [](#summary-view-text-view-and-annotate-view)所述，將任何編目內容都適用，您可以選取以轉換 **PDF** 取代已編輯的原生檔選項，以 PDF 中的已轉換複本取代原生檔案。</span><span class="sxs-lookup"><span data-stu-id="d67bc-332">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="d67bc-333">您可以選擇匯出至 Microsoft 提供的 Azure Blob 儲存容器，或提供您自己的 Azure Blob 儲存容器。</span><span class="sxs-lookup"><span data-stu-id="d67bc-333">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="d67bc-334">當您準備好開始匯出程式時，請按一下 [ **匯出>** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d67bc-334">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="d67bc-335">請參閱 [下載匯出工作](/microsoft-365/compliance/download-export-jobs) ，以取得如何存取 Azure Blob 儲存容器，以及匯出完成後下載匯出內容之詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d67bc-335">See [Download export jobs](/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="d67bc-336">匯出可能需要一段長的時間。</span><span class="sxs-lookup"><span data-stu-id="d67bc-336">Exporting can take an extended period of time.</span></span> <span data-ttu-id="d67bc-337">若要追蹤匯出程式的狀態，請離開 [檢查集> **定位停駐點** ，然後按一下 [ **匯出> 選項卡** 。</span><span class="sxs-lookup"><span data-stu-id="d67bc-337">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d67bc-338">相關主題</span><span class="sxs-lookup"><span data-stu-id="d67bc-338">Related topics</span></span>

- [<span data-ttu-id="d67bc-339">電子探索Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d67bc-339">eDiscovery in Microsoft 365</span></span>](/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="d67bc-340">TeamsPowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="d67bc-340">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)