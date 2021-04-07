---
title: 管理會議原則
author: CarolynRowe
ms.author: crowe
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
- seo-marvel-apr2020
description: 瞭解如何在 Teams 中管理會議策略設定，並使用這些設定來控制提供給會議參與者的功能，供使用者排程的會議使用。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598708"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="c3e65-103">管理 Teams 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="c3e65-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="c3e65-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="c3e65-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="c3e65-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="c3e65-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="c3e65-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="c3e65-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="c3e65-107">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="c3e65-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="c3e65-108">您可以使用全域 (全組織的預設) 自動建立或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="c3e65-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="c3e65-109">您可以在 Microsoft Teams 系統管理中心或使用 [PowerShell 管理會議政策](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3e65-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c3e65-110">有關使用角色管理會議簡報者和出席者許可權的資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="c3e65-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="c3e65-111">您可以用下列方式執行策略，這會影響會議開始前、會議期間或會議後使用者的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="c3e65-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="c3e65-112">實現類型</span><span class="sxs-lookup"><span data-stu-id="c3e65-112">Implementation type</span></span>  |<span data-ttu-id="c3e65-113">描述</span><span class="sxs-lookup"><span data-stu-id="c3e65-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c3e65-114">每個召集人</span><span class="sxs-lookup"><span data-stu-id="c3e65-114">Per-organizer</span></span>    |<span data-ttu-id="c3e65-115">當您執行每個召集人的政策時，所有會議參與者會繼承召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="c3e65-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="c3e65-116">例如， **自動** 准許人員是每個召集人的政策，並控制使用者是否直接加入會議，或是在大廳等候指派該政策的使用者排程的會議。</span><span class="sxs-lookup"><span data-stu-id="c3e65-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="c3e65-117">每個使用者</span><span class="sxs-lookup"><span data-stu-id="c3e65-117">Per-user</span></span>    |<span data-ttu-id="c3e65-118">當您執行每個使用者原則時，只會使用每個使用者原則來限制召集人和/或會議參與者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="c3e65-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="c3e65-119">例如， **在頻道中允許現在開會** 是每個使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="c3e65-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="c3e65-120">每個召集人和每個使用者</span><span class="sxs-lookup"><span data-stu-id="c3e65-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="c3e65-121">當您將每個召集人和每個使用者策略組合在一起時，根據會議參與者的政策和召集人的政策，某些功能會受到限制。</span><span class="sxs-lookup"><span data-stu-id="c3e65-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="c3e65-122">例如， **允許雲端錄製** 是每個召集人和每個使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="c3e65-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="c3e65-123">開啟此設定，讓會議召集人和參與者開始和停止錄製。</span><span class="sxs-lookup"><span data-stu-id="c3e65-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="c3e65-124">您可以編輯全域原則中的設定，或建立並指派一或多個自訂策略。</span><span class="sxs-lookup"><span data-stu-id="c3e65-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="c3e65-125">除非您建立並指派自訂策略，否則使用者將取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="c3e65-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c3e65-126">如果使用者已啟用音訊會議授權，或使用者允許進行音訊會議，則會議詳細資料將不可用，則會議詳細資料將可以使用。</span><span class="sxs-lookup"><span data-stu-id="c3e65-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="c3e65-127">建立自訂會議策略</span><span class="sxs-lookup"><span data-stu-id="c3e65-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="c3e65-128">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。</span><span class="sxs-lookup"><span data-stu-id="c3e65-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="c3e65-129">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="c3e65-129">Click **Add**.</span></span>
3. <span data-ttu-id="c3e65-130">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="c3e65-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="c3e65-131">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="c3e65-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="c3e65-132">選擇您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="c3e65-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="c3e65-133">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c3e65-133">Click **Save**.</span></span>

<span data-ttu-id="c3e65-134">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="c3e65-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="c3e65-135">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="c3e65-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="c3e65-136">在 [音訊與視訊] 下：</span><span class="sxs-lookup"><span data-stu-id="c3e65-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="c3e65-137">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="c3e65-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="c3e65-138">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="c3e65-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="c3e65-139">在 [內容共用] 下：</span><span class="sxs-lookup"><span data-stu-id="c3e65-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="c3e65-140">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="c3e65-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="c3e65-141">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="c3e65-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="c3e65-142">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="c3e65-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="c3e65-143">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c3e65-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="c3e65-144">編輯會議政策</span><span class="sxs-lookup"><span data-stu-id="c3e65-144">Edit a meeting policy</span></span>

<span data-ttu-id="c3e65-145">您可以編輯全域原則和您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="c3e65-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="c3e65-146">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。</span><span class="sxs-lookup"><span data-stu-id="c3e65-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="c3e65-147">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="c3e65-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c3e65-148">從此處，進行您需要的變更。</span><span class="sxs-lookup"><span data-stu-id="c3e65-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="c3e65-149">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c3e65-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c3e65-150">一次只能指派一個會議策略給使用者。</span><span class="sxs-lookup"><span data-stu-id="c3e65-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="c3e65-151">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="c3e65-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="c3e65-152">如果使用者已指派給使用者，則無法刪除該策略。</span><span class="sxs-lookup"><span data-stu-id="c3e65-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="c3e65-153">您必須先指派不同的策略給所有受影響的使用者，然後您可以刪除原始策略。</span><span class="sxs-lookup"><span data-stu-id="c3e65-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="c3e65-154">會議策略設定</span><span class="sxs-lookup"><span data-stu-id="c3e65-154">Meeting policy settings</span></span>

<span data-ttu-id="c3e65-155">當您在會議政策頁面上選取現有的策略或 **選取新增以** 新增策略時，您可以設定下列設定。</span><span class="sxs-lookup"><span data-stu-id="c3e65-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="c3e65-156">一般</span><span class="sxs-lookup"><span data-stu-id="c3e65-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="c3e65-157">音訊&影片</span><span class="sxs-lookup"><span data-stu-id="c3e65-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="c3e65-158">內容共用</span><span class="sxs-lookup"><span data-stu-id="c3e65-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="c3e65-159">參與者&來賓</span><span class="sxs-lookup"><span data-stu-id="c3e65-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="c3e65-160">相關主題</span><span class="sxs-lookup"><span data-stu-id="c3e65-160">Related topics</span></span>

- [<span data-ttu-id="c3e65-161">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="c3e65-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c3e65-162">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="c3e65-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="c3e65-163">從使用者移除 RestrictedAnonymousAccess Teams 會議政策</span><span class="sxs-lookup"><span data-stu-id="c3e65-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)