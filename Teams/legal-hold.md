---
title: 將Microsoft Teams或小組保留為法律保留狀態
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
description: 瞭解如何使用安全性Microsoft Teams合規性中心將使用者或小組擱置&，並瞭解根據資料需求需要法律保留哪些專案。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f2f269d75a7bf8bd97165329d2ae6b006b940f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112299"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="b1d9a-103">將Microsoft Teams或小組保留為法律保留狀態</span><span class="sxs-lookup"><span data-stu-id="b1d9a-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="b1d9a-104">當訴訟有合理的預期時，組織必須保留電子 (ESI) ，包括Teams與案件相關的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="b1d9a-105">組織可能需要保留與特定主題或特定人員相關的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="b1d9a-106">本文將涵蓋 Microsoft Teams (中的法律保留：若要在 M365 空間中解決保留的實現，請參閱管理電子檔探索[案例：](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)將內容位置保留 。) 。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="b1d9a-107">在 2020 年 2 月，我們啟用私人頻道的法律保留或案例保留 (私人頻道聊天會儲存在使用者信箱中，一般頻道聊天會儲存在小組的群組信箱) 。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-107">In February 2020, we enabled legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in a Team's group mailbox).</span></span> <span data-ttu-id="b1d9a-108">如果使用者信箱已有法律保留，保留原則現在會自動適用于儲存在該信箱中的私人通道郵件。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="b1d9a-109">系統管理員無需執行其他動作來開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="b1d9a-110">也支援合法保留在私人頻道中共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="b1d9a-111">在Microsoft Teams，整個團隊或選取的使用者都可以保留或合法保留。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="b1d9a-112">這麼做會確保組織合規性管理員或系統管理員 (在這些團隊中交換的所有郵件) 包括私人頻道) Teams或由這些人員交換的郵件。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="b1d9a-113">將使用者置於保留狀態不會自動將群組置於保留狀態，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

<span data-ttu-id="b1d9a-114">若要將使用者或小組置於法律保留狀態：</span><span class="sxs-lookup"><span data-stu-id="b1d9a-114">To put a user or a team on legal hold:</span></span>

1. <span data-ttu-id="b1d9a-115">流覽至 [安全性與&中心](https://go.microsoft.com/fwlink/?linkid=854628)。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-115">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="b1d9a-116">當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-116">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="b1d9a-117">前往 eDiscovery 或 Advanced eDiscovery，然後按一下 「建立案例」來建立案例。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-117">Go to eDiscovery or Advanced eDiscovery and create a case by clicking "Create a case".</span></span> <span data-ttu-id="b1d9a-118">建立案例後，請開啟它。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-118">Once the case is created, open it.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1d9a-119">![Microsoft Teams已選取 eDiscovery 定位停駐點，顯示建立大小寫按鈕。](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="b1d9a-119">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>

3. <span data-ttu-id="b1d9a-120">從頂端功能表前往 [保留> 區段，然後按一下 [+ 建立」 以建立保留狀態。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-120">Go to the "Holds" section from the top menu and click "+ Create" to create a hold.</span></span> <span data-ttu-id="b1d9a-121">保留使用者或團隊會保留這些使用者或郵件交換的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-121">Putting a user or a team on hold saves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="b1d9a-122">當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-122">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1d9a-123">![顯示已選取的保留選項卡，以及下方的建立按鈕的影像。](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="b1d9a-123">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>

   1. <span data-ttu-id="b1d9a-124">**為保留命名**。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-124">**Name your hold**.</span></span> <span data-ttu-id="b1d9a-125">針對要建立保留狀態，選取描述性且唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-125">Select a descriptive and unique name for the hold you are going to create.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b1d9a-126">![此螢幕擷取畫面顯示名稱您的保留點，您可以在其中輸入您建立保留的名稱和描述。](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="b1d9a-126">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>

    2. <span data-ttu-id="b1d9a-127">**選擇位置**。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-127">**Choose location**.</span></span> <span data-ttu-id="b1d9a-128">選擇是否要將保留狀態用於使用者或整個小組， (目前無法將保留) 。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-128">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="b1d9a-129">注意：如果使用者保持保留狀態，其所有訊息都會保留，包括他們在 1：1 聊天、1：多或群組聊天或頻道交談 (包括私人頻道) 。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-129">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
  
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="b1d9a-130">![在這裡，我們有建立新保留的選擇位置區段，您可以在此決定要申請的 M365 選項，包括 Microsoft Teams 選項。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="b1d9a-130">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    3. <span data-ttu-id="b1d9a-131">**建立查詢**。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-131">**Create Query**.</span></span> <span data-ttu-id="b1d9a-132">如果您想要保留原則的更精細度，您可以自訂保留。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-132">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="b1d9a-133">例如，您可以指定要尋找的關鍵字，或者您可以新增更多條件，讓保留生效時必須滿足這些條件。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-133">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    4. <span data-ttu-id="b1d9a-134">**在發佈至** 貴組織之前，先檢查您的設定。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-134">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="b1d9a-135">設定法律保留之後，您可以在電子檔探索一文之後，探索任何保留Teams[內容](eDiscovery-investigation.md)。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-135">After the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1d9a-136">當使用者或群組處於保留狀態時，所有郵件複本都會保留。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-136">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="b1d9a-137">例如，如果使用者在頻道中張貼郵件，然後修改郵件，在保留情況下，郵件的兩份複本會保留。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-137">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="b1d9a-138">若未就地保留法律，只會保留最新的郵件。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-138">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="b1d9a-139">保留保留內容的位置，以保留Teams內容</span><span class="sxs-lookup"><span data-stu-id="b1d9a-139">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="b1d9a-140">做為實用指南，您可以使用下表瞭解哪些內容位置 (例如信箱或網站) 會保留法律保留，以保留不同類型的Teams內容。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-140">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="b1d9a-141">案例</span><span class="sxs-lookup"><span data-stu-id="b1d9a-141">Scenario</span></span>  |<span data-ttu-id="b1d9a-142">內容位置</span><span class="sxs-lookup"><span data-stu-id="b1d9a-142">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="b1d9a-143">Teams使用者聊天 (例如 1：1 聊天、1：N 群組聊天，以及私人頻道交談) </span><span class="sxs-lookup"><span data-stu-id="b1d9a-143">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="b1d9a-144">使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-144">User mailbox.</span></span>         |
|<span data-ttu-id="b1d9a-145">Teams頻道聊天 (私人頻道) </span><span class="sxs-lookup"><span data-stu-id="b1d9a-145">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="b1d9a-146">小組使用的群組信箱。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-146">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="b1d9a-147">Teams檔案內容 (例如 Wiki 內容和檔案) </span><span class="sxs-lookup"><span data-stu-id="b1d9a-147">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="b1d9a-148">SharePoint小組使用的網站。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-148">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="b1d9a-149">Teams私人頻道檔案</span><span class="sxs-lookup"><span data-stu-id="b1d9a-149">Teams private channel files</span></span>     |<span data-ttu-id="b1d9a-150">私人SharePoint私人網路站。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-150">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="b1d9a-151">使用者的私人內容</span><span class="sxs-lookup"><span data-stu-id="b1d9a-151">User's private content</span></span>     |<span data-ttu-id="b1d9a-152">使用者的帳戶商務用 OneDrive帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-152">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="b1d9a-153">聊天中的卡片內容</span><span class="sxs-lookup"><span data-stu-id="b1d9a-153">Card content in chats</span></span>|<span data-ttu-id="b1d9a-154">1：1 聊天、1：N 群組聊天的使用者信箱，以及頻道訊息中卡片內容的私人頻道交談或群組信箱。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-154">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="b1d9a-155">若要詳細資訊，請參閱建立電子檔探索保留中的「保留卡片 [內容」一節](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-155">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="b1d9a-156">若要在私人頻道中保留通訊，您必須保留使用者信箱 (私人通道使用者) ，而使用 eDiscovery 工具進行搜尋時，您應該在該使用者的信箱中搜尋。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-156">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="b1d9a-157">如先前所述，私人頻道聊天會儲存在使用者信箱中，而不是儲存在小組的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-157">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="b1d9a-158">如果您想要進一步閱讀本主題中的非Teams區域，Microsoft 365管理[電子檔探索案例：](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)保留內容位置。</span><span class="sxs-lookup"><span data-stu-id="b1d9a-158">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>