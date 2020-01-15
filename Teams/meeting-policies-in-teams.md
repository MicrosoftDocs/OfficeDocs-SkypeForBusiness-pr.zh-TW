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
ms.openlocfilehash: 20382a41ac8d0a78d56ebcb51e852f5302ea74a7
ms.sourcegitcommit: 447c5ffc27c5b0928e033f85914810af56e510ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41120393"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="1cc9e-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="1cc9e-104">會議原則可用來控制會議參與者對於由您組織中的使用者排程之會議所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="1cc9e-105">建立原則並進行變更之後，您就可以將使用者指派給原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="1cc9e-106">您可以在 Microsoft 團隊系統管理中心或[使用 PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-106">You manage meeting policies in the Microsoft Teams admin center or by [using PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="1cc9e-107">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="1cc9e-108">實現類型</span><span class="sxs-lookup"><span data-stu-id="1cc9e-108">Implementation type</span></span>  |<span data-ttu-id="1cc9e-109">描述</span><span class="sxs-lookup"><span data-stu-id="1cc9e-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1cc9e-110">每個召集人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-110">Per-organizer</span></span>    |<span data-ttu-id="1cc9e-111">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="1cc9e-112">例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="1cc9e-113">每位使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-113">Per-user</span></span>    |<span data-ttu-id="1cc9e-114">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="1cc9e-115">例如，[**允許立即開會**] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-115">For example, **Allow Meet now** is a per-user policy.</span></span>     |
|<span data-ttu-id="1cc9e-116">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="1cc9e-117">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="1cc9e-118">例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="1cc9e-119">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span> 

<span data-ttu-id="1cc9e-120">根據預設，會建立名為 [全域] （組織範圍預設值）的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-120">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="1cc9e-121">貴組織中的所有使用者預設都會獲指派此會議原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-121">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="1cc9e-122">您可以對此原則進行變更，或是建立一或多個自訂原則，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-122">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="1cc9e-123">當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將其指派給將設定套用至其中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-123">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="1cc9e-124">變更或建立會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-124">Change or create a meeting policy</span></span>

<span data-ttu-id="1cc9e-125">若要變更或建立會議原則，請移至 Microsoft 團隊管理中心 >**會議** > **會議原則**。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-125">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="1cc9e-126">從清單中選取原則，或選取 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-126">Select a policy from the list or select **New policy**.</span></span> <span data-ttu-id="1cc9e-127">如果您要建立新的原則，請新增名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-127">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="1cc9e-128">名稱不能包含特殊字元，或長度不能超過64個字元。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-128">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="1cc9e-129">選擇您的設定，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-129">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="1cc9e-130">例如，假設您有一組使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-130">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="1cc9e-131">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="1cc9e-131">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="1cc9e-132">在 [**音訊 & 影片**] 底下：</span><span class="sxs-lookup"><span data-stu-id="1cc9e-132">Under **Audio & video**:</span></span>
- <span data-ttu-id="1cc9e-133">關閉雲端錄製</span><span class="sxs-lookup"><span data-stu-id="1cc9e-133">Turn off cloud recording</span></span>
- <span data-ttu-id="1cc9e-134">關閉 [允許 IP 影片]</span><span class="sxs-lookup"><span data-stu-id="1cc9e-134">Turn off Allow IP video</span></span>

<span data-ttu-id="1cc9e-135">[**內容共用**] 底下：</span><span class="sxs-lookup"><span data-stu-id="1cc9e-135">Under **Content sharing**:</span></span>
- <span data-ttu-id="1cc9e-136">停用螢幕共用模式</span><span class="sxs-lookup"><span data-stu-id="1cc9e-136">Disable screen sharing mode</span></span>
- <span data-ttu-id="1cc9e-137">關閉白板</span><span class="sxs-lookup"><span data-stu-id="1cc9e-137">Turn off whiteboard</span></span>
- <span data-ttu-id="1cc9e-138">關閉共用筆記</span><span class="sxs-lookup"><span data-stu-id="1cc9e-138">Turn off shared notes</span></span>

<span data-ttu-id="1cc9e-139">然後將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-139">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="1cc9e-140">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-140">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="1cc9e-141">指派會議原則給使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-141">Assign a meeting policy to users</span></span>

<span data-ttu-id="1cc9e-142">如果您要將原則套用到一個使用者，請選取左側流覽窗格中的 [**使用者**]，然後按一下使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-142">If you're applying the policy to one user, select **Users** on the left navigation pane, and then click the user's display name.</span></span> <span data-ttu-id="1cc9e-143">在使用者的頁面上，在 [**指派的原則**] 旁，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-143">On the user's page, next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="1cc9e-144">然後在 [**編輯使用者原則**] 窗格的 [**會議原則**] 底下，從下拉式清單中選取 [會議原則]，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-144">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and then select **Save**.</span></span> <span data-ttu-id="1cc9e-145">您也可以從使用者清單指派原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-145">You can also assign policies from the list of users.</span></span> <span data-ttu-id="1cc9e-146">若要這樣做，請按一下使用者的顯示名稱左方來選取使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-146">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="1cc9e-147">選取 [**編輯設定**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-147">Select **Edit settings**.</span></span> <span data-ttu-id="1cc9e-148">接著，在 [**編輯設定**] 窗格的 [**會議原則**] 底下，從下拉式清單中選取原則，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-148">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span> 
 
<span data-ttu-id="1cc9e-149">如果您要將原則套用到一個以上的使用者，請在左側流覽窗格中選取 [**使用者**]，然後按一下使用者名稱左邊的 [**編輯設定**]，選取每個使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-149">If you're applying a policy to more than one user, select **Users** on the left navigation pane, and then select each user by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="1cc9e-150">在 [**編輯設定**] 窗格的 [**會議原則**] 底下，從下拉式清單中選取原則，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-150">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span>
 
<span data-ttu-id="1cc9e-151">您也可以將會議原則指派給一或多位使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1cc9e-151">You can also assign a meeting policy to one or more users as follows:</span></span>

1. <span data-ttu-id="1cc9e-152">移至**Microsoft 團隊系統管理中心** > **會議** > **會議原則**。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-152">Go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="1cc9e-153">按一下原則名稱左方，選取原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1cc9e-154">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="1cc9e-155">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1cc9e-156">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1cc9e-157">完成新增使用者後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-157">When you're finished adding users, select **Save**.</span></span>
 
> [!NOTE] 
> <span data-ttu-id="1cc9e-158">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-158">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="1cc9e-159">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-159">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
## <a name="meeting-policy-settings"></a><span data-ttu-id="1cc9e-160">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="1cc9e-160">Meeting policy settings</span></span>

<span data-ttu-id="1cc9e-161">當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增原則**] 來新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-161">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="1cc9e-162">一般</span><span class="sxs-lookup"><span data-stu-id="1cc9e-162">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="1cc9e-163">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="1cc9e-163">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="1cc9e-164">內容共用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-164">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="1cc9e-165">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="1cc9e-165">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="1cc9e-166"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="1cc9e-166"></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="1cc9e-167">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="1cc9e-167">Meeting policy settings - General</span></span>

- <span data-ttu-id="1cc9e-168">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="1cc9e-168">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- <span data-ttu-id="1cc9e-169">[允許私人 [立即開會]](#allow-private-meet-now)</span><span class="sxs-lookup"><span data-stu-id="1cc9e-169">[Allow private Meet now](#allow-private-meet-now)</span></span>
- [<span data-ttu-id="1cc9e-170">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="1cc9e-170">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="1cc9e-171">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="1cc9e-171">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="1cc9e-172">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="1cc9e-172">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="1cc9e-173">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="1cc9e-173">Allow Meet now in channels</span></span>

<span data-ttu-id="1cc9e-174">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1cc9e-175">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-175">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="1cc9e-176">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-176">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** beneath the compose box to start an ad hoc meeting in the channel.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now"></a><span data-ttu-id="1cc9e-178">允許私人 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="1cc9e-178">Allow private Meet now</span></span>

<span data-ttu-id="1cc9e-179">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1cc9e-180">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-180">This setting controls whether a user can start an ad hoc private meeting.</span></span>  

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="1cc9e-181">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="1cc9e-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="1cc9e-182">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1cc9e-183">此設定控制團隊會議是否可在 Outlook 中排程（Windows、Mac、web 及行動裝置）。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="1cc9e-185">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="1cc9e-186">例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="1cc9e-187">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="1cc9e-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="1cc9e-188">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1cc9e-189">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="1cc9e-190">如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add a channel** option is disabled for users in Teams.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="1cc9e-193">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="1cc9e-193">Allow scheduling private meetings</span></span>

<span data-ttu-id="1cc9e-194">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-194">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1cc9e-195">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-195">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="1cc9e-196">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-196">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="1cc9e-197">請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-197">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="1cc9e-198"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="1cc9e-198"></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="1cc9e-199">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="1cc9e-199">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="1cc9e-200">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="1cc9e-200">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="1cc9e-201">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="1cc9e-201">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="1cc9e-202">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="1cc9e-202">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="1cc9e-203">媒體位元速率（KBs）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-203">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)
- [<span data-ttu-id="1cc9e-204">啟用即時標題（預覽版本）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-204">Enable live captions (preview)</span></span>](#enable-live-captions-preview)

### <a name="allow-transcription"></a><span data-ttu-id="1cc9e-205">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="1cc9e-205">Allow transcription</span></span>

<span data-ttu-id="1cc9e-206">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1cc9e-207">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="1cc9e-208">如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="1cc9e-209">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="1cc9e-210">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="1cc9e-212">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="1cc9e-212">Allow cloud recording</span></span>

<span data-ttu-id="1cc9e-213">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1cc9e-214">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="1cc9e-215">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="1cc9e-216">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="1cc9e-217">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-217">Guest users can't start or stop the recording.</span></span> 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="1cc9e-219">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-219">Let's look at the following example.</span></span>

|<span data-ttu-id="1cc9e-220">使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-220">User</span></span> |<span data-ttu-id="1cc9e-221">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-221">Meeting policy</span></span>  |<span data-ttu-id="1cc9e-222">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="1cc9e-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cc9e-223">Daniela</span></span> | <span data-ttu-id="1cc9e-224">全域</span><span class="sxs-lookup"><span data-stu-id="1cc9e-224">Global</span></span>   | <span data-ttu-id="1cc9e-225">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-225">False</span></span> |
|<span data-ttu-id="1cc9e-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="1cc9e-226">Amanda</span></span> | <span data-ttu-id="1cc9e-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc9e-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="1cc9e-228">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-228">True</span></span>|
|<span data-ttu-id="1cc9e-229">約翰（外部使用者）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-229">John (external user)</span></span> | <span data-ttu-id="1cc9e-230">不適用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-230">Not applicable</span></span> | <span data-ttu-id="1cc9e-231">不適用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-231">Not applicable</span></span>|

<span data-ttu-id="1cc9e-232">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="1cc9e-233">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="1cc9e-234">若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="1cc9e-235">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="1cc9e-235">Allow IP video</span></span>

<span data-ttu-id="1cc9e-236">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1cc9e-237">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-237">Video is a key component to meetings.</span></span> <span data-ttu-id="1cc9e-238">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-238">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="1cc9e-239">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="1cc9e-240">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="1cc9e-241">沒有指派任何原則的會議參與者（例如匿名及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="1cc9e-243">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-243">Let's look at the following example.</span></span>

|<span data-ttu-id="1cc9e-244">使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-244">User</span></span> |<span data-ttu-id="1cc9e-245">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-245">Meeting policy</span></span>  |<span data-ttu-id="1cc9e-246">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="1cc9e-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cc9e-247">Daniela</span></span>   | <span data-ttu-id="1cc9e-248">全域</span><span class="sxs-lookup"><span data-stu-id="1cc9e-248">Global</span></span>   | <span data-ttu-id="1cc9e-249">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-249">True</span></span>        |
|<span data-ttu-id="1cc9e-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="1cc9e-250">Amanda</span></span>    | <span data-ttu-id="1cc9e-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc9e-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1cc9e-252">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-252">False</span></span>      |

<span data-ttu-id="1cc9e-253">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="1cc9e-254">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="1cc9e-255">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-255">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="1cc9e-256">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="1cc9e-257">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="1cc9e-258">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-258">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="1cc9e-259">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="1cc9e-260">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-260">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="1cc9e-261">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="1cc9e-262">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="1cc9e-263">媒體位元速率（KBs）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-263">Media bit rate (KBs)</span></span>

<span data-ttu-id="1cc9e-264">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-264">This is a per-user policy.</span></span> <span data-ttu-id="1cc9e-265">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="1cc9e-266">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="1cc9e-267">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="1cc9e-268">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="1cc9e-269">最小值為 30 Kbps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="1cc9e-270">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="1cc9e-271">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-271">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="1cc9e-272">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="1cc9e-273">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

### <a name="enable-live-captions-preview"></a><span data-ttu-id="1cc9e-274">啟用即時標題（預覽版本）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-274">Enable live captions (preview)</span></span>

<span data-ttu-id="1cc9e-275">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-275">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="1cc9e-276">此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-276">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="1cc9e-278">設定值</span><span class="sxs-lookup"><span data-stu-id="1cc9e-278">Setting value</span></span> |<span data-ttu-id="1cc9e-279">行為</span><span class="sxs-lookup"><span data-stu-id="1cc9e-279">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="1cc9e-280">**停用且使用者可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-280">**Disabled and the user can override**</span></span>     | <span data-ttu-id="1cc9e-281">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-281">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="1cc9e-282">使用者會看到 [溢出（**...**）] 功能表中的 [**開啟即時標題**] 選項，以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-282">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="1cc9e-283">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-283">This is the default setting.</span></span> |
|<span data-ttu-id="1cc9e-284">**禁止**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-284">**Disabled**</span></span>     | <span data-ttu-id="1cc9e-285">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-285">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="1cc9e-286">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-286">The user doesn't have the option to turn them on.</span></span>          |


<span data-ttu-id="1cc9e-287"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="1cc9e-287"></span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="1cc9e-288">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-288">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="1cc9e-289">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="1cc9e-289">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="1cc9e-290">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="1cc9e-290">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="1cc9e-291">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="1cc9e-291">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="1cc9e-292">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-292">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="1cc9e-293">允許白板</span><span class="sxs-lookup"><span data-stu-id="1cc9e-293">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="1cc9e-294">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="1cc9e-294">Allow shared notes</span></span>](#allow-shared-notes)
- [<span data-ttu-id="1cc9e-295">允許在會議中聊天（即將推出）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-295">Allow chat in meetings (coming soon)</span></span>](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a><span data-ttu-id="1cc9e-296">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="1cc9e-296">Screen sharing mode</span></span>

<span data-ttu-id="1cc9e-297">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-297">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1cc9e-298">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-298">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="1cc9e-299">沒有指派任何原則的會議參與者（例如，匿名、來賓、B2B 及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-299">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="1cc9e-300">設定值</span><span class="sxs-lookup"><span data-stu-id="1cc9e-300">Setting value</span></span> |<span data-ttu-id="1cc9e-301">行為</span><span class="sxs-lookup"><span data-stu-id="1cc9e-301">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="1cc9e-302">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-302">**Entire screen**</span></span>    | <span data-ttu-id="1cc9e-303">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-303">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="1cc9e-304">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-304">**Single application**</span></span>   | <span data-ttu-id="1cc9e-305">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="1cc9e-305">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="1cc9e-306">**禁止**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-306">**Disabled**</span></span>     |<span data-ttu-id="1cc9e-307">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-307">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="1cc9e-308">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-308">Let's look at the following example.</span></span>

|<span data-ttu-id="1cc9e-309">使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-309">User</span></span> |<span data-ttu-id="1cc9e-310">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-310">Meeting policy</span></span> |<span data-ttu-id="1cc9e-311">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="1cc9e-311">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-312">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cc9e-312">Daniela</span></span>  | <span data-ttu-id="1cc9e-313">全域</span><span class="sxs-lookup"><span data-stu-id="1cc9e-313">Global</span></span>   | <span data-ttu-id="1cc9e-314">整個畫面</span><span class="sxs-lookup"><span data-stu-id="1cc9e-314">Entire screen</span></span> |
|<span data-ttu-id="1cc9e-315">Amanda</span><span class="sxs-lookup"><span data-stu-id="1cc9e-315">Amanda</span></span>   | <span data-ttu-id="1cc9e-316">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc9e-316">Location1MeetingPolicy</span></span>  | <span data-ttu-id="1cc9e-317">禁止</span><span class="sxs-lookup"><span data-stu-id="1cc9e-317">Disabled</span></span> |

<span data-ttu-id="1cc9e-318">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-318">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="1cc9e-319">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-319">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="1cc9e-320">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-320">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="1cc9e-321">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-321">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="1cc9e-322">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-322">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="1cc9e-323">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="1cc9e-323">Allow a participant to give or request control</span></span>

<span data-ttu-id="1cc9e-324">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-324">This is a per-user policy.</span></span> <span data-ttu-id="1cc9e-325">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-325">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="1cc9e-326">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-326">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="1cc9e-327">如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-327">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="1cc9e-329">如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-329">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="1cc9e-331">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-331">Let's look at the following example.</span></span>

|<span data-ttu-id="1cc9e-332">使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-332">User</span></span> |<span data-ttu-id="1cc9e-333">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-333">Meeting policy</span></span>  |<span data-ttu-id="1cc9e-334">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="1cc9e-334">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-335">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cc9e-335">Daniela</span></span>   | <span data-ttu-id="1cc9e-336">全域</span><span class="sxs-lookup"><span data-stu-id="1cc9e-336">Global</span></span>   | <span data-ttu-id="1cc9e-337">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-337">True</span></span>       |
|<span data-ttu-id="1cc9e-338">Babek</span><span class="sxs-lookup"><span data-stu-id="1cc9e-338">Babek</span></span>    | <span data-ttu-id="1cc9e-339">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc9e-339">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1cc9e-340">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-340">False</span></span>   |

<span data-ttu-id="1cc9e-341">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-341">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="1cc9e-342">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-342">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1cc9e-343">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-343">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="1cc9e-344">當某個參與方在瀏覽器中執行團隊時，不支援此控制項。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-344">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="1cc9e-345">這是由於我們計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-345">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="1cc9e-346">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="1cc9e-346">Allow an external participant to give or request control</span></span>

<span data-ttu-id="1cc9e-347">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-347">This is a per-user policy.</span></span> <span data-ttu-id="1cc9e-348">此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-348">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="1cc9e-349">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="1cc9e-349">External participants in Teams meetings can be categorized as follows:</span></span>  

   - <span data-ttu-id="1cc9e-350">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-350">Anonymous user</span></span>
   - <span data-ttu-id="1cc9e-351">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-351">Guest users</span></span>  
   - <span data-ttu-id="1cc9e-352">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-352">B2B user</span></span>
   - <span data-ttu-id="1cc9e-353">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-353">Federated user</span></span>  

<span data-ttu-id="1cc9e-354">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-354">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="1cc9e-355">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-355">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="1cc9e-356">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-356">Allow PowerPoint sharing</span></span>

<span data-ttu-id="1cc9e-357">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-357">This is a per-user policy.</span></span> <span data-ttu-id="1cc9e-358">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-358">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="1cc9e-359">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-359">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="1cc9e-360">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-360">Let's look at the following example.</span></span>

|<span data-ttu-id="1cc9e-361">使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-361">User</span></span> |<span data-ttu-id="1cc9e-362">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-362">Meeting policy</span></span>  |<span data-ttu-id="1cc9e-363">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="1cc9e-363">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-364">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cc9e-364">Daniela</span></span>   | <span data-ttu-id="1cc9e-365">全域</span><span class="sxs-lookup"><span data-stu-id="1cc9e-365">Global</span></span>   | <span data-ttu-id="1cc9e-366">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-366">True</span></span>       |
|<span data-ttu-id="1cc9e-367">Amanda</span><span class="sxs-lookup"><span data-stu-id="1cc9e-367">Amanda</span></span>   | <span data-ttu-id="1cc9e-368">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc9e-368">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1cc9e-369">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-369">False</span></span>   |

<span data-ttu-id="1cc9e-370">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-370">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="1cc9e-371">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-371">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="1cc9e-372">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-372">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="1cc9e-373">允許白板</span><span class="sxs-lookup"><span data-stu-id="1cc9e-373">Allow whiteboard</span></span>

<span data-ttu-id="1cc9e-374">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-374">This is a per-user policy.</span></span> <span data-ttu-id="1cc9e-375">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-375">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="1cc9e-376">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-376">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="1cc9e-377">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-377">Let's look at the following example.</span></span>

|<span data-ttu-id="1cc9e-378">使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-378">User</span></span> |<span data-ttu-id="1cc9e-379">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-379">Meeting policy</span></span>  |<span data-ttu-id="1cc9e-380">允許白板</span><span class="sxs-lookup"><span data-stu-id="1cc9e-380">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1cc9e-381">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cc9e-381">Daniela</span></span>   | <span data-ttu-id="1cc9e-382">全域</span><span class="sxs-lookup"><span data-stu-id="1cc9e-382">Global</span></span>   | <span data-ttu-id="1cc9e-383">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-383">True</span></span>       |
|<span data-ttu-id="1cc9e-384">Amanda</span><span class="sxs-lookup"><span data-stu-id="1cc9e-384">Amanda</span></span>   | <span data-ttu-id="1cc9e-385">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc9e-385">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1cc9e-386">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-386">False</span></span>   |

<span data-ttu-id="1cc9e-387">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-387">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="1cc9e-388">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-388">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="1cc9e-389">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="1cc9e-389">Allow shared notes</span></span>

<span data-ttu-id="1cc9e-390">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-390">This is a per-user policy.</span></span> <span data-ttu-id="1cc9e-391">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-391">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="1cc9e-392">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-392">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="1cc9e-393">目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-393">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span> 

<span data-ttu-id="1cc9e-394">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-394">Let's look at the following example.</span></span>

|<span data-ttu-id="1cc9e-395">使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-395">User</span></span> |<span data-ttu-id="1cc9e-396">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-396">Meeting policy</span></span>  |<span data-ttu-id="1cc9e-397">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="1cc9e-397">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-398">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cc9e-398">Daniela</span></span>   | <span data-ttu-id="1cc9e-399">全域</span><span class="sxs-lookup"><span data-stu-id="1cc9e-399">Global</span></span>   | <span data-ttu-id="1cc9e-400">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-400">True</span></span>       |
|<span data-ttu-id="1cc9e-401">Amanda</span><span class="sxs-lookup"><span data-stu-id="1cc9e-401">Amanda</span></span>   | <span data-ttu-id="1cc9e-402">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc9e-402">Location1MeetingPolicy</span></span> | <span data-ttu-id="1cc9e-403">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-403">False</span></span> |

<span data-ttu-id="1cc9e-404">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-404">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

### <a name="allow-chat-in-meetings-coming-soon"></a><span data-ttu-id="1cc9e-405">允許在會議中聊天（即將推出）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-405">Allow chat in meetings (coming soon)</span></span>

<span data-ttu-id="1cc9e-406">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-406">This is a per-organizer policy.</span></span> <span data-ttu-id="1cc9e-407">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-407">This setting controls whether meeting chat is allowed in the user's meeting.</span></span> 

<span data-ttu-id="1cc9e-408"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="1cc9e-408"></span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="1cc9e-409">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="1cc9e-409">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="1cc9e-410">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-410">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="1cc9e-411">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-411">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="1cc9e-412">允許匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="1cc9e-412">Allow anonymous people to start a meeting</span></span>](#allow-anonymous-people-to-start-a-meeting)
- [<span data-ttu-id="1cc9e-413">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="1cc9e-413">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)

> [!NOTE]
><span data-ttu-id="1cc9e-414">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-414">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="1cc9e-415">如果您的群組有音訊會議，且使用它來連接，請參閱[Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-415">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="1cc9e-416">如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-416">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="1cc9e-417">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-417">Automatically admit people</span></span>

<span data-ttu-id="1cc9e-418">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-418">This is a per-organizer policy.</span></span> <span data-ttu-id="1cc9e-419">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-419">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="1cc9e-421">會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-421">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="1cc9e-422">**（即將推出）**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-422">**(coming soon)**</span></span>
  
|<span data-ttu-id="1cc9e-423">設定值</span><span class="sxs-lookup"><span data-stu-id="1cc9e-423">Setting value</span></span>  |<span data-ttu-id="1cc9e-424">加入行為</span><span class="sxs-lookup"><span data-stu-id="1cc9e-424">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="1cc9e-425">**人員**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-425">**Everyone**</span></span>   |<span data-ttu-id="1cc9e-426">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-426">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="1cc9e-427">這包括經過驗證的使用者、聯盟使用者、來賓、匿名使用者，以及透過電話撥入的人員。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-427">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="1cc9e-428">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-428">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="1cc9e-429">組織內經過驗證的使用者，包括來賓使用者以及來自同盟組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-429">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="1cc9e-430">在大廳由手機撥入的匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-430">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="1cc9e-431">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="1cc9e-431">**Everyone in your organization**</span></span>    |<span data-ttu-id="1cc9e-432">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-432">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="1cc9e-433">在大廳以電話撥入的聯盟使用者、匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-433">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a><span data-ttu-id="1cc9e-434">允許匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="1cc9e-434">Allow anonymous people to start a meeting</span></span>

<span data-ttu-id="1cc9e-435">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-435">This is a per-organizer policy.</span></span> <span data-ttu-id="1cc9e-436">此設定會控制匿名人員（包括 B2B）與同盟使用者，是否可在沒有已驗證的使用者的情況下，從出席中的組織加入使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-436">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![螢幕擷取畫面顯示等候使用者的訊息](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="1cc9e-438">以下是在會議中有驗證使用者的情況下匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-438">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="1cc9e-439">允許匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="1cc9e-439">Allow anonymous people to start a meeting</span></span>  |<span data-ttu-id="1cc9e-440">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-440">Automatically admit people</span></span> |<span data-ttu-id="1cc9e-441">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="1cc9e-441">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-442">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-442">True</span></span>    | <span data-ttu-id="1cc9e-443">人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-443">Everyone</span></span>      | <span data-ttu-id="1cc9e-444">直接加入</span><span class="sxs-lookup"><span data-stu-id="1cc9e-444">Join directly</span></span>         |
|   | <span data-ttu-id="1cc9e-445">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-445">Everyone in your organization</span></span>       | <span data-ttu-id="1cc9e-446">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-446">Wait in lobby</span></span>        |
|   | <span data-ttu-id="1cc9e-447">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-447">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="1cc9e-448">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-448">Wait in lobby</span></span>         |
|<span data-ttu-id="1cc9e-449">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-449">False</span></span>    | <span data-ttu-id="1cc9e-450">人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-450">Everyone</span></span>        | <span data-ttu-id="1cc9e-451">直接加入</span><span class="sxs-lookup"><span data-stu-id="1cc9e-451">Join directly</span></span>        |
|   | <span data-ttu-id="1cc9e-452">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-452">Everyone in your organization</span></span>     | <span data-ttu-id="1cc9e-453">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-453">Wait in lobby</span></span>        |
|   | <span data-ttu-id="1cc9e-454">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-454">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="1cc9e-455">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-455">Wait in lobby</span></span>         |

<span data-ttu-id="1cc9e-456">以下是在會議中沒有經過驗證的使用者時，匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-456">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="1cc9e-457">允許匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="1cc9e-457">Allow anonymous people to start a meeting</span></span> |<span data-ttu-id="1cc9e-458">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-458">Automatically admit people</span></span>  |<span data-ttu-id="1cc9e-459">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="1cc9e-459">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-460">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-460">True</span></span>    | <span data-ttu-id="1cc9e-461">人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-461">Everyone</span></span>      | <span data-ttu-id="1cc9e-462">直接加入</span><span class="sxs-lookup"><span data-stu-id="1cc9e-462">Join directly</span></span>         |
|   | <span data-ttu-id="1cc9e-463">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-463">Everyone in your organization</span></span>       | <span data-ttu-id="1cc9e-464">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-464">Wait in lobby</span></span>        |
|   | <span data-ttu-id="1cc9e-465">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-465">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="1cc9e-466">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-466">Wait in lobby</span></span>         |
|<span data-ttu-id="1cc9e-467">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-467">False</span></span>    | <span data-ttu-id="1cc9e-468">人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-468">Everyone</span></span>        | <span data-ttu-id="1cc9e-469">在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-469">Wait in lobby.</span></span> <span data-ttu-id="1cc9e-470">當第一個經過驗證的使用者加入會議時，系統會自動准許使用者。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-470">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="1cc9e-471">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-471">Everyone in your organization</span></span>     |<span data-ttu-id="1cc9e-472">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-472">Wait in lobby</span></span>         |
|   | <span data-ttu-id="1cc9e-473">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-473">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="1cc9e-474">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-474">Wait in lobby</span></span>         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a><span data-ttu-id="1cc9e-475">允許撥入使用者略過大廳（即將推出）</span><span class="sxs-lookup"><span data-stu-id="1cc9e-475">Allow dial-in users to bypass the lobby (coming soon)</span></span>

<span data-ttu-id="1cc9e-476">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-476">This is a per-organizer policy.</span></span> <span data-ttu-id="1cc9e-477">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-477">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="1cc9e-478">以下是透過電話撥入的人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="1cc9e-478">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="1cc9e-479">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="1cc9e-479">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="1cc9e-480">自動承認使用者</span><span class="sxs-lookup"><span data-stu-id="1cc9e-480">Automatically admit users</span></span>  |<span data-ttu-id="1cc9e-481">撥入之人的加入行為</span><span class="sxs-lookup"><span data-stu-id="1cc9e-481">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cc9e-482">滿足</span><span class="sxs-lookup"><span data-stu-id="1cc9e-482">True</span></span>    | <span data-ttu-id="1cc9e-483">人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-483">Everyone</span></span>      | <span data-ttu-id="1cc9e-484">直接加入</span><span class="sxs-lookup"><span data-stu-id="1cc9e-484">Join directly</span></span>         |
|   | <span data-ttu-id="1cc9e-485">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-485">Everyone in your organization</span></span>       | <span data-ttu-id="1cc9e-486">直接加入</span><span class="sxs-lookup"><span data-stu-id="1cc9e-486">Join directly</span></span>        |
|   | <span data-ttu-id="1cc9e-487">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-487">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="1cc9e-488">直接加入</span><span class="sxs-lookup"><span data-stu-id="1cc9e-488">Join directly</span></span>         |
|<span data-ttu-id="1cc9e-489">虛假</span><span class="sxs-lookup"><span data-stu-id="1cc9e-489">False</span></span>    | <span data-ttu-id="1cc9e-490">人員</span><span class="sxs-lookup"><span data-stu-id="1cc9e-490">Everyone</span></span>        | <span data-ttu-id="1cc9e-491">直接加入</span><span class="sxs-lookup"><span data-stu-id="1cc9e-491">Join directly</span></span>        |
|   | <span data-ttu-id="1cc9e-492">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-492">Everyone in your organization</span></span>     |<span data-ttu-id="1cc9e-493">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-493">Wait in lobby</span></span>         |
|   | <span data-ttu-id="1cc9e-494">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="1cc9e-494">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="1cc9e-495">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="1cc9e-495">Wait in lobby</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="1cc9e-496">相關主題</span><span class="sxs-lookup"><span data-stu-id="1cc9e-496">Related topics</span></span>
[<span data-ttu-id="1cc9e-497">小組中的訊息原則</span><span class="sxs-lookup"><span data-stu-id="1cc9e-497">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
