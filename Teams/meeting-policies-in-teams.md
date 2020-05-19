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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 瞭解如何在團隊中管理會議原則設定，並使用他們來控制會議參與者針對使用者排程會議所提供的功能。
ms.openlocfilehash: 2b7579b9dfe1d70c0a570d6ca519491a263e9f09
ms.sourcegitcommit: 5a88788bd0a0b2ccbc5b977b38dcfe4681cd5d10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/18/2020
ms.locfileid: "44278196"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="84135-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="84135-104">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="84135-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="84135-105">建立原則並進行變更之後，您可以將使用者指派給該原則。</span><span class="sxs-lookup"><span data-stu-id="84135-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="84135-106">您可以在 Microsoft 團隊系統管理中心或使用[PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="84135-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="84135-107">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="84135-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="84135-108">實現類型</span><span class="sxs-lookup"><span data-stu-id="84135-108">Implementation type</span></span>  |<span data-ttu-id="84135-109">描述</span><span class="sxs-lookup"><span data-stu-id="84135-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="84135-110">每個召集人</span><span class="sxs-lookup"><span data-stu-id="84135-110">Per-organizer</span></span>    |<span data-ttu-id="84135-111">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="84135-112">例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="84135-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="84135-113">每位使用者</span><span class="sxs-lookup"><span data-stu-id="84135-113">Per-user</span></span>    |<span data-ttu-id="84135-114">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="84135-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="84135-115">例如，[**允許在頻道中立即開會**] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="84135-116">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="84135-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="84135-117">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="84135-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="84135-118">例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="84135-119">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="84135-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="84135-120">根據預設，會建立名為 [全域] （組織範圍預設值）的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="84135-121">貴組織中的所有使用者預設都會獲指派 [全域會議原則]。</span><span class="sxs-lookup"><span data-stu-id="84135-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="84135-122">您可以對其進行變更或建立一或多個自訂原則，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="84135-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="84135-123">除非您建立並指派自訂原則，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="84135-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="84135-124">當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將其指派給將設定套用至其中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

> [!NOTE]
> <span data-ttu-id="84135-125">如果使用者已啟用音訊會議授權，或使用者允許音訊會議，則 [會議詳細資料] 按鈕就會提供，會議詳細資料將無法使用。</span><span class="sxs-lookup"><span data-stu-id="84135-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="84135-126">變更或建立會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-126">Change or create a meeting policy</span></span>

<span data-ttu-id="84135-127">若要變更或建立會議原則，請移至 [Microsoft Teams 系統管理中心] > **[會議] \*\* > \*\* [會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="84135-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="84135-128">從清單中選取原則，或選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="84135-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="84135-129">如果您要建立新原則，請新增原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="84135-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="84135-130">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="84135-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="84135-131">選擇您的設定，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="84135-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="84135-132">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="84135-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="84135-133">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="84135-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="84135-134">在 [音訊與視訊]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="84135-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="84135-135">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="84135-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="84135-136">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="84135-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="84135-137">在 [內容共用]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="84135-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="84135-138">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="84135-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="84135-139">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="84135-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="84135-140">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="84135-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="84135-141">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="84135-142">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="84135-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="84135-143">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="84135-143">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="84135-144">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="84135-145">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84135-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="84135-146">在 [會議原則]\*\*\*\* 下，選取要指派的原則，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84135-146">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="84135-147">若要一次將原則指派給多個使用者，請參閱[大量編輯 Teams 使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="84135-147">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="84135-148">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="84135-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="84135-149">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="84135-149">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="84135-150">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="84135-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="84135-151">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84135-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="84135-152">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="84135-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="84135-153">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="84135-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="84135-154">完成新增使用者之後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="84135-154">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="84135-155">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="84135-155">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="84135-156">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="84135-156">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="84135-157">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="84135-157">Meeting policy settings</span></span>

<span data-ttu-id="84135-158">當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增**] 以新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="84135-158">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="84135-159">一般</span><span class="sxs-lookup"><span data-stu-id="84135-159">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="84135-160">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="84135-160">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="84135-161">內容共用</span><span class="sxs-lookup"><span data-stu-id="84135-161">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="84135-162">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="84135-162">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="84135-163"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="84135-163"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="84135-164">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="84135-164">Meeting policy settings - General</span></span>

- <span data-ttu-id="84135-165">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="84135-165">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="84135-166">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="84135-166">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="84135-167">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="84135-167">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="84135-168">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="84135-168">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="84135-169">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="84135-169">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="84135-170">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="84135-170">Allow Meet now in channels</span></span>

<span data-ttu-id="84135-171">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="84135-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="84135-172">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="84135-172">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="84135-173">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="84135-173">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="84135-174">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="84135-174">The default value is True.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="84135-176">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="84135-176">Allow the Outlook add-in</span></span>

<span data-ttu-id="84135-177">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="84135-177">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="84135-178">此設定控制團隊會議是否可在 Outlook 中排程（Windows、Mac、web 及行動裝置）。</span><span class="sxs-lookup"><span data-stu-id="84135-178">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="84135-180">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="84135-180">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="84135-181">例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="84135-181">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="84135-182">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="84135-182">Allow channel meeting scheduling</span></span>

<span data-ttu-id="84135-183">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="84135-183">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="84135-184">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="84135-184">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="84135-185">如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。</span><span class="sxs-lookup"><span data-stu-id="84135-185">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="84135-186">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="84135-186">The default value is True.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="84135-189">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="84135-189">Allow scheduling private meetings</span></span>

<span data-ttu-id="84135-190">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="84135-190">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="84135-191">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="84135-191">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="84135-192">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="84135-192">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="84135-193">請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。</span><span class="sxs-lookup"><span data-stu-id="84135-193">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="84135-194">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="84135-194">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="84135-195">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="84135-195">Allow Meet now in private meetings</span></span>

<span data-ttu-id="84135-196">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="84135-196">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="84135-197">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="84135-197">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="84135-198">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="84135-198">The default value is True.</span></span>

<span data-ttu-id="84135-199"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="84135-199"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="84135-200">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="84135-200">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="84135-201">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="84135-201">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="84135-202">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="84135-202">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="84135-203">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="84135-203">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="84135-204">媒體位元速率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="84135-204">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="84135-205">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="84135-205">Allow transcription</span></span>

<span data-ttu-id="84135-206">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="84135-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="84135-207">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="84135-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="84135-208">如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="84135-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="84135-209">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="84135-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="84135-210">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="84135-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="84135-212">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="84135-212">Allow cloud recording</span></span>

<span data-ttu-id="84135-213">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="84135-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="84135-214">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="84135-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="84135-215">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="84135-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="84135-216">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="84135-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="84135-217">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="84135-217">Guest users can't start or stop the recording.</span></span> 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="84135-219">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="84135-219">Let's look at the following example.</span></span>

|<span data-ttu-id="84135-220">使用者</span><span class="sxs-lookup"><span data-stu-id="84135-220">User</span></span> |<span data-ttu-id="84135-221">會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-221">Meeting policy</span></span>  |<span data-ttu-id="84135-222">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="84135-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="84135-223">Daniela</span></span> | <span data-ttu-id="84135-224">全域</span><span class="sxs-lookup"><span data-stu-id="84135-224">Global</span></span>   | <span data-ttu-id="84135-225">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-225">False</span></span> |
|<span data-ttu-id="84135-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="84135-226">Amanda</span></span> | <span data-ttu-id="84135-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="84135-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="84135-228">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-228">True</span></span>|
|<span data-ttu-id="84135-229">約翰（外部使用者）</span><span class="sxs-lookup"><span data-stu-id="84135-229">John (external user)</span></span> | <span data-ttu-id="84135-230">不適用</span><span class="sxs-lookup"><span data-stu-id="84135-230">Not applicable</span></span> | <span data-ttu-id="84135-231">不適用</span><span class="sxs-lookup"><span data-stu-id="84135-231">Not applicable</span></span>|

<span data-ttu-id="84135-232">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="84135-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="84135-233">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="84135-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="84135-234">若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="84135-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="84135-235">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="84135-235">Allow IP video</span></span>

<span data-ttu-id="84135-236">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="84135-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="84135-237">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="84135-237">Video is a key component to meetings.</span></span> <span data-ttu-id="84135-238">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="84135-238">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="84135-239">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="84135-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="84135-240">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="84135-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="84135-241">沒有指派任何原則的會議參與者（例如匿名及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="84135-243">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="84135-243">Let's look at the following example.</span></span>

|<span data-ttu-id="84135-244">使用者</span><span class="sxs-lookup"><span data-stu-id="84135-244">User</span></span> |<span data-ttu-id="84135-245">會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-245">Meeting policy</span></span>  |<span data-ttu-id="84135-246">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="84135-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="84135-247">Daniela</span></span>   | <span data-ttu-id="84135-248">全域</span><span class="sxs-lookup"><span data-stu-id="84135-248">Global</span></span>   | <span data-ttu-id="84135-249">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-249">True</span></span>        |
|<span data-ttu-id="84135-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="84135-250">Amanda</span></span>    | <span data-ttu-id="84135-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="84135-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="84135-252">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-252">False</span></span>      |

<span data-ttu-id="84135-253">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="84135-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="84135-254">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="84135-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="84135-255">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="84135-255">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="84135-256">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="84135-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="84135-257">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="84135-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="84135-258">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="84135-258">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="84135-259">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="84135-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="84135-260">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="84135-260">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="84135-261">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="84135-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="84135-262">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="84135-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="84135-263">媒體位元速率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="84135-263">Media bit rate (Kbs)</span></span>

<span data-ttu-id="84135-264">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-264">This is a per-user policy.</span></span> <span data-ttu-id="84135-265">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="84135-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="84135-266">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="84135-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="84135-267">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="84135-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="84135-268">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="84135-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="84135-269">最小值為 30 Kbps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="84135-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="84135-270">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="84135-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="84135-271">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="84135-271">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="84135-272">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="84135-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="84135-273">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="84135-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="84135-274">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="84135-274">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="84135-275">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="84135-275">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="84135-276">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="84135-276">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="84135-277">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="84135-277">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="84135-278">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="84135-278">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="84135-279">允許白板</span><span class="sxs-lookup"><span data-stu-id="84135-279">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="84135-280">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="84135-280">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="84135-281">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="84135-281">Screen sharing mode</span></span>

<span data-ttu-id="84135-282">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="84135-282">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="84135-283">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="84135-283">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="84135-284">沒有指派任何原則的會議參與者（例如，匿名、來賓、B2B 及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-284">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="84135-285">設定值</span><span class="sxs-lookup"><span data-stu-id="84135-285">Setting value</span></span> |<span data-ttu-id="84135-286">行為</span><span class="sxs-lookup"><span data-stu-id="84135-286">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="84135-287">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="84135-287">**Entire screen**</span></span>    | <span data-ttu-id="84135-288">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="84135-288">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="84135-289">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="84135-289">**Single application**</span></span>   | <span data-ttu-id="84135-290">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="84135-290">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="84135-291">**禁止**</span><span class="sxs-lookup"><span data-stu-id="84135-291">**Disabled**</span></span>     |<span data-ttu-id="84135-292">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="84135-292">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="84135-293">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="84135-293">Let's look at the following example.</span></span>

|<span data-ttu-id="84135-294">使用者</span><span class="sxs-lookup"><span data-stu-id="84135-294">User</span></span> |<span data-ttu-id="84135-295">會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-295">Meeting policy</span></span> |<span data-ttu-id="84135-296">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="84135-296">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-297">Daniela</span><span class="sxs-lookup"><span data-stu-id="84135-297">Daniela</span></span>  | <span data-ttu-id="84135-298">全域</span><span class="sxs-lookup"><span data-stu-id="84135-298">Global</span></span>   | <span data-ttu-id="84135-299">整個畫面</span><span class="sxs-lookup"><span data-stu-id="84135-299">Entire screen</span></span> |
|<span data-ttu-id="84135-300">Amanda</span><span class="sxs-lookup"><span data-stu-id="84135-300">Amanda</span></span>   | <span data-ttu-id="84135-301">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="84135-301">Location1MeetingPolicy</span></span>  | <span data-ttu-id="84135-302">禁止</span><span class="sxs-lookup"><span data-stu-id="84135-302">Disabled</span></span> |

<span data-ttu-id="84135-303">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="84135-303">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="84135-304">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="84135-304">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="84135-305">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="84135-305">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="84135-306">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="84135-306">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="84135-307">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="84135-307">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="84135-308">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="84135-308">Allow a participant to give or request control</span></span>

<span data-ttu-id="84135-309">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-309">This is a per-user policy.</span></span> <span data-ttu-id="84135-310">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="84135-310">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="84135-311">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="84135-311">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="84135-312">如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="84135-312">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="84135-314">如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="84135-314">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="84135-316">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="84135-316">Let's look at the following example.</span></span>

|<span data-ttu-id="84135-317">使用者</span><span class="sxs-lookup"><span data-stu-id="84135-317">User</span></span> |<span data-ttu-id="84135-318">會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-318">Meeting policy</span></span>  |<span data-ttu-id="84135-319">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="84135-319">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-320">Daniela</span><span class="sxs-lookup"><span data-stu-id="84135-320">Daniela</span></span>   | <span data-ttu-id="84135-321">全域</span><span class="sxs-lookup"><span data-stu-id="84135-321">Global</span></span>   | <span data-ttu-id="84135-322">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-322">True</span></span>       |
|<span data-ttu-id="84135-323">Babek</span><span class="sxs-lookup"><span data-stu-id="84135-323">Babek</span></span>    | <span data-ttu-id="84135-324">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="84135-324">Location1MeetingPolicy</span></span>        | <span data-ttu-id="84135-325">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-325">False</span></span>   |

<span data-ttu-id="84135-326">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="84135-326">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="84135-327">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84135-327">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="84135-328">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="84135-328">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="84135-329">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="84135-329">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="84135-330">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="84135-330">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="84135-331">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="84135-331">Allow an external participant to give or request control</span></span>

<span data-ttu-id="84135-332">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-332">This is a per-user policy.</span></span> <span data-ttu-id="84135-333">此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="84135-333">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="84135-334">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="84135-334">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="84135-335">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="84135-335">Anonymous user</span></span>
- <span data-ttu-id="84135-336">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="84135-336">Guest users</span></span>  
- <span data-ttu-id="84135-337">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="84135-337">B2B user</span></span>
- <span data-ttu-id="84135-338">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="84135-338">Federated user</span></span>  

<span data-ttu-id="84135-339">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。</span><span class="sxs-lookup"><span data-stu-id="84135-339">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="84135-340">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84135-340">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="84135-341">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="84135-341">Allow PowerPoint sharing</span></span>

<span data-ttu-id="84135-342">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-342">This is a per-user policy.</span></span> <span data-ttu-id="84135-343">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="84135-343">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="84135-344">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-344">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="84135-345">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="84135-345">Let's look at the following example.</span></span>

|<span data-ttu-id="84135-346">使用者</span><span class="sxs-lookup"><span data-stu-id="84135-346">User</span></span> |<span data-ttu-id="84135-347">會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-347">Meeting policy</span></span>  |<span data-ttu-id="84135-348">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="84135-348">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-349">Daniela</span><span class="sxs-lookup"><span data-stu-id="84135-349">Daniela</span></span>   | <span data-ttu-id="84135-350">全域</span><span class="sxs-lookup"><span data-stu-id="84135-350">Global</span></span>   | <span data-ttu-id="84135-351">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-351">True</span></span>       |
|<span data-ttu-id="84135-352">Amanda</span><span class="sxs-lookup"><span data-stu-id="84135-352">Amanda</span></span>   | <span data-ttu-id="84135-353">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="84135-353">Location1MeetingPolicy</span></span>        | <span data-ttu-id="84135-354">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-354">False</span></span>   |

<span data-ttu-id="84135-355">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="84135-355">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="84135-356">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="84135-356">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="84135-357">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="84135-357">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="84135-358">允許白板</span><span class="sxs-lookup"><span data-stu-id="84135-358">Allow whiteboard</span></span>

<span data-ttu-id="84135-359">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-359">This is a per-user policy.</span></span> <span data-ttu-id="84135-360">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="84135-360">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="84135-361">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-361">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="84135-362">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="84135-362">Let's look at the following example.</span></span>

|<span data-ttu-id="84135-363">使用者</span><span class="sxs-lookup"><span data-stu-id="84135-363">User</span></span> |<span data-ttu-id="84135-364">會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-364">Meeting policy</span></span>  |<span data-ttu-id="84135-365">允許白板</span><span class="sxs-lookup"><span data-stu-id="84135-365">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="84135-366">Daniela</span><span class="sxs-lookup"><span data-stu-id="84135-366">Daniela</span></span>   | <span data-ttu-id="84135-367">全域</span><span class="sxs-lookup"><span data-stu-id="84135-367">Global</span></span>   | <span data-ttu-id="84135-368">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-368">True</span></span>       |
|<span data-ttu-id="84135-369">Amanda</span><span class="sxs-lookup"><span data-stu-id="84135-369">Amanda</span></span>   | <span data-ttu-id="84135-370">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="84135-370">Location1MeetingPolicy</span></span>        | <span data-ttu-id="84135-371">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-371">False</span></span>   |

<span data-ttu-id="84135-372">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="84135-372">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="84135-373">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="84135-373">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="84135-374">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="84135-374">Allow shared notes</span></span>

<span data-ttu-id="84135-375">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-375">This is a per-user policy.</span></span> <span data-ttu-id="84135-376">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="84135-376">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="84135-377">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-377">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="84135-378">目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="84135-378">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="84135-379">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="84135-379">Let's look at the following example.</span></span>

|<span data-ttu-id="84135-380">使用者</span><span class="sxs-lookup"><span data-stu-id="84135-380">User</span></span> |<span data-ttu-id="84135-381">會議原則</span><span class="sxs-lookup"><span data-stu-id="84135-381">Meeting policy</span></span>  |<span data-ttu-id="84135-382">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="84135-382">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-383">Daniela</span><span class="sxs-lookup"><span data-stu-id="84135-383">Daniela</span></span>   | <span data-ttu-id="84135-384">全域</span><span class="sxs-lookup"><span data-stu-id="84135-384">Global</span></span>   | <span data-ttu-id="84135-385">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-385">True</span></span>       |
|<span data-ttu-id="84135-386">Amanda</span><span class="sxs-lookup"><span data-stu-id="84135-386">Amanda</span></span>   | <span data-ttu-id="84135-387">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="84135-387">Location1MeetingPolicy</span></span> | <span data-ttu-id="84135-388">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-388">False</span></span> |

<span data-ttu-id="84135-389">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="84135-389">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="84135-390">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="84135-390">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="84135-391">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="84135-391">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="84135-392">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="84135-392">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="84135-393">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="84135-393">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="84135-394">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="84135-394">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="84135-395">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="84135-395">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="84135-396">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="84135-396">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="84135-397">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="84135-397">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="84135-398">如果您的群組有音訊會議，且使用它來連接，請參閱[Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="84135-398">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="84135-399">如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="84135-399">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="84135-400">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="84135-400">Let anonymous people start a meeting</span></span>

<span data-ttu-id="84135-401">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="84135-401">This is a per-organizer policy.</span></span> <span data-ttu-id="84135-402">此設定會控制匿名人員（包括 B2B）與同盟使用者，是否可在沒有已驗證的使用者的情況下，從出席中的組織加入使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="84135-402">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="84135-403">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="84135-403">The default value is False.</span></span>

![螢幕擷取畫面顯示等候使用者的訊息](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="84135-405">以下是在會議中有驗證使用者的情況下匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="84135-405">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="84135-406">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="84135-406">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="84135-407">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="84135-407">Automatically admit people</span></span> |<span data-ttu-id="84135-408">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="84135-408">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-409">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-409">True</span></span>    | <span data-ttu-id="84135-410">任何人</span><span class="sxs-lookup"><span data-stu-id="84135-410">Everyone</span></span>      | <span data-ttu-id="84135-411">直接加入</span><span class="sxs-lookup"><span data-stu-id="84135-411">Join directly</span></span>         |
|   | <span data-ttu-id="84135-412">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-412">Everyone in your organization</span></span>       | <span data-ttu-id="84135-413">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-413">Wait in lobby</span></span>        |
|   | <span data-ttu-id="84135-414">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-414">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="84135-415">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-415">Wait in lobby</span></span>         |
|<span data-ttu-id="84135-416">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-416">False</span></span>    | <span data-ttu-id="84135-417">任何人</span><span class="sxs-lookup"><span data-stu-id="84135-417">Everyone</span></span>        | <span data-ttu-id="84135-418">直接加入</span><span class="sxs-lookup"><span data-stu-id="84135-418">Join directly</span></span>        |
|   | <span data-ttu-id="84135-419">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-419">Everyone in your organization</span></span>     | <span data-ttu-id="84135-420">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-420">Wait in lobby</span></span>        |
|   | <span data-ttu-id="84135-421">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-421">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="84135-422">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-422">Wait in lobby</span></span>         |

<span data-ttu-id="84135-423">以下是在會議中沒有經過驗證的使用者時，匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="84135-423">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="84135-424">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="84135-424">Let anonymous people start a meeting</span></span> |<span data-ttu-id="84135-425">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="84135-425">Automatically admit people</span></span>  |<span data-ttu-id="84135-426">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="84135-426">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-427">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-427">True</span></span>    | <span data-ttu-id="84135-428">任何人</span><span class="sxs-lookup"><span data-stu-id="84135-428">Everyone</span></span>      | <span data-ttu-id="84135-429">直接加入</span><span class="sxs-lookup"><span data-stu-id="84135-429">Join directly</span></span>         |
|   | <span data-ttu-id="84135-430">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-430">Everyone in your organization</span></span>       | <span data-ttu-id="84135-431">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-431">Wait in lobby</span></span>        |
|   | <span data-ttu-id="84135-432">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-432">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="84135-433">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-433">Wait in lobby</span></span>         |
|<span data-ttu-id="84135-434">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-434">False</span></span>    | <span data-ttu-id="84135-435">任何人</span><span class="sxs-lookup"><span data-stu-id="84135-435">Everyone</span></span>        | <span data-ttu-id="84135-436">在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="84135-436">Wait in lobby.</span></span> <span data-ttu-id="84135-437">當第一個經過驗證的使用者加入會議時，系統會自動准許使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-437">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="84135-438">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-438">Everyone in your organization</span></span>     |<span data-ttu-id="84135-439">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-439">Wait in lobby</span></span>         |
|   | <span data-ttu-id="84135-440">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-440">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="84135-441">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-441">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="84135-442">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="84135-442">Automatically admit people</span></span>

<span data-ttu-id="84135-443">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="84135-443">This is a per-organizer policy.</span></span> <span data-ttu-id="84135-444">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="84135-444">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="84135-446">會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="84135-446">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="84135-447">設定值</span><span class="sxs-lookup"><span data-stu-id="84135-447">Setting value</span></span>  |<span data-ttu-id="84135-448">加入行為</span><span class="sxs-lookup"><span data-stu-id="84135-448">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="84135-449">**任何人**</span><span class="sxs-lookup"><span data-stu-id="84135-449">**Everyone**</span></span>   |<span data-ttu-id="84135-450">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="84135-450">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="84135-451">這包括經過驗證的使用者、聯盟使用者、來賓、匿名使用者，以及透過電話撥入的人員。</span><span class="sxs-lookup"><span data-stu-id="84135-451">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="84135-452">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="84135-452">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="84135-453">組織內經過驗證的使用者，包括來賓使用者以及來自同盟組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="84135-453">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="84135-454">在大廳由手機撥入的匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-454">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="84135-455">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="84135-455">**Everyone in your organization**</span></span>    |<span data-ttu-id="84135-456">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="84135-456">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="84135-457">在大廳以電話撥入的聯盟使用者、匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-457">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span> <span data-ttu-id="84135-458">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="84135-458">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="84135-459">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="84135-459">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="84135-460">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="84135-460">This is a per-organizer policy.</span></span> <span data-ttu-id="84135-461">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="84135-461">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="84135-462">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="84135-462">The default value is False.</span></span>

<span data-ttu-id="84135-463">以下是透過電話撥入的人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="84135-463">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="84135-464">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="84135-464">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="84135-465">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="84135-465">Automatically admit people</span></span>  |<span data-ttu-id="84135-466">撥入之人的加入行為</span><span class="sxs-lookup"><span data-stu-id="84135-466">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="84135-467">滿足</span><span class="sxs-lookup"><span data-stu-id="84135-467">True</span></span>    | <span data-ttu-id="84135-468">任何人</span><span class="sxs-lookup"><span data-stu-id="84135-468">Everyone</span></span>      | <span data-ttu-id="84135-469">直接加入</span><span class="sxs-lookup"><span data-stu-id="84135-469">Join directly</span></span>         |
|   | <span data-ttu-id="84135-470">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-470">Everyone in your organization</span></span>       | <span data-ttu-id="84135-471">直接加入</span><span class="sxs-lookup"><span data-stu-id="84135-471">Join directly</span></span>        |
|   | <span data-ttu-id="84135-472">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-472">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="84135-473">直接加入</span><span class="sxs-lookup"><span data-stu-id="84135-473">Join directly</span></span>         |
|<span data-ttu-id="84135-474">虛假</span><span class="sxs-lookup"><span data-stu-id="84135-474">False</span></span>    | <span data-ttu-id="84135-475">任何人</span><span class="sxs-lookup"><span data-stu-id="84135-475">Everyone</span></span>        | <span data-ttu-id="84135-476">直接加入</span><span class="sxs-lookup"><span data-stu-id="84135-476">Join directly</span></span>        |
|   | <span data-ttu-id="84135-477">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-477">Everyone in your organization</span></span>     |<span data-ttu-id="84135-478">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-478">Wait in lobby</span></span>         |
|   | <span data-ttu-id="84135-479">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="84135-479">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="84135-480">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="84135-480">Wait in lobby</span></span>         |


### <a name="enable-live-captions"></a><span data-ttu-id="84135-481">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="84135-481">Enable live captions</span></span>

<span data-ttu-id="84135-482">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="84135-482">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="84135-483">此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="84135-483">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="84135-485">設定值</span><span class="sxs-lookup"><span data-stu-id="84135-485">Setting value</span></span> |<span data-ttu-id="84135-486">行為</span><span class="sxs-lookup"><span data-stu-id="84135-486">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="84135-487">**已停用，但召集人可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="84135-487">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="84135-488">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="84135-488">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="84135-489">使用者會看到 [溢出（**...**）] 功能表中的 [**開啟即時標題**] 選項，以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="84135-489">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="84135-490">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="84135-490">This is the default setting.</span></span> |
|<span data-ttu-id="84135-491">**禁止**</span><span class="sxs-lookup"><span data-stu-id="84135-491">**Disabled**</span></span>     | <span data-ttu-id="84135-492">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="84135-492">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="84135-493">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="84135-493">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="84135-494"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="84135-494"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="84135-495">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="84135-495">Allow chat in meetings</span></span>

<span data-ttu-id="84135-496">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="84135-496">This is a per-organizer policy.</span></span> <span data-ttu-id="84135-497">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="84135-497">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="84135-498"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="84135-498"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="84135-499">會議原則設定-指定的簡報者角色模式</span><span class="sxs-lookup"><span data-stu-id="84135-499">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="84135-500">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-500">This is a per-user policy.</span></span> <span data-ttu-id="84135-501">這項設定可讓您變更小組用戶端的 [**會議選項**] 中的 [**可以出示的人員**] 設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="84135-501">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="84135-502">此原則設定會影響所有會議，包括 [立即開會] 會議。</span><span class="sxs-lookup"><span data-stu-id="84135-502">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="84135-503">[**可以出席的人員**] 設定可讓會議召集人選擇要在會議中成為簡報者的人員。</span><span class="sxs-lookup"><span data-stu-id="84135-503">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="84135-504">若要深入瞭解，請參閱[在團隊會議中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)[變更團隊會議](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)與角色的參與者設定。</span><span class="sxs-lookup"><span data-stu-id="84135-504">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="84135-505">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="84135-505">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="84135-506">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="84135-506">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="84135-507">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-507">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="84135-508">若要指定 [**可以提出的人員**] 的預設值，請將**DesignatedPresenterRoleMode**參數設定為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="84135-508">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="84135-509">**EveryoneUserOverride**：所有會議參與者都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="84135-509">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="84135-510">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="84135-510">This is the default value.</span></span> <span data-ttu-id="84135-511">這個參數會對應到 [小組] 中的 [**所有人**] 設定。</span><span class="sxs-lookup"><span data-stu-id="84135-511">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="84135-512">**EveryoneInCompanyUserOverride**：組織中經過驗證的使用者，包括來賓使用者，都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="84135-512">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="84135-513">這個參數會對應到 [**我的組織**中的人員] 設定。</span><span class="sxs-lookup"><span data-stu-id="84135-513">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="84135-514">**EveryoneInSameAndFederatedCompanyUserOverride**：組織中經過驗證的使用者，包括來賓使用者和聯盟組織的使用者，都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="84135-514">**EveryoneInSameAndFederatedCompanyUserOverride**:  Authenticated users in the organization, including guest users and users from federated organizations, can be presenters.</span></span> <span data-ttu-id="84135-515">這個參數會對應到 [**我的組織中的人員] 和**[小組中受信任的組織] 設定。</span><span class="sxs-lookup"><span data-stu-id="84135-515">This parameter corresponds to the **People in my organization and trusted organizations** setting in Teams.</span></span>
- <span data-ttu-id="84135-516">**OrganizerOnlyUserOverride**：只有會議召集人可以成為簡報者，且所有會議參與者都指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="84135-516">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="84135-517">這個參數會對應到 [團隊] 中的 [**僅自己**] 設定。</span><span class="sxs-lookup"><span data-stu-id="84135-517">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="84135-518">請記住，在您設定預設值之後，會議召集人仍可在團隊中變更此設定，並選擇誰可以在排程的會議中出席。</span><span class="sxs-lookup"><span data-stu-id="84135-518">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="84135-519">會議原則設定-會議出席情況報告</span><span class="sxs-lookup"><span data-stu-id="84135-519">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="84135-520">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="84135-520">This is a per-user policy.</span></span> <span data-ttu-id="84135-521">此設定控制會議召集人是否可以下載[會議出席情況報告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="84135-521">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="84135-522">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="84135-522">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="84135-523">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="84135-523">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="84135-524">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="84135-524">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="84135-525">若要讓會議召集人下載會議出席情況報告，請將**AllowEngagementReport**參數設定為 [**已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="84135-525">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="84135-526">啟用時，會在**參與者**窗格中顯示下載報告的選項。</span><span class="sxs-lookup"><span data-stu-id="84135-526">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="84135-527">若要避免會議召集人下載報表，請將參數設定為 [**已停用**]。</span><span class="sxs-lookup"><span data-stu-id="84135-527">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="84135-528">根據預設，此設定會停用，而且無法使用下載報表的選項。</span><span class="sxs-lookup"><span data-stu-id="84135-528">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84135-529">相關主題</span><span class="sxs-lookup"><span data-stu-id="84135-529">Related topics</span></span>

- [<span data-ttu-id="84135-530">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="84135-530">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
