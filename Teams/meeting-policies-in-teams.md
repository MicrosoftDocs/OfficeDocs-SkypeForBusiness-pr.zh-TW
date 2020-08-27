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
ms.openlocfilehash: a075a432f57a6634a49e9442da0bdc215b1546d9
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255481"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="5ab3f-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="5ab3f-104">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="5ab3f-105">您可以使用全域 (組織範圍的預設) 原則，此原則會自動建立或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="5ab3f-106">您可以在 Microsoft 團隊系統管理中心或使用 [PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5ab3f-107">如需使用角色來管理會議簡報者與出席者權限的相關資訊，請參閱 [小組會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="5ab3f-108">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="5ab3f-109">實現類型</span><span class="sxs-lookup"><span data-stu-id="5ab3f-109">Implementation type</span></span>  |<span data-ttu-id="5ab3f-110">描述</span><span class="sxs-lookup"><span data-stu-id="5ab3f-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5ab3f-111">每個召集人</span><span class="sxs-lookup"><span data-stu-id="5ab3f-111">Per-organizer</span></span>    |<span data-ttu-id="5ab3f-112">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="5ab3f-113">例如， **自動承認人員** 是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="5ab3f-114">每位使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-114">Per-user</span></span>    |<span data-ttu-id="5ab3f-115">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="5ab3f-116">例如，[ **允許在頻道中立即開會** ] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="5ab3f-117">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="5ab3f-118">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="5ab3f-119">例如，[ **允許雲端錄製** ] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="5ab3f-120">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-120">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="5ab3f-121">您可以編輯全域原則中的設定，或是建立並指派一或多個自訂原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="5ab3f-122">除非您建立並指派自訂原則，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="5ab3f-123">如果使用者已啟用音訊會議授權，或使用者允許音訊會議，則 [會議詳細資料] 按鈕就會提供，會議詳細資料將無法使用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="5ab3f-124">建立自訂會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="5ab3f-125">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="5ab3f-126">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-126">Click **Add**.</span></span>
3. <span data-ttu-id="5ab3f-127">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="5ab3f-128">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="5ab3f-129">選擇您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="5ab3f-130">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-130">Click **Save**.</span></span>

<span data-ttu-id="5ab3f-131">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="5ab3f-132">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="5ab3f-133">在 [音訊與視訊]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="5ab3f-134">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="5ab3f-135">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="5ab3f-136">在 [內容共用]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="5ab3f-137">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="5ab3f-138">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="5ab3f-139">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="5ab3f-140">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="5ab3f-141">編輯會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-141">Edit a meeting policy</span></span>

<span data-ttu-id="5ab3f-142">您可以為全域原則編輯您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-142">You can edit the global policy an any custom policies that you create.</span></span>

1. <span data-ttu-id="5ab3f-143">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="5ab3f-144">按一下原則名稱左邊的，然後按一下 [ **編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="5ab3f-145">您可以從這裡進行所要的變更。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="5ab3f-146">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-146">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5ab3f-147">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="5ab3f-148">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="5ab3f-149">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="5ab3f-150">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="5ab3f-151">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="5ab3f-151">Meeting policy settings</span></span>

<span data-ttu-id="5ab3f-152">當您在 [ **會議原則** ] 頁面上選取現有的原則，或選取 [ **新增** ] 以新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="5ab3f-153">一般</span><span class="sxs-lookup"><span data-stu-id="5ab3f-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="5ab3f-154">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="5ab3f-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="5ab3f-155">內容共用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="5ab3f-156">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="5ab3f-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end

<span data-ttu-id="5ab3f-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="5ab3f-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="5ab3f-158">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="5ab3f-158">Meeting policy settings - General</span></span>

- <span data-ttu-id="5ab3f-159">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="5ab3f-159">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="5ab3f-160">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="5ab3f-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="5ab3f-161">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="5ab3f-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="5ab3f-162">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="5ab3f-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="5ab3f-163">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="5ab3f-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="5ab3f-164">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="5ab3f-164">Allow Meet now in channels</span></span>

<span data-ttu-id="5ab3f-165">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-165">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="5ab3f-166">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-166">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="5ab3f-167">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [ **立即開會** ]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-167">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="5ab3f-168">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-168">The default value is True.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="5ab3f-170">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="5ab3f-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="5ab3f-171">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="5ab3f-172">此設定可控制團隊會議是否可以在 Outlook (Windows、Mac、web 及行動裝置) 中排程。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="5ab3f-174">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-174">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="5ab3f-175">例如，在 Windows 版 Outlook 中，新的 [ **小組會議** ] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-175">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="5ab3f-176">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="5ab3f-176">Allow channel meeting scheduling</span></span>

<span data-ttu-id="5ab3f-177">使用現有的 AllowChannelMeetingScheduling 原則來控制可在小組頻道行事曆上建立的事件種類。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-177">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="5ab3f-178">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-178">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="5ab3f-179">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-179">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="5ab3f-180">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-180">The default value is True.</span></span>

<span data-ttu-id="5ab3f-181">如果關閉此原則，使用者將無法建立新的頻道會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-181">If this policy is OFF, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="5ab3f-182">不過，您可以透過事件的召集人來編輯現有的頻道會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-182">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="5ab3f-183">[排程會議] 將停用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-183">Schedule a meeting will be disabled.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/schedule-meeting-option.png)

<span data-ttu-id="5ab3f-185">頻道選取已停用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-185">Channel selection is disabled.</span></span>

![螢幕擷取畫面顯示您要在其中排程會議的頻道的 [行事曆] 選項。](media/meeting-policies-select-a-channel-to-meet-in.png)

<span data-ttu-id="5ab3f-187">在 [頻道貼上] 頁面中，下列將會停用：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-187">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="5ab3f-188">[頻道回復撰寫] 方塊上的 [**排程會議**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-188">**Schedule a meeting** button on the channel reply compose box.</span></span>
<span data-ttu-id="5ab3f-189">![螢幕擷取畫面顯示您要在其中排程會議的頻道的 [行事曆] 選項。](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="5ab3f-189">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
- <span data-ttu-id="5ab3f-190">頻道標題上的 [**排程會議**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-190">**Schedule a meeting** button on the channel header.</span></span>
<span data-ttu-id="5ab3f-191">![螢幕擷取畫面顯示您要在其中排程會議的頻道的 [行事曆] 選項。](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="5ab3f-191">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="5ab3f-192">在頻道行事曆中：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-192">In the channel calendar:</span></span>

- <span data-ttu-id="5ab3f-193">頻道行事曆標頭上的 [**新增活動**] 按鈕將會停用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-193">**Add new event** button on channel calendar header will be disabled.</span></span>
<span data-ttu-id="5ab3f-194">![螢幕擷取畫面顯示您要在其中排程會議的頻道的 [行事曆] 選項。](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="5ab3f-194">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/add-new-event-disabled.png)</span></span>
- <span data-ttu-id="5ab3f-195">使用者將無法在頻道行事曆中拖曳並選取時間區塊來建立頻道會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-195">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>
- <span data-ttu-id="5ab3f-196">使用者無法使用鍵盤快速鍵在頻道行事曆上建立會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-196">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="5ab3f-197">在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-197">In the Admin Center:</span></span>

<span data-ttu-id="5ab3f-198">[頻道行事曆] app 會顯示在 [管理員] 面板中的 [ **Microsoft app** ] 區段底下，以取得許可權原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-198">The channel calendar app will show up under the **Microsoft apps** section in the admin panel for permission policies.</span></span>

![螢幕擷取畫面顯示 [團隊管理] 主控台中的 Microsoft app 原則。](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="5ab3f-200">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="5ab3f-200">Allow scheduling private meetings</span></span>

<span data-ttu-id="5ab3f-201">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-201">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="5ab3f-202">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-202">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="5ab3f-203">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-203">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="5ab3f-204">請注意，如果您關閉 [ **允許排程私人會議** ] 和 [ **允許頻道會議排程**]，就會針對小組中的使用者停用 [ **新增必要的出席** 者] 和 [ **新增頻道** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-204">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="5ab3f-205">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-205">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="5ab3f-206">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="5ab3f-206">Allow Meet now in private meetings</span></span>

<span data-ttu-id="5ab3f-207">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-207">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="5ab3f-208">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-208">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="5ab3f-209">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-209">The default value is True.</span></span>

<span data-ttu-id="5ab3f-210"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="5ab3f-210"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="5ab3f-211">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="5ab3f-211">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="5ab3f-212">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="5ab3f-212">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="5ab3f-213">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="5ab3f-213">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="5ab3f-214">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="5ab3f-214">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="5ab3f-215">媒體位元速率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="5ab3f-215">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="5ab3f-216">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="5ab3f-216">Allow transcription</span></span>

<span data-ttu-id="5ab3f-217">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-217">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="5ab3f-218">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-218">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="5ab3f-219">如果您關閉此功能，則在播放會議錄製期間將無法使用 [ **搜尋** ] 和 [ **抄送** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-219">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="5ab3f-220">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-220">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="5ab3f-221">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-221">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="5ab3f-223">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="5ab3f-223">Allow cloud recording</span></span>

<span data-ttu-id="5ab3f-224">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-224">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="5ab3f-225">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-225">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="5ab3f-226">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-226">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="5ab3f-227">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-227">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="5ab3f-228">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-228">Guest users can't start or stop the recording.</span></span>

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="5ab3f-230">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-230">Let's look at the following example.</span></span>

|<span data-ttu-id="5ab3f-231">使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-231">User</span></span> |<span data-ttu-id="5ab3f-232">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-232">Meeting policy</span></span>  |<span data-ttu-id="5ab3f-233">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="5ab3f-233">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5ab3f-234">Daniela</span><span class="sxs-lookup"><span data-stu-id="5ab3f-234">Daniela</span></span> | <span data-ttu-id="5ab3f-235">全域</span><span class="sxs-lookup"><span data-stu-id="5ab3f-235">Global</span></span>   | <span data-ttu-id="5ab3f-236">虛假</span><span class="sxs-lookup"><span data-stu-id="5ab3f-236">False</span></span> |
|<span data-ttu-id="5ab3f-237">Amanda</span><span class="sxs-lookup"><span data-stu-id="5ab3f-237">Amanda</span></span> | <span data-ttu-id="5ab3f-238">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="5ab3f-238">Location1MeetingPolicy</span></span> | <span data-ttu-id="5ab3f-239">滿足</span><span class="sxs-lookup"><span data-stu-id="5ab3f-239">True</span></span>|
|<span data-ttu-id="5ab3f-240">John (外部使用者) </span><span class="sxs-lookup"><span data-stu-id="5ab3f-240">John (external user)</span></span> | <span data-ttu-id="5ab3f-241">不適用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-241">Not applicable</span></span> | <span data-ttu-id="5ab3f-242">不適用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-242">Not applicable</span></span>|

<span data-ttu-id="5ab3f-243">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-243">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="5ab3f-244">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-244">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="5ab3f-245">若要深入瞭解雲端會議錄製，請參閱 [小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-245">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="5ab3f-246">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="5ab3f-246">Allow IP video</span></span>

<span data-ttu-id="5ab3f-247">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-247">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="5ab3f-248">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-248">Video is a key component to meetings.</span></span> <span data-ttu-id="5ab3f-249">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-249">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="5ab3f-250">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-250">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="5ab3f-251">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-251">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="5ab3f-252">沒有指派任何原則的會議參與者 (例如，匿名和聯盟參與者) 繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-252">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="5ab3f-254">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-254">Let's look at the following example.</span></span>

|<span data-ttu-id="5ab3f-255">使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-255">User</span></span> |<span data-ttu-id="5ab3f-256">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-256">Meeting policy</span></span>  |<span data-ttu-id="5ab3f-257">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="5ab3f-257">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5ab3f-258">Daniela</span><span class="sxs-lookup"><span data-stu-id="5ab3f-258">Daniela</span></span>   | <span data-ttu-id="5ab3f-259">全域</span><span class="sxs-lookup"><span data-stu-id="5ab3f-259">Global</span></span>   | <span data-ttu-id="5ab3f-260">滿足</span><span class="sxs-lookup"><span data-stu-id="5ab3f-260">True</span></span>        |
|<span data-ttu-id="5ab3f-261">Amanda</span><span class="sxs-lookup"><span data-stu-id="5ab3f-261">Amanda</span></span>    | <span data-ttu-id="5ab3f-262">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="5ab3f-262">Location1MeetingPolicy</span></span>        | <span data-ttu-id="5ab3f-263">虛假</span><span class="sxs-lookup"><span data-stu-id="5ab3f-263">False</span></span>      |

<span data-ttu-id="5ab3f-264">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-264">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="5ab3f-265">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-265">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="5ab3f-266">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-266">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="5ab3f-267">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-267">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="5ab3f-268">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-268">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="5ab3f-269">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-269">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="5ab3f-270">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-270">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="5ab3f-271">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-271">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="5ab3f-272">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-272">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="5ab3f-273">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-273">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="5ab3f-274">媒體位元速率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="5ab3f-274">Media bit rate (Kbs)</span></span>

<span data-ttu-id="5ab3f-275">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-275">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-276">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-276">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="5ab3f-277">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-277">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="5ab3f-278">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-278">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="5ab3f-279">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-279">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="5ab3f-280">最小值為 30 Kbps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-280">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="5ab3f-281">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱 [頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-281">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="5ab3f-282">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-282">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="5ab3f-283">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-283">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="5ab3f-284">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-284">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="5ab3f-285">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-285">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="5ab3f-286">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="5ab3f-286">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="5ab3f-287">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="5ab3f-287">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="5ab3f-288">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="5ab3f-288">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="5ab3f-289">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-289">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="5ab3f-290">允許白板</span><span class="sxs-lookup"><span data-stu-id="5ab3f-290">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="5ab3f-291">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="5ab3f-291">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="5ab3f-292">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="5ab3f-292">Screen sharing mode</span></span>

<span data-ttu-id="5ab3f-293">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-293">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="5ab3f-294">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-294">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="5ab3f-295">沒有任何 (指派任何原則的會議參與者（例如匿名、來賓、B2B 及同盟參與者）) 會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-295">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="5ab3f-296">設定值</span><span class="sxs-lookup"><span data-stu-id="5ab3f-296">Setting value</span></span> |<span data-ttu-id="5ab3f-297">行為</span><span class="sxs-lookup"><span data-stu-id="5ab3f-297">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="5ab3f-298">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-298">**Entire screen**</span></span>    | <span data-ttu-id="5ab3f-299">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-299">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="5ab3f-300">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-300">**Single application**</span></span>   | <span data-ttu-id="5ab3f-301">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="5ab3f-301">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="5ab3f-302">**禁止**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-302">**Disabled**</span></span>     |<span data-ttu-id="5ab3f-303">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-303">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="5ab3f-304">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-304">Let's look at the following example.</span></span>

|<span data-ttu-id="5ab3f-305">使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-305">User</span></span> |<span data-ttu-id="5ab3f-306">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-306">Meeting policy</span></span> |<span data-ttu-id="5ab3f-307">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="5ab3f-307">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5ab3f-308">Daniela</span><span class="sxs-lookup"><span data-stu-id="5ab3f-308">Daniela</span></span>  | <span data-ttu-id="5ab3f-309">全域</span><span class="sxs-lookup"><span data-stu-id="5ab3f-309">Global</span></span>   | <span data-ttu-id="5ab3f-310">整個畫面</span><span class="sxs-lookup"><span data-stu-id="5ab3f-310">Entire screen</span></span> |
|<span data-ttu-id="5ab3f-311">Amanda</span><span class="sxs-lookup"><span data-stu-id="5ab3f-311">Amanda</span></span>   | <span data-ttu-id="5ab3f-312">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="5ab3f-312">Location1MeetingPolicy</span></span>  | <span data-ttu-id="5ab3f-313">禁止</span><span class="sxs-lookup"><span data-stu-id="5ab3f-313">Disabled</span></span> |

<span data-ttu-id="5ab3f-314">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-314">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="5ab3f-315">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-315">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="5ab3f-316">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-316">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="5ab3f-317">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-317">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="5ab3f-318">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-318">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="5ab3f-319">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="5ab3f-319">Allow a participant to give or request control</span></span>

<span data-ttu-id="5ab3f-320">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-320">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-321">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-321">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="5ab3f-322">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-322">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="5ab3f-323">如果使用者已開啟此設定，則 [取得 **控制權** ] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-323">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="5ab3f-325">如果使用者的設定已關閉，則無法使用 [ **提供控制權** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-325">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="5ab3f-327">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-327">Let's look at the following example.</span></span>

|<span data-ttu-id="5ab3f-328">使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-328">User</span></span> |<span data-ttu-id="5ab3f-329">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-329">Meeting policy</span></span>  |<span data-ttu-id="5ab3f-330">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="5ab3f-330">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5ab3f-331">Daniela</span><span class="sxs-lookup"><span data-stu-id="5ab3f-331">Daniela</span></span>   | <span data-ttu-id="5ab3f-332">全域</span><span class="sxs-lookup"><span data-stu-id="5ab3f-332">Global</span></span>   | <span data-ttu-id="5ab3f-333">滿足</span><span class="sxs-lookup"><span data-stu-id="5ab3f-333">True</span></span>       |
|<span data-ttu-id="5ab3f-334">Babek</span><span class="sxs-lookup"><span data-stu-id="5ab3f-334">Babek</span></span>    | <span data-ttu-id="5ab3f-335">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="5ab3f-335">Location1MeetingPolicy</span></span>        | <span data-ttu-id="5ab3f-336">虛假</span><span class="sxs-lookup"><span data-stu-id="5ab3f-336">False</span></span>   |

<span data-ttu-id="5ab3f-337">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-337">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="5ab3f-338">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-338">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="5ab3f-339">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-339">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="5ab3f-340">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-340">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="5ab3f-341">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-341">This is due to a technical limitation that we're planning to fix.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="5ab3f-342">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="5ab3f-342">Allow an external participant to give or request control</span></span>

<span data-ttu-id="5ab3f-343">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-343">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-344">組織是否有此組使用者無論會議召集人已設定的內容，都不會控制外部參與者所能執行的動作。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-344">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="5ab3f-345">這個參數會控制外部參與者是否可以受到控制或要求對共用者的螢幕進行控制，這要視共用資源在組織的會議原則中所設定的內容而定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-345">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="5ab3f-346">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-346">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="5ab3f-347">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-347">Anonymous user</span></span>
- <span data-ttu-id="5ab3f-348">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-348">Guest users</span></span>  
- <span data-ttu-id="5ab3f-349">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-349">B2B user</span></span>
- <span data-ttu-id="5ab3f-350">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-350">Federated user</span></span>  

<span data-ttu-id="5ab3f-351">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中 **提供或要求控制** 設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-351">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="5ab3f-352">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-352">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="5ab3f-353">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-353">Allow PowerPoint sharing</span></span>

<span data-ttu-id="5ab3f-354">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-354">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-355">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-355">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="5ab3f-356">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-356">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="5ab3f-357">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-357">Let's look at the following example.</span></span>

|<span data-ttu-id="5ab3f-358">使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-358">User</span></span> |<span data-ttu-id="5ab3f-359">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-359">Meeting policy</span></span>  |<span data-ttu-id="5ab3f-360">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="5ab3f-360">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5ab3f-361">Daniela</span><span class="sxs-lookup"><span data-stu-id="5ab3f-361">Daniela</span></span>   | <span data-ttu-id="5ab3f-362">全域</span><span class="sxs-lookup"><span data-stu-id="5ab3f-362">Global</span></span>   | <span data-ttu-id="5ab3f-363">滿足</span><span class="sxs-lookup"><span data-stu-id="5ab3f-363">True</span></span>       |
|<span data-ttu-id="5ab3f-364">Amanda</span><span class="sxs-lookup"><span data-stu-id="5ab3f-364">Amanda</span></span>   | <span data-ttu-id="5ab3f-365">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="5ab3f-365">Location1MeetingPolicy</span></span>        | <span data-ttu-id="5ab3f-366">虛假</span><span class="sxs-lookup"><span data-stu-id="5ab3f-366">False</span></span>   |

<span data-ttu-id="5ab3f-367">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-367">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="5ab3f-368">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-368">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="5ab3f-369">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-369">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="5ab3f-370">允許白板</span><span class="sxs-lookup"><span data-stu-id="5ab3f-370">Allow whiteboard</span></span>

<span data-ttu-id="5ab3f-371">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-371">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-372">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-372">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="5ab3f-373">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-373">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="5ab3f-374">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-374">Let's look at the following example.</span></span>

|<span data-ttu-id="5ab3f-375">使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-375">User</span></span> |<span data-ttu-id="5ab3f-376">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-376">Meeting policy</span></span>  |<span data-ttu-id="5ab3f-377">允許白板</span><span class="sxs-lookup"><span data-stu-id="5ab3f-377">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="5ab3f-378">Daniela</span><span class="sxs-lookup"><span data-stu-id="5ab3f-378">Daniela</span></span>   | <span data-ttu-id="5ab3f-379">全域</span><span class="sxs-lookup"><span data-stu-id="5ab3f-379">Global</span></span>   | <span data-ttu-id="5ab3f-380">滿足</span><span class="sxs-lookup"><span data-stu-id="5ab3f-380">True</span></span>       |
|<span data-ttu-id="5ab3f-381">Amanda</span><span class="sxs-lookup"><span data-stu-id="5ab3f-381">Amanda</span></span>   | <span data-ttu-id="5ab3f-382">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="5ab3f-382">Location1MeetingPolicy</span></span>        | <span data-ttu-id="5ab3f-383">虛假</span><span class="sxs-lookup"><span data-stu-id="5ab3f-383">False</span></span>   |

<span data-ttu-id="5ab3f-384">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-384">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="5ab3f-385">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-385">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="5ab3f-386">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="5ab3f-386">Allow shared notes</span></span>

<span data-ttu-id="5ab3f-387">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-387">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-388">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-388">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="5ab3f-389">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-389">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="5ab3f-390">目前只有超過20名參與者的會議才支援 [ **會議記事** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-390">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="5ab3f-391">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-391">Let's look at the following example.</span></span>

|<span data-ttu-id="5ab3f-392">使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-392">User</span></span> |<span data-ttu-id="5ab3f-393">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-393">Meeting policy</span></span>  |<span data-ttu-id="5ab3f-394">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="5ab3f-394">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5ab3f-395">Daniela</span><span class="sxs-lookup"><span data-stu-id="5ab3f-395">Daniela</span></span>   | <span data-ttu-id="5ab3f-396">全域</span><span class="sxs-lookup"><span data-stu-id="5ab3f-396">Global</span></span>   | <span data-ttu-id="5ab3f-397">滿足</span><span class="sxs-lookup"><span data-stu-id="5ab3f-397">True</span></span>       |
|<span data-ttu-id="5ab3f-398">Amanda</span><span class="sxs-lookup"><span data-stu-id="5ab3f-398">Amanda</span></span>   | <span data-ttu-id="5ab3f-399">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="5ab3f-399">Location1MeetingPolicy</span></span> | <span data-ttu-id="5ab3f-400">虛假</span><span class="sxs-lookup"><span data-stu-id="5ab3f-400">False</span></span> |

<span data-ttu-id="5ab3f-401">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-401">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="5ab3f-402">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="5ab3f-402">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="5ab3f-403">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-403">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="5ab3f-404">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="5ab3f-404">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="5ab3f-405">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="5ab3f-405">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="5ab3f-406">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="5ab3f-406">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="5ab3f-407">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="5ab3f-407">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="5ab3f-408">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="5ab3f-408">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="5ab3f-409">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-409">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="5ab3f-410">如果您的群組有音訊會議，且使用它來連接，請參閱 [音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-410">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="5ab3f-411">如果您的 [小組] 群組沒有音訊會議，請參閱 [在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-411">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="5ab3f-412">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="5ab3f-412">Let anonymous people start a meeting</span></span>

<span data-ttu-id="5ab3f-413">這是允許 leaderless 撥入會議會議的每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-413">This is a per-organizer policy that allows for leaderless dial in conferencing meetings.</span></span> <span data-ttu-id="5ab3f-414">此設定會控制撥入使用者是否無需經過驗證的使用者，就能從出席中的組織加入會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-414">This setting controls whether dial in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="5ab3f-415">預設值為 False，表示撥入使用者會在大廳等候，直到組織中的經過驗證的使用者加入會議為止。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-415">The default value is False which means dial in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

<span data-ttu-id="5ab3f-416">**記事** 如果是 False，而撥入使用者會先加入會議，並放在大廳，組織使用者必須加入會議與團隊用戶端，才能從大廳承認使用者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-416">**Note** If False and a dial in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="5ab3f-417">沒有可撥打給使用者的大廳控制項。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-417">There are no lobby controls available for dialed in users.</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="5ab3f-418">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="5ab3f-418">Automatically admit people</span></span>

<span data-ttu-id="5ab3f-419">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-419">This is a per-organizer policy.</span></span> <span data-ttu-id="5ab3f-420">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-420">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="5ab3f-421">此設定不會套用至 [撥入使用者]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-421">This setting does not apply to dial in users.</span></span>

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="5ab3f-423">會議召集人可以按一下會議邀請中的 [ **會議選項** ]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-423">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

 <span data-ttu-id="5ab3f-424">**記事** 在會議選項中，設定標示為「誰可以略過大廳」</span><span class="sxs-lookup"><span data-stu-id="5ab3f-424">**Note** In the meeting options the setting is labeled "Who can bypass the lobby"</span></span>
  
|<span data-ttu-id="5ab3f-425">設定值</span><span class="sxs-lookup"><span data-stu-id="5ab3f-425">Setting value</span></span>  |<span data-ttu-id="5ab3f-426">加入行為</span><span class="sxs-lookup"><span data-stu-id="5ab3f-426">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="5ab3f-427">**任何人**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-427">**Everyone**</span></span>   |<span data-ttu-id="5ab3f-428">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-428">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="5ab3f-429">這包括經過驗證的使用者、信任組織中的外部使用者 (聯盟) 、來賓及匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-429">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="5ab3f-430">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-430">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="5ab3f-431">組織內經過驗證的使用者，包括來賓使用者以及受信任組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-431">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="5ab3f-432">匿名使用者在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-432">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="5ab3f-433">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-433">**Everyone in your organization**</span></span>    |<span data-ttu-id="5ab3f-434">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-434">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="5ab3f-435">受信任的組織中的使用者和匿名使用者在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-435">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="5ab3f-436">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-436">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="5ab3f-437">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="5ab3f-437">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="5ab3f-438">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-438">This is a per-organizer policy.</span></span> <span data-ttu-id="5ab3f-439">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已 **自動准許 [人員** ] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-439">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="5ab3f-440">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-440">The default value is False.</span></span> <span data-ttu-id="5ab3f-441">當為 False 時，撥入使用者會在大廳等候，直到組織使用者與團隊用戶端加入會議，然後允許他們。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-441">When False, dial in users will wait in the lobby until a organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="5ab3f-442">當為 True 時，當組織使用者加入會議時，撥入使用者會自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-442">When True, dial in users will automatically join the meeting when an organization user joins the meeting.</span></span>

<span data-ttu-id="5ab3f-443">**記事** 如果撥入使用者在組織使用者加入會議之前加入會議，則會將它們放在大廳中，直到組織使用者使用團隊用戶端加入會議，然後允許他們。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-443">**Note** If a dial in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span>

### <a name="enable-live-captions"></a><span data-ttu-id="5ab3f-444">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="5ab3f-444">Enable live captions</span></span>

<span data-ttu-id="5ab3f-445">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-445">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="5ab3f-446">此設定會控制是否可使用 [ **開啟即時標題** ] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-446">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="5ab3f-448">設定值</span><span class="sxs-lookup"><span data-stu-id="5ab3f-448">Setting value</span></span> |<span data-ttu-id="5ab3f-449">行為</span><span class="sxs-lookup"><span data-stu-id="5ab3f-449">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="5ab3f-450">**已停用，但使用者可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-450">**Disabled but the user can override**</span></span>     | <span data-ttu-id="5ab3f-451">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-451">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="5ab3f-452">使用者可以在 [溢出 () **...** ] 功能表中看到 [**開啟即時標題**] 選項，將其開啟。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-452">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="5ab3f-453">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-453">This is the default setting.</span></span> |
|<span data-ttu-id="5ab3f-454">**禁止**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-454">**Disabled**</span></span>     | <span data-ttu-id="5ab3f-455">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-455">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="5ab3f-456">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-456">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="5ab3f-457"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="5ab3f-457"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="5ab3f-458">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="5ab3f-458">Allow chat in meetings</span></span>

<span data-ttu-id="5ab3f-459">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-459">This is a per-organizer policy.</span></span> <span data-ttu-id="5ab3f-460">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-460">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="5ab3f-461"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="5ab3f-461"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="5ab3f-462">會議原則設定-指定的簡報者角色模式</span><span class="sxs-lookup"><span data-stu-id="5ab3f-462">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="5ab3f-463">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-463">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-464">這項設定可讓您變更小組用戶端的 [**會議選項**] 中的 [**可以出示的人員**] 設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-464">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="5ab3f-465">此原則設定會影響所有會議，包括 [立即開會] 會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-465">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="5ab3f-466">[ **可以出席的人員** ] 設定可讓會議召集人選擇要在會議中成為簡報者的人員。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-466">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="5ab3f-467">若要深入瞭解，請參閱[在團隊會議中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)[變更團隊會議](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)與角色的參與者設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-467">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="5ab3f-468">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-468">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="5ab3f-469">您可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-469">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="5ab3f-470">或者，您可以使用 [新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-470">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="5ab3f-471">若要指定 [ **可以提出的人員** ] 的預設值，請將 **DesignatedPresenterRoleMode** 參數設定為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-471">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="5ab3f-472">**EveryoneUserOverride**：所有會議參與者都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-472">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="5ab3f-473">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-473">This is the default value.</span></span> <span data-ttu-id="5ab3f-474">這個參數會對應到 [小組] 中的 [ **所有人** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-474">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="5ab3f-475">**EveryoneInCompanyUserOverride**：組織中經過驗證的使用者，包括來賓使用者，都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-475">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="5ab3f-476">這個參數會對應到 [ **我的組織** 中的人員] 設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-476">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="5ab3f-477">**OrganizerOnlyUserOverride**：只有會議召集人可以成為簡報者，且所有會議參與者都指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-477">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="5ab3f-478">這個參數會對應到 [團隊] 中的 [ **僅自己** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-478">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="5ab3f-479">請記住，在您設定預設值之後，會議召集人仍可在團隊中變更此設定，並選擇誰可以在排程的會議中出席。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-479">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="5ab3f-480">會議原則設定-會議出席情況報告</span><span class="sxs-lookup"><span data-stu-id="5ab3f-480">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="5ab3f-481">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-481">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-482">此設定控制會議召集人是否可以下載 [會議出席情況報告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-482">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="5ab3f-483">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-483">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="5ab3f-484">您可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-484">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="5ab3f-485">或者，您可以使用 [新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-485">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="5ab3f-486">若要讓會議召集人下載會議出席情況報告，請將 **AllowEngagementReport** 參數設定為 [ **已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-486">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="5ab3f-487">啟用時，會在 **參與者** 窗格中顯示下載報告的選項。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-487">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="5ab3f-488">若要避免會議召集人下載報表，請將參數設定為 [ **已停用**]。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-488">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="5ab3f-489">根據預設，此設定會停用，而且無法使用下載報表的選項。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-489">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="5ab3f-490">會議原則設定-適用于孤島模式的會議提供者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-490">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="5ab3f-491">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-491">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-492">這個設定控制哪一個 Outlook 會議增益集會用於使用 *孤島模式的使用者*。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-492">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="5ab3f-493">您可以指定使用者是否只能使用 [團隊會議] 增益集，或是同時使用 [團隊會議] 和 [商務用 Skype 會議] 增益集，在 Outlook 中排程會議。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-493">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="5ab3f-494">您只能將此原則套用到使用孤島模式的使用者，並在其團隊會議原則中，將 **AllowOutlookAddIn** 參數設定為 **True** 。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-494">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="5ab3f-495">目前您只能使用 PowerShell 來設定此原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-495">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="5ab3f-496">您可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-496">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="5ab3f-497">或者，您可以使用 [新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-497">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="5ab3f-498">若要指定使用者可以使用的會議增益集，請設定 **PreferredMeetingProviderForIslandsMode** 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-498">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="5ab3f-499">將參數設定為 **TeamsAndSfB** ，以在 Outlook 中同時啟用 [團隊會議增益集] 和 [商務用 Skype] 增益集。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-499">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="5ab3f-500">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-500">This is the default value.</span></span>
- <span data-ttu-id="5ab3f-501">將參數設定為 [ **團隊** ]，只會在 Outlook 中啟用 [團隊會議] 增益集。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-501">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="5ab3f-502">此原則設定可確保所有未來的會議都有小組會議加入連結。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-502">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="5ab3f-503">它不會將現有的商務用 Skype 會議加入連結遷移至團隊。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-503">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="5ab3f-504">此原則設定不會影響商務用 Skype 中的目前狀態、聊天、PSTN 通話或任何其他功能，這表示使用者將繼續使用商務用 Skype 來取得這些功能。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-504">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="5ab3f-505">如果您將參數設定為 [ **團隊**]，然後切換回 **TeamsAndSfB**，則會啟用兩個會議增益集。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-505">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="5ab3f-506">不過，請注意，現有的團隊會議加入連結不會遷移到商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-506">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="5ab3f-507">只有在變更之後所排程的商務用 Skype 會議，才會有商務用 Skype 會議加入連結。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-507">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="5ab3f-508">會議原則設定-影片篩選模式</span><span class="sxs-lookup"><span data-stu-id="5ab3f-508">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="5ab3f-509">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-509">This is a per-user policy.</span></span> <span data-ttu-id="5ab3f-510">此設定可控制使用者是否可以在會議中自訂其影片背景。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-510">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="5ab3f-511">目前您只能使用 PowerShell 來設定此原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-511">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="5ab3f-512">您可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-512">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="5ab3f-513">或者，使用 [新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，然後將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-513">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="5ab3f-514">若要指定使用者是否可以在會議中自訂其影片背景，請設定 **VideoFiltersMode** 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ab3f-514">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="5ab3f-515">在 PowerShell 中設定值</span><span class="sxs-lookup"><span data-stu-id="5ab3f-515">Setting value in PowerShell</span></span> |<span data-ttu-id="5ab3f-516">行為</span><span class="sxs-lookup"><span data-stu-id="5ab3f-516">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="5ab3f-517">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-517">**NoFilters**</span></span>     |<span data-ttu-id="5ab3f-518">使用者無法自訂其影片背景。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-518">User can't customize their video background.</span></span>|
|<span data-ttu-id="5ab3f-519">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-519">**BlurOnly**</span></span>     |<span data-ttu-id="5ab3f-520">使用者可以選擇將影片背景模糊。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-520">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="5ab3f-521">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-521">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="5ab3f-522">使用者可以選擇將影片背景模糊，或從預設的影像集合中選擇，以做為其背景。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-522">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="5ab3f-523">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="5ab3f-523">**AllFilters**</span></span>     |<span data-ttu-id="5ab3f-524">使用選項可讓影片背景變模糊、選擇預設的影像，或上傳自訂圖像來作為其背景。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-524">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="5ab3f-525">使用者上傳的影像不會受到小組的篩選。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-525">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="5ab3f-526">當您使用 [ **AllFilters** ] 設定時，您應該擁有內部組織原則，以防止使用者上傳冒犯性或不適當的影像，或貴組織沒有許可權可供團隊會議背景使用。</span><span class="sxs-lookup"><span data-stu-id="5ab3f-526">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ab3f-527">相關主題</span><span class="sxs-lookup"><span data-stu-id="5ab3f-527">Related topics</span></span>

- [<span data-ttu-id="5ab3f-528">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="5ab3f-528">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="5ab3f-529">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="5ab3f-529">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="5ab3f-530">從使用者移除 RestrictedAnonymousAccess 團隊會議原則</span><span class="sxs-lookup"><span data-stu-id="5ab3f-530">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
