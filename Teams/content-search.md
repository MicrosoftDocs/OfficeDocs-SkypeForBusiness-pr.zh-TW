---
title: 在 Microsoft 團隊中使用內容搜尋
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 瞭解如何使用 Microsoft 365 合規性中心中的內容搜尋來搜尋儲存在 Exchange Online、SharePoint Online、商務用 OneDrive 和 OneNote 中的 Microsoft 團隊內容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980437"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="43e53-103">在 Microsoft 團隊中使用內容搜尋</span><span class="sxs-lookup"><span data-stu-id="43e53-103">Use Content search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="43e53-104">在 [私人通道](private-channels.md) 中，郵件和檔案的內容搜尋與在標準通道中的運作方式不同。</span><span class="sxs-lookup"><span data-stu-id="43e53-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="43e53-105">若要深入瞭解，請參閱 [私人頻道的內容搜尋](#content-search-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="43e53-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="43e53-106">[內容搜尋] 提供一種方式，可查詢 Microsoft 團隊資訊跨越 Exchange、SharePoint Online 和商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="43e53-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="43e53-107">若要深入瞭解，請參閱 [Microsoft 365 中的內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/content-search)。</span><span class="sxs-lookup"><span data-stu-id="43e53-107">To learn more, see [Content search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="43e53-108">例如，針對您的製造規格信箱和製造規格 SharePoint 網站使用 **內容搜尋** ，您可以從 Exchange、檔案上傳和 SharePoint Online 的修改，以及 OneNote 變更，在小組標準頻道交談中搜尋。</span><span class="sxs-lookup"><span data-stu-id="43e53-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="43e53-109">您也可以將查詢準則新增至 **內容搜尋** ，以縮小傳回的結果範圍。</span><span class="sxs-lookup"><span data-stu-id="43e53-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="43e53-110">在上述範例中，您可以尋找已使用 [**新的工廠規格]** 關鍵字的內容。</span><span class="sxs-lookup"><span data-stu-id="43e53-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="43e53-111">新增搜尋條件之後，您可以將報表或實際內容匯出到您的電腦以進行分析。</span><span class="sxs-lookup"><span data-stu-id="43e53-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="43e53-112">私人頻道的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="43e53-112">Content search of private channels</span></span>

<span data-ttu-id="43e53-113">在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。</span><span class="sxs-lookup"><span data-stu-id="43e53-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="43e53-114">記錄的標題會有格式設定，指出寄自哪一個私人頻道。</span><span class="sxs-lookup"><span data-stu-id="43e53-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="43e53-115">因為每個私人通道都有自己的 SharePoint 網站集合與父小組網站分開，所以專用通道中的檔案會獨立于父團隊進行管理。</span><span class="sxs-lookup"><span data-stu-id="43e53-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="43e53-116">小組不支援在單一頻道中搜尋內容，所以必須搜尋整個小組。</span><span class="sxs-lookup"><span data-stu-id="43e53-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="43e53-117">若要執行私人頻道的內容搜尋，請在整個小組中搜尋，與專用通道相關聯的網站集合 (，以包含) 的檔案，以及私人頻道成員的信箱 (，以包含) 的郵件。</span><span class="sxs-lookup"><span data-stu-id="43e53-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="43e53-118">使用下列步驟來識別私人頻道中要包含在內容搜尋中的檔案和訊息。</span><span class="sxs-lookup"><span data-stu-id="43e53-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="43e53-119">在內容搜尋中包含私人通道檔案</span><span class="sxs-lookup"><span data-stu-id="43e53-119">Include private channel files in a content search</span></span>

<span data-ttu-id="43e53-120">在執行這些步驟之前，請先安裝 [Sharepoint Online 管理命令介面並聯機至 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="43e53-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="43e53-121">執行下列動作，以取得與團隊中的私人頻道相關聯的所有 SharePoint 網站集合的清單。</span><span class="sxs-lookup"><span data-stu-id="43e53-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="43e53-122">執行下列 PowerShell 腳本，以取得與團隊中的私人頻道與父團隊群組識別碼相關聯的所有 SharePoint 網站集合 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="43e53-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="43e53-123">針對每個團隊或群組識別碼，請執行下列 PowerShell 腳本來識別所有相關的專用通道網站。</span><span class="sxs-lookup"><span data-stu-id="43e53-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="43e53-124">在內容搜尋中包含私人通道訊息</span><span class="sxs-lookup"><span data-stu-id="43e53-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="43e53-125">在執行這些步驟之前，請確定您已安裝 [最新版本的團隊 PowerShell 模組](teams-powershell-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="43e53-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="43e53-126">執行下列動作，取得小組中的私人頻道清單。</span><span class="sxs-lookup"><span data-stu-id="43e53-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="43e53-127">執行下列動作以取得私人頻道成員的清單。</span><span class="sxs-lookup"><span data-stu-id="43e53-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="43e53-128">從小組中的每個私人頻道包含所有成員的信箱，作為內容搜尋查詢的一部分。</span><span class="sxs-lookup"><span data-stu-id="43e53-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43e53-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="43e53-129">Related topics</span></span>

- [<span data-ttu-id="43e53-130">Microsoft 365 規範中心中的電子檔探索案例</span><span class="sxs-lookup"><span data-stu-id="43e53-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 