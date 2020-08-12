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
ms.openlocfilehash: c617669cdb5b0ee9f5a7acd52c2c9064b9cbc88e
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640958"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="02724-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="02724-104">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="02724-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="02724-105">您可以使用全域 (組織範圍的預設) 原則，此原則會自動建立或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="02724-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="02724-106">您可以在 Microsoft 團隊系統管理中心或使用[PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="02724-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="02724-107">如需使用角色來管理會議簡報者與出席者權限的相關資訊，請參閱[小組會議中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="02724-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="02724-108">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="02724-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="02724-109">實現類型</span><span class="sxs-lookup"><span data-stu-id="02724-109">Implementation type</span></span>  |<span data-ttu-id="02724-110">描述</span><span class="sxs-lookup"><span data-stu-id="02724-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="02724-111">每個召集人</span><span class="sxs-lookup"><span data-stu-id="02724-111">Per-organizer</span></span>    |<span data-ttu-id="02724-112">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="02724-113">例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="02724-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="02724-114">每位使用者</span><span class="sxs-lookup"><span data-stu-id="02724-114">Per-user</span></span>    |<span data-ttu-id="02724-115">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="02724-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="02724-116">例如，[**允許在頻道中立即開會**] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="02724-117">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="02724-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="02724-118">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="02724-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="02724-119">例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="02724-120">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="02724-120">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="02724-121">您可以編輯全域原則中的設定，或是建立並指派一或多個自訂原則。</span><span class="sxs-lookup"><span data-stu-id="02724-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="02724-122">除非您建立並指派自訂原則，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="02724-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="02724-123">如果使用者已啟用音訊會議授權，或使用者允許音訊會議，則 [會議詳細資料] 按鈕就會提供，會議詳細資料將無法使用。</span><span class="sxs-lookup"><span data-stu-id="02724-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="02724-124">建立自訂會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="02724-125">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="02724-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="02724-126">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="02724-126">Click **Add**.</span></span>
3. <span data-ttu-id="02724-127">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="02724-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="02724-128">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="02724-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="02724-129">選擇您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="02724-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="02724-130">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02724-130">Click **Save**.</span></span>

<span data-ttu-id="02724-131">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="02724-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="02724-132">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="02724-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="02724-133">在 [音訊與視訊]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="02724-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="02724-134">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="02724-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="02724-135">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="02724-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="02724-136">在 [內容共用]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="02724-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="02724-137">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="02724-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="02724-138">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="02724-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="02724-139">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="02724-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="02724-140">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="02724-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="02724-141">編輯會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-141">Edit a meeting policy</span></span>

<span data-ttu-id="02724-142">您可以為全域原則編輯您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="02724-142">You can edit the global policy an any custom policies that you create.</span></span> 

1. <span data-ttu-id="02724-143">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="02724-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="02724-144">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="02724-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="02724-145">您可以從這裡進行所要的變更。</span><span class="sxs-lookup"><span data-stu-id="02724-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="02724-146">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02724-146">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="02724-147">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="02724-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="02724-148">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="02724-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="02724-149">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="02724-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="02724-150">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="02724-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="02724-151">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="02724-151">Meeting policy settings</span></span>

<span data-ttu-id="02724-152">當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增**] 以新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="02724-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="02724-153">一般</span><span class="sxs-lookup"><span data-stu-id="02724-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="02724-154">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="02724-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="02724-155">內容共用</span><span class="sxs-lookup"><span data-stu-id="02724-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="02724-156">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="02724-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="02724-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="02724-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="02724-158">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="02724-158">Meeting policy settings - General</span></span>

- <span data-ttu-id="02724-159">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="02724-159">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="02724-160">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="02724-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="02724-161">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="02724-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="02724-162">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="02724-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="02724-163">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="02724-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="02724-164">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="02724-164">Allow Meet now in channels</span></span>

<span data-ttu-id="02724-165">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="02724-165">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="02724-166">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="02724-166">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="02724-167">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="02724-167">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="02724-168">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="02724-168">The default value is True.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="02724-170">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="02724-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="02724-171">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="02724-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="02724-172">此設定可控制團隊會議是否可以在 Outlook (Windows、Mac、web 及行動裝置) 中排程。</span><span class="sxs-lookup"><span data-stu-id="02724-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="02724-174">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="02724-174">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="02724-175">例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="02724-175">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="02724-176">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="02724-176">Allow channel meeting scheduling</span></span>

<span data-ttu-id="02724-177">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="02724-177">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="02724-178">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="02724-178">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="02724-179">如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。</span><span class="sxs-lookup"><span data-stu-id="02724-179">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="02724-180">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="02724-180">The default value is True.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="02724-183">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="02724-183">Allow scheduling private meetings</span></span>

<span data-ttu-id="02724-184">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="02724-184">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="02724-185">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="02724-185">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="02724-186">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="02724-186">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="02724-187">請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。</span><span class="sxs-lookup"><span data-stu-id="02724-187">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="02724-188">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="02724-188">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="02724-189">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="02724-189">Allow Meet now in private meetings</span></span>

<span data-ttu-id="02724-190">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="02724-190">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="02724-191">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="02724-191">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="02724-192">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="02724-192">The default value is True.</span></span>

<span data-ttu-id="02724-193"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="02724-193"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="02724-194">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="02724-194">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="02724-195">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="02724-195">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="02724-196">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="02724-196">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="02724-197">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="02724-197">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="02724-198">媒體位元速率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="02724-198">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="02724-199">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="02724-199">Allow transcription</span></span>

<span data-ttu-id="02724-200">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="02724-200">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="02724-201">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="02724-201">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="02724-202">如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="02724-202">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="02724-203">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="02724-203">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="02724-204">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="02724-204">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="02724-206">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="02724-206">Allow cloud recording</span></span>

<span data-ttu-id="02724-207">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="02724-207">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="02724-208">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="02724-208">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="02724-209">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="02724-209">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="02724-210">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="02724-210">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="02724-211">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="02724-211">Guest users can't start or stop the recording.</span></span> 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="02724-213">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="02724-213">Let's look at the following example.</span></span>

|<span data-ttu-id="02724-214">使用者</span><span class="sxs-lookup"><span data-stu-id="02724-214">User</span></span> |<span data-ttu-id="02724-215">會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-215">Meeting policy</span></span>  |<span data-ttu-id="02724-216">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="02724-216">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="02724-217">Daniela</span><span class="sxs-lookup"><span data-stu-id="02724-217">Daniela</span></span> | <span data-ttu-id="02724-218">全域</span><span class="sxs-lookup"><span data-stu-id="02724-218">Global</span></span>   | <span data-ttu-id="02724-219">虛假</span><span class="sxs-lookup"><span data-stu-id="02724-219">False</span></span> |
|<span data-ttu-id="02724-220">Amanda</span><span class="sxs-lookup"><span data-stu-id="02724-220">Amanda</span></span> | <span data-ttu-id="02724-221">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="02724-221">Location1MeetingPolicy</span></span> | <span data-ttu-id="02724-222">滿足</span><span class="sxs-lookup"><span data-stu-id="02724-222">True</span></span>|
|<span data-ttu-id="02724-223">John (外部使用者) </span><span class="sxs-lookup"><span data-stu-id="02724-223">John (external user)</span></span> | <span data-ttu-id="02724-224">不適用</span><span class="sxs-lookup"><span data-stu-id="02724-224">Not applicable</span></span> | <span data-ttu-id="02724-225">不適用</span><span class="sxs-lookup"><span data-stu-id="02724-225">Not applicable</span></span>|

<span data-ttu-id="02724-226">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="02724-226">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="02724-227">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="02724-227">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="02724-228">若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="02724-228">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="02724-229">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="02724-229">Allow IP video</span></span>

<span data-ttu-id="02724-230">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="02724-230">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="02724-231">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="02724-231">Video is a key component to meetings.</span></span> <span data-ttu-id="02724-232">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="02724-232">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="02724-233">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="02724-233">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="02724-234">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="02724-234">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="02724-235">沒有指派任何原則的會議參與者 (例如，匿名和聯盟參與者) 繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-235">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="02724-237">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="02724-237">Let's look at the following example.</span></span>

|<span data-ttu-id="02724-238">使用者</span><span class="sxs-lookup"><span data-stu-id="02724-238">User</span></span> |<span data-ttu-id="02724-239">會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-239">Meeting policy</span></span>  |<span data-ttu-id="02724-240">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="02724-240">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="02724-241">Daniela</span><span class="sxs-lookup"><span data-stu-id="02724-241">Daniela</span></span>   | <span data-ttu-id="02724-242">全域</span><span class="sxs-lookup"><span data-stu-id="02724-242">Global</span></span>   | <span data-ttu-id="02724-243">滿足</span><span class="sxs-lookup"><span data-stu-id="02724-243">True</span></span>        |
|<span data-ttu-id="02724-244">Amanda</span><span class="sxs-lookup"><span data-stu-id="02724-244">Amanda</span></span>    | <span data-ttu-id="02724-245">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="02724-245">Location1MeetingPolicy</span></span>        | <span data-ttu-id="02724-246">虛假</span><span class="sxs-lookup"><span data-stu-id="02724-246">False</span></span>      |

<span data-ttu-id="02724-247">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="02724-247">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="02724-248">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="02724-248">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="02724-249">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="02724-249">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="02724-250">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="02724-250">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="02724-251">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="02724-251">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="02724-252">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="02724-252">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="02724-253">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="02724-253">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="02724-254">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="02724-254">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="02724-255">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="02724-255">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="02724-256">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="02724-256">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="02724-257">媒體位元速率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="02724-257">Media bit rate (Kbs)</span></span>

<span data-ttu-id="02724-258">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-258">This is a per-user policy.</span></span> <span data-ttu-id="02724-259">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="02724-259">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="02724-260">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="02724-260">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="02724-261">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="02724-261">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="02724-262">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="02724-262">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="02724-263">最小值為 30 Kbps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="02724-263">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="02724-264">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="02724-264">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="02724-265">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="02724-265">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="02724-266">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="02724-266">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="02724-267">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="02724-267">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="02724-268">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="02724-268">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="02724-269">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="02724-269">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="02724-270">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="02724-270">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="02724-271">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="02724-271">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="02724-272">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="02724-272">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="02724-273">允許白板</span><span class="sxs-lookup"><span data-stu-id="02724-273">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="02724-274">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="02724-274">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="02724-275">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="02724-275">Screen sharing mode</span></span>

<span data-ttu-id="02724-276">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="02724-276">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="02724-277">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="02724-277">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="02724-278">沒有任何 (指派任何原則的會議參與者（例如匿名、來賓、B2B 及同盟參與者）) 會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-278">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="02724-279">設定值</span><span class="sxs-lookup"><span data-stu-id="02724-279">Setting value</span></span> |<span data-ttu-id="02724-280">行為</span><span class="sxs-lookup"><span data-stu-id="02724-280">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="02724-281">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="02724-281">**Entire screen**</span></span>    | <span data-ttu-id="02724-282">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="02724-282">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="02724-283">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="02724-283">**Single application**</span></span>   | <span data-ttu-id="02724-284">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="02724-284">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="02724-285">**禁止**</span><span class="sxs-lookup"><span data-stu-id="02724-285">**Disabled**</span></span>     |<span data-ttu-id="02724-286">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="02724-286">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="02724-287">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="02724-287">Let's look at the following example.</span></span>

|<span data-ttu-id="02724-288">使用者</span><span class="sxs-lookup"><span data-stu-id="02724-288">User</span></span> |<span data-ttu-id="02724-289">會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-289">Meeting policy</span></span> |<span data-ttu-id="02724-290">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="02724-290">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="02724-291">Daniela</span><span class="sxs-lookup"><span data-stu-id="02724-291">Daniela</span></span>  | <span data-ttu-id="02724-292">全域</span><span class="sxs-lookup"><span data-stu-id="02724-292">Global</span></span>   | <span data-ttu-id="02724-293">整個畫面</span><span class="sxs-lookup"><span data-stu-id="02724-293">Entire screen</span></span> |
|<span data-ttu-id="02724-294">Amanda</span><span class="sxs-lookup"><span data-stu-id="02724-294">Amanda</span></span>   | <span data-ttu-id="02724-295">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="02724-295">Location1MeetingPolicy</span></span>  | <span data-ttu-id="02724-296">禁止</span><span class="sxs-lookup"><span data-stu-id="02724-296">Disabled</span></span> |

<span data-ttu-id="02724-297">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="02724-297">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="02724-298">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="02724-298">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="02724-299">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="02724-299">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="02724-300">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="02724-300">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="02724-301">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="02724-301">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="02724-302">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="02724-302">Allow a participant to give or request control</span></span>

<span data-ttu-id="02724-303">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-303">This is a per-user policy.</span></span> <span data-ttu-id="02724-304">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="02724-304">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="02724-305">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="02724-305">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="02724-306">如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="02724-306">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="02724-308">如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="02724-308">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="02724-310">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="02724-310">Let's look at the following example.</span></span>

|<span data-ttu-id="02724-311">使用者</span><span class="sxs-lookup"><span data-stu-id="02724-311">User</span></span> |<span data-ttu-id="02724-312">會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-312">Meeting policy</span></span>  |<span data-ttu-id="02724-313">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="02724-313">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="02724-314">Daniela</span><span class="sxs-lookup"><span data-stu-id="02724-314">Daniela</span></span>   | <span data-ttu-id="02724-315">全域</span><span class="sxs-lookup"><span data-stu-id="02724-315">Global</span></span>   | <span data-ttu-id="02724-316">滿足</span><span class="sxs-lookup"><span data-stu-id="02724-316">True</span></span>       |
|<span data-ttu-id="02724-317">Babek</span><span class="sxs-lookup"><span data-stu-id="02724-317">Babek</span></span>    | <span data-ttu-id="02724-318">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="02724-318">Location1MeetingPolicy</span></span>        | <span data-ttu-id="02724-319">虛假</span><span class="sxs-lookup"><span data-stu-id="02724-319">False</span></span>   |

<span data-ttu-id="02724-320">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="02724-320">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="02724-321">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02724-321">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="02724-322">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="02724-322">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="02724-323">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="02724-323">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="02724-324">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="02724-324">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="02724-325">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="02724-325">Allow an external participant to give or request control</span></span>

<span data-ttu-id="02724-326">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-326">This is a per-user policy.</span></span> <span data-ttu-id="02724-327">組織是否有此組使用者無論會議召集人已設定的內容，都不會控制外部參與者所能執行的動作。</span><span class="sxs-lookup"><span data-stu-id="02724-327">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="02724-328">這個參數會控制外部參與者是否可以受到控制或要求對共用者的螢幕進行控制，這要視共用資源在組織的會議原則中所設定的內容而定。</span><span class="sxs-lookup"><span data-stu-id="02724-328">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="02724-329">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="02724-329">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="02724-330">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="02724-330">Anonymous user</span></span>
- <span data-ttu-id="02724-331">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="02724-331">Guest users</span></span>  
- <span data-ttu-id="02724-332">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="02724-332">B2B user</span></span>
- <span data-ttu-id="02724-333">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="02724-333">Federated user</span></span>  

<span data-ttu-id="02724-334">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。</span><span class="sxs-lookup"><span data-stu-id="02724-334">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="02724-335">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02724-335">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="02724-336">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="02724-336">Allow PowerPoint sharing</span></span>

<span data-ttu-id="02724-337">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-337">This is a per-user policy.</span></span> <span data-ttu-id="02724-338">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="02724-338">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="02724-339">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-339">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="02724-340">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="02724-340">Let's look at the following example.</span></span>

|<span data-ttu-id="02724-341">使用者</span><span class="sxs-lookup"><span data-stu-id="02724-341">User</span></span> |<span data-ttu-id="02724-342">會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-342">Meeting policy</span></span>  |<span data-ttu-id="02724-343">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="02724-343">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="02724-344">Daniela</span><span class="sxs-lookup"><span data-stu-id="02724-344">Daniela</span></span>   | <span data-ttu-id="02724-345">全域</span><span class="sxs-lookup"><span data-stu-id="02724-345">Global</span></span>   | <span data-ttu-id="02724-346">滿足</span><span class="sxs-lookup"><span data-stu-id="02724-346">True</span></span>       |
|<span data-ttu-id="02724-347">Amanda</span><span class="sxs-lookup"><span data-stu-id="02724-347">Amanda</span></span>   | <span data-ttu-id="02724-348">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="02724-348">Location1MeetingPolicy</span></span>        | <span data-ttu-id="02724-349">虛假</span><span class="sxs-lookup"><span data-stu-id="02724-349">False</span></span>   |

<span data-ttu-id="02724-350">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="02724-350">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="02724-351">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="02724-351">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="02724-352">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="02724-352">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="02724-353">允許白板</span><span class="sxs-lookup"><span data-stu-id="02724-353">Allow whiteboard</span></span>

<span data-ttu-id="02724-354">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-354">This is a per-user policy.</span></span> <span data-ttu-id="02724-355">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="02724-355">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="02724-356">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-356">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="02724-357">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="02724-357">Let's look at the following example.</span></span>

|<span data-ttu-id="02724-358">使用者</span><span class="sxs-lookup"><span data-stu-id="02724-358">User</span></span> |<span data-ttu-id="02724-359">會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-359">Meeting policy</span></span>  |<span data-ttu-id="02724-360">允許白板</span><span class="sxs-lookup"><span data-stu-id="02724-360">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="02724-361">Daniela</span><span class="sxs-lookup"><span data-stu-id="02724-361">Daniela</span></span>   | <span data-ttu-id="02724-362">全域</span><span class="sxs-lookup"><span data-stu-id="02724-362">Global</span></span>   | <span data-ttu-id="02724-363">滿足</span><span class="sxs-lookup"><span data-stu-id="02724-363">True</span></span>       |
|<span data-ttu-id="02724-364">Amanda</span><span class="sxs-lookup"><span data-stu-id="02724-364">Amanda</span></span>   | <span data-ttu-id="02724-365">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="02724-365">Location1MeetingPolicy</span></span>        | <span data-ttu-id="02724-366">虛假</span><span class="sxs-lookup"><span data-stu-id="02724-366">False</span></span>   |

<span data-ttu-id="02724-367">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="02724-367">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="02724-368">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="02724-368">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="02724-369">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="02724-369">Allow shared notes</span></span>

<span data-ttu-id="02724-370">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-370">This is a per-user policy.</span></span> <span data-ttu-id="02724-371">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="02724-371">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="02724-372">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-372">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="02724-373">目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="02724-373">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="02724-374">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="02724-374">Let's look at the following example.</span></span>

|<span data-ttu-id="02724-375">使用者</span><span class="sxs-lookup"><span data-stu-id="02724-375">User</span></span> |<span data-ttu-id="02724-376">會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-376">Meeting policy</span></span>  |<span data-ttu-id="02724-377">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="02724-377">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="02724-378">Daniela</span><span class="sxs-lookup"><span data-stu-id="02724-378">Daniela</span></span>   | <span data-ttu-id="02724-379">全域</span><span class="sxs-lookup"><span data-stu-id="02724-379">Global</span></span>   | <span data-ttu-id="02724-380">滿足</span><span class="sxs-lookup"><span data-stu-id="02724-380">True</span></span>       |
|<span data-ttu-id="02724-381">Amanda</span><span class="sxs-lookup"><span data-stu-id="02724-381">Amanda</span></span>   | <span data-ttu-id="02724-382">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="02724-382">Location1MeetingPolicy</span></span> | <span data-ttu-id="02724-383">虛假</span><span class="sxs-lookup"><span data-stu-id="02724-383">False</span></span> |

<span data-ttu-id="02724-384">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="02724-384">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="02724-385">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="02724-385">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="02724-386">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="02724-386">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="02724-387">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="02724-387">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="02724-388">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="02724-388">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="02724-389">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="02724-389">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="02724-390">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="02724-390">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="02724-391">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="02724-391">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="02724-392">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="02724-392">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="02724-393">如果您的群組有音訊會議，且使用它來連接，請參閱[音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="02724-393">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="02724-394">如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="02724-394">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="02724-395">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="02724-395">Let anonymous people start a meeting</span></span>

<span data-ttu-id="02724-396">這是允許 leaderless 撥入會議會議的每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="02724-396">This is a per-organizer policy that allows for leaderless dial in conferencing meetings.</span></span> <span data-ttu-id="02724-397">此設定會控制撥入使用者是否無需經過驗證的使用者，就能從出席中的組織加入會議。</span><span class="sxs-lookup"><span data-stu-id="02724-397">This setting controls whether dial in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="02724-398">預設值為 False，表示撥入使用者會在大廳等候，直到組織中的經過驗證的使用者加入會議為止。</span><span class="sxs-lookup"><span data-stu-id="02724-398">The default value is False which means dial in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span> 

<span data-ttu-id="02724-399">**記事**如果是 False，而撥入使用者會先加入會議，並放在大廳，組織使用者必須加入會議與團隊用戶端，才能從大廳承認使用者。</span><span class="sxs-lookup"><span data-stu-id="02724-399">**Note** If False and a dial in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="02724-400">沒有可撥打給使用者的大廳控制項。</span><span class="sxs-lookup"><span data-stu-id="02724-400">There are no lobby controls available for dialed in users.</span></span> 


### <a name="automatically-admit-people"></a><span data-ttu-id="02724-401">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="02724-401">Automatically admit people</span></span>

<span data-ttu-id="02724-402">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="02724-402">This is a per-organizer policy.</span></span> <span data-ttu-id="02724-403">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="02724-403">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="02724-404">此設定不會套用至 [撥入使用者]。</span><span class="sxs-lookup"><span data-stu-id="02724-404">This setting does not apply to dial in users.</span></span> 

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="02724-406">會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="02724-406">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
 
 <span data-ttu-id="02724-407">**記事**在會議選項中，設定標示為「誰可以略過大廳」</span><span class="sxs-lookup"><span data-stu-id="02724-407">**Note** In the meeting options the setting is labeled "Who can bypass the lobby"</span></span>
  
|<span data-ttu-id="02724-408">設定值</span><span class="sxs-lookup"><span data-stu-id="02724-408">Setting value</span></span>  |<span data-ttu-id="02724-409">加入行為</span><span class="sxs-lookup"><span data-stu-id="02724-409">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="02724-410">**任何人**</span><span class="sxs-lookup"><span data-stu-id="02724-410">**Everyone**</span></span>   |<span data-ttu-id="02724-411">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="02724-411">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="02724-412">這包括經過驗證的使用者、信任組織中的外部使用者 (聯盟) 、來賓及匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="02724-412">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="02724-413">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="02724-413">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="02724-414">組織內經過驗證的使用者，包括來賓使用者以及受信任組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="02724-414">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="02724-415">匿名使用者在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="02724-415">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="02724-416">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="02724-416">**Everyone in your organization**</span></span>    |<span data-ttu-id="02724-417">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="02724-417">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="02724-418">受信任的組織中的使用者和匿名使用者在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="02724-418">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="02724-419">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="02724-419">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="02724-420">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="02724-420">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="02724-421">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="02724-421">This is a per-organizer policy.</span></span> <span data-ttu-id="02724-422">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="02724-422">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="02724-423">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="02724-423">The default value is False.</span></span> <span data-ttu-id="02724-424">當為 False 時，撥入使用者會在大廳等候，直到組織使用者與團隊用戶端加入會議，然後允許他們。</span><span class="sxs-lookup"><span data-stu-id="02724-424">When False, dial in users will wait in the lobby until a organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="02724-425">當為 True 時，當組織使用者加入會議時，撥入使用者會自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="02724-425">When True, dial in users will automatically join the meeting when an organization user joins the meeting.</span></span> 

<span data-ttu-id="02724-426">**記事**如果撥入使用者在組織使用者加入會議之前加入會議，則會將它們放在大廳中，直到組織使用者使用團隊用戶端加入會議，然後允許他們。</span><span class="sxs-lookup"><span data-stu-id="02724-426">**Note** If a dial in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> 


### <a name="enable-live-captions"></a><span data-ttu-id="02724-427">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="02724-427">Enable live captions</span></span>

<span data-ttu-id="02724-428">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="02724-428">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="02724-429">此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="02724-429">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="02724-431">設定值</span><span class="sxs-lookup"><span data-stu-id="02724-431">Setting value</span></span> |<span data-ttu-id="02724-432">行為</span><span class="sxs-lookup"><span data-stu-id="02724-432">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="02724-433">**已停用，但使用者可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="02724-433">**Disabled but the user can override**</span></span>     | <span data-ttu-id="02724-434">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="02724-434">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="02724-435">使用者可以在 [溢出 () **...** ] 功能表中看到 [**開啟即時標題**] 選項，將其開啟。</span><span class="sxs-lookup"><span data-stu-id="02724-435">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="02724-436">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="02724-436">This is the default setting.</span></span> |
|<span data-ttu-id="02724-437">**禁止**</span><span class="sxs-lookup"><span data-stu-id="02724-437">**Disabled**</span></span>     | <span data-ttu-id="02724-438">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="02724-438">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="02724-439">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="02724-439">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="02724-440"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="02724-440"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="02724-441">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="02724-441">Allow chat in meetings</span></span>

<span data-ttu-id="02724-442">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="02724-442">This is a per-organizer policy.</span></span> <span data-ttu-id="02724-443">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="02724-443">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="02724-444"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="02724-444"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="02724-445">會議原則設定-指定的簡報者角色模式</span><span class="sxs-lookup"><span data-stu-id="02724-445">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="02724-446">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-446">This is a per-user policy.</span></span> <span data-ttu-id="02724-447">這項設定可讓您變更小組用戶端的 [**會議選項**] 中的 [**可以出示的人員**] 設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="02724-447">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="02724-448">此原則設定會影響所有會議，包括 [立即開會] 會議。</span><span class="sxs-lookup"><span data-stu-id="02724-448">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="02724-449">[**可以出席的人員**] 設定可讓會議召集人選擇要在會議中成為簡報者的人員。</span><span class="sxs-lookup"><span data-stu-id="02724-449">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="02724-450">若要深入瞭解，請參閱[在團隊會議中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)[變更團隊會議](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)與角色的參與者設定。</span><span class="sxs-lookup"><span data-stu-id="02724-450">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="02724-451">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="02724-451">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="02724-452">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="02724-452">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="02724-453">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="02724-453">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="02724-454">若要指定 [**可以提出的人員**] 的預設值，請將**DesignatedPresenterRoleMode**參數設定為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="02724-454">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="02724-455">**EveryoneUserOverride**：所有會議參與者都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="02724-455">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="02724-456">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="02724-456">This is the default value.</span></span> <span data-ttu-id="02724-457">這個參數會對應到 [小組] 中的 [**所有人**] 設定。</span><span class="sxs-lookup"><span data-stu-id="02724-457">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="02724-458">**EveryoneInCompanyUserOverride**：組織中經過驗證的使用者，包括來賓使用者，都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="02724-458">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="02724-459">這個參數會對應到 [**我的組織**中的人員] 設定。</span><span class="sxs-lookup"><span data-stu-id="02724-459">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="02724-460">**OrganizerOnlyUserOverride**：只有會議召集人可以成為簡報者，且所有會議參與者都指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="02724-460">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="02724-461">這個參數會對應到 [團隊] 中的 [**僅自己**] 設定。</span><span class="sxs-lookup"><span data-stu-id="02724-461">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="02724-462">請記住，在您設定預設值之後，會議召集人仍可在團隊中變更此設定，並選擇誰可以在排程的會議中出席。</span><span class="sxs-lookup"><span data-stu-id="02724-462">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="02724-463">會議原則設定-會議出席情況報告</span><span class="sxs-lookup"><span data-stu-id="02724-463">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="02724-464">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-464">This is a per-user policy.</span></span> <span data-ttu-id="02724-465">此設定控制會議召集人是否可以下載[會議出席情況報告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="02724-465">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="02724-466">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="02724-466">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="02724-467">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="02724-467">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="02724-468">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="02724-468">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="02724-469">若要讓會議召集人下載會議出席情況報告，請將**AllowEngagementReport**參數設定為 [**已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="02724-469">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="02724-470">啟用時，會在**參與者**窗格中顯示下載報告的選項。</span><span class="sxs-lookup"><span data-stu-id="02724-470">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="02724-471">若要避免會議召集人下載報表，請將參數設定為 [**已停用**]。</span><span class="sxs-lookup"><span data-stu-id="02724-471">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="02724-472">根據預設，此設定會停用，而且無法使用下載報表的選項。</span><span class="sxs-lookup"><span data-stu-id="02724-472">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="02724-473">會議原則設定-適用于孤島模式的會議提供者</span><span class="sxs-lookup"><span data-stu-id="02724-473">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="02724-474">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-474">This is a per-user policy.</span></span> <span data-ttu-id="02724-475">這個設定控制哪一個 Outlook 會議增益集會用於使用*孤島模式的使用者*。</span><span class="sxs-lookup"><span data-stu-id="02724-475">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="02724-476">您可以指定使用者是否只能使用 [團隊會議] 增益集，或是同時使用 [團隊會議] 和 [商務用 Skype 會議] 增益集，在 Outlook 中排程會議。</span><span class="sxs-lookup"><span data-stu-id="02724-476">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="02724-477">您只能將此原則套用到使用孤島模式的使用者，並在其團隊會議原則中，將**AllowOutlookAddIn**參數設定為**True** 。</span><span class="sxs-lookup"><span data-stu-id="02724-477">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="02724-478">目前您只能使用 PowerShell 來設定此原則。</span><span class="sxs-lookup"><span data-stu-id="02724-478">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="02724-479">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="02724-479">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="02724-480">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="02724-480">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="02724-481">若要指定使用者可以使用的會議增益集，請設定**PreferredMeetingProviderForIslandsMode**參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="02724-481">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="02724-482">將參數設定為**TeamsAndSfB** ，以在 Outlook 中同時啟用 [團隊會議增益集] 和 [商務用 Skype] 增益集。</span><span class="sxs-lookup"><span data-stu-id="02724-482">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="02724-483">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="02724-483">This is the default value.</span></span>
- <span data-ttu-id="02724-484">將參數設定為 [**團隊**]，只會在 Outlook 中啟用 [團隊會議] 增益集。</span><span class="sxs-lookup"><span data-stu-id="02724-484">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="02724-485">此原則設定可確保所有未來的會議都有小組會議加入連結。</span><span class="sxs-lookup"><span data-stu-id="02724-485">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="02724-486">它不會將現有的商務用 Skype 會議加入連結遷移至團隊。</span><span class="sxs-lookup"><span data-stu-id="02724-486">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="02724-487">此原則設定不會影響商務用 Skype 中的目前狀態、聊天、PSTN 通話或任何其他功能，這表示使用者將繼續使用商務用 Skype 來取得這些功能。</span><span class="sxs-lookup"><span data-stu-id="02724-487">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="02724-488">如果您將參數設定為 [**團隊**]，然後切換回**TeamsAndSfB**，則會啟用兩個會議增益集。</span><span class="sxs-lookup"><span data-stu-id="02724-488">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="02724-489">不過，請注意，現有的團隊會議加入連結不會遷移到商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="02724-489">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="02724-490">只有在變更之後所排程的商務用 Skype 會議，才會有商務用 Skype 會議加入連結。</span><span class="sxs-lookup"><span data-stu-id="02724-490">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="02724-491">會議原則設定-影片篩選模式</span><span class="sxs-lookup"><span data-stu-id="02724-491">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="02724-492">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02724-492">This is a per-user policy.</span></span> <span data-ttu-id="02724-493">此設定可控制使用者是否可以在會議中自訂其影片背景。</span><span class="sxs-lookup"><span data-stu-id="02724-493">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="02724-494">目前您只能使用 PowerShell 來設定此原則。</span><span class="sxs-lookup"><span data-stu-id="02724-494">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="02724-495">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="02724-495">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="02724-496">或者，使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，然後將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="02724-496">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="02724-497">若要指定使用者是否可以在會議中自訂其影片背景，請設定**VideoFiltersMode**參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="02724-497">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="02724-498">在 PowerShell 中設定值</span><span class="sxs-lookup"><span data-stu-id="02724-498">Setting value in PowerShell</span></span> |<span data-ttu-id="02724-499">行為</span><span class="sxs-lookup"><span data-stu-id="02724-499">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="02724-500">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="02724-500">**NoFilters**</span></span>     |<span data-ttu-id="02724-501">使用者無法自訂其影片背景。</span><span class="sxs-lookup"><span data-stu-id="02724-501">User can't customize their video background.</span></span>|
|<span data-ttu-id="02724-502">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="02724-502">**BlurOnly**</span></span>     |<span data-ttu-id="02724-503">使用者可以選擇將影片背景模糊。</span><span class="sxs-lookup"><span data-stu-id="02724-503">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="02724-504">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="02724-504">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="02724-505">使用者可以選擇將影片背景模糊，或從預設的影像集合中選擇，以做為其背景。</span><span class="sxs-lookup"><span data-stu-id="02724-505">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="02724-506">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="02724-506">**AllFilters**</span></span>     |<span data-ttu-id="02724-507">使用選項可讓影片背景變模糊、選擇預設的影像，或上傳自訂圖像來作為其背景。</span><span class="sxs-lookup"><span data-stu-id="02724-507">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="02724-508">使用者上傳的影像不會受到小組的篩選。</span><span class="sxs-lookup"><span data-stu-id="02724-508">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="02724-509">當您使用 [ **AllFilters** ] 設定時，您應該擁有內部組織原則，以防止使用者上傳冒犯性或不適當的影像，或貴組織沒有許可權可供團隊會議背景使用。</span><span class="sxs-lookup"><span data-stu-id="02724-509">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02724-510">相關主題</span><span class="sxs-lookup"><span data-stu-id="02724-510">Related topics</span></span>

- [<span data-ttu-id="02724-511">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="02724-511">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="02724-512">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="02724-512">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="02724-513">從使用者移除 RestrictedAnonymousAccess 團隊會議原則</span><span class="sxs-lookup"><span data-stu-id="02724-513">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
