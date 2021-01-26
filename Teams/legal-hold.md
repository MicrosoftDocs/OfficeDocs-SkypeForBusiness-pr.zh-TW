---
title: 在法律封存上放置 Microsoft 團隊使用者或團隊
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何使用安全性 & 合規性中心在 Microsoft 團隊使用者或小組中進行法律封存，以及如何根據資料需求來瞭解需要法律封存。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c04f3584aa7207d9d9ee1126df992657f84aa213
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980447"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="73b53-103">在法律封存上放置 Microsoft 團隊使用者或團隊</span><span class="sxs-lookup"><span data-stu-id="73b53-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="73b53-104">當您合理地預期受到訴訟時，組織必須保留以電子方式儲存的資訊 (ESI) ，包括與案例相關的小組聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="73b53-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="73b53-105">組織可能需要保留與特定主題或特定人員相關的所有訊息。</span><span class="sxs-lookup"><span data-stu-id="73b53-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="73b53-106">本文將涵蓋 Microsoft 團隊 (在整個 M365 空間中進行保留的保留，請參閱 [管理電子檔探索案例： [保留中的內容位置](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)]。 ) 。</span><span class="sxs-lookup"><span data-stu-id="73b53-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="73b53-107">在2020年2月，我們已針對私人頻道啟用法律封存或案例封存 (私人通道聊天是儲存在使用者信箱中，一般通道聊天會儲存在小組群組信箱) 中。</span><span class="sxs-lookup"><span data-stu-id="73b53-107">In February 2020, we enabled legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in a Team's group mailbox).</span></span> <span data-ttu-id="73b53-108">如果已有合法保留使用者信箱，保留原則現在會自動套用至儲存在該信箱中的私人通道訊息。</span><span class="sxs-lookup"><span data-stu-id="73b53-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="73b53-109">系統管理員不需要採取進一步的動作，就能開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="73b53-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="73b53-110">在專用通道中共用的檔案的法定保留也受到支援。</span><span class="sxs-lookup"><span data-stu-id="73b53-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="73b53-111">在 Microsoft 團隊中，整個團隊或選取的使用者都可以保留或法律封存。</span><span class="sxs-lookup"><span data-stu-id="73b53-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="73b53-112">執行此動作將會確保在那些小組中交換的所有郵件 (包括私人通道) 或由這些人員所交換的訊息，都可以透過組織的合規性管理員或團隊管理員來發現。</span><span class="sxs-lookup"><span data-stu-id="73b53-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="73b53-113">[保留使用者] 不會自動將群組放在 [保留] 或 [相反]。</span><span class="sxs-lookup"><span data-stu-id="73b53-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

<span data-ttu-id="73b53-114">若要讓使用者或團隊在法律上保留：</span><span class="sxs-lookup"><span data-stu-id="73b53-114">To put a user or a team on legal hold:</span></span>

1. <span data-ttu-id="73b53-115">流覽至 [安全性 & 合規性中心](https://go.microsoft.com/fwlink/?linkid=854628)。</span><span class="sxs-lookup"><span data-stu-id="73b53-115">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="73b53-116">當您建立新的案例時，系統會顯示將信箱或網站保留的選項。</span><span class="sxs-lookup"><span data-stu-id="73b53-116">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="73b53-117">移至 eDiscovery 或高級 eDiscovery，然後按一下 [建立案例] 來建立案例。</span><span class="sxs-lookup"><span data-stu-id="73b53-117">Go to eDiscovery or Advanced eDiscovery and create a case by clicking "Create a case".</span></span> <span data-ttu-id="73b53-118">一旦建立案例，請將其開啟。</span><span class="sxs-lookup"><span data-stu-id="73b53-118">Once the case is created, open it.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="73b53-119">![已選取 [Microsoft 團隊 eDiscovery] 索引標籤，並顯示 [建立案例] 按鈕。](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="73b53-119">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>

3. <span data-ttu-id="73b53-120">從頂端功能表移至 [保留] 區段，然後按一下 [+ 建立] 來建立保留。</span><span class="sxs-lookup"><span data-stu-id="73b53-120">Go to the "Holds" section from the top menu and click "+ Create" to create a hold.</span></span> <span data-ttu-id="73b53-121">將使用者或團隊放在暫留會儲存由這些使用者或郵件交換的所有訊息。</span><span class="sxs-lookup"><span data-stu-id="73b53-121">Putting a user or a team on hold saves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="73b53-122">當您建立新的案例時，系統會顯示將信箱或網站保留的選項。</span><span class="sxs-lookup"><span data-stu-id="73b53-122">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="73b53-123">![顯示已選取 [保留] 索引標籤的影像，以及下方的 [建立] 按鈕。](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="73b53-123">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>

   1. <span data-ttu-id="73b53-124">為 **您的保留命名**。</span><span class="sxs-lookup"><span data-stu-id="73b53-124">**Name your hold**.</span></span> <span data-ttu-id="73b53-125">針對您要建立的保留，選取一個描述性且唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="73b53-125">Select a descriptive and unique name for the hold you are going to create.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="73b53-126">![此螢幕擷取畫面顯示 [名稱] 您的 [保留] 索引標籤，您可以在此輸入您要建立之保留的名稱和描述。](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="73b53-126">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>

    2. <span data-ttu-id="73b53-127">**選擇 [位置**]。</span><span class="sxs-lookup"><span data-stu-id="73b53-127">**Choose location**.</span></span> <span data-ttu-id="73b53-128">選擇您是否要在使用者或整個小組中套用保留， (只能在個別頻道上使用 [保留]) 。</span><span class="sxs-lookup"><span data-stu-id="73b53-128">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="73b53-129">注意：如果使用者已保留，則所有郵件都會保留，包括在1:1 聊天中傳送的任何內容、1：許多或群組聊天，或是頻道交談 (包括私人頻道) 。</span><span class="sxs-lookup"><span data-stu-id="73b53-129">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
  
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="73b53-130">![在這裡，我們有 [選擇位置] 區段來建立新的保留，您可以在其中決定要將 [保留] 套用到哪個 M365 選項（包括 Microsoft 團隊）。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="73b53-130">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    3. <span data-ttu-id="73b53-131">**建立查詢**。</span><span class="sxs-lookup"><span data-stu-id="73b53-131">**Create Query**.</span></span> <span data-ttu-id="73b53-132">如果您想要在保留原則中有更多的細微性，您可以自訂 [保留]。</span><span class="sxs-lookup"><span data-stu-id="73b53-132">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="73b53-133">例如，您可以指定要尋找的關鍵字，或者您可以新增更多的條件，保留才能生效。</span><span class="sxs-lookup"><span data-stu-id="73b53-133">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    4. <span data-ttu-id="73b53-134">在發佈到您的組織之前，請先 **檢查您的設定**。</span><span class="sxs-lookup"><span data-stu-id="73b53-134">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="73b53-135">設定法定保留之後，您可以在 [團隊 eDiscovery](eDiscovery-investigation.md) 文章中發現任何保留原則所保留的所有內容。</span><span class="sxs-lookup"><span data-stu-id="73b53-135">After the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73b53-136">當使用者或群組處於保留狀態時，所有郵件複本都會保留下來。</span><span class="sxs-lookup"><span data-stu-id="73b53-136">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="73b53-137">例如，如果使用者在頻道中張貼一封郵件，然後修改該郵件，請在保留案例中，這兩份郵件複本都會保留下來。</span><span class="sxs-lookup"><span data-stu-id="73b53-137">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="73b53-138">如果沒有合法保留，就只會保留最新的訊息。</span><span class="sxs-lookup"><span data-stu-id="73b53-138">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="73b53-139">保留法律封存的內容位置，以保留團隊內容</span><span class="sxs-lookup"><span data-stu-id="73b53-139">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="73b53-140">做為有用的指南，您可以使用下表來瞭解哪個內容位置 (例如信箱或網站) 放在法律封存上，以保留不同類型的小組內容。</span><span class="sxs-lookup"><span data-stu-id="73b53-140">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="73b53-141">案例</span><span class="sxs-lookup"><span data-stu-id="73b53-141">Scenario</span></span>  |<span data-ttu-id="73b53-142">內容位置</span><span class="sxs-lookup"><span data-stu-id="73b53-142">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="73b53-143">使用者 (的小組聊天例如，1:1 聊天、1： N 群組聊天和私人頻道交談) </span><span class="sxs-lookup"><span data-stu-id="73b53-143">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="73b53-144">使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="73b53-144">User mailbox.</span></span>         |
|<span data-ttu-id="73b53-145">團隊頻道聊天 (不包括私人頻道) </span><span class="sxs-lookup"><span data-stu-id="73b53-145">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="73b53-146">小組所用的信箱。</span><span class="sxs-lookup"><span data-stu-id="73b53-146">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="73b53-147">小組檔案內容 (例如 Wiki 內容和檔案) </span><span class="sxs-lookup"><span data-stu-id="73b53-147">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="73b53-148">小組使用的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="73b53-148">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="73b53-149">團隊私人頻道檔案</span><span class="sxs-lookup"><span data-stu-id="73b53-149">Teams private channel files</span></span>     |<span data-ttu-id="73b53-150">專用頻道的專用 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="73b53-150">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="73b53-151">使用者的私人內容</span><span class="sxs-lookup"><span data-stu-id="73b53-151">User's private content</span></span>     |<span data-ttu-id="73b53-152">使用者的商務用 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="73b53-152">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="73b53-153">聊天中的卡片內容</span><span class="sxs-lookup"><span data-stu-id="73b53-153">Card content in chats</span></span>|<span data-ttu-id="73b53-154">1:1 聊天的使用者信箱、1： N 群組聊天、私人頻道交談或頻道訊息中卡片內容的群組信箱。</span><span class="sxs-lookup"><span data-stu-id="73b53-154">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="73b53-155">如需詳細資訊，請參閱 [建立 eDiscovery 保留](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)中的 [保留卡片內容] 區段。</span><span class="sxs-lookup"><span data-stu-id="73b53-155">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="73b53-156">若要在私人通道中保留通訊，您必須將使用者信箱放 ( 私人通道) 使用者，並在使用 eDiscovery 工具進行搜尋時，在該使用者的信箱中搜尋。</span><span class="sxs-lookup"><span data-stu-id="73b53-156">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="73b53-157">如先前所述，私人通道聊天是儲存在使用者信箱中，而不是在小組的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="73b53-157">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="73b53-158">如果您想進一步閱讀本主題中關於 Microsoft 365 中非團隊區域的內容，請參閱 [管理 eDiscovery 案例：保留內容位置](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。</span><span class="sxs-lookup"><span data-stu-id="73b53-158">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
