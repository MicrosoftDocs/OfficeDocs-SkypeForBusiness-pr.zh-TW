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
- m365initiative-meetings
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
description: 瞭解如何在 Teams 中管理會議政策設定，並使用這些設定來控制提供給會議參與者的功能，供使用者排程的會議使用。
ms.openlocfilehash: 5b3b2e3975906e130d81804c2db51973bf50521c
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50408199"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="d79f9-103">在 Teams 中管理會議政策</span><span class="sxs-lookup"><span data-stu-id="d79f9-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="d79f9-104">使用會議策略來控制組織中使用者排程的會議參與者可使用的功能。</span><span class="sxs-lookup"><span data-stu-id="d79f9-104">Use meeting policies to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="d79f9-105">您可以使用自動建立 (自訂) 全域自訂規則。</span><span class="sxs-lookup"><span data-stu-id="d79f9-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="d79f9-106">您可以在 Microsoft Teams 系統管理中心或 PowerShell 中管理 [會議政策](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-107">有關使用角色管理會議簡報者和出席者許可權的資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="d79f9-108">您可以用下列方式執行策略，這會影響使用者在會議開始、會議期間或會議後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="d79f9-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="d79f9-109">執行類型</span><span class="sxs-lookup"><span data-stu-id="d79f9-109">Implementation type</span></span>  |<span data-ttu-id="d79f9-110">說明</span><span class="sxs-lookup"><span data-stu-id="d79f9-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d79f9-111">每個召集人</span><span class="sxs-lookup"><span data-stu-id="d79f9-111">Per-organizer</span></span>    |<span data-ttu-id="d79f9-112">當您執行每個會議召集人的政策時，所有會議參與者會繼承該召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="d79f9-113">例如， **自動准許人員** 是每個召集人的一項政策，可控制使用者是否直接加入會議，或是在大廳等候已指派該政策的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="d79f9-114">每個使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-114">Per-user</span></span>    |<span data-ttu-id="d79f9-115">當您執行每個使用者原則時，只有每個使用者原則會適用于限制召集人和/或會議參與者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="d79f9-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="d79f9-116">例如，在頻道 **中允許現在開會** 是每個使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="d79f9-117">每一個召集人和每個使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="d79f9-118">當您執行每個召集人和每個使用者的組合時，某些功能會受限於會議參與者，其基礎是他們的政策與召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="d79f9-119">例如， **允許雲端錄製** 是每個召集人和每個使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="d79f9-120">開啟此設定以允許使用者開始和停止錄製。</span><span class="sxs-lookup"><span data-stu-id="d79f9-120">Turn on this setting to allow users to start and stop a recording.</span></span>

<span data-ttu-id="d79f9-121">您可以編輯全域原則中的設定，或建立及指派一或多個自訂策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="d79f9-122">除非您建立並指派自訂策略，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="d79f9-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-123">如果使用者已啟用音訊會議授權，或使用者允許進行音訊會議，則會議詳細資料按鈕將可供使用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="d79f9-124">建立自訂會議政策</span><span class="sxs-lookup"><span data-stu-id="d79f9-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="d79f9-125">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d79f9-126">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-126">Select **Add**.</span></span>
3. <span data-ttu-id="d79f9-127">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="d79f9-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="d79f9-128">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="d79f9-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="d79f9-129">選擇您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="d79f9-130">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-130">Select **Save**.</span></span>

<span data-ttu-id="d79f9-131">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="d79f9-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="d79f9-132">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="d79f9-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="d79f9-133">在 [音訊與視訊] 下：</span><span class="sxs-lookup"><span data-stu-id="d79f9-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="d79f9-134">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="d79f9-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="d79f9-135">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="d79f9-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="d79f9-136">在 [內容共用] 下：</span><span class="sxs-lookup"><span data-stu-id="d79f9-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="d79f9-137">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="d79f9-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="d79f9-138">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="d79f9-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="d79f9-139">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="d79f9-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="d79f9-140">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="d79f9-141">編輯會議政策</span><span class="sxs-lookup"><span data-stu-id="d79f9-141">Edit a meeting policy</span></span>

<span data-ttu-id="d79f9-142">您可以編輯全域原則和您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-142">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="d79f9-143">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d79f9-144">按一下政策名稱的左側以選取該政策， **然後選取編輯**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-144">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>
3. <span data-ttu-id="d79f9-145">從此處，進行您需要的變更。</span><span class="sxs-lookup"><span data-stu-id="d79f9-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="d79f9-146">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-146">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-147">一次只能指派一個會議政策給使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="d79f9-148">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="d79f9-149">如果已指派使用者，您即無法刪除該政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="d79f9-150">您必須先將不同的策略指派給所有受影響的使用者，然後您可以刪除原始策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="d79f9-151">會議政策設定</span><span class="sxs-lookup"><span data-stu-id="d79f9-151">Meeting policy settings</span></span>

<span data-ttu-id="d79f9-152">當您在會議政策頁面上選取現有政策或選取新增以新增策略時，您可以設定下列功能的設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following features.</span></span>

- [<span data-ttu-id="d79f9-153">一般</span><span class="sxs-lookup"><span data-stu-id="d79f9-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="d79f9-154">音訊&影片</span><span class="sxs-lookup"><span data-stu-id="d79f9-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="d79f9-155">內容共用</span><span class="sxs-lookup"><span data-stu-id="d79f9-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="d79f9-156">參與者&來賓</span><span class="sxs-lookup"><span data-stu-id="d79f9-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end

<span data-ttu-id="d79f9-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="d79f9-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="d79f9-158">會議政策設定 - 一般</span><span class="sxs-lookup"><span data-stu-id="d79f9-158">Meeting policy settings - General</span></span>

- [<span data-ttu-id="d79f9-159">在頻道中允許現在開會</span><span class="sxs-lookup"><span data-stu-id="d79f9-159">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="d79f9-160">允許 Outlook 附加元件</span><span class="sxs-lookup"><span data-stu-id="d79f9-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="d79f9-161">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="d79f9-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="d79f9-162">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="d79f9-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="d79f9-163">在私人會議中允許現在開會</span><span class="sxs-lookup"><span data-stu-id="d79f9-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="d79f9-164">在頻道中允許現在開會</span><span class="sxs-lookup"><span data-stu-id="d79f9-164">Allow Meet now in channels</span></span>

<span data-ttu-id="d79f9-165">允許 **開會** 是一項每個使用者原則，在會議開始之前即適用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-165">Allow **Meet now** is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d79f9-166">此設定可控制使用者是否可以在 Teams 頻道中啟動非計畫的會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-166">This setting controls whether a user can start an unplanned meeting in a Teams channel.</span></span> <span data-ttu-id="d79f9-167">如果您開啟此設定，使用者可以選取會議按鈕來開始非計畫的會議，或在頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-167">If you turn on this setting, users can select the **Meet** button to start an unplanned meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="d79f9-168">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="d79f9-168">The default value is True.</span></span>

![顯示訊息下方的目前開會圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="d79f9-170">允許 Outlook 附加元件</span><span class="sxs-lookup"><span data-stu-id="d79f9-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="d79f9-171">這是每個使用者原則，在會議開始之前適用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d79f9-172">此設定可控制 Teams 會議是否可以從 Outlook (Windows、Mac、Web 及行動) 。</span><span class="sxs-lookup"><span data-stu-id="d79f9-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的能力](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="d79f9-174">如果您關閉此功能，使用者就無法排程。</span><span class="sxs-lookup"><span data-stu-id="d79f9-174">If you turn this off, users are unable to schedule.</span></span> <span data-ttu-id="d79f9-175">Teams 會議在 Outlook 中建立新會議時。</span><span class="sxs-lookup"><span data-stu-id="d79f9-175">Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="d79f9-176">例如，在 Windows 上的 Outlook 中，功能區中不會顯示新 **Teams** 會議選項。</span><span class="sxs-lookup"><span data-stu-id="d79f9-176">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="d79f9-177">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="d79f9-177">Allow channel meeting scheduling</span></span>

<span data-ttu-id="d79f9-178">使用現有的 AllowChannelMeeting 排程策略來控制可以在小組頻道日曆上建立的事件種類。</span><span class="sxs-lookup"><span data-stu-id="d79f9-178">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="d79f9-179">這是每個使用者原則，在會議開始之前適用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d79f9-180">此設定會控制使用者是否可以在 Teams 頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-180">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="d79f9-181">此設定預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="d79f9-181">By default, this setting is turned on.</span></span>

<span data-ttu-id="d79f9-182">如果關閉此政策，使用者無法建立新頻道會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-182">If this policy is turned off, users can't create new channel meetings.</span></span> <span data-ttu-id="d79f9-183">不過，活動召集人可以編輯現有的頻道會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-183">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="d79f9-184">排程會議將會停用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-184">Schedule a meeting will be disabled.</span></span>

 ![顯示 Teams 中排程會議選項的螢幕擷取畫面](media/schedule-meeting-option.png)

<span data-ttu-id="d79f9-186">頻道選取已停用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-186">Channel selection is disabled.</span></span>

![選取要排程會議之頻道的月曆選項。](media/meeting-policies-select-a-channel-to-meet-in.png)

<span data-ttu-id="d79f9-188">在頻道文章頁面中，下列功能將會停用：</span><span class="sxs-lookup"><span data-stu-id="d79f9-188">In the channel posts page, the following features will be disabled:</span></span>

- <span data-ttu-id="d79f9-189">**頻道回復撰寫** 方塊上的排程會議按鈕。</span><span class="sxs-lookup"><span data-stu-id="d79f9-189">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="d79f9-190">![排程會議按鈕回復撰寫方塊](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="d79f9-190">![schedule a meeting button reply compose box](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="d79f9-191">**頻道標題上的** 排程會議按鈕。</span><span class="sxs-lookup"><span data-stu-id="d79f9-191">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="d79f9-192">![頻道標題中的排程會議按鈕](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="d79f9-192">![schedule a meeting button in the channel header](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="d79f9-193">在頻道日曆中：</span><span class="sxs-lookup"><span data-stu-id="d79f9-193">In the channel calendar:</span></span>

- <span data-ttu-id="d79f9-194">**頻道月曆標題** 上的新增活動按鈕將會停用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-194">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="d79f9-195">![已停用頻道月曆標題上的按鈕](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="d79f9-195">![button on channel calendar header disabled](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="d79f9-196">使用者無法拖曳並選取頻道日曆上的時間區塊，以建立頻道會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-196">Users won't be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="d79f9-197">使用者無法使用鍵盤快速鍵在頻道日曆上建立會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-197">Users can't use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="d79f9-198">在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="d79f9-198">In the admin center:</span></span>

<span data-ttu-id="d79f9-199">頻道日曆應用程式會顯示在應用程式許可權政策頁面上 **的 Microsoft 應用程式** 區段。</span><span class="sxs-lookup"><span data-stu-id="d79f9-199">The channel calendar app will show up in the **Microsoft apps** section on the app permission policies page.</span></span>

 ![Teams 系統管理中心中的應用程式許可權政策](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="d79f9-201">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="d79f9-201">Allow scheduling private meetings</span></span>

<span data-ttu-id="d79f9-202">這是每個使用者原則，在會議開始之前適用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-202">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d79f9-203">此設定會控制使用者是否可以在 Teams 中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-203">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="d79f9-204">當會議未發佈到團隊中的頻道時，會議即為私人會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-204">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="d79f9-205">如果您關閉允許排 **程** 私人會議和允許頻道會議 **排** 程，Teams 中的使用者會停用新增必要的出席者及新增頻道選項。</span><span class="sxs-lookup"><span data-stu-id="d79f9-205">If you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="d79f9-206">此設定預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="d79f9-206">By default, this setting is turned on.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="d79f9-207">在私人會議中允許現在開會</span><span class="sxs-lookup"><span data-stu-id="d79f9-207">Allow Meet now in private meetings</span></span>

<span data-ttu-id="d79f9-208">這是每個使用者原則，在會議開始之前適用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-208">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d79f9-209">此設定可控制使用者是否可以啟動非計畫的私人會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-209">This setting controls whether a user can start an unplanned private meeting.</span></span> <span data-ttu-id="d79f9-210">此設定預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="d79f9-210">By default, this setting is turned on.</span></span>

<span data-ttu-id="d79f9-211"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="d79f9-211"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="d79f9-212">會議政策設定 - 音訊&影片</span><span class="sxs-lookup"><span data-stu-id="d79f9-212">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="d79f9-213">允許抄寫</span><span class="sxs-lookup"><span data-stu-id="d79f9-213">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="d79f9-214">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="d79f9-214">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="d79f9-215">IP 音訊模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-215">Mode for IP audio</span></span>](#mode-for-ip-audio)
- [<span data-ttu-id="d79f9-216">IP 影片模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-216">Mode for IP video</span></span>](#mode-for-ip-video)
- [<span data-ttu-id="d79f9-217">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-217">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="d79f9-218">媒體位元速率 (Kb) </span><span class="sxs-lookup"><span data-stu-id="d79f9-218">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="d79f9-219">允許抄寫</span><span class="sxs-lookup"><span data-stu-id="d79f9-219">Allow transcription</span></span>

<span data-ttu-id="d79f9-220">這是每個召集人和每個使用者政策的組合。</span><span class="sxs-lookup"><span data-stu-id="d79f9-220">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d79f9-221">此設定可控制在播放會議錄製時，是否可以使用字幕和文字抄寫功能。</span><span class="sxs-lookup"><span data-stu-id="d79f9-221">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="d79f9-222">如果您關閉此功能，在播放會議錄製時，將無法使用搜尋和 CC 選項。</span><span class="sxs-lookup"><span data-stu-id="d79f9-222">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="d79f9-223">開始錄製的人必須開啟此設定，如此一來，錄製也會包含文字抄寫。</span><span class="sxs-lookup"><span data-stu-id="d79f9-223">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="d79f9-224">錄製的會議文字抄寫功能目前僅支援在 Teams 中將語言設定為英文，以及會議中會使用英文的使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-224">Transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![會議中的抄寫選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="d79f9-226">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="d79f9-226">Allow cloud recording</span></span>

<span data-ttu-id="d79f9-227">這是根據每個使用者策略控制。</span><span class="sxs-lookup"><span data-stu-id="d79f9-227">This is controlled at a per-user policy.</span></span> <span data-ttu-id="d79f9-228">此設定會控制使用者是否可以錄製。</span><span class="sxs-lookup"><span data-stu-id="d79f9-228">This setting controls whether a user can record.</span></span> <span data-ttu-id="d79f9-229">如果會議召集人或另一個會議參與者的特定策略設定已開啟，且如果他們是來自與會議召集人同一個組織的已驗證使用者，就可以開始錄製。</span><span class="sxs-lookup"><span data-stu-id="d79f9-229">The recording can be started by the meeting organizer or by another meeting participant if their specific policy setting is turned on and if they're an authenticated user from the same organization as the organizer.</span></span>

<span data-ttu-id="d79f9-230">組織外部人員 ，例如聯盟和匿名使用者，無法開始錄製。</span><span class="sxs-lookup"><span data-stu-id="d79f9-230">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="d79f9-231">來賓使用者無法開始或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="d79f9-231">Guest users can't start or stop the recording.</span></span>

![錄製選項](media/meeting-policies-recording.png)

<span data-ttu-id="d79f9-233">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-233">Let's look at the following example.</span></span>

|<span data-ttu-id="d79f9-234">使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-234">User</span></span> |<span data-ttu-id="d79f9-235">會議原則</span><span class="sxs-lookup"><span data-stu-id="d79f9-235">Meeting policy</span></span>  |<span data-ttu-id="d79f9-236">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="d79f9-236">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d79f9-237">Daniela</span><span class="sxs-lookup"><span data-stu-id="d79f9-237">Daniela</span></span> | <span data-ttu-id="d79f9-238">全域</span><span class="sxs-lookup"><span data-stu-id="d79f9-238">Global</span></span>   | <span data-ttu-id="d79f9-239">關閉</span><span class="sxs-lookup"><span data-stu-id="d79f9-239">Off</span></span> |
|<span data-ttu-id="d79f9-240">艾曼達</span><span class="sxs-lookup"><span data-stu-id="d79f9-240">Amanda</span></span> | <span data-ttu-id="d79f9-241">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d79f9-241">Location1MeetingPolicy</span></span> | <span data-ttu-id="d79f9-242">On</span><span class="sxs-lookup"><span data-stu-id="d79f9-242">On</span></span>|
|<span data-ttu-id="d79f9-243">John (外部使用者) </span><span class="sxs-lookup"><span data-stu-id="d79f9-243">John (external user)</span></span> | <span data-ttu-id="d79f9-244">不適用</span><span class="sxs-lookup"><span data-stu-id="d79f9-244">Not applicable</span></span> | <span data-ttu-id="d79f9-245">不適用</span><span class="sxs-lookup"><span data-stu-id="d79f9-245">Not applicable</span></span>|

<span data-ttu-id="d79f9-246">她即使是召集人，也無法錄製，因為她的政策已設定為關閉。</span><span class="sxs-lookup"><span data-stu-id="d79f9-246">Daniela, even if she were the organizer, can't record because her policy is set to off.</span></span> <span data-ttu-id="d79f9-247">已啟用策略設定的安百達可以錄製會議，即使是由方安達組織的會議也可以。</span><span class="sxs-lookup"><span data-stu-id="d79f9-247">Amanda, who has the policy setting enabled, can record meetings, even those organized by Daniela.</span></span> <span data-ttu-id="d79f9-248">如果 Amanda 要組織會議，她將能夠錄製會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-248">If Amanda were to organize a meeting, she'll be able to record that meeting.</span></span> <span data-ttu-id="d79f9-249">不過，已停用該政策設定且 John 是外部使用者，因此無法錄製該會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-249">However, Daniela, who has the policy setting disabled and John who is an external user, can't record that meeting.</span></span>

<span data-ttu-id="d79f9-250">若要深入瞭解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-250">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="mode-for-ip-audio"></a><span data-ttu-id="d79f9-251">IP 音訊模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-251">Mode for IP audio</span></span>

<span data-ttu-id="d79f9-252">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-252">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-253">此設定可控制是否可以在會議和群組通話中開啟音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-253">This setting controls whether audio can be turned on in meetings and group calls.</span></span> <span data-ttu-id="d79f9-254">以下是此設定的值。</span><span class="sxs-lookup"><span data-stu-id="d79f9-254">Here are the values for this setting.</span></span>

|<span data-ttu-id="d79f9-255">設定值</span><span class="sxs-lookup"><span data-stu-id="d79f9-255">Setting value</span></span> |<span data-ttu-id="d79f9-256">行為</span><span class="sxs-lookup"><span data-stu-id="d79f9-256">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d79f9-257">**已啟用外向和傳入音訊**</span><span class="sxs-lookup"><span data-stu-id="d79f9-257">**Outgoing and incoming audio enabled**</span></span>    |<span data-ttu-id="d79f9-258">會議允許外發和傳入音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-258">Outgoing and incoming audio is allowed in the meeting.</span></span> <span data-ttu-id="d79f9-259">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-259">This is the default setting.</span></span> |
|<span data-ttu-id="d79f9-260">**禁用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-260">**Disabled**</span></span>     |<span data-ttu-id="d79f9-261">傳出和傳入音訊在會議中會關閉。</span><span class="sxs-lookup"><span data-stu-id="d79f9-261">Outgoing and incoming audio is turned off in the meeting.</span></span>     |

<span data-ttu-id="d79f9-262">如果使用者設為停用，該使用者仍然可以排程和組織會議，但他們無法使用音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-262">If set to **Disabled** for a user, that user can still schedule and organize meetings but they can't use audio.</span></span> <span data-ttu-id="d79f9-263">若要加入會議，他們必須透過公用交換電話網路 (PSTN) 或透過電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-263">To join a meeting, they have to dial in through the Public Switched Telephone Network (PSTN) or have the meeting call and join them by phone.</span></span> <span data-ttu-id="d79f9-264">未指派任何規則的會議參與者 (例如，匿名參與者) 預設會啟用撥出和傳入音訊。 </span><span class="sxs-lookup"><span data-stu-id="d79f9-264">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming audio enabled** by default.</span></span> <span data-ttu-id="d79f9-265">在 Teams 行動用戶端上，如果這項設定已停用，使用者必須透過 PSTN 撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-265">On Teams mobile clients, if this setting is disabled, the user has to dial in to the meeting through the PSTN.</span></span>

<span data-ttu-id="d79f9-266">此設定不適用於 1 對 1 通話。</span><span class="sxs-lookup"><span data-stu-id="d79f9-266">This setting doesn't apply to 1:1 calls.</span></span> <span data-ttu-id="d79f9-267">若要限制 1 對 1 通話，請設定 Teams [通話政策](teams-calling-policy.md) ，並關閉撥打私人 **電話** 設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-267">To restrict 1:1 calls, configure a Teams [calling policy](teams-calling-policy.md) and turn off the **Make private calls** setting.</span></span> <span data-ttu-id="d79f9-268">這項設定也不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="d79f9-268">This setting also doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="d79f9-269">Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD 環境) 這項設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-269">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

<span data-ttu-id="d79f9-270">若要深入瞭解，請參閱管理 [會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-270">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="mode-for-ip-video"></a><span data-ttu-id="d79f9-271">IP 影片模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-271">Mode for IP video</span></span>

<span data-ttu-id="d79f9-272">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-272">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-273">此設定可控制是否可以在會議和群組通話中開啟視音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-273">This setting controls whether video can be turned on in meetings and group calls.</span></span> <span data-ttu-id="d79f9-274">以下是此設定的值。</span><span class="sxs-lookup"><span data-stu-id="d79f9-274">Here are the values for this setting.</span></span>

|<span data-ttu-id="d79f9-275">設定值</span><span class="sxs-lookup"><span data-stu-id="d79f9-275">Setting value</span></span> |<span data-ttu-id="d79f9-276">行為</span><span class="sxs-lookup"><span data-stu-id="d79f9-276">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d79f9-277">**已啟用外向和傳入視**</span><span class="sxs-lookup"><span data-stu-id="d79f9-277">**Outgoing and incoming video enabled**</span></span>    | <span data-ttu-id="d79f9-278">會議允許外發和傳入視音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-278">Outgoing and incoming video is allowed in the meeting.</span></span> <span data-ttu-id="d79f9-279">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-279">This is the default setting.</span></span> |
|<span data-ttu-id="d79f9-280">**禁用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-280">**Disabled**</span></span>     | <span data-ttu-id="d79f9-281">外發和傳入的視音訊在會議中會關閉。</span><span class="sxs-lookup"><span data-stu-id="d79f9-281">Outgoing and incoming video is turned off in the meeting.</span></span> <span data-ttu-id="d79f9-282">在 Teams 行動用戶端上，使用者無法共用會議中的影片或相片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-282">On Teams mobile clients, users can't share videos or photos in the meeting.</span></span> <br><br><span data-ttu-id="d79f9-283">請注意，如果 **IP 音訊模式** 已停用， **則 IP** 視障模式也會維持停用狀態。</span><span class="sxs-lookup"><span data-stu-id="d79f9-283">Note that if **Mode for IP audio** is disabled, then **Mode for IP video** will also remain disabled.</span></span>  |

<span data-ttu-id="d79f9-284">如果使用者設為停用，該使用者無法開啟視障或觀看其他會議參與者共用的影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-284">If set to **Disabled** for a  user, that user can't turn on video or view videos shared by other meeting participants.</span></span> <span data-ttu-id="d79f9-285">未指派任何規則的會議參與者 (例如，匿名參與者) 預設會啟用此設定為外) 和傳入影片。 </span><span class="sxs-lookup"><span data-stu-id="d79f9-285">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming video enabled** by default.</span></span>

<span data-ttu-id="d79f9-286">這項設定不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="d79f9-286">This setting doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="d79f9-287">Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD 環境) 這項設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-287">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-288">請記住，此設定會控制外發和傳入視事，而 **允許 IP 視** 區設定則控制外接視。</span><span class="sxs-lookup"><span data-stu-id="d79f9-288">Keep in mind that this setting controls both outgoing and incoming video whereas the **Allow IP video** setting controls outgoing video.</span></span> <span data-ttu-id="d79f9-289">若要深入瞭解，請參閱 [哪個 IP 視視策略設定為優先？](#which-ip-video-policy-setting-takes-precedence) 以及管理會議參與者 [的音訊/視音訊](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-289">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

<span data-ttu-id="d79f9-290">若要深入瞭解，請參閱管理 [會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-290">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="d79f9-291">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-291">Allow IP video</span></span>

<span data-ttu-id="d79f9-292">這是每個召集人和每個使用者政策的組合。</span><span class="sxs-lookup"><span data-stu-id="d79f9-292">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d79f9-293">影片是會議的重要元件。</span><span class="sxs-lookup"><span data-stu-id="d79f9-293">Video is a key component to meetings.</span></span> <span data-ttu-id="d79f9-294">在某些組織中，系統管理員可能會想要進一控制哪些使用者的會議有視音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-294">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="d79f9-295">此設定可控制是否可以在使用者主持的會議，以及由使用者啟動的 1：1 和群組通話中開啟視訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-295">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 and group calls started by a user.</span></span> <span data-ttu-id="d79f9-296">在 Teams 行動用戶端上，此設定可控制使用者是否可以在會議共用相片和影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-296">On Teams mobile clients, this setting control whether users can share photos and videos in a meeting.</span></span>

<span data-ttu-id="d79f9-297">由已啟用此策略設定的使用者所組織的會議，允許會議參與者在會議中共用視像，如果參與者也已啟用該策略設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-297">Meetings organized by a user who has this policy setting enabled, allow video sharing in the meeting by the meeting participants, if the participants also have the policy setting enabled.</span></span> <span data-ttu-id="d79f9-298">未指派任何策略的會議參與者 (例如匿名和) 繼承會議召集人的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-298">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-299">請記住，此設定會控制外接視視， **而 IP 視** 區模式則同時控制外接和傳入視事。</span><span class="sxs-lookup"><span data-stu-id="d79f9-299">Keep in mind that this setting controls outgoing video whereas the **Mode for IP video** setting controls both outgoing and incoming video.</span></span> <span data-ttu-id="d79f9-300">若要深入瞭解，請參閱 [哪個 IP 視視策略設定為優先？](#which-ip-video-policy-setting-takes-precedence) 以及管理會議參與者 [的音訊/視音訊](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-300">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

| <span data-ttu-id="d79f9-301">Teams 桌面與 Web 用戶端</span><span class="sxs-lookup"><span data-stu-id="d79f9-301">Teams desktop and web client</span></span> |<span data-ttu-id="d79f9-302">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="d79f9-302">Teams mobile client</span></span>  |
|:-------:|:-------:|
|![螢幕擷取畫面顯示桌上型電腦音訊/視音訊設定的會議加入](media/meeting-policies-audio-video-settings.png)    |![螢幕擷取畫面顯示使用行動版音訊/視音訊設定加入會議](media/meeting-policies-mobile-join.png)          |

<span data-ttu-id="d79f9-305">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-305">Let's look at the following example.</span></span>

|<span data-ttu-id="d79f9-306">使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-306">User</span></span> |<span data-ttu-id="d79f9-307">會議原則</span><span class="sxs-lookup"><span data-stu-id="d79f9-307">Meeting policy</span></span>  |<span data-ttu-id="d79f9-308">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-308">Allow IP video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d79f9-309">Daniela</span><span class="sxs-lookup"><span data-stu-id="d79f9-309">Daniela</span></span>   | <span data-ttu-id="d79f9-310">全域</span><span class="sxs-lookup"><span data-stu-id="d79f9-310">Global</span></span>   | <span data-ttu-id="d79f9-311">On</span><span class="sxs-lookup"><span data-stu-id="d79f9-311">On</span></span>       |
|<span data-ttu-id="d79f9-312">艾曼達</span><span class="sxs-lookup"><span data-stu-id="d79f9-312">Amanda</span></span>    | <span data-ttu-id="d79f9-313">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d79f9-313">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d79f9-314">關閉</span><span class="sxs-lookup"><span data-stu-id="d79f9-314">Off</span></span>      |

<span data-ttu-id="d79f9-315">由 Daniela 主持的會議允許開啟視區。</span><span class="sxs-lookup"><span data-stu-id="d79f9-315">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="d79f9-316">Daniela 可以加入會議並開啟影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-316">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="d79f9-317">Amanda 無法開啟在雅可的會議視像，因為安百達的這個政策設定為不允許視視。</span><span class="sxs-lookup"><span data-stu-id="d79f9-317">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="d79f9-318">Amanda 可以在會議中查看其他參與者共用的影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-318">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="d79f9-319">在由 Amanda 主持的會議中，無論指派的視音訊策略如何，沒有人可以開啟視音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-319">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="d79f9-320">這表示在安甘達的會議中，有一段影片無法開啟。</span><span class="sxs-lookup"><span data-stu-id="d79f9-320">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="d79f9-321">如果 Daniela 撥打 Amanda 視音訊，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="d79f9-321">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span> <span data-ttu-id="d79f9-322">當通話接通時，Amanda 可以看到張雅華的視視，但無法開啟視視。</span><span class="sxs-lookup"><span data-stu-id="d79f9-322">When the call is connected, Amanda can see Daniela's video but can't turn on video.</span></span> <span data-ttu-id="d79f9-323">如果 Amanda 打電話給立達，立達可以使用視音訊和視音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="d79f9-323">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="d79f9-324">當通話接通時，Daniela 可以視需要開啟或關閉視音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-324">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

<span data-ttu-id="d79f9-325">若要深入瞭解，請參閱管理 [會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-325">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

#### <a name="which-ip-video-policy-setting-takes-precedence"></a><span data-ttu-id="d79f9-326">哪個 IP 視視策略設定優先</span><span class="sxs-lookup"><span data-stu-id="d79f9-326">Which IP video policy setting takes precedence</span></span>

<span data-ttu-id="d79f9-327">對於使用者，影片的最嚴格政策設定會優先。</span><span class="sxs-lookup"><span data-stu-id="d79f9-327">For a user, the most restrictive policy setting for video takes precedence.</span></span> <span data-ttu-id="d79f9-328">以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-328">Here's some examples.</span></span>

|<span data-ttu-id="d79f9-329">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-329">Allow IP video</span></span>|<span data-ttu-id="d79f9-330">IP 影片模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-330">Mode for IP video</span></span>|<span data-ttu-id="d79f9-331">會議體驗</span><span class="sxs-lookup"><span data-stu-id="d79f9-331">Meeting experience</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d79f9-332">召集人： **在**</span><span class="sxs-lookup"><span data-stu-id="d79f9-332">Organizer: **On**</span></span><br><br><span data-ttu-id="d79f9-333">參與者： **已**</span><span class="sxs-lookup"><span data-stu-id="d79f9-333">Participant: **On**</span></span> |<span data-ttu-id="d79f9-334">參與者： **已停用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-334">Participant: **Disabled**</span></span>        |<span data-ttu-id="d79f9-335">IP **視區模式設定** 會優先。</span><span class="sxs-lookup"><span data-stu-id="d79f9-335">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="d79f9-336">指派此政策的參與者無法開啟或觀看其他人共用的影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-336">The participant who is assigned this policy can't turn on or view videos shared by others.</span></span>|
|<span data-ttu-id="d79f9-337">召集人： **在**</span><span class="sxs-lookup"><span data-stu-id="d79f9-337">Organizer: **On**</span></span><br><br><span data-ttu-id="d79f9-338">參與者： **已**</span><span class="sxs-lookup"><span data-stu-id="d79f9-338">Participant: **On**</span></span> |<span data-ttu-id="d79f9-339">參與者： **已啟用外向和傳入視訊**</span><span class="sxs-lookup"><span data-stu-id="d79f9-339">Participant: **Outgoing and incoming video enabled**</span></span>          |<span data-ttu-id="d79f9-340">指派此政策的參與者可以開啟或觀看其他人共用的影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-340">The participant who is assigned this policy can turn on or view videos shared by others.</span></span>         |
|<span data-ttu-id="d79f9-341">召集人： **在**</span><span class="sxs-lookup"><span data-stu-id="d79f9-341">Organizer: **On**</span></span><br><br><span data-ttu-id="d79f9-342">參與者： **關閉**</span><span class="sxs-lookup"><span data-stu-id="d79f9-342">Participant: **Off**</span></span> |<span data-ttu-id="d79f9-343">參與者： **已啟用外向和傳入視訊**</span><span class="sxs-lookup"><span data-stu-id="d79f9-343">Participant: **Outgoing and incoming video enabled**</span></span>         |<span data-ttu-id="d79f9-344">允許 **IP 視區** 設定會優先。</span><span class="sxs-lookup"><span data-stu-id="d79f9-344">The **Allow IP video** setting takes precedence.</span></span> <span data-ttu-id="d79f9-345">參與者只能看到傳入的影片，而且無法傳送外寄影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-345">Participants can only see incoming video and can't send outgoing video.</span></span>         |
|<span data-ttu-id="d79f9-346">召集人： **在**</span><span class="sxs-lookup"><span data-stu-id="d79f9-346">Organizer: **On**</span></span><br><br><span data-ttu-id="d79f9-347">參與者： **關閉**</span><span class="sxs-lookup"><span data-stu-id="d79f9-347">Participant: **Off**</span></span> |<span data-ttu-id="d79f9-348">參與者： **已停用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-348">Participant: **Disabled**</span></span>         |<span data-ttu-id="d79f9-349">IP **視區模式設定** 會優先。</span><span class="sxs-lookup"><span data-stu-id="d79f9-349">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="d79f9-350">參與者無法看到傳入或傳出的影片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-350">The participant can't see incoming or outgoing video.</span></span>|
|<span data-ttu-id="d79f9-351">召集人： **關閉**</span><span class="sxs-lookup"><span data-stu-id="d79f9-351">Organizer: **Off**</span></span>    |       |<span data-ttu-id="d79f9-352">允許 **IP 視區** 設定會優先，因為會議召集人已關閉此設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-352">The **Allow IP video** setting takes precedence because it's turned off for the organizer.</span></span> <span data-ttu-id="d79f9-353">在指派此政策的使用者所組織的會議中，沒有人可以開啟視音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-353">No one can turn on video in meetings organized by the user who is assigned this policy.</span></span>         |

### <a name="manage-audiovideo-for-meeting-participants"></a><span data-ttu-id="d79f9-354">管理會議參與者的音訊/視音訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-354">Manage audio/video for meeting participants</span></span>

|<span data-ttu-id="d79f9-355">如果您想要...</span><span class="sxs-lookup"><span data-stu-id="d79f9-355">If you want to...</span></span>  |<span data-ttu-id="d79f9-356">設定下列政策設定</span><span class="sxs-lookup"><span data-stu-id="d79f9-356">Set the following policy settings</span></span>  |
|---------|---------|
|<span data-ttu-id="d79f9-357">停用會議參與者的音訊和視音訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-357">Disable audio and video for participants in meetings</span></span>  |<span data-ttu-id="d79f9-358">IP 音訊模式： **已停用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-358">Mode for IP audio: **Disabled**</span></span><br> <span data-ttu-id="d79f9-359">IP 視訊模式： **已停用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-359">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="d79f9-360">允許 IP 影片：N/A</span><span class="sxs-lookup"><span data-stu-id="d79f9-360">Allow IP video: N/A</span></span>       |
|<span data-ttu-id="d79f9-361">僅為會議參與者啟用傳入視像和音訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-361">Enable only incoming video and audio for participants in meetings</span></span>  |<span data-ttu-id="d79f9-362">IP 音訊模式：已啟用外 **接和傳入音訊**</span><span class="sxs-lookup"><span data-stu-id="d79f9-362">Mode for IP audio: **Outgoing and incoming audio enabled**</span></span><br> <span data-ttu-id="d79f9-363">IP 視訊模式： **已啟用外接和傳入視訊**</span><span class="sxs-lookup"><span data-stu-id="d79f9-363">Mode for IP video: **Outgoing and incoming video enabled**</span></span><br><span data-ttu-id="d79f9-364">允許 IP 影片： **關閉**</span><span class="sxs-lookup"><span data-stu-id="d79f9-364">Allow IP video: **Off**</span></span>       |
|<span data-ttu-id="d79f9-365">停用會議參與者的視 (參與者只有音訊) </span><span class="sxs-lookup"><span data-stu-id="d79f9-365">Disable video for participants in meetings (participants have audio only)</span></span>|  <span data-ttu-id="d79f9-366">IP 音訊模式： **啟用外接和傳入音訊**</span><span class="sxs-lookup"><span data-stu-id="d79f9-366">Mode for IP audio: **Enable outgoing and incoming audio**</span></span><br> <span data-ttu-id="d79f9-367">IP 視訊模式： **已停用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-367">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="d79f9-368">允許 IP 影片：N/A</span><span class="sxs-lookup"><span data-stu-id="d79f9-368">Allow IP video: N/A</span></span>
|<span data-ttu-id="d79f9-369">為會議參與者啟用音訊和視音訊</span><span class="sxs-lookup"><span data-stu-id="d79f9-369">Enable audio and video for participants in meetings</span></span>    |<span data-ttu-id="d79f9-370">IP 音訊模式：預設會 **啟用** 外 (傳入) </span><span class="sxs-lookup"><span data-stu-id="d79f9-370">Mode for IP audio: **Outgoing and incoming audio enabled** (default)</span></span><br> <span data-ttu-id="d79f9-371">IP 視訊模式 **：啟用** 外 (視訊) </span><span class="sxs-lookup"><span data-stu-id="d79f9-371">Mode for IP video: **Outgoing and incoming video enabled** (default)</span></span><br><span data-ttu-id="d79f9-372">允許 IP 視訊 **： (** 預設) </span><span class="sxs-lookup"><span data-stu-id="d79f9-372">Allow IP video: **On** (default)</span></span>    |

<span data-ttu-id="d79f9-373">會採用會議召集人原則與使用者原則之間限制最嚴格的原則。</span><span class="sxs-lookup"><span data-stu-id="d79f9-373">The most restrictive policy between the meeting organizer’s policy and the user’s policy applies.</span></span> <span data-ttu-id="d79f9-374">例如，如果會議召集人有限制視音訊的政策，而使用者的政策沒有限制視視，則會議參與者會繼承會議召集人的政策，而且無法存取會議中的視音訊。</span><span class="sxs-lookup"><span data-stu-id="d79f9-374">For example, if an organizer has a policy that restricts video and a user’s policy doesn't restrict video, meeting participants inherit the policy of the meeting organizer and don't have access to video in meetings.</span></span> <span data-ttu-id="d79f9-375">這表示他們只能使用音訊加入會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-375">This means that they can join the meeting with audio only.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-376">當使用者啟動群組通話以使用電話加入時，音訊 **畫面** 中不會顯示使用電話。</span><span class="sxs-lookup"><span data-stu-id="d79f9-376">When a user starts a group call to join by phone, the **Use phone for audio** screen doesn't appear.</span></span> <span data-ttu-id="d79f9-377">這是我們正在努力解決的已知問題。</span><span class="sxs-lookup"><span data-stu-id="d79f9-377">This is a known issue that we're working to resolve.</span></span> <span data-ttu-id="d79f9-378">若要解決此問題，請在其他連接選項 **下** 選取 **電話音訊**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-378">To work around this issue, select **Phone audio** under **Other join options**.</span></span>  

#### <a name="teams-mobile-clients"></a><span data-ttu-id="d79f9-379">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="d79f9-379">Teams mobile clients</span></span>

<span data-ttu-id="d79f9-380">對於 Teams 行動用戶端的使用者，在會議期間共用相片和影片的能力也取決於允許 **IP 視視** 或 **IP 視區模式** 設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-380">For users on Teams mobile clients, the ability to share photos and videos during a meeting is also determined by the **Allow IP video** or **IP video mode** setting.</span></span> <span data-ttu-id="d79f9-381">根據優先處理哪些政策設定，無法共用影片和相片。</span><span class="sxs-lookup"><span data-stu-id="d79f9-381">Depending on which policy setting takes precedence, the ability to share videos and photos won't be available.</span></span> <span data-ttu-id="d79f9-382">這不會影響螢幕畫面分享，因為螢幕畫面分享是使用個別的螢幕 [畫面分享模式](#screen-sharing-mode) 設定所設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-382">This doesn't affect screen sharing, which you configure using a separate [Screen sharing mode](#screen-sharing-mode) setting.</span></span> <span data-ttu-id="d79f9-383">此外，您可以設定 [Teams 行動](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) 性政策，防止行動使用者以行動資料線連接使用 IP 影片，這表示他們必須使用 WiFi 連接。</span><span class="sxs-lookup"><span data-stu-id="d79f9-383">Additionally, you can set a [Teams mobility policy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) to prevent mobile users from using IP video over a cellular connection, which means they must use a WiFi connection.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="d79f9-384">媒體位元速率 (Kb) </span><span class="sxs-lookup"><span data-stu-id="d79f9-384">Media bit rate (Kbs)</span></span>

<span data-ttu-id="d79f9-385">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-385">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-386">此設定會決定使用者在通話和會議中進行音訊、視視和視視應用程式共用傳輸的媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="d79f9-386">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="d79f9-387">它會同時適用于通話或會議使用者上下移動的上行和下行媒體。</span><span class="sxs-lookup"><span data-stu-id="d79f9-387">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="d79f9-388">此設定讓您精細地控制管理貴組織的頻寬。</span><span class="sxs-lookup"><span data-stu-id="d79f9-388">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="d79f9-389">根據使用者所需的會議案例，我們建議有足夠的頻寬，提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="d79f9-389">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="d79f9-390">最小值為 30 Kbps，最大值取決於會議案例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-390">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="d79f9-391">若要深入瞭解 Teams 中高品質會議、通話和即時活動的最低建議頻寬，請參閱 [頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-391">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="d79f9-392">如果會議沒有足夠的頻寬，參與者會看到一則訊息，指出網路品質不佳。</span><span class="sxs-lookup"><span data-stu-id="d79f9-392">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="d79f9-393">針對需要最高品質影片體驗的會議，例如 CEO 會議及 Teams 即時活動，建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="d79f9-393">For meetings that need the highest-quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="d79f9-394">即使已設定最大使用體驗，當偵測到特定網路條件時，Teams 媒體堆疊會視情況調整為低頻寬條件。</span><span class="sxs-lookup"><span data-stu-id="d79f9-394">Even when the maximum experience is set, the Teams media stack adapts to low-bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="d79f9-395">會議政策設定 - 內容共用</span><span class="sxs-lookup"><span data-stu-id="d79f9-395">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="d79f9-396">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-396">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="d79f9-397">允許參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="d79f9-397">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="d79f9-398">允許外部參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="d79f9-398">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="d79f9-399">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="d79f9-399">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="d79f9-400">允許白板</span><span class="sxs-lookup"><span data-stu-id="d79f9-400">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="d79f9-401">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="d79f9-401">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="d79f9-402">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-402">Screen sharing mode</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-403">這項功能仍在開發中。</span><span class="sxs-lookup"><span data-stu-id="d79f9-403">This feature is still in development.</span></span> <span data-ttu-id="d79f9-404">螢幕畫面分享是每個參與者的一項政策，但如本節所述，可能會受召集人的螢幕畫面分享設定影響。</span><span class="sxs-lookup"><span data-stu-id="d79f9-404">Screen sharing is a per-participant policy, however, it can be affected by the organizer's screen sharing settings, as described in this section.</span></span>

<span data-ttu-id="d79f9-405">此設定會控制使用者會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-405">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="d79f9-406">未指派任何策略的會議參與者 (例如匿名、來賓、B2B 和) 繼承會議召集人的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-406">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="d79f9-407">設定值</span><span class="sxs-lookup"><span data-stu-id="d79f9-407">Setting value</span></span> |<span data-ttu-id="d79f9-408">行為</span><span class="sxs-lookup"><span data-stu-id="d79f9-408">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d79f9-409">**整個螢幕**</span><span class="sxs-lookup"><span data-stu-id="d79f9-409">**Entire screen**</span></span>    | <span data-ttu-id="d79f9-410">會議允許完整桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="d79f9-410">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="d79f9-411">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="d79f9-411">**Single application**</span></span>   | <span data-ttu-id="d79f9-412">會議允許應用程式共用</span><span class="sxs-lookup"><span data-stu-id="d79f9-412">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="d79f9-413">**禁用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-413">**Disabled**</span></span>     |<span data-ttu-id="d79f9-414">會議已關閉螢幕畫面分享和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-414">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="d79f9-415">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-415">Let's look at the following example.</span></span>

|<span data-ttu-id="d79f9-416">使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-416">User</span></span> |<span data-ttu-id="d79f9-417">會議原則</span><span class="sxs-lookup"><span data-stu-id="d79f9-417">Meeting policy</span></span> |<span data-ttu-id="d79f9-418">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-418">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d79f9-419">Daniela</span><span class="sxs-lookup"><span data-stu-id="d79f9-419">Daniela</span></span>  | <span data-ttu-id="d79f9-420">全域</span><span class="sxs-lookup"><span data-stu-id="d79f9-420">Global</span></span>   | <span data-ttu-id="d79f9-421">整個螢幕</span><span class="sxs-lookup"><span data-stu-id="d79f9-421">Entire screen</span></span> |
|<span data-ttu-id="d79f9-422">艾曼達</span><span class="sxs-lookup"><span data-stu-id="d79f9-422">Amanda</span></span>   | <span data-ttu-id="d79f9-423">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d79f9-423">Location1MeetingPolicy</span></span>  | <span data-ttu-id="d79f9-424">禁用</span><span class="sxs-lookup"><span data-stu-id="d79f9-424">Disabled</span></span> |

<span data-ttu-id="d79f9-425">Daniela 主持的會議允許會議參與者共用其整個螢幕或特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="d79f9-425">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="d79f9-426">如果 Amanda 加入立安達的會議，由於她的政策設定已停用，因此她無法共用螢幕或特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="d79f9-426">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="d79f9-427">在由 Amanda 主持的會議中，無論指派的螢幕共用模式策略如何，都不允許任何人共用螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="d79f9-427">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="d79f9-428">這表示雅心無法共用螢幕畫面或 Amanda 會議中的單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="d79f9-428">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="d79f9-429">目前，如果使用者使用的是 Google Chrome，他們無法播放影片或在 Teams 會議分享螢幕畫面。</span><span class="sxs-lookup"><span data-stu-id="d79f9-429">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="d79f9-430">允許參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="d79f9-430">Allow a participant to give or request control</span></span>

<span data-ttu-id="d79f9-431">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-431">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-432">此設定會控制使用者是否可以將共用桌面或視窗的控制權授予其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-432">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="d79f9-433">若要提供控制權，請將游標停留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="d79f9-433">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="d79f9-434">如果使用者已開啟此設定，共用會話的頂端列會顯示提供控制選項。</span><span class="sxs-lookup"><span data-stu-id="d79f9-434">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![顯示提供控制項選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="d79f9-436">如果使用者的設定已關閉， **則沒有提供** 控制項選項。</span><span class="sxs-lookup"><span data-stu-id="d79f9-436">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示沒有提供控制權選項](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="d79f9-438">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-438">Let's look at the following example.</span></span>

|<span data-ttu-id="d79f9-439">使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-439">User</span></span> |<span data-ttu-id="d79f9-440">會議原則</span><span class="sxs-lookup"><span data-stu-id="d79f9-440">Meeting policy</span></span>  |<span data-ttu-id="d79f9-441">允許參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="d79f9-441">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d79f9-442">Daniela</span><span class="sxs-lookup"><span data-stu-id="d79f9-442">Daniela</span></span>   | <span data-ttu-id="d79f9-443">全域</span><span class="sxs-lookup"><span data-stu-id="d79f9-443">Global</span></span>   | <span data-ttu-id="d79f9-444">On</span><span class="sxs-lookup"><span data-stu-id="d79f9-444">On</span></span>       |
|<span data-ttu-id="d79f9-445">納克克</span><span class="sxs-lookup"><span data-stu-id="d79f9-445">Babek</span></span>    | <span data-ttu-id="d79f9-446">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d79f9-446">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d79f9-447">關閉</span><span class="sxs-lookup"><span data-stu-id="d79f9-447">Off</span></span>   |

<span data-ttu-id="d79f9-448">在由他克組織的會議中，有方能將共用桌面或視窗的控制權授予其他參與者，而立克則無法將控制權授予其他參與者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-448">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="d79f9-449">若要使用 PowerShell 來控制誰可以給予控制權或接受控制權要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d79f9-449">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-450">若要在共用期間提供並控制共用內容，雙方必須使用 Teams 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="d79f9-450">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="d79f9-451">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="d79f9-451">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="d79f9-452">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="d79f9-452">This is due to a technical limitation that we're planning to fix.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="d79f9-453">允許外部參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="d79f9-453">Allow an external participant to give or request control</span></span>

<span data-ttu-id="d79f9-454">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-454">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-455">無論會議召集人已設定什麼，組織是否為使用者設定此設定，都無法控制外部參與者可以執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="d79f9-455">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="d79f9-456">此參數根據共用者在其組織的會議政策中設定的內容，控制外部參與者是否可以獲得控制權或要求控制共用者螢幕。</span><span class="sxs-lookup"><span data-stu-id="d79f9-456">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="d79f9-457">Teams 會議的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="d79f9-457">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="d79f9-458">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-458">Anonymous user</span></span>
- <span data-ttu-id="d79f9-459">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-459">Guest users</span></span>  
- <span data-ttu-id="d79f9-460">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-460">B2B user</span></span>
- <span data-ttu-id="d79f9-461">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-461">Federated user</span></span>  

<span data-ttu-id="d79f9-462">在共用時，聯合使用者是否可以將控制權授予外部使用者，而共用是由允許外部參與者提供或要求其組織中控制權設定所控制。</span><span class="sxs-lookup"><span data-stu-id="d79f9-462">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="d79f9-463">若要使用 PowerShell 來控制外部參與者是否可以提供控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d79f9-463">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="d79f9-464">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="d79f9-464">Allow PowerPoint sharing</span></span>

<span data-ttu-id="d79f9-465">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-465">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-466">此設定會控制使用者是否可以在會議共用 PowerPoint 幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="d79f9-466">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="d79f9-467">外部使用者 ，包括匿名、來賓和聯盟使用者，會繼承會議召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-467">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="d79f9-468">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-468">Let's look at the following example.</span></span>

|<span data-ttu-id="d79f9-469">使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-469">User</span></span> |<span data-ttu-id="d79f9-470">會議原則</span><span class="sxs-lookup"><span data-stu-id="d79f9-470">Meeting policy</span></span>  |<span data-ttu-id="d79f9-471">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="d79f9-471">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d79f9-472">Daniela</span><span class="sxs-lookup"><span data-stu-id="d79f9-472">Daniela</span></span>   | <span data-ttu-id="d79f9-473">全域</span><span class="sxs-lookup"><span data-stu-id="d79f9-473">Global</span></span>   | <span data-ttu-id="d79f9-474">On</span><span class="sxs-lookup"><span data-stu-id="d79f9-474">On</span></span>       |
|<span data-ttu-id="d79f9-475">艾曼達</span><span class="sxs-lookup"><span data-stu-id="d79f9-475">Amanda</span></span>   | <span data-ttu-id="d79f9-476">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d79f9-476">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d79f9-477">關閉</span><span class="sxs-lookup"><span data-stu-id="d79f9-477">Off</span></span>   |

<span data-ttu-id="d79f9-478">即使 Amanda 是會議召集人，她也無法共用會議中的 PowerPoint 幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="d79f9-478">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="d79f9-479">即使會議是由張安達組織，但方安達也可以共用 PowerPoint 幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="d79f9-479">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="d79f9-480">雖然她無法共用 PowerPoint 幻燈片組，她還是可以查看會議中其他人共用的 PowerPoint 幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="d79f9-480">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="d79f9-481">允許白板</span><span class="sxs-lookup"><span data-stu-id="d79f9-481">Allow whiteboard</span></span>

<span data-ttu-id="d79f9-482">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-482">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-483">此設定會控制使用者是否可以在會議共用白板。</span><span class="sxs-lookup"><span data-stu-id="d79f9-483">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="d79f9-484">外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-484">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="d79f9-485">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-485">Let's look at the following example.</span></span>

|<span data-ttu-id="d79f9-486">使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-486">User</span></span> |<span data-ttu-id="d79f9-487">會議原則</span><span class="sxs-lookup"><span data-stu-id="d79f9-487">Meeting policy</span></span>  |<span data-ttu-id="d79f9-488">允許白板</span><span class="sxs-lookup"><span data-stu-id="d79f9-488">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d79f9-489">Daniela</span><span class="sxs-lookup"><span data-stu-id="d79f9-489">Daniela</span></span>   | <span data-ttu-id="d79f9-490">全域</span><span class="sxs-lookup"><span data-stu-id="d79f9-490">Global</span></span>   | <span data-ttu-id="d79f9-491">On</span><span class="sxs-lookup"><span data-stu-id="d79f9-491">On</span></span>       |
|<span data-ttu-id="d79f9-492">艾曼達</span><span class="sxs-lookup"><span data-stu-id="d79f9-492">Amanda</span></span>   | <span data-ttu-id="d79f9-493">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d79f9-493">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d79f9-494">關閉</span><span class="sxs-lookup"><span data-stu-id="d79f9-494">Off</span></span>   |

<span data-ttu-id="d79f9-495">即使 Amanda 是會議召集人，她也無法共用會議中的白板。</span><span class="sxs-lookup"><span data-stu-id="d79f9-495">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="d79f9-496">即使會議是由張安達組織，但方安達也可以共用白板。</span><span class="sxs-lookup"><span data-stu-id="d79f9-496">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="d79f9-497">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="d79f9-497">Allow shared notes</span></span>

<span data-ttu-id="d79f9-498">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-498">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-499">此設定會控制使用者是否可以在會議建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="d79f9-499">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="d79f9-500">外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-500">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="d79f9-501">會議 **最多支援** 100 位參與者的會議記錄。</span><span class="sxs-lookup"><span data-stu-id="d79f9-501">The **Meeting Notes** tab is supported in meetings with up to 100 participants.</span></span>

<span data-ttu-id="d79f9-502">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="d79f9-502">Let's look at the following example.</span></span>

|<span data-ttu-id="d79f9-503">使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-503">User</span></span> |<span data-ttu-id="d79f9-504">會議原則</span><span class="sxs-lookup"><span data-stu-id="d79f9-504">Meeting policy</span></span>  |<span data-ttu-id="d79f9-505">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="d79f9-505">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d79f9-506">Daniela</span><span class="sxs-lookup"><span data-stu-id="d79f9-506">Daniela</span></span>   | <span data-ttu-id="d79f9-507">全域</span><span class="sxs-lookup"><span data-stu-id="d79f9-507">Global</span></span>   | <span data-ttu-id="d79f9-508">On</span><span class="sxs-lookup"><span data-stu-id="d79f9-508">On</span></span>       |
|<span data-ttu-id="d79f9-509">艾曼達</span><span class="sxs-lookup"><span data-stu-id="d79f9-509">Amanda</span></span>   | <span data-ttu-id="d79f9-510">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d79f9-510">Location1MeetingPolicy</span></span> | <span data-ttu-id="d79f9-511">關閉</span><span class="sxs-lookup"><span data-stu-id="d79f9-511">Off</span></span> |

<span data-ttu-id="d79f9-512">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 不能在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="d79f9-512">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="d79f9-513">會議政策設定 - 參與者&來賓</span><span class="sxs-lookup"><span data-stu-id="d79f9-513">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="d79f9-514">這些設定會控制哪些會議參與者在獲准進入會議前在大廳等候，以及允許他們參與會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-514">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="d79f9-515">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="d79f9-515">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="d79f9-516">自動准許人員進入</span><span class="sxs-lookup"><span data-stu-id="d79f9-516">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="d79f9-517">允許撥入使用者旁路大廳</span><span class="sxs-lookup"><span data-stu-id="d79f9-517">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="d79f9-518">啟用即時字幕</span><span class="sxs-lookup"><span data-stu-id="d79f9-518">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="d79f9-519">在會議中允許聊天</span><span class="sxs-lookup"><span data-stu-id="d79f9-519">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="d79f9-520">加入會議的選項會因每個 Teams 群組的設定和連接方法而異。</span><span class="sxs-lookup"><span data-stu-id="d79f9-520">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="d79f9-521">如果您的群組有音訊會議，並使用音訊會議來連接，請參閱 [音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-521">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="d79f9-522">如果您的 Teams 群組沒有音訊會議，請參閱在 Teams 中 [加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-522">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="d79f9-523">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="d79f9-523">Let anonymous people start a meeting</span></span>

<span data-ttu-id="d79f9-524">這是允許無主席電話撥入式會議之每個召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-524">This is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="d79f9-525">此設定會控制撥入使用者是否可以在未經過驗證的組織使用者的情況下加入會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-525">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="d79f9-526">根據預設，此設定為關閉，這表示撥入式使用者將等候在大廳，直到組織已驗證的使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-526">By default, this setting is turned off which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-527">如果此設定已關閉，且電話撥入使用者會先加入會議，且位於大廳，則組織使用者必須與 Teams 用戶端加入會議，以從大廳准許使用者進入。</span><span class="sxs-lookup"><span data-stu-id="d79f9-527">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="d79f9-528">沒有大廳控制項可供撥入的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-528">There are no lobby controls available for dialed in users.</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="d79f9-529">自動准許人員進入</span><span class="sxs-lookup"><span data-stu-id="d79f9-529">Automatically admit people</span></span>

<span data-ttu-id="d79f9-530">這是每個召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-530">This is a per-organizer policy.</span></span> <span data-ttu-id="d79f9-531">此設定會控制人員是否直接加入會議，或等候在大廳等候，直到通過驗證的使用者獲准參加。</span><span class="sxs-lookup"><span data-stu-id="d79f9-531">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="d79f9-532">此設定不適用於撥入使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-532">This setting does not apply to dial-in users.</span></span>

![顯示與使用者在大廳開會的螢幕擷取畫面](media/meeting-policies-lobby.png)

 <span data-ttu-id="d79f9-534">會議召集人可以在會議 **邀請** 中選取會議選項，以針對他們排定的每一個會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-534">Meeting organizers can select **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-535">在會議選項中，設定會標示為「誰可以避開大廳」。</span><span class="sxs-lookup"><span data-stu-id="d79f9-535">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="d79f9-536">如果您變更任何使用者的預設設定，該設定會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-536">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="d79f9-537">設定值</span><span class="sxs-lookup"><span data-stu-id="d79f9-537">Setting value</span></span>  |<span data-ttu-id="d79f9-538">加入行為</span><span class="sxs-lookup"><span data-stu-id="d79f9-538">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="d79f9-539">**任何人**</span><span class="sxs-lookup"><span data-stu-id="d79f9-539">**Everyone**</span></span>   |<span data-ttu-id="d79f9-540">所有會議參與者直接加入會議，而不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="d79f9-540">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="d79f9-541">這包括已驗證的使用者、來自信任組織的外部 (、) 、來賓和匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-541">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="d79f9-542">**貴組織及聯盟組織的每個人**</span><span class="sxs-lookup"><span data-stu-id="d79f9-542">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="d79f9-543">組織中已驗證的使用者 ，包括來賓使用者和來自信任組織的使用者，可以直接加入會議，而不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="d79f9-543">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="d79f9-544">匿名使用者在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="d79f9-544">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="d79f9-545">**貴組織所有人**</span><span class="sxs-lookup"><span data-stu-id="d79f9-545">**Everyone in your organization**</span></span>    |<span data-ttu-id="d79f9-546">組織內部已驗證的使用者 ，包括來賓使用者，可以直接加入會議，而不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="d79f9-546">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="d79f9-547">來自信任組織和匿名使用者的使用者在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="d79f9-547">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="d79f9-548">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-548">This is the default setting.</span></span>           |
|<span data-ttu-id="d79f9-549">**僅召集人**</span><span class="sxs-lookup"><span data-stu-id="d79f9-549">**Organizer only**</span></span>    |<span data-ttu-id="d79f9-550">只有會議召集人可以直接加入會議，而不必在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="d79f9-550">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="d79f9-551">其他所有人 ，包括組織中已驗證的使用者、來賓使用者、信任組織的使用者和匿名使用者，都必須在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="d79f9-551">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="d79f9-552">允許撥入使用者旁路大廳</span><span class="sxs-lookup"><span data-stu-id="d79f9-552">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="d79f9-553">這是每個召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-553">This is a per-organizer policy.</span></span> <span data-ttu-id="d79f9-554">此設定會控制不論自動准許人員進入，是否由電話撥入的人直接加入會議或在大廳 **等候** 。</span><span class="sxs-lookup"><span data-stu-id="d79f9-554">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="d79f9-555">此設定預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="d79f9-555">By default, this setting is turned off.</span></span> <span data-ttu-id="d79f9-556">關閉此設定時，撥入使用者會等候在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入。</span><span class="sxs-lookup"><span data-stu-id="d79f9-556">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="d79f9-557">開啟此設定時，撥入使用者會在組織使用者加入會議時自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-557">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-558">如果撥入式使用者在組織使用者加入會議之前加入會議，他們會被放置在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入。</span><span class="sxs-lookup"><span data-stu-id="d79f9-558">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="d79f9-559">如果您變更任何使用者的預設設定，該設定會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-559">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

### <a name="enable-live-captions"></a><span data-ttu-id="d79f9-560">啟用即時字幕</span><span class="sxs-lookup"><span data-stu-id="d79f9-560">Enable live captions</span></span>

<span data-ttu-id="d79f9-561">這是每個使用者原則，在會議期間適用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-561">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="d79f9-562">此設定會控制使用者是否可以使用開啟即時字幕選項，以在使用者出席的會議中開啟和關閉即時字幕。</span><span class="sxs-lookup"><span data-stu-id="d79f9-562">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示開啟即時字幕選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="d79f9-564">設定值</span><span class="sxs-lookup"><span data-stu-id="d79f9-564">Setting value</span></span> |<span data-ttu-id="d79f9-565">行為</span><span class="sxs-lookup"><span data-stu-id="d79f9-565">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d79f9-566">**已停用，但使用者可以覆蓋**</span><span class="sxs-lookup"><span data-stu-id="d79f9-566">**Disabled but the user can override**</span></span>     | <span data-ttu-id="d79f9-567">在會議期間，使用者不會自動開啟即時字幕。</span><span class="sxs-lookup"><span data-stu-id="d79f9-567">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="d79f9-568">使用者在溢點陣圖上看到開啟即時字幕選項 **(...)** 功能表來開啟它們。</span><span class="sxs-lookup"><span data-stu-id="d79f9-568">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="d79f9-569">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-569">This is the default setting.</span></span> |
|<span data-ttu-id="d79f9-570">**禁用**</span><span class="sxs-lookup"><span data-stu-id="d79f9-570">**Disabled**</span></span>     | <span data-ttu-id="d79f9-571">在會議期間，使用者會停用即時字幕。</span><span class="sxs-lookup"><span data-stu-id="d79f9-571">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="d79f9-572">使用者沒有開啟的選項。</span><span class="sxs-lookup"><span data-stu-id="d79f9-572">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="d79f9-573"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="d79f9-573"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="d79f9-574">在會議中允許聊天</span><span class="sxs-lookup"><span data-stu-id="d79f9-574">Allow chat in meetings</span></span>

<span data-ttu-id="d79f9-575">這是每個參與者的設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-575">This is a per-participant setting.</span></span> <span data-ttu-id="d79f9-576">此設定會控制使用者會議是否允許會議聊天。</span><span class="sxs-lookup"><span data-stu-id="d79f9-576">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="d79f9-577"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="d79f9-577"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="d79f9-578">會議政策設定 - 指定的簡報者角色模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-578">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="d79f9-579">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-579">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-580">此設定可讓您變更 Teams 用戶端中會議選項中之 Who  **can present？** 設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="d79f9-580">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="d79f9-581">此策略設定會影響所有會議，包括 Now Meetings 會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-581">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="d79f9-582">誰 **可以出席？** 設定可讓會議召集人選擇會議簡報者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-582">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="d79f9-583">若要深入瞭解，請參閱變更 Teams 會議的參與者 [設定](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 和 [Teams 會議的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-583">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="d79f9-584">您可以使用 [Set-CsTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 編輯現有的 Teams 會議政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-584">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d79f9-585">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議政策，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-585">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="d79f9-586">若要在 Teams 中指定 Who **can present？** 設定預設值，請設定 **DesignatedPresenterRoleMode** 參數為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d79f9-586">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="d79f9-587">**EveryoneUserOverride：** 所有會議參與者都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-587">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="d79f9-588">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="d79f9-588">This is the default value.</span></span> <span data-ttu-id="d79f9-589">此參數會對應到 Teams **中的所有人** 設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-589">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="d79f9-590">**EveryoneInCompanyUserOverride：** 組織中已驗證的使用者 ，包括來賓使用者，可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-590">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="d79f9-591">此參數會對應到 Teams **中的組織** 人員設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-591">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="d79f9-592">**OrganizerOnlyUserOverride：** 只有會議召集人可以擔任簡報者，而所有會議參與者都指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-592">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="d79f9-593">此參數會對應到 Teams **中的僅自己** 設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-593">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="d79f9-594">此外，您也可以在 Teams 系統管理中心編輯此政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-594">Additionally, you can edit this policy in the Teams admin center.</span></span>

![Teams 系統管理中心的螢幕擷取畫面](media/designated-presenter-role.png)

<span data-ttu-id="d79f9-596">請記住，設定預設值之後，會議召集人仍然可以在 Teams 中變更此設定，並選擇誰可以在他們排程的會議中展示。</span><span class="sxs-lookup"><span data-stu-id="d79f9-596">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="d79f9-597">會議政策設定 - 會議出席報告</span><span class="sxs-lookup"><span data-stu-id="d79f9-597">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="d79f9-598">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-598">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-599">此設定會控制會議召集人是否可以下載 [會議出席報告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-599">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="d79f9-600">目前，您僅能使用 PowerShell 來設定此策略設定。</span><span class="sxs-lookup"><span data-stu-id="d79f9-600">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="d79f9-601">您可以使用 [Set-CsTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 編輯現有的 Teams 會議政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-601">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d79f9-602">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議政策，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-602">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="d79f9-603">若要讓會議召集人下載會議出席報告，請設定 **AllowEngagementReport 參數** 為 **Enabled。**</span><span class="sxs-lookup"><span data-stu-id="d79f9-603">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="d79f9-604">啟用時，下載報表的選項會顯示在參與者 **窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="d79f9-604">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="d79f9-605">若要防止會議召集人下載報表，請設定參數為 **停用**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-605">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="d79f9-606">根據預設，此設定會停用，而且無法下載報表。</span><span class="sxs-lookup"><span data-stu-id="d79f9-606">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="d79f9-607">會議政策設定 - 群島模式的會議提供者</span><span class="sxs-lookup"><span data-stu-id="d79f9-607">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="d79f9-608">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-608">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-609">此設定會控制哪些 Outlook 會議附加元件適用于位於 *群島模式的使用者*。</span><span class="sxs-lookup"><span data-stu-id="d79f9-609">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="d79f9-610">您可以指定使用者只能使用 [Teams 會議] 增益集，或是可同時使用 [Teams 會議] 和 [商務用 Skype 會議] 增益集在 Outlook 中排程會議。</span><span class="sxs-lookup"><span data-stu-id="d79f9-610">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="d79f9-611">您只能將此原則套用到處於離島模式的使用者，並在其 Teams 會議原則中將 **AllowOutlookAddIn** 參數設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="d79f9-611">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="d79f9-612">目前，您僅能使用 PowerShell 設定此策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-612">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="d79f9-613">您可以使用 [Set-CsTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 編輯現有的 Teams 會議政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-613">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d79f9-614">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議政策，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-614">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="d79f9-615">若要指定您想要提供給使用者使用的會議附加元件，請設定 **PreferredMeetingProviderForIslandsMode** 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d79f9-615">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="d79f9-616">將參數設定為 **TeamsAndSfB，** 以在 Outlook 中同時啟用 Teams 會議附加元件和商務用 Skype 附加元件。</span><span class="sxs-lookup"><span data-stu-id="d79f9-616">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="d79f9-617">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="d79f9-617">This is the default value.</span></span>
- <span data-ttu-id="d79f9-618">將參數設定為 **Teams，** 以在 Outlook 中僅啟用 Teams 會議附加元件。</span><span class="sxs-lookup"><span data-stu-id="d79f9-618">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="d79f9-619">此策略設定可確保所有未來的會議都有 Teams 會議加入連結。</span><span class="sxs-lookup"><span data-stu-id="d79f9-619">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="d79f9-620">它不會將現有的商務用 Skype 會議加入連結遷移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="d79f9-620">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="d79f9-621">此策略設定不會影響目前狀態、聊天、PSTN 通話，或商務用 Skype 中的其他任何功能，這表示使用者將繼續使用商務用 Skype 來使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="d79f9-621">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="d79f9-622">如果您將參數設定為 **Teams，** 然後切換回 **TeamsAndSfB，** 兩個會議附加元件都已啟用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-622">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="d79f9-623">現有的 Teams 會議加入 **連結不會** 移入商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="d79f9-623">Existing Teams meeting join links **won't** be migrated to Skype for Business.</span></span> <span data-ttu-id="d79f9-624">只有變更之後排程的商務用 Skype 會議會擁有商務用 Skype 會議加入連結。</span><span class="sxs-lookup"><span data-stu-id="d79f9-624">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="d79f9-625">會議政策設定 - 視視篩選模式</span><span class="sxs-lookup"><span data-stu-id="d79f9-625">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="d79f9-626">這是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-626">This is a per-user policy.</span></span> <span data-ttu-id="d79f9-627">此設定會控制使用者是否可以在會議中自訂其視視背景。</span><span class="sxs-lookup"><span data-stu-id="d79f9-627">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="d79f9-628">目前，您僅能使用 PowerShell 設定此策略。</span><span class="sxs-lookup"><span data-stu-id="d79f9-628">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="d79f9-629">您可以使用 [Set-CsTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 編輯現有的 Teams 會議政策。</span><span class="sxs-lookup"><span data-stu-id="d79f9-629">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d79f9-630">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的 Teams 會議政策，然後將該策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d79f9-630">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="d79f9-631">若要指定使用者是否可以在會議中自訂視訊背景，請設定 **VideoFiltersMode** 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d79f9-631">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="d79f9-632">在 PowerShell 中設定值</span><span class="sxs-lookup"><span data-stu-id="d79f9-632">Setting value in PowerShell</span></span> |<span data-ttu-id="d79f9-633">行為</span><span class="sxs-lookup"><span data-stu-id="d79f9-633">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d79f9-634">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="d79f9-634">**NoFilters**</span></span>     |<span data-ttu-id="d79f9-635">使用者無法自訂其視視背景。</span><span class="sxs-lookup"><span data-stu-id="d79f9-635">User can't customize their video background.</span></span>|
|<span data-ttu-id="d79f9-636">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="d79f9-636">**BlurOnly**</span></span>     |<span data-ttu-id="d79f9-637">使用者可以選擇模糊其視視背景。</span><span class="sxs-lookup"><span data-stu-id="d79f9-637">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="d79f9-638">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="d79f9-638">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="d79f9-639">使用者可以選擇模糊其視視背景，或選擇使用預設影像組作為背景。</span><span class="sxs-lookup"><span data-stu-id="d79f9-639">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="d79f9-640">**所有篩選**</span><span class="sxs-lookup"><span data-stu-id="d79f9-640">**AllFilters**</span></span>     |<span data-ttu-id="d79f9-641">使用者可以選擇模糊其視視背景、選擇預設的影像集，或上傳自訂影像以做為背景使用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-641">User has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="d79f9-642">Teams 不會篩選使用者上傳的影像。</span><span class="sxs-lookup"><span data-stu-id="d79f9-642">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="d79f9-643">當您使用 **AllFilters** 設定時，您應有內部組織原則來防止使用者上傳令人反感或不適當的影像，或是貴組織沒有許可權用於 Teams 會議背景的影像。</span><span class="sxs-lookup"><span data-stu-id="d79f9-643">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

> [!NOTE]
> <span data-ttu-id="d79f9-644">並非所有 Teams 用戶端都提供這些功能。</span><span class="sxs-lookup"><span data-stu-id="d79f9-644">These features are not available for all Teams clients.</span></span> <span data-ttu-id="d79f9-645">詳細資訊請參閱會議和即時活動中 _的_ 影片 [和背景標題](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e)。</span><span class="sxs-lookup"><span data-stu-id="d79f9-645">For more information, see the _Video and backgrounds_ title in [Meetings and live events](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e).</span></span>

## <a name="meeting-policy-settings---meeting-reactions"></a><span data-ttu-id="d79f9-646">會議政策設定 - 會議反應</span><span class="sxs-lookup"><span data-stu-id="d79f9-646">Meeting policy settings - Meeting reactions</span></span>

<span data-ttu-id="d79f9-647">AllowMeetingReactions 設定只能使用 PowerShell 來使用。</span><span class="sxs-lookup"><span data-stu-id="d79f9-647">The AllowMeetingReactions setting can only be applied using PowerShell.</span></span> <span data-ttu-id="d79f9-648">Teams 系統管理中心無法開啟或關閉 AllowMeetingReactions。</span><span class="sxs-lookup"><span data-stu-id="d79f9-648">There is no option to toggle AllowMeetingReactions on or off from the Teams admin center.</span></span>

<span data-ttu-id="d79f9-649">會議反應預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="d79f9-649">Meeting reactions are Off by default.</span></span> <span data-ttu-id="d79f9-650">為使用者關閉反應並不表示使用者在排程的會議中無法使用反應。</span><span class="sxs-lookup"><span data-stu-id="d79f9-650">Turning off reactions for a user doesn't mean that a user can't use reactions in meetings they schedule.</span></span> <span data-ttu-id="d79f9-651">無論預設設定如何，會議召集人仍然可以從會議選項頁面開啟回應。</span><span class="sxs-lookup"><span data-stu-id="d79f9-651">The meeting organizer can still turn on reactions from the meeting option page, regardless of the default setting.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d79f9-652">相關主題</span><span class="sxs-lookup"><span data-stu-id="d79f9-652">Related topics</span></span>

- [<span data-ttu-id="d79f9-653">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="d79f9-653">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d79f9-654">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="d79f9-654">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="d79f9-655">從使用者移除 RestrictedAnonymousAccess Teams 會議政策</span><span class="sxs-lookup"><span data-stu-id="d79f9-655">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
