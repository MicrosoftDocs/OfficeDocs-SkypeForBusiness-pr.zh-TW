---
title: 管理會議原則
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 瞭解如何在團隊中管理會議原則設定。
ms.openlocfilehash: 9199be5eced7faee3e72f7b94c1f9e3be3c9573c
ms.sourcegitcommit: a47bd5194672820380d30722b60779ce2d8a8f78
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2020
ms.locfileid: "41649096"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="dfbf1-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="dfbf1-104">會議原則可用來控制會議參與者對於由您組織中的使用者排程之會議所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="dfbf1-105">建立原則並進行變更之後，您就可以將使用者指派給原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="dfbf1-106">您可以在 Microsoft 團隊系統管理中心或使用[PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="dfbf1-107">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="dfbf1-108">實現類型</span><span class="sxs-lookup"><span data-stu-id="dfbf1-108">Implementation type</span></span>  |<span data-ttu-id="dfbf1-109">描述</span><span class="sxs-lookup"><span data-stu-id="dfbf1-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="dfbf1-110">每個召集人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-110">Per-organizer</span></span>    |<span data-ttu-id="dfbf1-111">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="dfbf1-112">例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="dfbf1-113">每位使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-113">Per-user</span></span>    |<span data-ttu-id="dfbf1-114">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="dfbf1-115">例如，[**允許在頻道中立即開會**] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="dfbf1-116">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="dfbf1-117">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="dfbf1-118">例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="dfbf1-119">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="dfbf1-120">根據預設，會建立名為 [全域] （組織範圍預設值）的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="dfbf1-121">貴組織中的所有使用者預設都會獲指派 [全域會議原則]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="dfbf1-122">您可以對其進行變更或建立一或多個自訂原則，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="dfbf1-123">除非您建立並指派自訂原則，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="dfbf1-124">當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將其指派給將設定套用至其中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="dfbf1-125">變更或建立會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-125">Change or create a meeting policy</span></span>

<span data-ttu-id="dfbf1-126">若要變更或建立會議原則，請移至 Microsoft 團隊管理中心 >**會議** > **會議原則**。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-126">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="dfbf1-127">從清單中選取原則，或選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-127">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="dfbf1-128">如果您要建立新的原則，請新增名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-128">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="dfbf1-129">名稱不能包含特殊字元，或長度不能超過64個字元。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-129">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="dfbf1-130">選擇您的設定，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-130">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="dfbf1-131">例如，假設您有一組使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="dfbf1-132">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="dfbf1-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="dfbf1-133">在 [**音訊 & 影片**] 底下：</span><span class="sxs-lookup"><span data-stu-id="dfbf1-133">Under **Audio & video**:</span></span>
- <span data-ttu-id="dfbf1-134">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="dfbf1-135">關閉 [允許 IP 視頻]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="dfbf1-136">[**內容共用**] 底下：</span><span class="sxs-lookup"><span data-stu-id="dfbf1-136">Under **Content sharing**:</span></span>
- <span data-ttu-id="dfbf1-137">停用螢幕共用模式。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="dfbf1-138">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="dfbf1-139">關閉 [允許共用筆記]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="dfbf1-140">然後將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-140">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="dfbf1-141">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-141">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="dfbf1-142">指派會議原則給使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-142">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="dfbf1-143">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="dfbf1-144">按一下使用者名稱左邊的，然後按一下 [**編輯設定**]，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-144">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="dfbf1-145">在 [**會議原則**] 底下，選取您要指派的原則，然後**按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-145">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="dfbf1-146">若要一次將原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-146">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="dfbf1-147">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dfbf1-147">Or, you can also do the following:</span></span>

1. <span data-ttu-id="dfbf1-148">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議** > **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-148">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="dfbf1-149">按一下原則名稱左方，選取原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-149">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="dfbf1-150">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-150">Select **Manage users**.</span></span>
4. <span data-ttu-id="dfbf1-151">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-151">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="dfbf1-152">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-152">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="dfbf1-153">完成新增使用者之後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-153">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="dfbf1-154">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-154">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="dfbf1-155">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-155">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="dfbf1-156">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="dfbf1-156">Meeting policy settings</span></span>

<span data-ttu-id="dfbf1-157">當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增**] 以新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-157">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="dfbf1-158">一般</span><span class="sxs-lookup"><span data-stu-id="dfbf1-158">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="dfbf1-159">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="dfbf1-159">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="dfbf1-160">內容共用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-160">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="dfbf1-161">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="dfbf1-161">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="dfbf1-162"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="dfbf1-162"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="dfbf1-163">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="dfbf1-163">Meeting policy settings - General</span></span>

- <span data-ttu-id="dfbf1-164">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="dfbf1-164">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="dfbf1-165">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="dfbf1-165">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="dfbf1-166">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="dfbf1-166">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="dfbf1-167">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="dfbf1-167">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="dfbf1-168">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="dfbf1-168">Allow Meet now in channels</span></span>

<span data-ttu-id="dfbf1-169">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-169">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dfbf1-170">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-170">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="dfbf1-171">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-171">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="dfbf1-173">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="dfbf1-173">Allow the Outlook add-in</span></span>

<span data-ttu-id="dfbf1-174">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dfbf1-175">此設定控制團隊會議是否可在 Outlook 中排程（Windows、Mac、web 及行動裝置）。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-175">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="dfbf1-177">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-177">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="dfbf1-178">例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-178">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="dfbf1-179">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="dfbf1-179">Allow channel meeting scheduling</span></span>

<span data-ttu-id="dfbf1-180">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-180">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dfbf1-181">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-181">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="dfbf1-182">如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-182">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="dfbf1-185">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="dfbf1-185">Allow scheduling private meetings</span></span>

<span data-ttu-id="dfbf1-186">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-186">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dfbf1-187">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-187">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="dfbf1-188">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-188">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="dfbf1-189">請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-189">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="dfbf1-190"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="dfbf1-190"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="dfbf1-191">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="dfbf1-191">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="dfbf1-192">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="dfbf1-192">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="dfbf1-193">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="dfbf1-193">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="dfbf1-194">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="dfbf1-194">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="dfbf1-195">媒體位元速率（KBs）</span><span class="sxs-lookup"><span data-stu-id="dfbf1-195">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="dfbf1-196">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="dfbf1-196">Allow transcription</span></span>

<span data-ttu-id="dfbf1-197">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-197">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dfbf1-198">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-198">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="dfbf1-199">如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-199">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="dfbf1-200">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-200">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="dfbf1-201">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-201">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="dfbf1-203">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="dfbf1-203">Allow cloud recording</span></span>

<span data-ttu-id="dfbf1-204">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-204">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dfbf1-205">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-205">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="dfbf1-206">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-206">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="dfbf1-207">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-207">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="dfbf1-208">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-208">Guest users can't start or stop the recording.</span></span> 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="dfbf1-210">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-210">Let's look at the following example.</span></span>

|<span data-ttu-id="dfbf1-211">使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-211">User</span></span> |<span data-ttu-id="dfbf1-212">會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-212">Meeting policy</span></span>  |<span data-ttu-id="dfbf1-213">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="dfbf1-213">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-214">Daniela</span><span class="sxs-lookup"><span data-stu-id="dfbf1-214">Daniela</span></span> | <span data-ttu-id="dfbf1-215">全域</span><span class="sxs-lookup"><span data-stu-id="dfbf1-215">Global</span></span>   | <span data-ttu-id="dfbf1-216">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-216">False</span></span> |
|<span data-ttu-id="dfbf1-217">Amanda</span><span class="sxs-lookup"><span data-stu-id="dfbf1-217">Amanda</span></span> | <span data-ttu-id="dfbf1-218">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dfbf1-218">Location1MeetingPolicy</span></span> | <span data-ttu-id="dfbf1-219">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-219">True</span></span>|
|<span data-ttu-id="dfbf1-220">約翰（外部使用者）</span><span class="sxs-lookup"><span data-stu-id="dfbf1-220">John (external user)</span></span> | <span data-ttu-id="dfbf1-221">不適用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-221">Not applicable</span></span> | <span data-ttu-id="dfbf1-222">不適用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-222">Not applicable</span></span>|

<span data-ttu-id="dfbf1-223">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-223">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="dfbf1-224">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-224">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="dfbf1-225">若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-225">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="dfbf1-226">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="dfbf1-226">Allow IP video</span></span>

<span data-ttu-id="dfbf1-227">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-227">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dfbf1-228">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-228">Video is a key component to meetings.</span></span> <span data-ttu-id="dfbf1-229">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-229">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="dfbf1-230">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-230">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="dfbf1-231">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-231">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="dfbf1-232">沒有指派任何原則的會議參與者（例如匿名及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-232">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="dfbf1-234">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-234">Let's look at the following example.</span></span>

|<span data-ttu-id="dfbf1-235">使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-235">User</span></span> |<span data-ttu-id="dfbf1-236">會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-236">Meeting policy</span></span>  |<span data-ttu-id="dfbf1-237">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="dfbf1-237">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-238">Daniela</span><span class="sxs-lookup"><span data-stu-id="dfbf1-238">Daniela</span></span>   | <span data-ttu-id="dfbf1-239">全域</span><span class="sxs-lookup"><span data-stu-id="dfbf1-239">Global</span></span>   | <span data-ttu-id="dfbf1-240">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-240">True</span></span>        |
|<span data-ttu-id="dfbf1-241">Amanda</span><span class="sxs-lookup"><span data-stu-id="dfbf1-241">Amanda</span></span>    | <span data-ttu-id="dfbf1-242">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dfbf1-242">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dfbf1-243">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-243">False</span></span>      |

<span data-ttu-id="dfbf1-244">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-244">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="dfbf1-245">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-245">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="dfbf1-246">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-246">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="dfbf1-247">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-247">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="dfbf1-248">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-248">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="dfbf1-249">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-249">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="dfbf1-250">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-250">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="dfbf1-251">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-251">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="dfbf1-252">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-252">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="dfbf1-253">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-253">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="dfbf1-254">媒體位元速率（KBs）</span><span class="sxs-lookup"><span data-stu-id="dfbf1-254">Media bit rate (KBs)</span></span>

<span data-ttu-id="dfbf1-255">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-255">This is a per-user policy.</span></span> <span data-ttu-id="dfbf1-256">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-256">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="dfbf1-257">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-257">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="dfbf1-258">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-258">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="dfbf1-259">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-259">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="dfbf1-260">最小值為 30 Kbps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-260">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="dfbf1-261">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-261">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="dfbf1-262">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-262">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="dfbf1-263">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-263">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="dfbf1-264">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-264">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="dfbf1-265">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-265">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="dfbf1-266">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="dfbf1-266">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="dfbf1-267">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="dfbf1-267">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="dfbf1-268">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="dfbf1-268">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="dfbf1-269">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-269">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="dfbf1-270">允許白板</span><span class="sxs-lookup"><span data-stu-id="dfbf1-270">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="dfbf1-271">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="dfbf1-271">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="dfbf1-272">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="dfbf1-272">Screen sharing mode</span></span>

<span data-ttu-id="dfbf1-273">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-273">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dfbf1-274">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-274">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="dfbf1-275">沒有指派任何原則的會議參與者（例如，匿名、來賓、B2B 及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-275">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="dfbf1-276">設定值</span><span class="sxs-lookup"><span data-stu-id="dfbf1-276">Setting value</span></span> |<span data-ttu-id="dfbf1-277">行為</span><span class="sxs-lookup"><span data-stu-id="dfbf1-277">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="dfbf1-278">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-278">**Entire screen**</span></span>    | <span data-ttu-id="dfbf1-279">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-279">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="dfbf1-280">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-280">**Single application**</span></span>   | <span data-ttu-id="dfbf1-281">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="dfbf1-281">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="dfbf1-282">**禁止**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-282">**Disabled**</span></span>     |<span data-ttu-id="dfbf1-283">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-283">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="dfbf1-284">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-284">Let's look at the following example.</span></span>

|<span data-ttu-id="dfbf1-285">使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-285">User</span></span> |<span data-ttu-id="dfbf1-286">會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-286">Meeting policy</span></span> |<span data-ttu-id="dfbf1-287">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="dfbf1-287">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-288">Daniela</span><span class="sxs-lookup"><span data-stu-id="dfbf1-288">Daniela</span></span>  | <span data-ttu-id="dfbf1-289">全域</span><span class="sxs-lookup"><span data-stu-id="dfbf1-289">Global</span></span>   | <span data-ttu-id="dfbf1-290">整個畫面</span><span class="sxs-lookup"><span data-stu-id="dfbf1-290">Entire screen</span></span> |
|<span data-ttu-id="dfbf1-291">Amanda</span><span class="sxs-lookup"><span data-stu-id="dfbf1-291">Amanda</span></span>   | <span data-ttu-id="dfbf1-292">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dfbf1-292">Location1MeetingPolicy</span></span>  | <span data-ttu-id="dfbf1-293">禁止</span><span class="sxs-lookup"><span data-stu-id="dfbf1-293">Disabled</span></span> |

<span data-ttu-id="dfbf1-294">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-294">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="dfbf1-295">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-295">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="dfbf1-296">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-296">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="dfbf1-297">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-297">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="dfbf1-298">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-298">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="dfbf1-299">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="dfbf1-299">Allow a participant to give or request control</span></span>

<span data-ttu-id="dfbf1-300">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-300">This is a per-user policy.</span></span> <span data-ttu-id="dfbf1-301">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-301">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="dfbf1-302">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-302">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="dfbf1-303">如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-303">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="dfbf1-305">如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-305">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="dfbf1-307">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-307">Let's look at the following example.</span></span>

|<span data-ttu-id="dfbf1-308">使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-308">User</span></span> |<span data-ttu-id="dfbf1-309">會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-309">Meeting policy</span></span>  |<span data-ttu-id="dfbf1-310">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="dfbf1-310">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-311">Daniela</span><span class="sxs-lookup"><span data-stu-id="dfbf1-311">Daniela</span></span>   | <span data-ttu-id="dfbf1-312">全域</span><span class="sxs-lookup"><span data-stu-id="dfbf1-312">Global</span></span>   | <span data-ttu-id="dfbf1-313">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-313">True</span></span>       |
|<span data-ttu-id="dfbf1-314">Babek</span><span class="sxs-lookup"><span data-stu-id="dfbf1-314">Babek</span></span>    | <span data-ttu-id="dfbf1-315">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dfbf1-315">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dfbf1-316">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-316">False</span></span>   |

<span data-ttu-id="dfbf1-317">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-317">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="dfbf1-318">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-318">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="dfbf1-319">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-319">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="dfbf1-320">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-320">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="dfbf1-321">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-321">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="dfbf1-322">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="dfbf1-322">Allow an external participant to give or request control</span></span>

<span data-ttu-id="dfbf1-323">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-323">This is a per-user policy.</span></span> <span data-ttu-id="dfbf1-324">此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-324">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="dfbf1-325">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="dfbf1-325">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="dfbf1-326">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-326">Anonymous user</span></span>
- <span data-ttu-id="dfbf1-327">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-327">Guest users</span></span>  
- <span data-ttu-id="dfbf1-328">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-328">B2B user</span></span>
- <span data-ttu-id="dfbf1-329">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-329">Federated user</span></span>  

<span data-ttu-id="dfbf1-330">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-330">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="dfbf1-331">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-331">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="dfbf1-332">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-332">Allow PowerPoint sharing</span></span>

<span data-ttu-id="dfbf1-333">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-333">This is a per-user policy.</span></span> <span data-ttu-id="dfbf1-334">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-334">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="dfbf1-335">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-335">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="dfbf1-336">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-336">Let's look at the following example.</span></span>

|<span data-ttu-id="dfbf1-337">使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-337">User</span></span> |<span data-ttu-id="dfbf1-338">會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-338">Meeting policy</span></span>  |<span data-ttu-id="dfbf1-339">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="dfbf1-339">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-340">Daniela</span><span class="sxs-lookup"><span data-stu-id="dfbf1-340">Daniela</span></span>   | <span data-ttu-id="dfbf1-341">全域</span><span class="sxs-lookup"><span data-stu-id="dfbf1-341">Global</span></span>   | <span data-ttu-id="dfbf1-342">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-342">True</span></span>       |
|<span data-ttu-id="dfbf1-343">Amanda</span><span class="sxs-lookup"><span data-stu-id="dfbf1-343">Amanda</span></span>   | <span data-ttu-id="dfbf1-344">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dfbf1-344">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dfbf1-345">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-345">False</span></span>   |

<span data-ttu-id="dfbf1-346">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-346">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="dfbf1-347">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-347">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="dfbf1-348">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-348">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="dfbf1-349">允許白板</span><span class="sxs-lookup"><span data-stu-id="dfbf1-349">Allow whiteboard</span></span>

<span data-ttu-id="dfbf1-350">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-350">This is a per-user policy.</span></span> <span data-ttu-id="dfbf1-351">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-351">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="dfbf1-352">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-352">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="dfbf1-353">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-353">Let's look at the following example.</span></span>

|<span data-ttu-id="dfbf1-354">使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-354">User</span></span> |<span data-ttu-id="dfbf1-355">會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-355">Meeting policy</span></span>  |<span data-ttu-id="dfbf1-356">允許白板</span><span class="sxs-lookup"><span data-stu-id="dfbf1-356">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="dfbf1-357">Daniela</span><span class="sxs-lookup"><span data-stu-id="dfbf1-357">Daniela</span></span>   | <span data-ttu-id="dfbf1-358">全域</span><span class="sxs-lookup"><span data-stu-id="dfbf1-358">Global</span></span>   | <span data-ttu-id="dfbf1-359">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-359">True</span></span>       |
|<span data-ttu-id="dfbf1-360">Amanda</span><span class="sxs-lookup"><span data-stu-id="dfbf1-360">Amanda</span></span>   | <span data-ttu-id="dfbf1-361">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dfbf1-361">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dfbf1-362">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-362">False</span></span>   |

<span data-ttu-id="dfbf1-363">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-363">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="dfbf1-364">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-364">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="dfbf1-365">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="dfbf1-365">Allow shared notes</span></span>

<span data-ttu-id="dfbf1-366">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-366">This is a per-user policy.</span></span> <span data-ttu-id="dfbf1-367">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-367">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="dfbf1-368">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-368">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="dfbf1-369">目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-369">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="dfbf1-370">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-370">Let's look at the following example.</span></span>

|<span data-ttu-id="dfbf1-371">使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf1-371">User</span></span> |<span data-ttu-id="dfbf1-372">會議原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-372">Meeting policy</span></span>  |<span data-ttu-id="dfbf1-373">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="dfbf1-373">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-374">Daniela</span><span class="sxs-lookup"><span data-stu-id="dfbf1-374">Daniela</span></span>   | <span data-ttu-id="dfbf1-375">全域</span><span class="sxs-lookup"><span data-stu-id="dfbf1-375">Global</span></span>   | <span data-ttu-id="dfbf1-376">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-376">True</span></span>       |
|<span data-ttu-id="dfbf1-377">Amanda</span><span class="sxs-lookup"><span data-stu-id="dfbf1-377">Amanda</span></span>   | <span data-ttu-id="dfbf1-378">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dfbf1-378">Location1MeetingPolicy</span></span> | <span data-ttu-id="dfbf1-379">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-379">False</span></span> |

<span data-ttu-id="dfbf1-380">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-380">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="dfbf1-381">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="dfbf1-381">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="dfbf1-382">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-382">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="dfbf1-383">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="dfbf1-383">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="dfbf1-384">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-384">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="dfbf1-385">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="dfbf1-385">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="dfbf1-386">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="dfbf1-386">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="dfbf1-387">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="dfbf1-387">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="dfbf1-388">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="dfbf1-388">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="dfbf1-389">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-389">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="dfbf1-390">如果您的群組有音訊會議，且使用它來連接，請參閱[Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-390">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="dfbf1-391">如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-391">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="dfbf1-392">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="dfbf1-392">Let anonymous people start a meeting</span></span>

<span data-ttu-id="dfbf1-393">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-393">This is a per-organizer policy.</span></span> <span data-ttu-id="dfbf1-394">此設定會控制匿名人員（包括 B2B）與同盟使用者，是否可在沒有已驗證的使用者的情況下，從出席中的組織加入使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-394">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![螢幕擷取畫面顯示等候使用者的訊息](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="dfbf1-396">以下是在會議中有驗證使用者的情況下匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-396">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="dfbf1-397">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="dfbf1-397">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="dfbf1-398">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-398">Automatically admit people</span></span> |<span data-ttu-id="dfbf1-399">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="dfbf1-399">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-400">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-400">True</span></span>    | <span data-ttu-id="dfbf1-401">人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-401">Everyone</span></span>      | <span data-ttu-id="dfbf1-402">直接加入</span><span class="sxs-lookup"><span data-stu-id="dfbf1-402">Join directly</span></span>         |
|   | <span data-ttu-id="dfbf1-403">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-403">Everyone in your organization</span></span>       | <span data-ttu-id="dfbf1-404">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-404">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dfbf1-405">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-405">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dfbf1-406">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-406">Wait in lobby</span></span>         |
|<span data-ttu-id="dfbf1-407">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-407">False</span></span>    | <span data-ttu-id="dfbf1-408">人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-408">Everyone</span></span>        | <span data-ttu-id="dfbf1-409">直接加入</span><span class="sxs-lookup"><span data-stu-id="dfbf1-409">Join directly</span></span>        |
|   | <span data-ttu-id="dfbf1-410">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-410">Everyone in your organization</span></span>     | <span data-ttu-id="dfbf1-411">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-411">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dfbf1-412">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-412">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dfbf1-413">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-413">Wait in lobby</span></span>         |

<span data-ttu-id="dfbf1-414">以下是在會議中沒有經過驗證的使用者時，匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-414">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="dfbf1-415">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="dfbf1-415">Let anonymous people start a meeting</span></span> |<span data-ttu-id="dfbf1-416">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-416">Automatically admit people</span></span>  |<span data-ttu-id="dfbf1-417">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="dfbf1-417">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-418">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-418">True</span></span>    | <span data-ttu-id="dfbf1-419">人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-419">Everyone</span></span>      | <span data-ttu-id="dfbf1-420">直接加入</span><span class="sxs-lookup"><span data-stu-id="dfbf1-420">Join directly</span></span>         |
|   | <span data-ttu-id="dfbf1-421">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-421">Everyone in your organization</span></span>       | <span data-ttu-id="dfbf1-422">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-422">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dfbf1-423">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-423">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dfbf1-424">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-424">Wait in lobby</span></span>         |
|<span data-ttu-id="dfbf1-425">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-425">False</span></span>    | <span data-ttu-id="dfbf1-426">人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-426">Everyone</span></span>        | <span data-ttu-id="dfbf1-427">在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-427">Wait in lobby.</span></span> <span data-ttu-id="dfbf1-428">當第一個經過驗證的使用者加入會議時，系統會自動准許使用者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-428">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="dfbf1-429">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-429">Everyone in your organization</span></span>     |<span data-ttu-id="dfbf1-430">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-430">Wait in lobby</span></span>         |
|   | <span data-ttu-id="dfbf1-431">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-431">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dfbf1-432">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-432">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="dfbf1-433">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-433">Automatically admit people</span></span>

<span data-ttu-id="dfbf1-434">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-434">This is a per-organizer policy.</span></span> <span data-ttu-id="dfbf1-435">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-435">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="dfbf1-437">會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-437">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="dfbf1-438">**（即將推出）**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-438">**(coming soon)**</span></span>
  
|<span data-ttu-id="dfbf1-439">設定值</span><span class="sxs-lookup"><span data-stu-id="dfbf1-439">Setting value</span></span>  |<span data-ttu-id="dfbf1-440">加入行為</span><span class="sxs-lookup"><span data-stu-id="dfbf1-440">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="dfbf1-441">**人員**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-441">**Everyone**</span></span>   |<span data-ttu-id="dfbf1-442">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-442">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="dfbf1-443">這包括經過驗證的使用者、聯盟使用者、來賓、匿名使用者，以及透過電話撥入的人員。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-443">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="dfbf1-444">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-444">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="dfbf1-445">組織內經過驗證的使用者，包括來賓使用者以及來自同盟組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-445">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="dfbf1-446">在大廳由手機撥入的匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-446">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="dfbf1-447">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-447">**Everyone in your organization**</span></span>    |<span data-ttu-id="dfbf1-448">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-448">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="dfbf1-449">在大廳以電話撥入的聯盟使用者、匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-449">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="dfbf1-450">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="dfbf1-450">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="dfbf1-451">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-451">This is a per-organizer policy.</span></span> <span data-ttu-id="dfbf1-452">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-452">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="dfbf1-453">以下是透過電話撥入的人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-453">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="dfbf1-454">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="dfbf1-454">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="dfbf1-455">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-455">Automatically admit people</span></span>  |<span data-ttu-id="dfbf1-456">撥入之人的加入行為</span><span class="sxs-lookup"><span data-stu-id="dfbf1-456">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dfbf1-457">滿足</span><span class="sxs-lookup"><span data-stu-id="dfbf1-457">True</span></span>    | <span data-ttu-id="dfbf1-458">人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-458">Everyone</span></span>      | <span data-ttu-id="dfbf1-459">直接加入</span><span class="sxs-lookup"><span data-stu-id="dfbf1-459">Join directly</span></span>         |
|   | <span data-ttu-id="dfbf1-460">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-460">Everyone in your organization</span></span>       | <span data-ttu-id="dfbf1-461">直接加入</span><span class="sxs-lookup"><span data-stu-id="dfbf1-461">Join directly</span></span>        |
|   | <span data-ttu-id="dfbf1-462">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-462">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dfbf1-463">直接加入</span><span class="sxs-lookup"><span data-stu-id="dfbf1-463">Join directly</span></span>         |
|<span data-ttu-id="dfbf1-464">虛假</span><span class="sxs-lookup"><span data-stu-id="dfbf1-464">False</span></span>    | <span data-ttu-id="dfbf1-465">人員</span><span class="sxs-lookup"><span data-stu-id="dfbf1-465">Everyone</span></span>        | <span data-ttu-id="dfbf1-466">直接加入</span><span class="sxs-lookup"><span data-stu-id="dfbf1-466">Join directly</span></span>        |
|   | <span data-ttu-id="dfbf1-467">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-467">Everyone in your organization</span></span>     |<span data-ttu-id="dfbf1-468">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-468">Wait in lobby</span></span>         |
|   | <span data-ttu-id="dfbf1-469">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="dfbf1-469">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dfbf1-470">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="dfbf1-470">Wait in lobby</span></span>         |

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="dfbf1-471">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="dfbf1-471">Allow Meet now in private meetings</span></span>

<span data-ttu-id="dfbf1-472">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-472">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dfbf1-473">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-473">This setting controls whether a user can start an ad hoc private meeting.</span></span> 

### <a name="enable-live-captions"></a><span data-ttu-id="dfbf1-474">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="dfbf1-474">Enable live captions</span></span>

<span data-ttu-id="dfbf1-475">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-475">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="dfbf1-476">此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-476">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="dfbf1-478">設定值</span><span class="sxs-lookup"><span data-stu-id="dfbf1-478">Setting value</span></span> |<span data-ttu-id="dfbf1-479">行為</span><span class="sxs-lookup"><span data-stu-id="dfbf1-479">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="dfbf1-480">**已停用，但召集人可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-480">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="dfbf1-481">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-481">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="dfbf1-482">使用者會看到 [溢出（**...**）] 功能表中的 [**開啟即時標題**] 選項，以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-482">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="dfbf1-483">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-483">This is the default setting.</span></span> |
|<span data-ttu-id="dfbf1-484">**禁止**</span><span class="sxs-lookup"><span data-stu-id="dfbf1-484">**Disabled**</span></span>     | <span data-ttu-id="dfbf1-485">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-485">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="dfbf1-486">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-486">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="dfbf1-487"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="dfbf1-487"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="dfbf1-488">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="dfbf1-488">Allow chat in meetings</span></span>

<span data-ttu-id="dfbf1-489">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-489">This is a per-organizer policy.</span></span> <span data-ttu-id="dfbf1-490">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="dfbf1-490">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="dfbf1-491"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="dfbf1-491"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="dfbf1-492">相關主題</span><span class="sxs-lookup"><span data-stu-id="dfbf1-492">Related topics</span></span>

[<span data-ttu-id="dfbf1-493">小組中的訊息原則</span><span class="sxs-lookup"><span data-stu-id="dfbf1-493">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
