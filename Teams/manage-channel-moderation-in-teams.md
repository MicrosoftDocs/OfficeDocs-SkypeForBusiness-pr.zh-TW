---
title: 設定及管理頻道模式
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在頻道中設定仲裁Microsoft Teams，包括如何將小組成員新增為頻道仲裁者。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 81e5159cf0e64a4c5b88afea51de528c299daf80
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948639"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="699a7-103">在頻道中設定及管理頻道Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="699a7-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="699a7-104">在 Microsoft Teams中，團隊擁有者可以開啟標準頻道的審核，以控制誰可以開始新文章，以及回復該頻道中的文章。</span><span class="sxs-lookup"><span data-stu-id="699a7-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="699a7-105">團隊擁有者也可以將小組成員新增為仲裁者。</span><span class="sxs-lookup"><span data-stu-id="699a7-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="699a7-106">團隊擁有者可能沒有頻道層級的主題專業知識，因此無法提供最佳支援通道管理。</span><span class="sxs-lookup"><span data-stu-id="699a7-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="699a7-107">允許特定小組成員管理頻道，讓團隊擁有者和頻道仲裁者分擔管理頻道內內容和內容的責任。</span><span class="sxs-lookup"><span data-stu-id="699a7-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="699a7-108">例如，團隊擁有者可以將企業擁有者或內容擁有者新增為仲裁者，讓他們控制該頻道的資訊共用。</span><span class="sxs-lookup"><span data-stu-id="699a7-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="699a7-109">頻道模式適用于標準頻道。</span><span class="sxs-lookup"><span data-stu-id="699a7-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="699a7-110">不適用於一般頻道或私人頻道。</span><span class="sxs-lookup"><span data-stu-id="699a7-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="699a7-111">頻道仲裁者可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="699a7-111">What can a channel moderator do?</span></span>

<span data-ttu-id="699a7-112">頻道仲裁者可以：</span><span class="sxs-lookup"><span data-stu-id="699a7-112">Channel moderators can:</span></span>

- <span data-ttu-id="699a7-113">在頻道中開始新文章。</span><span class="sxs-lookup"><span data-stu-id="699a7-113">Start new posts in the channel.</span></span> <span data-ttu-id="699a7-114">當頻道開啟仲裁時，只有仲裁者可以在該頻道中開始新貼文。</span><span class="sxs-lookup"><span data-stu-id="699a7-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="699a7-115">將小組成員新增並移除為仲裁者至頻道。</span><span class="sxs-lookup"><span data-stu-id="699a7-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="699a7-116">請記住，根據預設，團隊擁有者是頻道仲裁者，無法移除。</span><span class="sxs-lookup"><span data-stu-id="699a7-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="699a7-117">控制小組成員是否可以回復現有的頻道訊息，以及 Bot 和連接器是否可以提交頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="699a7-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="699a7-118">案例</span><span class="sxs-lookup"><span data-stu-id="699a7-118">Scenarios</span></span>

<span data-ttu-id="699a7-119">以下範例說明貴組織如何在 Teams。</span><span class="sxs-lookup"><span data-stu-id="699a7-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="699a7-120">使用頻道做為公告頻道</span><span class="sxs-lookup"><span data-stu-id="699a7-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="699a7-121">行銷小組使用特定頻道來共用重要的專案公告和交付專案。</span><span class="sxs-lookup"><span data-stu-id="699a7-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="699a7-122">有時候小組成員會張貼內容至其他頻道中較適當的頻道。</span><span class="sxs-lookup"><span data-stu-id="699a7-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="699a7-123">團隊擁有者想要將頻道中的資訊共用限制為只有公告，讓小組成員可以使用該頻道，隨時瞭解重要內容。</span><span class="sxs-lookup"><span data-stu-id="699a7-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="699a7-124">在此情境中，團隊擁有者會將行銷潛在客戶新增為仲裁者，這樣他們就可以在頻道中張貼公告，並關閉小組成員回復該頻道中的訊息的能力。</span><span class="sxs-lookup"><span data-stu-id="699a7-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="699a7-125">在教育用頻道中Teams討論</span><span class="sxs-lookup"><span data-stu-id="699a7-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="699a7-126">在 Teams教育課程中，科學教師想要使用頻道讓學生參與特定課堂主題的專注討論。</span><span class="sxs-lookup"><span data-stu-id="699a7-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="699a7-127">在此情境中，教師允許其教學助理管理頻道。</span><span class="sxs-lookup"><span data-stu-id="699a7-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="699a7-128">然後，教學小幫手可以建立新文章，以啟動和推動與學生討論。</span><span class="sxs-lookup"><span data-stu-id="699a7-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="699a7-129">管理頻道模式</span><span class="sxs-lookup"><span data-stu-id="699a7-129">Manage channel moderation</span></span>

<span data-ttu-id="699a7-130">在 Teams中，前往頻道，按一下 [**更多選項...**  > **管理頻道**。</span><span class="sxs-lookup"><span data-stu-id="699a7-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="699a7-131">您可以在這裡開啟並關閉仲裁、將小組成員新增為仲裁者，以及設定喜好設定。</span><span class="sxs-lookup"><span data-stu-id="699a7-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="699a7-132">通道模式是每個頻道的設定。</span><span class="sxs-lookup"><span data-stu-id="699a7-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="699a7-133">頻道模式沒有租使用者層級設定。</span><span class="sxs-lookup"><span data-stu-id="699a7-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="699a7-134">如果您想要我們新增租使用者層級通道管理設定，請于[UserVoice](https://microsoftteams.uservoice.com/)Teams要求。</span><span class="sxs-lookup"><span data-stu-id="699a7-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![管理 -channel-moderation-in-teams 的喜好設定](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="699a7-136">開啟或關閉頻道的頻道模式</span><span class="sxs-lookup"><span data-stu-id="699a7-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="699a7-137">根據預設，模式設定為關閉，這表示一般頻道設定會適用于團隊擁有者和小組成員。</span><span class="sxs-lookup"><span data-stu-id="699a7-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="699a7-138">例如，您可以將新文章限制為只有小組成員，或允許每個人 ，包括來賓，開始新文章。</span><span class="sxs-lookup"><span data-stu-id="699a7-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="699a7-139">若要開啟頻道的 [模式模式」，請在 [ **頻道模式** 模式> 下，按一下 **[開啟**。</span><span class="sxs-lookup"><span data-stu-id="699a7-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="699a7-140">頻道仲裁為啟用時，只有仲裁者可以開始新的文章。</span><span class="sxs-lookup"><span data-stu-id="699a7-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="699a7-141">新增或移除頻道仲裁者</span><span class="sxs-lookup"><span data-stu-id="699a7-141">Add or remove channel moderators</span></span>

<span data-ttu-id="699a7-142">在 [神秘是仲裁者 **嗎？** 下，按一下 [管理」，然後新增或移除小組成員做為仲裁者。</span><span class="sxs-lookup"><span data-stu-id="699a7-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="699a7-143">團隊擁有者和仲裁者可以新增和移除其他仲裁者。</span><span class="sxs-lookup"><span data-stu-id="699a7-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="699a7-144">設定團隊成員許可權</span><span class="sxs-lookup"><span data-stu-id="699a7-144">Set team member permissions</span></span>

<span data-ttu-id="699a7-145">在 **團隊成員許可權下**，選取您想要允許的活動旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="699a7-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="699a7-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="699a7-146">Related topics</span></span>

- [<span data-ttu-id="699a7-147">Teams 的小組和頻道概觀</span><span class="sxs-lookup"><span data-stu-id="699a7-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
