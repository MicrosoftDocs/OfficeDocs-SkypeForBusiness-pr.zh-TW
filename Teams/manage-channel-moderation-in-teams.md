---
title: 設定及管理頻道裁決
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
description: 瞭解如何在 Microsoft 團隊中設定裁決的頻道，包括如何將團隊成員新增為頻道審查程式。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822893"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="582ef-103">在 Microsoft 團隊中設定及管理頻道裁決</span><span class="sxs-lookup"><span data-stu-id="582ef-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="582ef-104">在 Microsoft 團隊中，小組擁有者可以針對標準頻道開啟 [裁決]，以控制誰可以開始新的文章，以及如何在該頻道中回復文章。</span><span class="sxs-lookup"><span data-stu-id="582ef-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="582ef-105">小組擁有者也可以將團隊成員新增為版主。</span><span class="sxs-lookup"><span data-stu-id="582ef-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="582ef-106">小組擁有者可能不具備頻道階層的主題專業技能，以最佳支援管道裁決。</span><span class="sxs-lookup"><span data-stu-id="582ef-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="582ef-107">透過讓特定的小組成員能夠適中的頻道，在小組擁有者和管道版主之間，管理頻道內的內容與內容的責任。</span><span class="sxs-lookup"><span data-stu-id="582ef-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="582ef-108">例如，小組擁有者可以將企業擁有者或內容擁有者新增為仲裁者，讓他們控制該頻道中的資訊共用。</span><span class="sxs-lookup"><span data-stu-id="582ef-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="582ef-109">[頻道裁決] 可供標準通道使用。</span><span class="sxs-lookup"><span data-stu-id="582ef-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="582ef-110">[一般] 通道或 [私人頻道] 無法使用。</span><span class="sxs-lookup"><span data-stu-id="582ef-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="582ef-111">頻道審查者能做什麼？</span><span class="sxs-lookup"><span data-stu-id="582ef-111">What can a channel moderator do?</span></span>

<span data-ttu-id="582ef-112">頻道審查者可以：</span><span class="sxs-lookup"><span data-stu-id="582ef-112">Channel moderators can:</span></span>

- <span data-ttu-id="582ef-113">在頻道中開始新的文章。</span><span class="sxs-lookup"><span data-stu-id="582ef-113">Start new posts in the channel.</span></span> <span data-ttu-id="582ef-114">針對頻道開啟 [裁決] 時，只有版主可以在該頻道中開始新的文章。</span><span class="sxs-lookup"><span data-stu-id="582ef-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="582ef-115">新增或移除團隊成員為頻道的版主。</span><span class="sxs-lookup"><span data-stu-id="582ef-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="582ef-116">請記住，小組擁有者預設是 [頻道審查程式]，而且無法移除。</span><span class="sxs-lookup"><span data-stu-id="582ef-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="582ef-117">控制小組成員是否可以回復現有的通道訊息，以及機器人與連接器是否可以提交頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="582ef-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="582ef-118">案例</span><span class="sxs-lookup"><span data-stu-id="582ef-118">Scenarios</span></span>

<span data-ttu-id="582ef-119">以下是貴組織在團隊中使用管道裁決的一些範例。</span><span class="sxs-lookup"><span data-stu-id="582ef-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="582ef-120">使用通道做為宣告通道</span><span class="sxs-lookup"><span data-stu-id="582ef-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="582ef-121">行銷團隊使用特定的通道來共用重要的專案宣告與交付專案。</span><span class="sxs-lookup"><span data-stu-id="582ef-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="582ef-122">有時候，小組成員會將內容張貼到更適當地歸屬其他頻道的頻道。</span><span class="sxs-lookup"><span data-stu-id="582ef-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="582ef-123">小組擁有者想要將頻道中的資訊共用限制為僅限宣告，讓小組成員可以使用該通道來掌握重要的內容。</span><span class="sxs-lookup"><span data-stu-id="582ef-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="582ef-124">在這種情況下，小組擁有者會將行銷主管新增為版主，讓他們可以在頻道中張貼宣告，然後關閉小組成員回復該頻道中之訊息的功能。</span><span class="sxs-lookup"><span data-stu-id="582ef-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="582ef-125">在教育版小組中使用課程討論的頻道</span><span class="sxs-lookup"><span data-stu-id="582ef-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="582ef-126">在教育版團隊中，科學老師想要使用頻道，在特定教室主題進行重點討論。</span><span class="sxs-lookup"><span data-stu-id="582ef-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="582ef-127">在這種情況下，教師可以讓其教學助手來適中頻道。</span><span class="sxs-lookup"><span data-stu-id="582ef-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="582ef-128">[教學助手] 接著可以建立新的貼文，以啟動並將討論放在學生中。</span><span class="sxs-lookup"><span data-stu-id="582ef-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="582ef-129">管理通道裁決</span><span class="sxs-lookup"><span data-stu-id="582ef-129">Manage channel moderation</span></span>

<span data-ttu-id="582ef-130">在 [團隊] 中，移至頻道，按一下 [**更多選項]。**  > **管理頻道**。</span><span class="sxs-lookup"><span data-stu-id="582ef-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="582ef-131">您可以從這裡開啟和關閉「裁決」、將小組成員新增為仲裁者，以及設定喜好設定。</span><span class="sxs-lookup"><span data-stu-id="582ef-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="582ef-132">[頻道裁決] 是 [每個通道] 設定。</span><span class="sxs-lookup"><span data-stu-id="582ef-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="582ef-133">通道裁決沒有租使用者層級設定。</span><span class="sxs-lookup"><span data-stu-id="582ef-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="582ef-134">如果您想要我們新增租使用者層級通道裁決設定，請在 [團隊 UserVoice](https://microsoftteams.uservoice.com/)上要求它。</span><span class="sxs-lookup"><span data-stu-id="582ef-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="582ef-136">開啟或關閉頻道的裁決</span><span class="sxs-lookup"><span data-stu-id="582ef-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="582ef-137">根據預設，「裁決」是關閉的，這表示一般的頻道設定會套用至小組擁有者和小組成員。</span><span class="sxs-lookup"><span data-stu-id="582ef-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="582ef-138">例如，您可以將新的文章限制為只有小組成員，或允許每個人（包括來賓）開始新的文章。</span><span class="sxs-lookup"><span data-stu-id="582ef-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="582ef-139">若要為頻道開啟 [裁決]，請在 [ **管道裁決**] 底下，按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="582ef-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="582ef-140">當頻道裁決開啟時，只有版主可以開始新的文章。</span><span class="sxs-lookup"><span data-stu-id="582ef-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="582ef-141">新增或移除頻道版主</span><span class="sxs-lookup"><span data-stu-id="582ef-141">Add or remove channel moderators</span></span>

<span data-ttu-id="582ef-142">在 **[誰是仲裁者？**] 底下，按一下 [ **管理**]，然後將小組成員新增或移除為 [版主]。</span><span class="sxs-lookup"><span data-stu-id="582ef-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="582ef-143">小組擁有者和版主可以新增及移除其他版主。</span><span class="sxs-lookup"><span data-stu-id="582ef-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="582ef-144">設定小組成員許可權</span><span class="sxs-lookup"><span data-stu-id="582ef-144">Set team member permissions</span></span>

<span data-ttu-id="582ef-145">在 [ **小組成員許可權**] 底下，選取您要允許之活動旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="582ef-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="582ef-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="582ef-146">Related topics</span></span>

- [<span data-ttu-id="582ef-147">Teams 的小組和頻道概觀</span><span class="sxs-lookup"><span data-stu-id="582ef-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
