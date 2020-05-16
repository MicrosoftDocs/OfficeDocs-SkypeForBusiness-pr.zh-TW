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
ms.openlocfilehash: a2c921da824bdbbcd6b0f6baf49887e55df08ca9
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256498"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="54407-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="54407-104">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="54407-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="54407-105">建立原則並進行變更之後，您可以將使用者指派給該原則。</span><span class="sxs-lookup"><span data-stu-id="54407-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="54407-106">您可以在 Microsoft 團隊系統管理中心或使用[PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="54407-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="54407-107">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="54407-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="54407-108">實現類型</span><span class="sxs-lookup"><span data-stu-id="54407-108">Implementation type</span></span>  |<span data-ttu-id="54407-109">描述</span><span class="sxs-lookup"><span data-stu-id="54407-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="54407-110">每個召集人</span><span class="sxs-lookup"><span data-stu-id="54407-110">Per-organizer</span></span>    |<span data-ttu-id="54407-111">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="54407-112">例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="54407-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="54407-113">每位使用者</span><span class="sxs-lookup"><span data-stu-id="54407-113">Per-user</span></span>    |<span data-ttu-id="54407-114">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="54407-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="54407-115">例如，[**允許在頻道中立即開會**] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="54407-116">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="54407-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="54407-117">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="54407-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="54407-118">例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="54407-119">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="54407-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="54407-120">根據預設，會建立名為 [全域] （組織範圍預設值）的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="54407-121">貴組織中的所有使用者預設都會獲指派 [全域會議原則]。</span><span class="sxs-lookup"><span data-stu-id="54407-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="54407-122">您可以對其進行變更或建立一或多個自訂原則，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="54407-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="54407-123">除非您建立並指派自訂原則，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="54407-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="54407-124">當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將其指派給將設定套用至其中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="54407-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

> [!NOTE]
> <span data-ttu-id="54407-125">如果使用者已啟用音訊會議授權，或使用者允許音訊會議，則 [會議詳細資料] 按鈕就會提供，會議詳細資料將無法使用。</span><span class="sxs-lookup"><span data-stu-id="54407-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="54407-126">變更或建立會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-126">Change or create a meeting policy</span></span>

<span data-ttu-id="54407-127">若要變更或建立會議原則，請移至 [Microsoft Teams 系統管理中心] > **[會議] \*\* > \*\* [會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="54407-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="54407-128">從清單中選取原則，或選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="54407-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="54407-129">如果您要建立新原則，請新增原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="54407-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="54407-130">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="54407-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="54407-131">選擇您的設定，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="54407-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="54407-132">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="54407-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="54407-133">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="54407-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="54407-134">在 [音訊與視訊]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="54407-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="54407-135">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="54407-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="54407-136">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="54407-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="54407-137">在 [內容共用]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="54407-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="54407-138">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="54407-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="54407-139">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="54407-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="54407-140">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="54407-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="54407-141">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="54407-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="54407-142">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="54407-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="54407-143">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="54407-143">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="54407-144">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="54407-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="54407-145">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54407-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="54407-146">在 [會議原則]\*\*\*\* 下，選取要指派的原則，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54407-146">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="54407-147">若要一次將原則指派給多個使用者，請參閱[大量編輯 Teams 使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="54407-147">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="54407-148">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="54407-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="54407-149">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="54407-149">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="54407-150">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="54407-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="54407-151">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54407-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="54407-152">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="54407-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="54407-153">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="54407-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="54407-154">完成新增使用者之後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="54407-154">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="54407-155">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="54407-155">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="54407-156">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="54407-156">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="54407-157">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="54407-157">Meeting policy settings</span></span>

<span data-ttu-id="54407-158">當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增**] 以新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="54407-158">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="54407-159">一般</span><span class="sxs-lookup"><span data-stu-id="54407-159">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="54407-160">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="54407-160">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="54407-161">內容共用</span><span class="sxs-lookup"><span data-stu-id="54407-161">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="54407-162">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="54407-162">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="54407-163"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="54407-163"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="54407-164">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="54407-164">Meeting policy settings - General</span></span>

- <span data-ttu-id="54407-165">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="54407-165">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="54407-166">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="54407-166">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="54407-167">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="54407-167">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="54407-168">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="54407-168">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="54407-169">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="54407-169">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="54407-170">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="54407-170">Allow Meet now in channels</span></span>

<span data-ttu-id="54407-171">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="54407-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="54407-172">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="54407-172">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="54407-173">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="54407-173">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="54407-174">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="54407-174">The default value is True.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="54407-176">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="54407-176">Allow the Outlook add-in</span></span>

<span data-ttu-id="54407-177">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="54407-177">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="54407-178">此設定控制團隊會議是否可在 Outlook 中排程（Windows、Mac、web 及行動裝置）。</span><span class="sxs-lookup"><span data-stu-id="54407-178">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="54407-180">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="54407-180">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="54407-181">例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="54407-181">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="54407-182">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="54407-182">Allow channel meeting scheduling</span></span>

<span data-ttu-id="54407-183">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="54407-183">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="54407-184">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="54407-184">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="54407-185">如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。</span><span class="sxs-lookup"><span data-stu-id="54407-185">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="54407-186">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="54407-186">The default value is True.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="54407-189">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="54407-189">Allow scheduling private meetings</span></span>

<span data-ttu-id="54407-190">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="54407-190">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="54407-191">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="54407-191">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="54407-192">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="54407-192">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="54407-193">請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。</span><span class="sxs-lookup"><span data-stu-id="54407-193">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="54407-194">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="54407-194">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="54407-195">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="54407-195">Allow Meet now in private meetings</span></span>

<span data-ttu-id="54407-196">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="54407-196">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="54407-197">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="54407-197">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="54407-198">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="54407-198">The default value is True.</span></span>

<span data-ttu-id="54407-199"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="54407-199"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="54407-200">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="54407-200">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="54407-201">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="54407-201">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="54407-202">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="54407-202">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="54407-203">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="54407-203">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="54407-204">媒體位元速率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="54407-204">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="54407-205">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="54407-205">Allow transcription</span></span>

<span data-ttu-id="54407-206">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="54407-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="54407-207">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="54407-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="54407-208">如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="54407-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="54407-209">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="54407-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="54407-210">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="54407-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="54407-212">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="54407-212">Allow cloud recording</span></span>

<span data-ttu-id="54407-213">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="54407-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="54407-214">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="54407-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="54407-215">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="54407-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="54407-216">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="54407-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="54407-217">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="54407-217">Guest users can't start or stop the recording.</span></span> 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="54407-219">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="54407-219">Let's look at the following example.</span></span>

|<span data-ttu-id="54407-220">使用者</span><span class="sxs-lookup"><span data-stu-id="54407-220">User</span></span> |<span data-ttu-id="54407-221">會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-221">Meeting policy</span></span>  |<span data-ttu-id="54407-222">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="54407-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="54407-223">Daniela</span></span> | <span data-ttu-id="54407-224">全域</span><span class="sxs-lookup"><span data-stu-id="54407-224">Global</span></span>   | <span data-ttu-id="54407-225">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-225">False</span></span> |
|<span data-ttu-id="54407-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="54407-226">Amanda</span></span> | <span data-ttu-id="54407-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="54407-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="54407-228">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-228">True</span></span>|
|<span data-ttu-id="54407-229">約翰（外部使用者）</span><span class="sxs-lookup"><span data-stu-id="54407-229">John (external user)</span></span> | <span data-ttu-id="54407-230">不適用</span><span class="sxs-lookup"><span data-stu-id="54407-230">Not applicable</span></span> | <span data-ttu-id="54407-231">不適用</span><span class="sxs-lookup"><span data-stu-id="54407-231">Not applicable</span></span>|

<span data-ttu-id="54407-232">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="54407-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="54407-233">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="54407-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="54407-234">若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="54407-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="54407-235">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="54407-235">Allow IP video</span></span>

<span data-ttu-id="54407-236">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="54407-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="54407-237">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="54407-237">Video is a key component to meetings.</span></span> <span data-ttu-id="54407-238">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="54407-238">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="54407-239">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="54407-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="54407-240">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="54407-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="54407-241">沒有指派任何原則的會議參與者（例如匿名及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="54407-243">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="54407-243">Let's look at the following example.</span></span>

|<span data-ttu-id="54407-244">使用者</span><span class="sxs-lookup"><span data-stu-id="54407-244">User</span></span> |<span data-ttu-id="54407-245">會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-245">Meeting policy</span></span>  |<span data-ttu-id="54407-246">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="54407-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="54407-247">Daniela</span></span>   | <span data-ttu-id="54407-248">全域</span><span class="sxs-lookup"><span data-stu-id="54407-248">Global</span></span>   | <span data-ttu-id="54407-249">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-249">True</span></span>        |
|<span data-ttu-id="54407-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="54407-250">Amanda</span></span>    | <span data-ttu-id="54407-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="54407-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="54407-252">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-252">False</span></span>      |

<span data-ttu-id="54407-253">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="54407-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="54407-254">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="54407-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="54407-255">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="54407-255">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="54407-256">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="54407-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="54407-257">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="54407-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="54407-258">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="54407-258">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="54407-259">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="54407-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="54407-260">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="54407-260">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="54407-261">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="54407-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="54407-262">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="54407-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="54407-263">媒體位元速率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="54407-263">Media bit rate (Kbs)</span></span>

<span data-ttu-id="54407-264">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-264">This is a per-user policy.</span></span> <span data-ttu-id="54407-265">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="54407-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="54407-266">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="54407-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="54407-267">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="54407-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="54407-268">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="54407-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="54407-269">最小值為 30 Kbps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="54407-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="54407-270">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="54407-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="54407-271">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="54407-271">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="54407-272">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="54407-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="54407-273">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="54407-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="54407-274">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="54407-274">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="54407-275">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="54407-275">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="54407-276">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="54407-276">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="54407-277">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="54407-277">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="54407-278">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="54407-278">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="54407-279">允許白板</span><span class="sxs-lookup"><span data-stu-id="54407-279">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="54407-280">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="54407-280">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="54407-281">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="54407-281">Screen sharing mode</span></span>

<span data-ttu-id="54407-282">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="54407-282">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="54407-283">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="54407-283">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="54407-284">沒有指派任何原則的會議參與者（例如，匿名、來賓、B2B 及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-284">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="54407-285">設定值</span><span class="sxs-lookup"><span data-stu-id="54407-285">Setting value</span></span> |<span data-ttu-id="54407-286">行為</span><span class="sxs-lookup"><span data-stu-id="54407-286">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="54407-287">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="54407-287">**Entire screen**</span></span>    | <span data-ttu-id="54407-288">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="54407-288">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="54407-289">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="54407-289">**Single application**</span></span>   | <span data-ttu-id="54407-290">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="54407-290">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="54407-291">**禁止**</span><span class="sxs-lookup"><span data-stu-id="54407-291">**Disabled**</span></span>     |<span data-ttu-id="54407-292">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="54407-292">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="54407-293">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="54407-293">Let's look at the following example.</span></span>

|<span data-ttu-id="54407-294">使用者</span><span class="sxs-lookup"><span data-stu-id="54407-294">User</span></span> |<span data-ttu-id="54407-295">會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-295">Meeting policy</span></span> |<span data-ttu-id="54407-296">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="54407-296">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-297">Daniela</span><span class="sxs-lookup"><span data-stu-id="54407-297">Daniela</span></span>  | <span data-ttu-id="54407-298">全域</span><span class="sxs-lookup"><span data-stu-id="54407-298">Global</span></span>   | <span data-ttu-id="54407-299">整個畫面</span><span class="sxs-lookup"><span data-stu-id="54407-299">Entire screen</span></span> |
|<span data-ttu-id="54407-300">Amanda</span><span class="sxs-lookup"><span data-stu-id="54407-300">Amanda</span></span>   | <span data-ttu-id="54407-301">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="54407-301">Location1MeetingPolicy</span></span>  | <span data-ttu-id="54407-302">禁止</span><span class="sxs-lookup"><span data-stu-id="54407-302">Disabled</span></span> |

<span data-ttu-id="54407-303">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="54407-303">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="54407-304">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="54407-304">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="54407-305">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="54407-305">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="54407-306">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="54407-306">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="54407-307">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="54407-307">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="54407-308">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="54407-308">Allow a participant to give or request control</span></span>

<span data-ttu-id="54407-309">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-309">This is a per-user policy.</span></span> <span data-ttu-id="54407-310">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="54407-310">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="54407-311">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="54407-311">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="54407-312">如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="54407-312">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="54407-314">如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="54407-314">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="54407-316">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="54407-316">Let's look at the following example.</span></span>

|<span data-ttu-id="54407-317">使用者</span><span class="sxs-lookup"><span data-stu-id="54407-317">User</span></span> |<span data-ttu-id="54407-318">會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-318">Meeting policy</span></span>  |<span data-ttu-id="54407-319">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="54407-319">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-320">Daniela</span><span class="sxs-lookup"><span data-stu-id="54407-320">Daniela</span></span>   | <span data-ttu-id="54407-321">全域</span><span class="sxs-lookup"><span data-stu-id="54407-321">Global</span></span>   | <span data-ttu-id="54407-322">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-322">True</span></span>       |
|<span data-ttu-id="54407-323">Babek</span><span class="sxs-lookup"><span data-stu-id="54407-323">Babek</span></span>    | <span data-ttu-id="54407-324">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="54407-324">Location1MeetingPolicy</span></span>        | <span data-ttu-id="54407-325">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-325">False</span></span>   |

<span data-ttu-id="54407-326">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="54407-326">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="54407-327">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54407-327">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="54407-328">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="54407-328">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="54407-329">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="54407-329">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="54407-330">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="54407-330">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="54407-331">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="54407-331">Allow an external participant to give or request control</span></span>

<span data-ttu-id="54407-332">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-332">This is a per-user policy.</span></span> <span data-ttu-id="54407-333">此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="54407-333">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="54407-334">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="54407-334">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="54407-335">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="54407-335">Anonymous user</span></span>
- <span data-ttu-id="54407-336">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="54407-336">Guest users</span></span>  
- <span data-ttu-id="54407-337">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="54407-337">B2B user</span></span>
- <span data-ttu-id="54407-338">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="54407-338">Federated user</span></span>  

<span data-ttu-id="54407-339">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。</span><span class="sxs-lookup"><span data-stu-id="54407-339">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="54407-340">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54407-340">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="54407-341">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="54407-341">Allow PowerPoint sharing</span></span>

<span data-ttu-id="54407-342">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-342">This is a per-user policy.</span></span> <span data-ttu-id="54407-343">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="54407-343">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="54407-344">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-344">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="54407-345">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="54407-345">Let's look at the following example.</span></span>

|<span data-ttu-id="54407-346">使用者</span><span class="sxs-lookup"><span data-stu-id="54407-346">User</span></span> |<span data-ttu-id="54407-347">會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-347">Meeting policy</span></span>  |<span data-ttu-id="54407-348">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="54407-348">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-349">Daniela</span><span class="sxs-lookup"><span data-stu-id="54407-349">Daniela</span></span>   | <span data-ttu-id="54407-350">全域</span><span class="sxs-lookup"><span data-stu-id="54407-350">Global</span></span>   | <span data-ttu-id="54407-351">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-351">True</span></span>       |
|<span data-ttu-id="54407-352">Amanda</span><span class="sxs-lookup"><span data-stu-id="54407-352">Amanda</span></span>   | <span data-ttu-id="54407-353">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="54407-353">Location1MeetingPolicy</span></span>        | <span data-ttu-id="54407-354">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-354">False</span></span>   |

<span data-ttu-id="54407-355">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="54407-355">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="54407-356">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="54407-356">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="54407-357">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="54407-357">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="54407-358">允許白板</span><span class="sxs-lookup"><span data-stu-id="54407-358">Allow whiteboard</span></span>

<span data-ttu-id="54407-359">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-359">This is a per-user policy.</span></span> <span data-ttu-id="54407-360">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="54407-360">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="54407-361">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-361">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="54407-362">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="54407-362">Let's look at the following example.</span></span>

|<span data-ttu-id="54407-363">使用者</span><span class="sxs-lookup"><span data-stu-id="54407-363">User</span></span> |<span data-ttu-id="54407-364">會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-364">Meeting policy</span></span>  |<span data-ttu-id="54407-365">允許白板</span><span class="sxs-lookup"><span data-stu-id="54407-365">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="54407-366">Daniela</span><span class="sxs-lookup"><span data-stu-id="54407-366">Daniela</span></span>   | <span data-ttu-id="54407-367">全域</span><span class="sxs-lookup"><span data-stu-id="54407-367">Global</span></span>   | <span data-ttu-id="54407-368">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-368">True</span></span>       |
|<span data-ttu-id="54407-369">Amanda</span><span class="sxs-lookup"><span data-stu-id="54407-369">Amanda</span></span>   | <span data-ttu-id="54407-370">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="54407-370">Location1MeetingPolicy</span></span>        | <span data-ttu-id="54407-371">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-371">False</span></span>   |

<span data-ttu-id="54407-372">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="54407-372">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="54407-373">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="54407-373">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="54407-374">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="54407-374">Allow shared notes</span></span>

<span data-ttu-id="54407-375">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-375">This is a per-user policy.</span></span> <span data-ttu-id="54407-376">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="54407-376">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="54407-377">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-377">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="54407-378">目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="54407-378">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="54407-379">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="54407-379">Let's look at the following example.</span></span>

|<span data-ttu-id="54407-380">使用者</span><span class="sxs-lookup"><span data-stu-id="54407-380">User</span></span> |<span data-ttu-id="54407-381">會議原則</span><span class="sxs-lookup"><span data-stu-id="54407-381">Meeting policy</span></span>  |<span data-ttu-id="54407-382">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="54407-382">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-383">Daniela</span><span class="sxs-lookup"><span data-stu-id="54407-383">Daniela</span></span>   | <span data-ttu-id="54407-384">全域</span><span class="sxs-lookup"><span data-stu-id="54407-384">Global</span></span>   | <span data-ttu-id="54407-385">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-385">True</span></span>       |
|<span data-ttu-id="54407-386">Amanda</span><span class="sxs-lookup"><span data-stu-id="54407-386">Amanda</span></span>   | <span data-ttu-id="54407-387">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="54407-387">Location1MeetingPolicy</span></span> | <span data-ttu-id="54407-388">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-388">False</span></span> |

<span data-ttu-id="54407-389">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="54407-389">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="54407-390">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="54407-390">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="54407-391">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="54407-391">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="54407-392">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="54407-392">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="54407-393">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="54407-393">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="54407-394">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="54407-394">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="54407-395">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="54407-395">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="54407-396">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="54407-396">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="54407-397">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="54407-397">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="54407-398">如果您的群組有音訊會議，且使用它來連接，請參閱[Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="54407-398">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="54407-399">如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="54407-399">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="54407-400">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="54407-400">Let anonymous people start a meeting</span></span>

<span data-ttu-id="54407-401">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="54407-401">This is a per-organizer policy.</span></span> <span data-ttu-id="54407-402">此設定會控制匿名人員（包括 B2B）與同盟使用者，是否可在沒有已驗證的使用者的情況下，從出席中的組織加入使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="54407-402">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="54407-403">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="54407-403">The default value is False.</span></span>

![螢幕擷取畫面顯示等候使用者的訊息](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="54407-405">以下是在會議中有驗證使用者的情況下匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="54407-405">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="54407-406">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="54407-406">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="54407-407">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="54407-407">Automatically admit people</span></span> |<span data-ttu-id="54407-408">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="54407-408">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-409">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-409">True</span></span>    | <span data-ttu-id="54407-410">任何人</span><span class="sxs-lookup"><span data-stu-id="54407-410">Everyone</span></span>      | <span data-ttu-id="54407-411">直接加入</span><span class="sxs-lookup"><span data-stu-id="54407-411">Join directly</span></span>         |
|   | <span data-ttu-id="54407-412">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-412">Everyone in your organization</span></span>       | <span data-ttu-id="54407-413">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-413">Wait in lobby</span></span>        |
|   | <span data-ttu-id="54407-414">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-414">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="54407-415">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-415">Wait in lobby</span></span>         |
|<span data-ttu-id="54407-416">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-416">False</span></span>    | <span data-ttu-id="54407-417">任何人</span><span class="sxs-lookup"><span data-stu-id="54407-417">Everyone</span></span>        | <span data-ttu-id="54407-418">直接加入</span><span class="sxs-lookup"><span data-stu-id="54407-418">Join directly</span></span>        |
|   | <span data-ttu-id="54407-419">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-419">Everyone in your organization</span></span>     | <span data-ttu-id="54407-420">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-420">Wait in lobby</span></span>        |
|   | <span data-ttu-id="54407-421">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-421">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="54407-422">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-422">Wait in lobby</span></span>         |

<span data-ttu-id="54407-423">以下是在會議中沒有經過驗證的使用者時，匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="54407-423">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="54407-424">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="54407-424">Let anonymous people start a meeting</span></span> |<span data-ttu-id="54407-425">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="54407-425">Automatically admit people</span></span>  |<span data-ttu-id="54407-426">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="54407-426">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-427">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-427">True</span></span>    | <span data-ttu-id="54407-428">任何人</span><span class="sxs-lookup"><span data-stu-id="54407-428">Everyone</span></span>      | <span data-ttu-id="54407-429">直接加入</span><span class="sxs-lookup"><span data-stu-id="54407-429">Join directly</span></span>         |
|   | <span data-ttu-id="54407-430">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-430">Everyone in your organization</span></span>       | <span data-ttu-id="54407-431">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-431">Wait in lobby</span></span>        |
|   | <span data-ttu-id="54407-432">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-432">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="54407-433">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-433">Wait in lobby</span></span>         |
|<span data-ttu-id="54407-434">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-434">False</span></span>    | <span data-ttu-id="54407-435">任何人</span><span class="sxs-lookup"><span data-stu-id="54407-435">Everyone</span></span>        | <span data-ttu-id="54407-436">在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="54407-436">Wait in lobby.</span></span> <span data-ttu-id="54407-437">當第一個經過驗證的使用者加入會議時，系統會自動准許使用者。</span><span class="sxs-lookup"><span data-stu-id="54407-437">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="54407-438">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-438">Everyone in your organization</span></span>     |<span data-ttu-id="54407-439">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-439">Wait in lobby</span></span>         |
|   | <span data-ttu-id="54407-440">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-440">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="54407-441">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-441">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="54407-442">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="54407-442">Automatically admit people</span></span>

<span data-ttu-id="54407-443">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="54407-443">This is a per-organizer policy.</span></span> <span data-ttu-id="54407-444">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="54407-444">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="54407-446">會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="54407-446">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="54407-447">設定值</span><span class="sxs-lookup"><span data-stu-id="54407-447">Setting value</span></span>  |<span data-ttu-id="54407-448">加入行為</span><span class="sxs-lookup"><span data-stu-id="54407-448">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="54407-449">**任何人**</span><span class="sxs-lookup"><span data-stu-id="54407-449">**Everyone**</span></span>   |<span data-ttu-id="54407-450">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="54407-450">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="54407-451">這包括經過驗證的使用者、聯盟使用者、來賓、匿名使用者，以及透過電話撥入的人員。</span><span class="sxs-lookup"><span data-stu-id="54407-451">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="54407-452">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="54407-452">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="54407-453">組織內經過驗證的使用者，包括來賓使用者以及來自同盟組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="54407-453">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="54407-454">在大廳由手機撥入的匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="54407-454">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="54407-455">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="54407-455">**Everyone in your organization**</span></span>    |<span data-ttu-id="54407-456">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="54407-456">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="54407-457">在大廳以電話撥入的聯盟使用者、匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="54407-457">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span> <span data-ttu-id="54407-458">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="54407-458">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="54407-459">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="54407-459">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="54407-460">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="54407-460">This is a per-organizer policy.</span></span> <span data-ttu-id="54407-461">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="54407-461">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="54407-462">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="54407-462">The default value is False.</span></span>

<span data-ttu-id="54407-463">以下是透過電話撥入的人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="54407-463">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="54407-464">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="54407-464">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="54407-465">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="54407-465">Automatically admit people</span></span>  |<span data-ttu-id="54407-466">撥入之人的加入行為</span><span class="sxs-lookup"><span data-stu-id="54407-466">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54407-467">滿足</span><span class="sxs-lookup"><span data-stu-id="54407-467">True</span></span>    | <span data-ttu-id="54407-468">任何人</span><span class="sxs-lookup"><span data-stu-id="54407-468">Everyone</span></span>      | <span data-ttu-id="54407-469">直接加入</span><span class="sxs-lookup"><span data-stu-id="54407-469">Join directly</span></span>         |
|   | <span data-ttu-id="54407-470">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-470">Everyone in your organization</span></span>       | <span data-ttu-id="54407-471">直接加入</span><span class="sxs-lookup"><span data-stu-id="54407-471">Join directly</span></span>        |
|   | <span data-ttu-id="54407-472">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-472">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="54407-473">直接加入</span><span class="sxs-lookup"><span data-stu-id="54407-473">Join directly</span></span>         |
|<span data-ttu-id="54407-474">虛假</span><span class="sxs-lookup"><span data-stu-id="54407-474">False</span></span>    | <span data-ttu-id="54407-475">任何人</span><span class="sxs-lookup"><span data-stu-id="54407-475">Everyone</span></span>        | <span data-ttu-id="54407-476">直接加入</span><span class="sxs-lookup"><span data-stu-id="54407-476">Join directly</span></span>        |
|   | <span data-ttu-id="54407-477">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-477">Everyone in your organization</span></span>     |<span data-ttu-id="54407-478">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-478">Wait in lobby</span></span>         |
|   | <span data-ttu-id="54407-479">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="54407-479">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="54407-480">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="54407-480">Wait in lobby</span></span>         |


### <a name="enable-live-captions"></a><span data-ttu-id="54407-481">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="54407-481">Enable live captions</span></span>

<span data-ttu-id="54407-482">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="54407-482">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="54407-483">此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="54407-483">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="54407-485">設定值</span><span class="sxs-lookup"><span data-stu-id="54407-485">Setting value</span></span> |<span data-ttu-id="54407-486">行為</span><span class="sxs-lookup"><span data-stu-id="54407-486">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="54407-487">**已停用，但召集人可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="54407-487">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="54407-488">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="54407-488">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="54407-489">使用者會看到 [溢出（**...**）] 功能表中的 [**開啟即時標題**] 選項，以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="54407-489">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="54407-490">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="54407-490">This is the default setting.</span></span> |
|<span data-ttu-id="54407-491">**禁止**</span><span class="sxs-lookup"><span data-stu-id="54407-491">**Disabled**</span></span>     | <span data-ttu-id="54407-492">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="54407-492">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="54407-493">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="54407-493">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="54407-494"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="54407-494"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="54407-495">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="54407-495">Allow chat in meetings</span></span>

<span data-ttu-id="54407-496">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="54407-496">This is a per-organizer policy.</span></span> <span data-ttu-id="54407-497">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="54407-497">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="54407-498"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="54407-498"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="54407-499">會議原則設定-會議出席情況報告</span><span class="sxs-lookup"><span data-stu-id="54407-499">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="54407-500">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54407-500">This is a per-user policy.</span></span> <span data-ttu-id="54407-501">此設定控制會議召集人是否可以下載[會議出席情況報告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="54407-501">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="54407-502">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="54407-502">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="54407-503">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="54407-503">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="54407-504">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="54407-504">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="54407-505">若要讓會議召集人下載會議出席情況報告，請將**AllowEngagementReport**參數設定為 [**已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="54407-505">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="54407-506">啟用時，會在**參與者**窗格中顯示下載報告的選項。</span><span class="sxs-lookup"><span data-stu-id="54407-506">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="54407-507">若要避免會議召集人下載報表，請將參數設定為 [**已停用**]。</span><span class="sxs-lookup"><span data-stu-id="54407-507">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="54407-508">根據預設，此設定會停用，而且無法使用下載報表的選項。</span><span class="sxs-lookup"><span data-stu-id="54407-508">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="54407-509">相關主題</span><span class="sxs-lookup"><span data-stu-id="54407-509">Related topics</span></span>

- [<span data-ttu-id="54407-510">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="54407-510">Teams PowerShell overview</span></span>](teams-powershell-overview.md)