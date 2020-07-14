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
ms.openlocfilehash: 0bdd14db1fd0e849effe9ffe1789c06e1e012d90
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121393"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="298a5-103">在 Microsoft 團隊中進行 eDiscovery 調查內容</span><span class="sxs-lookup"><span data-stu-id="298a5-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="298a5-104">大型企業通常會面臨大量要求提交所有以電子方式儲存資訊（ESI）的法律訴訟。</span><span class="sxs-lookup"><span data-stu-id="298a5-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="298a5-105">Microsoft 團隊內容可以在 eDiscovery 調查期間進行搜尋和使用。</span><span class="sxs-lookup"><span data-stu-id="298a5-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="298a5-106">概觀</span><span class="sxs-lookup"><span data-stu-id="298a5-106">Overview</span></span>

<span data-ttu-id="298a5-107">所有團隊1:1 或群組聊天都會在各個使用者的信箱中進行日記。</span><span class="sxs-lookup"><span data-stu-id="298a5-107">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="298a5-108">所有標準通道訊息都會在代表小組的群組信箱中進行歸檔。</span><span class="sxs-lookup"><span data-stu-id="298a5-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="298a5-109">在標準頻道中上傳的檔案涵蓋在 SharePoint Online 和商務用 OneDrive 的 eDiscovery 功能底下。</span><span class="sxs-lookup"><span data-stu-id="298a5-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="298a5-110">電子檔探索[私人通道](private-channels.md)中的訊息和檔案，與在標準通道中的運作方式不同。</span><span class="sxs-lookup"><span data-stu-id="298a5-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="298a5-111">若要深入瞭解，請參閱電子檔探索（[私人頻道](#ediscovery-of-private-channels)）。</span><span class="sxs-lookup"><span data-stu-id="298a5-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="298a5-112">並非所有團隊內容都是 eDiscoverable。</span><span class="sxs-lookup"><span data-stu-id="298a5-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="298a5-113">下表顯示可透過 eDiscovery 找到的內容類型。</span><span class="sxs-lookup"><span data-stu-id="298a5-113">The following table shows the content types that can be located through eDiscovery.</span></span>

| <span data-ttu-id="298a5-114">內容類型</span><span class="sxs-lookup"><span data-stu-id="298a5-114">Content type</span></span> | <span data-ttu-id="298a5-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="298a5-115">eDiscoverable</span></span> | <span data-ttu-id="298a5-116">筆記</span><span class="sxs-lookup"><span data-stu-id="298a5-116">Notes</span></span> |
|:--- | --- |:--- |
| <span data-ttu-id="298a5-117">小組聊天訊息</span><span class="sxs-lookup"><span data-stu-id="298a5-117">Teams chat messages</span></span> | <span data-ttu-id="298a5-118">是</span><span class="sxs-lookup"><span data-stu-id="298a5-118">Yes</span></span> |  |
| <span data-ttu-id="298a5-119">音訊錄製</span><span class="sxs-lookup"><span data-stu-id="298a5-119">Audio recordings</span></span> | <span data-ttu-id="298a5-120">否</span><span class="sxs-lookup"><span data-stu-id="298a5-120">No</span></span> | |
| <span data-ttu-id="298a5-121">私人通道訊息</span><span class="sxs-lookup"><span data-stu-id="298a5-121">Private channel messages</span></span> | <span data-ttu-id="298a5-122">是</span><span class="sxs-lookup"><span data-stu-id="298a5-122">Yes</span></span> | |
| <span data-ttu-id="298a5-123">Emoji、Gif、不乾膠標籤</span><span class="sxs-lookup"><span data-stu-id="298a5-123">Emojis, GIFs, stickers</span></span> | <span data-ttu-id="298a5-124">是</span><span class="sxs-lookup"><span data-stu-id="298a5-124">Yes</span></span> | |
| <span data-ttu-id="298a5-125">程式碼片段</span><span class="sxs-lookup"><span data-stu-id="298a5-125">Code snippets</span></span> | <span data-ttu-id="298a5-126">否</span><span class="sxs-lookup"><span data-stu-id="298a5-126">No</span></span> | |
| <span data-ttu-id="298a5-127">聊天連結</span><span class="sxs-lookup"><span data-stu-id="298a5-127">Chat links</span></span> | <span data-ttu-id="298a5-128">是</span><span class="sxs-lookup"><span data-stu-id="298a5-128">Yes</span></span> | |
| <span data-ttu-id="298a5-129">反應（贊、紅心等等）</span><span class="sxs-lookup"><span data-stu-id="298a5-129">Reactions (likes, hearts, and so on)</span></span> | <span data-ttu-id="298a5-130">否</span><span class="sxs-lookup"><span data-stu-id="298a5-130">No</span></span> | |
| <span data-ttu-id="298a5-131">已編輯的郵件</span><span class="sxs-lookup"><span data-stu-id="298a5-131">Edited messages</span></span> | <span data-ttu-id="298a5-132">是</span><span class="sxs-lookup"><span data-stu-id="298a5-132">Yes</span></span> | <span data-ttu-id="298a5-133">如果使用者已保留，則會保留先前版本的已編輯郵件。</span><span class="sxs-lookup"><span data-stu-id="298a5-133">If the user is on hold, previous versions of edited messages are preserved.</span></span> |
| <span data-ttu-id="298a5-134">內嵌圖像</span><span class="sxs-lookup"><span data-stu-id="298a5-134">Inline images</span></span> | <span data-ttu-id="298a5-135">是</span><span class="sxs-lookup"><span data-stu-id="298a5-135">Yes</span></span> | |
| <span data-ttu-id="298a5-136">該表</span><span class="sxs-lookup"><span data-stu-id="298a5-136">Tables</span></span> | <span data-ttu-id="298a5-137">是</span><span class="sxs-lookup"><span data-stu-id="298a5-137">Yes</span></span> | |
| <span data-ttu-id="298a5-138">主題</span><span class="sxs-lookup"><span data-stu-id="298a5-138">Subject</span></span> | <span data-ttu-id="298a5-139">是</span><span class="sxs-lookup"><span data-stu-id="298a5-139">Yes</span></span> | |
| <span data-ttu-id="298a5-140">引述</span><span class="sxs-lookup"><span data-stu-id="298a5-140">Quotes</span></span> | <span data-ttu-id="298a5-141">是</span><span class="sxs-lookup"><span data-stu-id="298a5-141">Yes</span></span> | <span data-ttu-id="298a5-142">已報價的內容可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="298a5-142">Quoted content is searchable.</span></span> <span data-ttu-id="298a5-143">不過，搜尋結果不會指出內容已加上引號。</span><span class="sxs-lookup"><span data-stu-id="298a5-143">However, search results don't indicate that the content was quoted.</span></span> |
| <span data-ttu-id="298a5-144">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="298a5-144">Name of channel</span></span> | <span data-ttu-id="298a5-145">否</span><span class="sxs-lookup"><span data-stu-id="298a5-145">No</span></span> | |

- <span data-ttu-id="298a5-146">若要使用 Microsoft 團隊內容進行 eDiscovery 調查，請參閱在[安全性 & 合規性中心連結中管理 ediscovery 案例](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)中的步驟1。</span><span class="sxs-lookup"><span data-stu-id="298a5-146">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [Manage eDiscovery cases in the Security & Compliance Center](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

- <span data-ttu-id="298a5-147">Microsoft 團隊資料將在 Excel eDiscovery 匯出輸出中顯示為 IM 或交談。</span><span class="sxs-lookup"><span data-stu-id="298a5-147">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="298a5-148">您可以 `.pst` 在 Outlook 中開啟檔案，以在匯出後查看這些郵件。</span><span class="sxs-lookup"><span data-stu-id="298a5-148">You can open the `.pst` file in Outlook to view those messages after export.</span></span>

    <span data-ttu-id="298a5-149">當您查看小組的檔案時 `.pst` ，請注意所有交談都保留在 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="298a5-149">When viewing the `.pst` file for the team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="298a5-150">郵件標題包含團隊名稱和頻道名稱。</span><span class="sxs-lookup"><span data-stu-id="298a5-150">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="298a5-151">例如，下圖顯示的是來自王俊元的訊息，其中 messaged 製造規範小組的專案7標準頻道。</span><span class="sxs-lookup"><span data-stu-id="298a5-151">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Outlook 中使用者信箱的小組聊天資料夾螢幕擷取畫面](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

- <span data-ttu-id="298a5-153">使用者信箱中的私人聊天儲存在 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="298a5-153">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="298a5-154">電子檔探索（私人頻道）</span><span class="sxs-lookup"><span data-stu-id="298a5-154">eDiscovery of private channels</span></span>

<span data-ttu-id="298a5-155">在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。</span><span class="sxs-lookup"><span data-stu-id="298a5-155">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="298a5-156">記錄的標題會有格式設定，指出寄自哪一個私人頻道。</span><span class="sxs-lookup"><span data-stu-id="298a5-156">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="298a5-157">因為每個私人通道都有自己的 SharePoint 網站集合與父小組網站分開，所以專用通道中的檔案會獨立于父團隊進行管理。</span><span class="sxs-lookup"><span data-stu-id="298a5-157">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="298a5-158">小組不支援小組內單一頻道的 eDiscovery 搜尋，所以必須搜尋整個小組。</span><span class="sxs-lookup"><span data-stu-id="298a5-158">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="298a5-159">若要在私人頻道中執行電子檔探索搜尋，請在整個小組中搜尋、與私人頻道相關聯的網站集合（包括檔案），以及私人頻道成員的信箱（以包含郵件）。</span><span class="sxs-lookup"><span data-stu-id="298a5-159">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="298a5-160">使用下列步驟來識別您在 eDiscovery 搜尋中包含的私人頻道中的檔案和訊息。</span><span class="sxs-lookup"><span data-stu-id="298a5-160">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="298a5-161">在 eDiscovery 搜尋中包含私人通道檔案</span><span class="sxs-lookup"><span data-stu-id="298a5-161">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="298a5-162">在執行這些步驟之前，請先安裝[Sharepoint Online 管理命令介面並聯機至 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="298a5-162">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="298a5-163">執行下列動作，以取得與團隊中的私人頻道相關聯的所有 SharePoint 網站集合的清單。</span><span class="sxs-lookup"><span data-stu-id="298a5-163">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="298a5-164">執行下列 PowerShell 腳本，以取得與團隊中的私人頻道與父團隊群組識別碼相關聯的所有 SharePoint 網站集合 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="298a5-164">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="298a5-165">針對每個團隊或群組識別碼，請執行下列 PowerShell 腳本來找出所有相關的專用通道網站，其中 $groupID 是團隊的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="298a5-165">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="298a5-166">在 eDiscovery 搜尋中包含私人通道訊息</span><span class="sxs-lookup"><span data-stu-id="298a5-166">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="298a5-167">在執行這些步驟之前，請確定您已安裝[最新版本的團隊 PowerShell 模組](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="298a5-167">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="298a5-168">執行下列動作，取得小組中的私人頻道清單。</span><span class="sxs-lookup"><span data-stu-id="298a5-168">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="298a5-169">執行下列動作以取得私人頻道成員的清單。</span><span class="sxs-lookup"><span data-stu-id="298a5-169">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="298a5-170">從小組中的每個私人頻道包含所有成員的信箱，成為 eDiscovery 搜尋查詢的一部分。</span><span class="sxs-lookup"><span data-stu-id="298a5-170">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="298a5-171">高級 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="298a5-171">Advanced eDiscovery</span></span>

<span data-ttu-id="298a5-172">您也可以使用 [[高級 eDiscovery 工作流程](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)] 來搜尋及保留部分 Microsoft 團隊內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-172">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="298a5-173">雖然 eDiscovery 提供一系列的搜尋、保留和匯出功能，但高級 eDiscovery 則提供合規性管理員更多工具來識別資料來源並分析其內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-173">While eDiscovery provides a range of search, hold, and export functionality, advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="298a5-174">小組內容的高級 eDiscovery 保管人工作流程</span><span class="sxs-lookup"><span data-stu-id="298a5-174">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="298a5-175">保管人可能是各種團隊的成員。</span><span class="sxs-lookup"><span data-stu-id="298a5-175">Custodians might be a member of various teams.</span></span> <span data-ttu-id="298a5-176">您可以捕獲與這些保管人相關的小組內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-176">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="298a5-177">如需管理員工作流程的背景與指示，請參閱[高級 eDiscovery 工作流程](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="298a5-177">For background and instructions on the custodian workflow, see [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span>

<span data-ttu-id="298a5-178">在新增保管人之後，按一下 [**下一步]** 按鈕，然後按一下 [**新增**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="298a5-178">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="298a5-179">接著會顯示一個視窗，提示您選取其他位置，這會顯示所有保管人的成員資格以及其資料對應的 SharePoint 網站位置。</span><span class="sxs-lookup"><span data-stu-id="298a5-179">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="298a5-180">從所有這些資料來源和小組中，您可以選擇您想要用於 eDiscovery 的內容，然後將該使用者及您已識別的所有資料來源保留。</span><span class="sxs-lookup"><span data-stu-id="298a5-180">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="298a5-181">您可以選取是否要包括其 Exchange 內容、其 OneDrive 內容，或同時包含兩者。</span><span class="sxs-lookup"><span data-stu-id="298a5-181">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="298a5-182">Exchange 內容包括使用者信箱中的所有應用程式內容，例如他們的電子郵件、儲存在其信箱中的小組內容等。</span><span class="sxs-lookup"><span data-stu-id="298a5-182">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="298a5-183">OneDrive 內容不僅包括使用者的內容，還包含儲存在 OneDrive 中的所有小組內容，例如1:1 聊天、1： N 聊天，以及在聊天中共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="298a5-183">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="298a5-184">您也可以選擇將保管人中的任何小組相關聯，讓保管人擁有存取權的通道交談訊息和檔案都包含在其中。</span><span class="sxs-lookup"><span data-stu-id="298a5-184">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="298a5-185">此外，任何其他團隊都可以與保管人建立關聯。</span><span class="sxs-lookup"><span data-stu-id="298a5-185">Additionally, any other team can be associated with a custodian.</span></span> <span data-ttu-id="298a5-186">如需詳細資訊，請參閱[將保管人新增至高級 eDiscovery 案例](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="298a5-186">For more information, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

> [!NOTE]
> <span data-ttu-id="298a5-187">電子檔探索[私人通道](private-channels.md)中的訊息和檔案，與在標準通道中的運作方式不同。</span><span class="sxs-lookup"><span data-stu-id="298a5-187">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="298a5-188">若要深入瞭解，請參閱電子檔探索（[私人頻道](#ediscovery-of-private-channels)）。</span><span class="sxs-lookup"><span data-stu-id="298a5-188">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="298a5-189">保留資料來源</span><span class="sxs-lookup"><span data-stu-id="298a5-189">Placing a data source on hold</span></span>

<span data-ttu-id="298a5-190">如果沒有指派給保管人的特定使用者，您可以保留整個資料來源。</span><span class="sxs-lookup"><span data-stu-id="298a5-190">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="298a5-191">如需保留的詳細資訊，請參閱[在高級 eDiscovery 中管理保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="298a5-191">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="298a5-192">建立小組內容的保留時間時，您可以選擇要在保留中包含的所有位置。</span><span class="sxs-lookup"><span data-stu-id="298a5-192">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="298a5-193">即使使用者正在刪除或變更內容，保留也會維持該內容所有先前版本的複本。</span><span class="sxs-lookup"><span data-stu-id="298a5-193">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="298a5-194">您也可以使用選擇性查詢，根據關鍵字、日期範圍、作者及許多其他準則來設定保留條件。</span><span class="sxs-lookup"><span data-stu-id="298a5-194">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="298a5-195">如果您沒有指定關鍵字，則來自該資料來源的所有內容都會受到保留。</span><span class="sxs-lookup"><span data-stu-id="298a5-195">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="298a5-196">[高級 eDiscovery 搜尋]</span><span class="sxs-lookup"><span data-stu-id="298a5-196">Advanced eDiscovery searches</span></span>

<span data-ttu-id="298a5-197">您也可以搜尋小組內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-197">Teams content can also be searched.</span></span> <span data-ttu-id="298a5-198">如需搜尋的詳細資訊，請參閱[在 [高級 eDiscovery] 中收集案例的資料](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="298a5-198">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="298a5-199">如果即使一封郵件符合搜尋查詢，搜尋將會傳回整個交談。</span><span class="sxs-lookup"><span data-stu-id="298a5-199">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="298a5-200">建立搜尋查詢時，您可以選擇 [保管人]，讓您已選取的所有來源都經過搜尋。</span><span class="sxs-lookup"><span data-stu-id="298a5-200">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="298a5-201">您也可以搜尋非 custodial 來源，例如未對應至使用者的小組網站。</span><span class="sxs-lookup"><span data-stu-id="298a5-201">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="298a5-202">您也可以在小組內容中縮小搜尋範圍，提供選用的查詢。</span><span class="sxs-lookup"><span data-stu-id="298a5-202">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="298a5-203">在您建立並選取搜尋後，會顯示一個視窗，其中包含您可以在選取的搜尋上執行的其他詳細資料和動作。</span><span class="sxs-lookup"><span data-stu-id="298a5-203">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="298a5-204">如果您按一下 [**統計資料]** 按鈕，您可以查看有關搜尋的統計資料，包括根據位置類型、內容的原始來源，以及內容是否位於群組信箱、個別使用者信箱或 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="298a5-204">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="298a5-205">這可讓您查看搜尋結果所產生的來源明細。</span><span class="sxs-lookup"><span data-stu-id="298a5-205">This allows you to see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="298a5-206">您也可以使用 [**查詢**] 視圖，查看哪些個別關鍵字對您的結果有影響。</span><span class="sxs-lookup"><span data-stu-id="298a5-206">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="298a5-207">完成搜尋之後，您可以按一下 [**新增結果至審閱設定**] 按鈕，然後將其新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="298a5-207">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="298a5-208">如需有關審閱集的詳細資訊，請參閱本文稍後的管理高級 eDiscovery 和[審閱集合工作流程](#review-sets-workflow)[中的審閱集合](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="298a5-208">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="298a5-209">標準的審閱集和交談審查集合</span><span class="sxs-lookup"><span data-stu-id="298a5-209">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="298a5-210">在將搜尋新增至審閱集合時，您可以從一般的審閱集或交談審查集合中進行選擇。</span><span class="sxs-lookup"><span data-stu-id="298a5-210">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="298a5-211">標準的審閱集與匯出類似;它提供小組內容的個別檔案 `.msg` ，並在 [基本視圖] 中呈現內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-211">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="298a5-212">您通常會在規劃使用其他軟體工具以稍後重新處理檔案時，使用一般的審閱集。</span><span class="sxs-lookup"><span data-stu-id="298a5-212">You would typically use a normal review set when you plan to use other software tools to re-process the files later.</span></span>

<span data-ttu-id="298a5-213">交談審查集合提供更直觀、更具執行緒的交談視圖;它會以正確的順序來顯示相關的郵件。</span><span class="sxs-lookup"><span data-stu-id="298a5-213">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

<span data-ttu-id="298a5-214">在兩種類型的審閱集中都提供密文等功能。</span><span class="sxs-lookup"><span data-stu-id="298a5-214">Functionality such as redaction is available in both types of review sets.</span></span>

<span data-ttu-id="298a5-215">如需有關審閱集的詳細資訊，請參閱[在高級 eDiscovery 中查看交談](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="298a5-215">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="298a5-216">收集選項</span><span class="sxs-lookup"><span data-stu-id="298a5-216">Collection options</span></span>

<span data-ttu-id="298a5-217">新增至審閱集合時，視窗的 [**收集選項**] 區段下有幾個選項可供使用，包括**交談檢索選項**和**團隊交談**。</span><span class="sxs-lookup"><span data-stu-id="298a5-217">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="298a5-218">如果您啟用這些選項，任何屬於您的審閱集中的個別團隊訊息，也會顯示在其周圍有其他訊息，以供內容使用。</span><span class="sxs-lookup"><span data-stu-id="298a5-218">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="298a5-219">例如，如果您的查詢非常特殊且只傳回一封郵件，則啟用這些選項也會傳回數個郵件，並追蹤符合您查詢的訊息。</span><span class="sxs-lookup"><span data-stu-id="298a5-219">For example, if your query is very specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="298a5-220">許多邏輯準則是用來判斷其他訊息是否提供與您查詢相符之訊息的內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-220">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="298a5-221">例如，針對小組內容，啟用這些選項將會因郵件進行執行緒化的方式來檢索上層訊息和所有子郵件。</span><span class="sxs-lookup"><span data-stu-id="298a5-221">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="298a5-222">也會檢查郵件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="298a5-222">Message time stamps are also checked.</span></span> <span data-ttu-id="298a5-223">如果郵件符合您的查詢，在4小時內，或在4個小時內追蹤的相鄰訊息，就會被視為交談的一部分，也會包含在結果中。</span><span class="sxs-lookup"><span data-stu-id="298a5-223">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="298a5-224">如果您必須確定哪些上下文訊息會傳回與您的搜尋查詢相符的內容，您就不需要使用這些選項。</span><span class="sxs-lookup"><span data-stu-id="298a5-224">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="298a5-225">您可以收集所有內容，或者您可以放寬搜尋的日期範圍，以便讓您查詢的結果傳回更多的郵件。</span><span class="sxs-lookup"><span data-stu-id="298a5-225">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="298a5-226">審閱集合工作流程</span><span class="sxs-lookup"><span data-stu-id="298a5-226">Review sets workflow</span></span>

<span data-ttu-id="298a5-227">您可以按一下 [**審閱集**] 索引標籤，查看現有的審閱集或建立新的評論。如需有關審閱集的詳細資訊，請參閱[在高級 eDiscovery 中管理審閱集合](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="298a5-227">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="298a5-228">除了檔之外，您還可以將電子郵件、團隊訊息、Yammer 郵件及其他內容新增到您的審閱集中。</span><span class="sxs-lookup"><span data-stu-id="298a5-228">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="298a5-229">在審閱集中，您也可以執行許多您可以在其他上下文中執行的相同作業，例如搜尋內容和建立自訂查詢。</span><span class="sxs-lookup"><span data-stu-id="298a5-229">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="298a5-230">這些操作只適用于已新增至審閱集的專案。</span><span class="sxs-lookup"><span data-stu-id="298a5-230">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="298a5-231">[**管理審閱設定**] 按鈕可提供其他選項，例如 [分析]、[摘要報告]、已新增多少個載入組等等。</span><span class="sxs-lookup"><span data-stu-id="298a5-231">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="298a5-232">若要存取資料的視覺效果與圖表，請按一下右上角的 [**個別結果** \> **搜尋設定檔] 視圖**。</span><span class="sxs-lookup"><span data-stu-id="298a5-232">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="298a5-233">您可以按一下這些圖表中的 [楔形]，以互動方式選取您要查詢的內容類型。</span><span class="sxs-lookup"><span data-stu-id="298a5-233">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="298a5-234">例如，您可以選擇只查詢團隊內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-234">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="298a5-235">您也可以儲存這些查詢，就像儲存您手動撰寫的查詢一樣。</span><span class="sxs-lookup"><span data-stu-id="298a5-235">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="298a5-236">[摘要] 視圖、[文字視圖] 和 [批註] 視圖</span><span class="sxs-lookup"><span data-stu-id="298a5-236">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="298a5-237">如果您按一下 [審查] 集中的 [小組交談]，就會顯示 [**摘要] 視圖**，將整個小組交談顯示為您可以個別互動的訊息清單。</span><span class="sxs-lookup"><span data-stu-id="298a5-237">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="298a5-238">按一下訊息右邊的向下箭號，以顯示操作功能表，可讓您查看訊息詳細資料或下載個別檔案 `.msg` 。</span><span class="sxs-lookup"><span data-stu-id="298a5-238">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="298a5-239">按一下 [郵件詳細資料]，就會顯示該郵件的中繼資料或完整中繼資料摘要。</span><span class="sxs-lookup"><span data-stu-id="298a5-239">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="298a5-240">若要下載 PDF，請按一下 [摘要] 視圖右上方的 [下載] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="298a5-240">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="298a5-241">按一下 [**文字視圖**] 索引標籤，以顯示已提取的小組交談文字的純文字視圖。</span><span class="sxs-lookup"><span data-stu-id="298a5-241">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="298a5-242">這適用于匯出，您可以使用其他軟體工具輕鬆處理此解壓縮的文字。</span><span class="sxs-lookup"><span data-stu-id="298a5-242">This is suitable for export and you can easily work with this extracted text using other software tools.</span></span>

<span data-ttu-id="298a5-243">按一下 [批註] [**查看**] 索引標籤，即可存取 [批註] 功能。</span><span class="sxs-lookup"><span data-stu-id="298a5-243">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="298a5-244">這個索引標籤會以類似團隊交談的格式來顯示內容，但是還有其他編輯選項。</span><span class="sxs-lookup"><span data-stu-id="298a5-244">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="298a5-245">您可以使用鉛筆工具來製作筆記、在郵件上繪圖，或進行精細的 scratching 以進行密文。</span><span class="sxs-lookup"><span data-stu-id="298a5-245">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="298a5-246">您也可以使用「**區域密文**」工具來繪製黑色外框，並將它標示為「Redacted」的矩形。</span><span class="sxs-lookup"><span data-stu-id="298a5-246">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="298a5-247">[**批註視圖**] 索引標籤底部是 [**標記檔**] 按鈕，會顯示 [標記] 面板。</span><span class="sxs-lookup"><span data-stu-id="298a5-247">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="298a5-248">在此面板中，您可以將標記套用至團隊交談中的所有訊息。</span><span class="sxs-lookup"><span data-stu-id="298a5-248">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="298a5-249">您可以將交談標記為「回應」或「無回應」、[無論是否包含有趣的專案] （無論是否應包含在匯出中），以及是否需要進一步審查。</span><span class="sxs-lookup"><span data-stu-id="298a5-249">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="298a5-250">您也可以管理並套用其他可自訂的標記。</span><span class="sxs-lookup"><span data-stu-id="298a5-250">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="298a5-251">[動作] 功能表</span><span class="sxs-lookup"><span data-stu-id="298a5-251">Action menu</span></span>

<span data-ttu-id="298a5-252">您可以在 [審閱集合] 視窗中按一下 [**動作**匯出] 來匯出內容 \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="298a5-252">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="298a5-253">匯出時有許多選項可供使用。</span><span class="sxs-lookup"><span data-stu-id="298a5-253">There are many options available when exporting.</span></span>

<span data-ttu-id="298a5-254">若要匯出包含所有小組郵件之所有中繼資料的檔案，請按一下以選取 [**載入**檔案] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="298a5-254">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="298a5-255">若要在檔案中包含任何您已套用至內容的標記，請按一下以選取 **[卷**標] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="298a5-255">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="298a5-256">使用 [**原生**檔案] 選項，以其原生格式匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="298a5-256">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="298a5-257">您可以選擇將交談匯出為單一檔案，或是將所有個別聊天訊息匯出為自己的個別檔案。</span><span class="sxs-lookup"><span data-stu-id="298a5-257">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="298a5-258">[**文字檔**] 選項可讓您儲存純文字版本的內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-258">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="298a5-259">如需如何在審閱集中取得小組交談的純文字視圖，請參閱上面的 [[摘要視圖]、[文字視圖] 和 [批註] 視圖](#summary-view-text-view-and-annotate-view)。</span><span class="sxs-lookup"><span data-stu-id="298a5-259">See [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above for more information about how to obtain a plain text view of Teams conversations in the review set.</span></span>

<span data-ttu-id="298a5-260">如果您對內容套用任何密文，如上面的 [[摘要視圖]、[文字視圖] 和 [批註](#summary-view-text-view-and-annotate-view)] 區段所述，您可以選取 [**使用轉換過的 pdf 取代 redacted natives** ] 選項，以 PDF 中的已轉換複本來取代原生檔案。</span><span class="sxs-lookup"><span data-stu-id="298a5-260">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="298a5-261">您可以選擇匯出至 Microsoft 提供的 Azure blob 儲存體容器，或提供您自己的 Azure Blob 儲存體容器。</span><span class="sxs-lookup"><span data-stu-id="298a5-261">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="298a5-262">當您準備好要開始匯出程式時，請按一下 [**匯出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="298a5-262">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="298a5-263">匯出完成後，請參閱[下載匯出作業](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs)，以取得更多關於如何存取 Azure blob 儲存容器的資訊，以及下載匯出的內容。</span><span class="sxs-lookup"><span data-stu-id="298a5-263">After export is complete, see [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content.</span></span>

> [!NOTE]
> <span data-ttu-id="298a5-264">匯出可能需要較長的時間。</span><span class="sxs-lookup"><span data-stu-id="298a5-264">Exporting can take an extended period of time.</span></span> <span data-ttu-id="298a5-265">若要追蹤匯出程式的狀態，請結束 [**審閱集**] 索引標籤，然後按一下 [**匯出**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="298a5-265">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="298a5-266">相關主題</span><span class="sxs-lookup"><span data-stu-id="298a5-266">Related topics</span></span>

- [<span data-ttu-id="298a5-267">Microsoft 365 中的 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="298a5-267">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="298a5-268">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="298a5-268">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
