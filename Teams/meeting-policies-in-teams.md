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
ms.openlocfilehash: 689b22a98c986ca73ae3926785f75dcb6c6a9e74
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918702"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="a46d0-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="a46d0-104">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="a46d0-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="a46d0-105">建立原則並進行變更之後，您可以將使用者指派給該原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="a46d0-106">您可以在 Microsoft 團隊系統管理中心或使用[PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="a46d0-107">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="a46d0-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="a46d0-108">實現類型</span><span class="sxs-lookup"><span data-stu-id="a46d0-108">Implementation type</span></span>  |<span data-ttu-id="a46d0-109">說明</span><span class="sxs-lookup"><span data-stu-id="a46d0-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="a46d0-110">每個召集人</span><span class="sxs-lookup"><span data-stu-id="a46d0-110">Per-organizer</span></span>    |<span data-ttu-id="a46d0-111">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="a46d0-112">例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="a46d0-113">每位使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-113">Per-user</span></span>    |<span data-ttu-id="a46d0-114">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="a46d0-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="a46d0-115">例如，[**允許在頻道中立即開會**] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="a46d0-116">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="a46d0-117">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="a46d0-118">例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="a46d0-119">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="a46d0-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="a46d0-120">根據預設，會建立名為 [全域] （組織範圍預設值）的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="a46d0-121">貴組織中的所有使用者預設都會獲指派 [全域會議原則]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="a46d0-122">您可以對其進行變更或建立一或多個自訂原則，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="a46d0-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="a46d0-123">除非您建立並指派自訂原則，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="a46d0-124">當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將其指派給將設定套用至其中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>
<span data-ttu-id="a46d0-125">-注意-[會議詳細資料] 按鈕會 availiable 如果使用者已啟用 audioconference 授權，或使用者允許 audioconferencing，則不會 availiable 會議詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a46d0-125">-Note- Meeting details button will be availiable if a user has the audioconference licenses enabled or the user is allow for audioconferencing, if not, the meeting details will not be availiable</span></span>
## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="a46d0-126">變更或建立會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-126">Change or create a meeting policy</span></span>

<span data-ttu-id="a46d0-127">若要變更或建立會議原則，請移至 [Microsoft Teams 系統管理中心] > **[會議] \*\* > \*\* [會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="a46d0-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="a46d0-128">從清單中選取原則，或選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="a46d0-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="a46d0-129">如果您要建立新原則，請新增原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="a46d0-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="a46d0-130">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="a46d0-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="a46d0-131">選擇您的設定，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="a46d0-132">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="a46d0-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="a46d0-133">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="a46d0-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="a46d0-134">在 [音訊與視訊]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="a46d0-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="a46d0-135">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="a46d0-136">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="a46d0-137">在 [內容共用]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="a46d0-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="a46d0-138">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="a46d0-139">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="a46d0-140">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="a46d0-141">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="a46d0-142">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="a46d0-143">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-143">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="a46d0-144">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a46d0-145">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a46d0-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a46d0-146">在 [會議原則]\*\*\*\* 下，選取要指派的原則，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a46d0-146">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="a46d0-147">若要一次將原則指派給多個使用者，請參閱[大量編輯 Teams 使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="a46d0-147">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="a46d0-148">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a46d0-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a46d0-149">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議** > **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-149">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="a46d0-150">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="a46d0-151">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a46d0-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="a46d0-152">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="a46d0-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="a46d0-153">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="a46d0-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="a46d0-154">完成新增使用者之後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-154">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a46d0-155">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-155">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="a46d0-156">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-156">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="a46d0-157">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="a46d0-157">Meeting policy settings</span></span>

<span data-ttu-id="a46d0-158">當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增**] 以新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="a46d0-158">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="a46d0-159">一般</span><span class="sxs-lookup"><span data-stu-id="a46d0-159">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="a46d0-160">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="a46d0-160">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="a46d0-161">內容共用</span><span class="sxs-lookup"><span data-stu-id="a46d0-161">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="a46d0-162">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="a46d0-162">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="a46d0-163"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="a46d0-163"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="a46d0-164">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="a46d0-164">Meeting policy settings - General</span></span>

- <span data-ttu-id="a46d0-165">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="a46d0-165">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="a46d0-166">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="a46d0-166">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="a46d0-167">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="a46d0-167">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="a46d0-168">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="a46d0-168">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="a46d0-169">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="a46d0-169">Allow Meet now in channels</span></span>

<span data-ttu-id="a46d0-170">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-170">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a46d0-171">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-171">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="a46d0-172">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-172">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="a46d0-174">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="a46d0-174">Allow the Outlook add-in</span></span>

<span data-ttu-id="a46d0-175">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-175">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a46d0-176">此設定控制團隊會議是否可在 Outlook 中排程（Windows、Mac、web 及行動裝置）。</span><span class="sxs-lookup"><span data-stu-id="a46d0-176">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="a46d0-178">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-178">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="a46d0-179">例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="a46d0-179">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="a46d0-180">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="a46d0-180">Allow channel meeting scheduling</span></span>

<span data-ttu-id="a46d0-181">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-181">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a46d0-182">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-182">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="a46d0-183">如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。</span><span class="sxs-lookup"><span data-stu-id="a46d0-183">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="a46d0-186">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="a46d0-186">Allow scheduling private meetings</span></span>

<span data-ttu-id="a46d0-187">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-187">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a46d0-188">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-188">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="a46d0-189">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="a46d0-189">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="a46d0-190">請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。</span><span class="sxs-lookup"><span data-stu-id="a46d0-190">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="a46d0-191"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="a46d0-191"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="a46d0-192">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="a46d0-192">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="a46d0-193">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="a46d0-193">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="a46d0-194">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="a46d0-194">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="a46d0-195">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="a46d0-195">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="a46d0-196">媒體位元速率（Kps）</span><span class="sxs-lookup"><span data-stu-id="a46d0-196">Media bit rate (Kps)</span></span>](#media-bit-rate-kps)

### <a name="allow-transcription"></a><span data-ttu-id="a46d0-197">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="a46d0-197">Allow transcription</span></span>

<span data-ttu-id="a46d0-198">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="a46d0-198">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="a46d0-199">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="a46d0-199">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="a46d0-200">如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="a46d0-200">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="a46d0-201">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="a46d0-201">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="a46d0-202">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-202">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="a46d0-204">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="a46d0-204">Allow cloud recording</span></span>

<span data-ttu-id="a46d0-205">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="a46d0-205">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="a46d0-206">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-206">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="a46d0-207">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="a46d0-207">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="a46d0-208">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="a46d0-208">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="a46d0-209">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="a46d0-209">Guest users can't start or stop the recording.</span></span> 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="a46d0-211">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="a46d0-211">Let's look at the following example.</span></span>

|<span data-ttu-id="a46d0-212">使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-212">User</span></span> |<span data-ttu-id="a46d0-213">會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-213">Meeting policy</span></span>  |<span data-ttu-id="a46d0-214">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="a46d0-214">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-215">Daniela</span><span class="sxs-lookup"><span data-stu-id="a46d0-215">Daniela</span></span> | <span data-ttu-id="a46d0-216">全域</span><span class="sxs-lookup"><span data-stu-id="a46d0-216">Global</span></span>   | <span data-ttu-id="a46d0-217">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-217">False</span></span> |
|<span data-ttu-id="a46d0-218">Amanda</span><span class="sxs-lookup"><span data-stu-id="a46d0-218">Amanda</span></span> | <span data-ttu-id="a46d0-219">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a46d0-219">Location1MeetingPolicy</span></span> | <span data-ttu-id="a46d0-220">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-220">True</span></span>|
|<span data-ttu-id="a46d0-221">約翰（外部使用者）</span><span class="sxs-lookup"><span data-stu-id="a46d0-221">John (external user)</span></span> | <span data-ttu-id="a46d0-222">不適用</span><span class="sxs-lookup"><span data-stu-id="a46d0-222">Not applicable</span></span> | <span data-ttu-id="a46d0-223">不適用</span><span class="sxs-lookup"><span data-stu-id="a46d0-223">Not applicable</span></span>|

<span data-ttu-id="a46d0-224">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-224">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="a46d0-225">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-225">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="a46d0-226">若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="a46d0-226">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="a46d0-227">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="a46d0-227">Allow IP video</span></span>

<span data-ttu-id="a46d0-228">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="a46d0-228">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="a46d0-229">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="a46d0-229">Video is a key component to meetings.</span></span> <span data-ttu-id="a46d0-230">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-230">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="a46d0-231">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-231">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="a46d0-232">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-232">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="a46d0-233">沒有指派任何原則的會議參與者（例如匿名及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-233">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="a46d0-235">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="a46d0-235">Let's look at the following example.</span></span>

|<span data-ttu-id="a46d0-236">使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-236">User</span></span> |<span data-ttu-id="a46d0-237">會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-237">Meeting policy</span></span>  |<span data-ttu-id="a46d0-238">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="a46d0-238">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-239">Daniela</span><span class="sxs-lookup"><span data-stu-id="a46d0-239">Daniela</span></span>   | <span data-ttu-id="a46d0-240">全域</span><span class="sxs-lookup"><span data-stu-id="a46d0-240">Global</span></span>   | <span data-ttu-id="a46d0-241">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-241">True</span></span>        |
|<span data-ttu-id="a46d0-242">Amanda</span><span class="sxs-lookup"><span data-stu-id="a46d0-242">Amanda</span></span>    | <span data-ttu-id="a46d0-243">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a46d0-243">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a46d0-244">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-244">False</span></span>      |

<span data-ttu-id="a46d0-245">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-245">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="a46d0-246">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-246">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="a46d0-247">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="a46d0-247">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="a46d0-248">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-248">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="a46d0-249">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-249">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="a46d0-250">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-250">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="a46d0-251">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="a46d0-251">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="a46d0-252">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-252">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="a46d0-253">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="a46d0-253">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="a46d0-254">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-254">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kps"></a><span data-ttu-id="a46d0-255">媒體位元速率（Kps）</span><span class="sxs-lookup"><span data-stu-id="a46d0-255">Media bit rate (Kps)</span></span>

<span data-ttu-id="a46d0-256">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-256">This is a per-user policy.</span></span> <span data-ttu-id="a46d0-257">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="a46d0-257">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="a46d0-258">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="a46d0-258">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="a46d0-259">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="a46d0-259">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="a46d0-260">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="a46d0-260">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="a46d0-261">最小值為30個 Kps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="a46d0-261">The minimum value is 30 Kps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="a46d0-262">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="a46d0-262">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="a46d0-263">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="a46d0-263">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="a46d0-264">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="a46d0-264">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="a46d0-265">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="a46d0-265">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="a46d0-266">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="a46d0-266">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="a46d0-267">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="a46d0-267">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="a46d0-268">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="a46d0-268">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="a46d0-269">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="a46d0-269">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="a46d0-270">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="a46d0-270">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="a46d0-271">允許白板</span><span class="sxs-lookup"><span data-stu-id="a46d0-271">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="a46d0-272">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="a46d0-272">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="a46d0-273">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="a46d0-273">Screen sharing mode</span></span>

<span data-ttu-id="a46d0-274">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="a46d0-274">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="a46d0-275">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-275">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="a46d0-276">沒有指派任何原則的會議參與者（例如，匿名、來賓、B2B 及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-276">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="a46d0-277">設定值</span><span class="sxs-lookup"><span data-stu-id="a46d0-277">Setting value</span></span> |<span data-ttu-id="a46d0-278">行為</span><span class="sxs-lookup"><span data-stu-id="a46d0-278">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="a46d0-279">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="a46d0-279">**Entire screen**</span></span>    | <span data-ttu-id="a46d0-280">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="a46d0-280">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="a46d0-281">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="a46d0-281">**Single application**</span></span>   | <span data-ttu-id="a46d0-282">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="a46d0-282">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="a46d0-283">**禁止**</span><span class="sxs-lookup"><span data-stu-id="a46d0-283">**Disabled**</span></span>     |<span data-ttu-id="a46d0-284">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-284">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="a46d0-285">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="a46d0-285">Let's look at the following example.</span></span>

|<span data-ttu-id="a46d0-286">使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-286">User</span></span> |<span data-ttu-id="a46d0-287">會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-287">Meeting policy</span></span> |<span data-ttu-id="a46d0-288">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="a46d0-288">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-289">Daniela</span><span class="sxs-lookup"><span data-stu-id="a46d0-289">Daniela</span></span>  | <span data-ttu-id="a46d0-290">全域</span><span class="sxs-lookup"><span data-stu-id="a46d0-290">Global</span></span>   | <span data-ttu-id="a46d0-291">整個畫面</span><span class="sxs-lookup"><span data-stu-id="a46d0-291">Entire screen</span></span> |
|<span data-ttu-id="a46d0-292">Amanda</span><span class="sxs-lookup"><span data-stu-id="a46d0-292">Amanda</span></span>   | <span data-ttu-id="a46d0-293">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a46d0-293">Location1MeetingPolicy</span></span>  | <span data-ttu-id="a46d0-294">禁止</span><span class="sxs-lookup"><span data-stu-id="a46d0-294">Disabled</span></span> |

<span data-ttu-id="a46d0-295">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a46d0-295">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="a46d0-296">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-296">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="a46d0-297">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="a46d0-297">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="a46d0-298">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="a46d0-298">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="a46d0-299">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="a46d0-299">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="a46d0-300">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="a46d0-300">Allow a participant to give or request control</span></span>

<span data-ttu-id="a46d0-301">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-301">This is a per-user policy.</span></span> <span data-ttu-id="a46d0-302">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-302">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="a46d0-303">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="a46d0-303">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="a46d0-304">如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="a46d0-304">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="a46d0-306">如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="a46d0-306">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="a46d0-308">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="a46d0-308">Let's look at the following example.</span></span>

|<span data-ttu-id="a46d0-309">使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-309">User</span></span> |<span data-ttu-id="a46d0-310">會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-310">Meeting policy</span></span>  |<span data-ttu-id="a46d0-311">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="a46d0-311">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-312">Daniela</span><span class="sxs-lookup"><span data-stu-id="a46d0-312">Daniela</span></span>   | <span data-ttu-id="a46d0-313">全域</span><span class="sxs-lookup"><span data-stu-id="a46d0-313">Global</span></span>   | <span data-ttu-id="a46d0-314">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-314">True</span></span>       |
|<span data-ttu-id="a46d0-315">Babek</span><span class="sxs-lookup"><span data-stu-id="a46d0-315">Babek</span></span>    | <span data-ttu-id="a46d0-316">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a46d0-316">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a46d0-317">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-317">False</span></span>   |

<span data-ttu-id="a46d0-318">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-318">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="a46d0-319">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a46d0-319">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a46d0-320">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="a46d0-320">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="a46d0-321">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="a46d0-321">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="a46d0-322">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="a46d0-322">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="a46d0-323">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="a46d0-323">Allow an external participant to give or request control</span></span>

<span data-ttu-id="a46d0-324">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-324">This is a per-user policy.</span></span> <span data-ttu-id="a46d0-325">此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-325">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="a46d0-326">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="a46d0-326">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="a46d0-327">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-327">Anonymous user</span></span>
- <span data-ttu-id="a46d0-328">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-328">Guest users</span></span>  
- <span data-ttu-id="a46d0-329">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-329">B2B user</span></span>
- <span data-ttu-id="a46d0-330">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-330">Federated user</span></span>  

<span data-ttu-id="a46d0-331">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。</span><span class="sxs-lookup"><span data-stu-id="a46d0-331">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="a46d0-332">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a46d0-332">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="a46d0-333">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="a46d0-333">Allow PowerPoint sharing</span></span>

<span data-ttu-id="a46d0-334">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-334">This is a per-user policy.</span></span> <span data-ttu-id="a46d0-335">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="a46d0-335">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="a46d0-336">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-336">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="a46d0-337">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="a46d0-337">Let's look at the following example.</span></span>

|<span data-ttu-id="a46d0-338">使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-338">User</span></span> |<span data-ttu-id="a46d0-339">會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-339">Meeting policy</span></span>  |<span data-ttu-id="a46d0-340">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="a46d0-340">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-341">Daniela</span><span class="sxs-lookup"><span data-stu-id="a46d0-341">Daniela</span></span>   | <span data-ttu-id="a46d0-342">全域</span><span class="sxs-lookup"><span data-stu-id="a46d0-342">Global</span></span>   | <span data-ttu-id="a46d0-343">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-343">True</span></span>       |
|<span data-ttu-id="a46d0-344">Amanda</span><span class="sxs-lookup"><span data-stu-id="a46d0-344">Amanda</span></span>   | <span data-ttu-id="a46d0-345">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a46d0-345">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a46d0-346">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-346">False</span></span>   |

<span data-ttu-id="a46d0-347">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="a46d0-347">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="a46d0-348">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="a46d0-348">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="a46d0-349">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="a46d0-349">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="a46d0-350">允許白板</span><span class="sxs-lookup"><span data-stu-id="a46d0-350">Allow whiteboard</span></span>

<span data-ttu-id="a46d0-351">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-351">This is a per-user policy.</span></span> <span data-ttu-id="a46d0-352">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="a46d0-352">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="a46d0-353">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-353">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="a46d0-354">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="a46d0-354">Let's look at the following example.</span></span>

|<span data-ttu-id="a46d0-355">使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-355">User</span></span> |<span data-ttu-id="a46d0-356">會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-356">Meeting policy</span></span>  |<span data-ttu-id="a46d0-357">允許白板</span><span class="sxs-lookup"><span data-stu-id="a46d0-357">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a46d0-358">Daniela</span><span class="sxs-lookup"><span data-stu-id="a46d0-358">Daniela</span></span>   | <span data-ttu-id="a46d0-359">全域</span><span class="sxs-lookup"><span data-stu-id="a46d0-359">Global</span></span>   | <span data-ttu-id="a46d0-360">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-360">True</span></span>       |
|<span data-ttu-id="a46d0-361">Amanda</span><span class="sxs-lookup"><span data-stu-id="a46d0-361">Amanda</span></span>   | <span data-ttu-id="a46d0-362">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a46d0-362">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a46d0-363">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-363">False</span></span>   |

<span data-ttu-id="a46d0-364">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="a46d0-364">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="a46d0-365">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="a46d0-365">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="a46d0-366">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="a46d0-366">Allow shared notes</span></span>

<span data-ttu-id="a46d0-367">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-367">This is a per-user policy.</span></span> <span data-ttu-id="a46d0-368">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="a46d0-368">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="a46d0-369">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-369">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="a46d0-370">目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a46d0-370">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="a46d0-371">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="a46d0-371">Let's look at the following example.</span></span>

|<span data-ttu-id="a46d0-372">使用者</span><span class="sxs-lookup"><span data-stu-id="a46d0-372">User</span></span> |<span data-ttu-id="a46d0-373">會議原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-373">Meeting policy</span></span>  |<span data-ttu-id="a46d0-374">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="a46d0-374">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-375">Daniela</span><span class="sxs-lookup"><span data-stu-id="a46d0-375">Daniela</span></span>   | <span data-ttu-id="a46d0-376">全域</span><span class="sxs-lookup"><span data-stu-id="a46d0-376">Global</span></span>   | <span data-ttu-id="a46d0-377">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-377">True</span></span>       |
|<span data-ttu-id="a46d0-378">Amanda</span><span class="sxs-lookup"><span data-stu-id="a46d0-378">Amanda</span></span>   | <span data-ttu-id="a46d0-379">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a46d0-379">Location1MeetingPolicy</span></span> | <span data-ttu-id="a46d0-380">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-380">False</span></span> |

<span data-ttu-id="a46d0-381">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="a46d0-381">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="a46d0-382">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="a46d0-382">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="a46d0-383">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="a46d0-383">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="a46d0-384">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="a46d0-384">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="a46d0-385">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="a46d0-385">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="a46d0-386">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="a46d0-386">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="a46d0-387">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="a46d0-387">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="a46d0-388">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="a46d0-388">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="a46d0-389">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="a46d0-389">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="a46d0-390">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="a46d0-390">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="a46d0-391">如果您的群組有音訊會議，且使用它來連接，請參閱[Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="a46d0-391">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="a46d0-392">如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="a46d0-392">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="a46d0-393">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="a46d0-393">Let anonymous people start a meeting</span></span>

<span data-ttu-id="a46d0-394">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-394">This is a per-organizer policy.</span></span> <span data-ttu-id="a46d0-395">此設定會控制匿名人員（包括 B2B）與同盟使用者，是否可在沒有已驗證的使用者的情況下，從出席中的組織加入使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-395">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![螢幕擷取畫面顯示等候使用者的訊息](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="a46d0-397">以下是在會議中有驗證使用者的情況下匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="a46d0-397">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="a46d0-398">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="a46d0-398">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="a46d0-399">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="a46d0-399">Automatically admit people</span></span> |<span data-ttu-id="a46d0-400">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="a46d0-400">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-401">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-401">True</span></span>    | <span data-ttu-id="a46d0-402">任何人</span><span class="sxs-lookup"><span data-stu-id="a46d0-402">Everyone</span></span>      | <span data-ttu-id="a46d0-403">直接加入</span><span class="sxs-lookup"><span data-stu-id="a46d0-403">Join directly</span></span>         |
|   | <span data-ttu-id="a46d0-404">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-404">Everyone in your organization</span></span>       | <span data-ttu-id="a46d0-405">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-405">Wait in lobby</span></span>        |
|   | <span data-ttu-id="a46d0-406">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-406">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="a46d0-407">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-407">Wait in lobby</span></span>         |
|<span data-ttu-id="a46d0-408">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-408">False</span></span>    | <span data-ttu-id="a46d0-409">任何人</span><span class="sxs-lookup"><span data-stu-id="a46d0-409">Everyone</span></span>        | <span data-ttu-id="a46d0-410">直接加入</span><span class="sxs-lookup"><span data-stu-id="a46d0-410">Join directly</span></span>        |
|   | <span data-ttu-id="a46d0-411">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-411">Everyone in your organization</span></span>     | <span data-ttu-id="a46d0-412">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-412">Wait in lobby</span></span>        |
|   | <span data-ttu-id="a46d0-413">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-413">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="a46d0-414">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-414">Wait in lobby</span></span>         |

<span data-ttu-id="a46d0-415">以下是在會議中沒有經過驗證的使用者時，匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="a46d0-415">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="a46d0-416">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="a46d0-416">Let anonymous people start a meeting</span></span> |<span data-ttu-id="a46d0-417">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="a46d0-417">Automatically admit people</span></span>  |<span data-ttu-id="a46d0-418">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="a46d0-418">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-419">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-419">True</span></span>    | <span data-ttu-id="a46d0-420">任何人</span><span class="sxs-lookup"><span data-stu-id="a46d0-420">Everyone</span></span>      | <span data-ttu-id="a46d0-421">直接加入</span><span class="sxs-lookup"><span data-stu-id="a46d0-421">Join directly</span></span>         |
|   | <span data-ttu-id="a46d0-422">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-422">Everyone in your organization</span></span>       | <span data-ttu-id="a46d0-423">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-423">Wait in lobby</span></span>        |
|   | <span data-ttu-id="a46d0-424">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-424">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="a46d0-425">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-425">Wait in lobby</span></span>         |
|<span data-ttu-id="a46d0-426">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-426">False</span></span>    | <span data-ttu-id="a46d0-427">任何人</span><span class="sxs-lookup"><span data-stu-id="a46d0-427">Everyone</span></span>        | <span data-ttu-id="a46d0-428">在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="a46d0-428">Wait in lobby.</span></span> <span data-ttu-id="a46d0-429">當第一個經過驗證的使用者加入會議時，系統會自動准許使用者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-429">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="a46d0-430">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-430">Everyone in your organization</span></span>     |<span data-ttu-id="a46d0-431">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-431">Wait in lobby</span></span>         |
|   | <span data-ttu-id="a46d0-432">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-432">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="a46d0-433">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-433">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="a46d0-434">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="a46d0-434">Automatically admit people</span></span>

<span data-ttu-id="a46d0-435">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-435">This is a per-organizer policy.</span></span> <span data-ttu-id="a46d0-436">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="a46d0-436">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="a46d0-438">會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="a46d0-438">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="a46d0-439">設定值</span><span class="sxs-lookup"><span data-stu-id="a46d0-439">Setting value</span></span>  |<span data-ttu-id="a46d0-440">加入行為</span><span class="sxs-lookup"><span data-stu-id="a46d0-440">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="a46d0-441">**任何人**</span><span class="sxs-lookup"><span data-stu-id="a46d0-441">**Everyone**</span></span>   |<span data-ttu-id="a46d0-442">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="a46d0-442">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="a46d0-443">這包括經過驗證的使用者、聯盟使用者、來賓、匿名使用者，以及透過電話撥入的人員。</span><span class="sxs-lookup"><span data-stu-id="a46d0-443">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="a46d0-444">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="a46d0-444">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="a46d0-445">組織內經過驗證的使用者，包括來賓使用者以及來自同盟組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="a46d0-445">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="a46d0-446">在大廳由手機撥入的匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-446">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="a46d0-447">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="a46d0-447">**Everyone in your organization**</span></span>    |<span data-ttu-id="a46d0-448">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="a46d0-448">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="a46d0-449">在大廳以電話撥入的聯盟使用者、匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="a46d0-449">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="a46d0-450">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="a46d0-450">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="a46d0-451">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-451">This is a per-organizer policy.</span></span> <span data-ttu-id="a46d0-452">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="a46d0-452">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="a46d0-453">以下是透過電話撥入的人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="a46d0-453">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="a46d0-454">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="a46d0-454">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="a46d0-455">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="a46d0-455">Automatically admit people</span></span>  |<span data-ttu-id="a46d0-456">撥入之人的加入行為</span><span class="sxs-lookup"><span data-stu-id="a46d0-456">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a46d0-457">滿足</span><span class="sxs-lookup"><span data-stu-id="a46d0-457">True</span></span>    | <span data-ttu-id="a46d0-458">任何人</span><span class="sxs-lookup"><span data-stu-id="a46d0-458">Everyone</span></span>      | <span data-ttu-id="a46d0-459">直接加入</span><span class="sxs-lookup"><span data-stu-id="a46d0-459">Join directly</span></span>         |
|   | <span data-ttu-id="a46d0-460">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-460">Everyone in your organization</span></span>       | <span data-ttu-id="a46d0-461">直接加入</span><span class="sxs-lookup"><span data-stu-id="a46d0-461">Join directly</span></span>        |
|   | <span data-ttu-id="a46d0-462">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-462">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="a46d0-463">直接加入</span><span class="sxs-lookup"><span data-stu-id="a46d0-463">Join directly</span></span>         |
|<span data-ttu-id="a46d0-464">虛假</span><span class="sxs-lookup"><span data-stu-id="a46d0-464">False</span></span>    | <span data-ttu-id="a46d0-465">任何人</span><span class="sxs-lookup"><span data-stu-id="a46d0-465">Everyone</span></span>        | <span data-ttu-id="a46d0-466">直接加入</span><span class="sxs-lookup"><span data-stu-id="a46d0-466">Join directly</span></span>        |
|   | <span data-ttu-id="a46d0-467">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-467">Everyone in your organization</span></span>     |<span data-ttu-id="a46d0-468">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-468">Wait in lobby</span></span>         |
|   | <span data-ttu-id="a46d0-469">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="a46d0-469">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="a46d0-470">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="a46d0-470">Wait in lobby</span></span>         |

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="a46d0-471">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="a46d0-471">Allow Meet now in private meetings</span></span>

<span data-ttu-id="a46d0-472">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="a46d0-472">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a46d0-473">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="a46d0-473">This setting controls whether a user can start an ad hoc private meeting.</span></span> 

### <a name="enable-live-captions"></a><span data-ttu-id="a46d0-474">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="a46d0-474">Enable live captions</span></span>

<span data-ttu-id="a46d0-475">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="a46d0-475">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="a46d0-476">此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="a46d0-476">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="a46d0-478">設定值</span><span class="sxs-lookup"><span data-stu-id="a46d0-478">Setting value</span></span> |<span data-ttu-id="a46d0-479">行為</span><span class="sxs-lookup"><span data-stu-id="a46d0-479">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="a46d0-480">**已停用，但召集人可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="a46d0-480">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="a46d0-481">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="a46d0-481">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="a46d0-482">使用者會看到 [溢出（**...**）] 功能表中的 [**開啟即時標題**] 選項，以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="a46d0-482">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="a46d0-483">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="a46d0-483">This is the default setting.</span></span> |
|<span data-ttu-id="a46d0-484">**禁止**</span><span class="sxs-lookup"><span data-stu-id="a46d0-484">**Disabled**</span></span>     | <span data-ttu-id="a46d0-485">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="a46d0-485">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="a46d0-486">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="a46d0-486">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="a46d0-487"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="a46d0-487"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="a46d0-488">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="a46d0-488">Allow chat in meetings</span></span>

<span data-ttu-id="a46d0-489">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="a46d0-489">This is a per-organizer policy.</span></span> <span data-ttu-id="a46d0-490">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="a46d0-490">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="a46d0-491"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="a46d0-491"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="a46d0-492">相關主題</span><span class="sxs-lookup"><span data-stu-id="a46d0-492">Related topics</span></span>

[<span data-ttu-id="a46d0-493">小組中的訊息原則</span><span class="sxs-lookup"><span data-stu-id="a46d0-493">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
