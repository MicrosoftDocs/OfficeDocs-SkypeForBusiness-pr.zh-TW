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
ms.openlocfilehash: b78fba2a85cd45c07183ebc9df8016f16036dce5
ms.sourcegitcommit: e023c3023f49e196315e176ce346f0dc5825fa56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53275662"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="04705-103">將Microsoft Teams或小組保留為法律保留狀態</span><span class="sxs-lookup"><span data-stu-id="04705-103">Place a Microsoft Teams user or team on legal hold</span></span>

<span data-ttu-id="04705-104">當訴訟有合理的預期時，組織必須保留電子 (ESI) ，包括Teams與案件相關的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="04705-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="04705-105">組織可能需要保留與特定主題或特定人員相關的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="04705-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="04705-106">本文將涵蓋在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="04705-106">This article will cover legal hold in Microsoft Teams.</span></span> <span data-ttu-id="04705-107">若要保留所有Microsoft 365，請參閱[建立電子檔探索保留](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds)。</span><span class="sxs-lookup"><span data-stu-id="04705-107">To hold content across Microsoft 365, see [Create an eDiscovery hold](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds).</span></span>

> [!NOTE]
> <span data-ttu-id="04705-108">我們在 2020 年 2 月開啟私人頻道的法律保留。</span><span class="sxs-lookup"><span data-stu-id="04705-108">In February 2020, we turned on legal hold for private channels.</span></span> <span data-ttu-id="04705-109">私人頻道聊天會儲存在使用者信箱中，而一般頻道聊天則儲存在Teams群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="04705-109">Private channel chats are stored in user mailboxes, while normal channel chats are stored in the Teams’ group mailbox.</span></span> <span data-ttu-id="04705-110">如果使用者信箱已有合法保留狀態，保留原則現在會自動適用于儲存在該信箱中的私人通道郵件。</span><span class="sxs-lookup"><span data-stu-id="04705-110">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="04705-111">系統管理員無需執行其他動作來開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="04705-111">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="04705-112">也支援合法保留在私人頻道中共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="04705-112">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="04705-113">在Microsoft Teams，整個團隊或選取的使用者都可以被置於法律保留狀態。</span><span class="sxs-lookup"><span data-stu-id="04705-113">Within Microsoft Teams, an entire team or select users can be put on legal hold.</span></span> <span data-ttu-id="04705-114">這麼做會確保組織合規性管理員或系統管理員 (在這些團隊中交換的所有郵件) 包括私人頻道) Teams或由這些人員交換的郵件。</span><span class="sxs-lookup"><span data-stu-id="04705-114">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization's compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="04705-115">將使用者置於保留狀態不會自動將群組置於保留狀態，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="04705-115">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>
> <span data-ttu-id="04705-116">無法保留以活動提要送出的通知。</span><span class="sxs-lookup"><span data-stu-id="04705-116">Notifications sent in activity feed can't be placed on hold.</span></span>

<span data-ttu-id="04705-117">若要將使用者或小組置於核心電子檔探索案例的保留狀態：</span><span class="sxs-lookup"><span data-stu-id="04705-117">To put a user or a team on legal hold in a Core eDiscovery case:</span></span>

1. <span data-ttu-id="04705-118">請[前往](https://compliance.microsoft.com)Microsoft 365 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="04705-118">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="04705-119">當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。</span><span class="sxs-lookup"><span data-stu-id="04705-119">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="04705-120">按一下建立案例，前往 **eDiscovery**  >  **Core** **並建立案例**。</span><span class="sxs-lookup"><span data-stu-id="04705-120">Go to **eDiscovery** > **Core** and create a case by clicking **Create a case**.</span></span> <span data-ttu-id="04705-121">建立案例之後，請開啟它。</span><span class="sxs-lookup"><span data-stu-id="04705-121">After the case is created, open it.</span></span>
  
   ![Microsoft Teams已選取 eDiscovery 定位停駐點，顯示建立大小寫按鈕。](media/LegalHold1.png)

   > [!NOTE]
   > <span data-ttu-id="04705-123">您也可以將使用者放在與案例相關聯的保留Advanced eDiscovery狀態。</span><span class="sxs-lookup"><span data-stu-id="04705-123">You can also place a user on a hold that's associated with an Advanced eDiscovery case.</span></span> <span data-ttu-id="04705-124">詳細資訊，請參閱在 中[管理保留Advanced eDiscovery。](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)</span><span class="sxs-lookup"><span data-stu-id="04705-124">For more information, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

3. <span data-ttu-id="04705-125">前往 **頂端功能表上的** [保留資料表>，然後按一下 [ **建立** 以建立保留狀態。</span><span class="sxs-lookup"><span data-stu-id="04705-125">Go to the **Holds** tab on the top menu and click **Create** to create a hold.</span></span> <span data-ttu-id="04705-126">將使用者或團隊置於保留狀態會保留這些使用者或郵件交換的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="04705-126">Placing a user or a team on hold preserves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="04705-127">當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。</span><span class="sxs-lookup"><span data-stu-id="04705-127">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   ![顯示已選取的保留選項卡和下方的建立按鈕的影像。](media/LegalHold2.png)
    
    1. <span data-ttu-id="04705-129">**為保留命名**。</span><span class="sxs-lookup"><span data-stu-id="04705-129">**Name your hold**.</span></span> <span data-ttu-id="04705-130">針對要建立保留狀態，選取描述性且唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="04705-130">Select a descriptive and unique name for the hold you are going to create.</span></span>
  
       ![此螢幕擷取畫面顯示名稱您的保留點，您可以在其中輸入您建立保留的名稱和描述。](media/LegalHold3.png)

    1. <span data-ttu-id="04705-132">**選擇位置**。</span><span class="sxs-lookup"><span data-stu-id="04705-132">**Choose location**.</span></span> <span data-ttu-id="04705-133">選擇是否要將保留狀態用於使用者或整個小組， (目前無法將保留) 。</span><span class="sxs-lookup"><span data-stu-id="04705-133">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="04705-134">注意：如果使用者保持保留狀態，其所有訊息都會保留，包括他們在 1：1 聊天、1：多或群組聊天或頻道交談 (包括私人頻道) 。</span><span class="sxs-lookup"><span data-stu-id="04705-134">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
    <span data-ttu-id="04705-135">![在這裡，我們有建立新保留的選擇位置區段，您可以在此決定要申請的 M365 選項，包括 Microsoft Teams 選項。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="04705-135">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    2. <span data-ttu-id="04705-136">**建立查詢**。</span><span class="sxs-lookup"><span data-stu-id="04705-136">**Create query**.</span></span> <span data-ttu-id="04705-137">如果您想要保留原則的更精細度，您可以自訂保留。</span><span class="sxs-lookup"><span data-stu-id="04705-137">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="04705-138">例如，您可以指定要尋找的關鍵字，或者您可以新增更多條件，讓保留生效時必須滿足這些條件。</span><span class="sxs-lookup"><span data-stu-id="04705-138">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    3. <span data-ttu-id="04705-139">**建立保留之前，** 先檢查您的設定。</span><span class="sxs-lookup"><span data-stu-id="04705-139">**Review your settings** before creating the hold.</span></span>

<span data-ttu-id="04705-140">建立法律保留之後，您可以搜尋任何保留政策所保留的內容。</span><span class="sxs-lookup"><span data-stu-id="04705-140">After the legal hold has been created, you can search the content retained by any hold policy.</span></span> <span data-ttu-id="04705-141">詳細資訊，請參閱在 Teams[中執行電子資料探索Teams。](eDiscovery-investigation.md)</span><span class="sxs-lookup"><span data-stu-id="04705-141">For more information, see [Conduct an eDiscovery investigation in Teams](eDiscovery-investigation.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04705-142">當使用者或群組處於保留狀態時，所有郵件複本都會保留。</span><span class="sxs-lookup"><span data-stu-id="04705-142">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="04705-143">例如，如果使用者在頻道中張貼郵件，然後修改郵件，在保留情況下，郵件的兩份複本會保留。</span><span class="sxs-lookup"><span data-stu-id="04705-143">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="04705-144">若未就地保留法律，只會保留最新的郵件。</span><span class="sxs-lookup"><span data-stu-id="04705-144">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="04705-145">保留保留內容的位置，以保留Teams內容</span><span class="sxs-lookup"><span data-stu-id="04705-145">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="04705-146">做為實用指南，您可以使用下表瞭解哪些內容位置 (例如信箱或網站) 可置於法律保留狀態，以保留不同類型的Teams內容。</span><span class="sxs-lookup"><span data-stu-id="04705-146">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="04705-147">案例</span><span class="sxs-lookup"><span data-stu-id="04705-147">Scenario</span></span>  |<span data-ttu-id="04705-148">內容位置</span><span class="sxs-lookup"><span data-stu-id="04705-148">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="04705-149">Teams使用者聊天 (例如 1：1 聊天、1：N 群組聊天，以及私人頻道交談) </span><span class="sxs-lookup"><span data-stu-id="04705-149">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="04705-150">使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="04705-150">User mailbox.</span></span>         |
|<span data-ttu-id="04705-151">Teams頻道聊天 (私人頻道) </span><span class="sxs-lookup"><span data-stu-id="04705-151">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="04705-152">小組使用的群組信箱。</span><span class="sxs-lookup"><span data-stu-id="04705-152">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="04705-153">Teams檔案內容 (例如 Wiki 內容和檔案) </span><span class="sxs-lookup"><span data-stu-id="04705-153">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="04705-154">SharePoint小組使用的網站。</span><span class="sxs-lookup"><span data-stu-id="04705-154">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="04705-155">Teams私人頻道檔案</span><span class="sxs-lookup"><span data-stu-id="04705-155">Teams private channel files</span></span>     |<span data-ttu-id="04705-156">私人SharePoint私人網路站。</span><span class="sxs-lookup"><span data-stu-id="04705-156">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="04705-157">使用者的私人內容</span><span class="sxs-lookup"><span data-stu-id="04705-157">User's private content</span></span>     |<span data-ttu-id="04705-158">使用者的帳戶商務用 OneDrive帳戶。</span><span class="sxs-lookup"><span data-stu-id="04705-158">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="04705-159">聊天中的卡片內容</span><span class="sxs-lookup"><span data-stu-id="04705-159">Card content in chats</span></span>|<span data-ttu-id="04705-160">1：1 聊天、1：N 群組聊天的使用者信箱，以及頻道訊息中卡片內容的私人頻道交談或群組信箱。</span><span class="sxs-lookup"><span data-stu-id="04705-160">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="04705-161">若要詳細資訊，請參閱建立電子檔探索保留中的「保留卡片 [內容」一節](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。</span><span class="sxs-lookup"><span data-stu-id="04705-161">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="04705-162">若要保留私人頻道中的通訊，您必須保留使用者信箱 (私人頻道使用者) ，而使用 eDiscovery 工具來搜尋時，您應該在該使用者的信箱中搜尋。</span><span class="sxs-lookup"><span data-stu-id="04705-162">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="04705-163">如先前所述，私人頻道聊天會儲存在使用者信箱中，而不是儲存在小組的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="04705-163">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="04705-164">如果您想要進一步閱讀本主題中的非Teams區域，Microsoft 365請參閱管理電子檔探索[案例：](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)保留內容位置。</span><span class="sxs-lookup"><span data-stu-id="04705-164">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
