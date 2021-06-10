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
description: 瞭解如何在會議中管理會議Teams，並使用這些設定來控制提供給會議參與者的功能，供使用者排程的會議使用。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598708"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="6b95f-103">在 Teams 中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="6b95f-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="6b95f-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="6b95f-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="6b95f-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="6b95f-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="6b95f-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="6b95f-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="6b95f-107">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="6b95f-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="6b95f-108">您可以使用自動建立的全域 (全組織預設值) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="6b95f-109">您可以在 Microsoft Teams 系統管理中心或使用 [PowerShell](teams-powershell-overview.md) 來管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6b95f-110">如需使用角色來管理會議簡報者和出席者權限的詳細資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="6b95f-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="6b95f-111">您可以以下列方式來實作原則，這會影響使用者在會議開始、會議期間或會議後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="6b95f-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="6b95f-112">實作類型</span><span class="sxs-lookup"><span data-stu-id="6b95f-112">Implementation type</span></span>  |<span data-ttu-id="6b95f-113">描述</span><span class="sxs-lookup"><span data-stu-id="6b95f-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6b95f-114">每一召集人</span><span class="sxs-lookup"><span data-stu-id="6b95f-114">Per-organizer</span></span>    |<span data-ttu-id="6b95f-115">當您實作每一召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="6b95f-116">例如， **自動** 准許人員是每個召集人的政策，並控制使用者是直接加入會議，還是等候在大廳等候指派該政策的使用者排程的會議。</span><span class="sxs-lookup"><span data-stu-id="6b95f-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="6b95f-117">每一使用者</span><span class="sxs-lookup"><span data-stu-id="6b95f-117">Per-user</span></span>    |<span data-ttu-id="6b95f-118">當您實作每一使用者原則時，僅會套用每一使用者原則，以限制召集人和/或會議參與者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="6b95f-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="6b95f-119">例如，[允許在頻道中立即開會 **]** 是每一使用者原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="6b95f-120">每一召集人和每一使用者</span><span class="sxs-lookup"><span data-stu-id="6b95f-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="6b95f-121">當您實作每一召集人和每一使用者的原則組合時，系統會根據參與者的原則和召集人的原則，限制會議參與者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="6b95f-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="6b95f-122">例如，**允許雲端錄製** 是每一召集人和每一使用者原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="6b95f-123">開啟此設定，讓會議召集人和參與者開始和停止錄製。</span><span class="sxs-lookup"><span data-stu-id="6b95f-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="6b95f-124">您可以編輯全域原則中的設定，或建立並指派一或多個自訂原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="6b95f-125">除非您建立並指派自訂原則，否則使用者將會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="6b95f-126">如果使用者已啟用音訊會議授權，或使用者已獲允許進行音訊會議，則 [會議詳細資料] 按鈕將可供使用，否則會議詳細資料將無法使用。</span><span class="sxs-lookup"><span data-stu-id="6b95f-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="6b95f-127">建立自訂會議原則</span><span class="sxs-lookup"><span data-stu-id="6b95f-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="6b95f-128">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [會議 **]**  >  [會議原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="6b95f-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6b95f-129">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="6b95f-129">Click **Add**.</span></span>
3. <span data-ttu-id="6b95f-130">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="6b95f-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="6b95f-131">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="6b95f-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="6b95f-132">選擇您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="6b95f-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="6b95f-133">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="6b95f-133">Click **Save**.</span></span>

<span data-ttu-id="6b95f-134">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="6b95f-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="6b95f-135">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="6b95f-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="6b95f-136">在 [音訊與視訊] 下：</span><span class="sxs-lookup"><span data-stu-id="6b95f-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="6b95f-137">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="6b95f-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="6b95f-138">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="6b95f-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="6b95f-139">在 [內容共用] 下：</span><span class="sxs-lookup"><span data-stu-id="6b95f-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="6b95f-140">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="6b95f-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="6b95f-141">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="6b95f-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="6b95f-142">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="6b95f-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="6b95f-143">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6b95f-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="6b95f-144">編輯會議原則</span><span class="sxs-lookup"><span data-stu-id="6b95f-144">Edit a meeting policy</span></span>

<span data-ttu-id="6b95f-145">您可以編輯全域原則和您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="6b95f-146">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [會議 **]**  >  [會議原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="6b95f-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6b95f-147">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="6b95f-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6b95f-148">從此處，進行您需要的變更。</span><span class="sxs-lookup"><span data-stu-id="6b95f-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="6b95f-149">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="6b95f-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6b95f-150">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="6b95f-151">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="6b95f-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="6b95f-152">如果已將原則指派給使用者，就無法刪除該原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="6b95f-153">您必須先為所有受影響的使用者指派不同的原則，之後才可以刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="6b95f-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="6b95f-154">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="6b95f-154">Meeting policy settings</span></span>

<span data-ttu-id="6b95f-155">當您在會議政策頁面上選取現有策略或選取新增以新增策略時，您可以設定下列設定。</span><span class="sxs-lookup"><span data-stu-id="6b95f-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="6b95f-156">一般</span><span class="sxs-lookup"><span data-stu-id="6b95f-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="6b95f-157">音訊與視訊</span><span class="sxs-lookup"><span data-stu-id="6b95f-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="6b95f-158">內容共用</span><span class="sxs-lookup"><span data-stu-id="6b95f-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="6b95f-159">參與者與來賓</span><span class="sxs-lookup"><span data-stu-id="6b95f-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="6b95f-160">相關主題</span><span class="sxs-lookup"><span data-stu-id="6b95f-160">Related topics</span></span>

- [<span data-ttu-id="6b95f-161">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="6b95f-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6b95f-162">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="6b95f-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="6b95f-163">從使用者移除 RestrictedAnonymousAccess Teams 會議原則</span><span class="sxs-lookup"><span data-stu-id="6b95f-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)