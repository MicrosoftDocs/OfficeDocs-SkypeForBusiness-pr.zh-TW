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
ms.openlocfilehash: 2f6a88276a2b5d3214b89555d0008e2b58cf1aa2
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349557"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="6d2f7-103">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="6d2f7-104">會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="6d2f7-105">建立原則並進行變更之後，您可以將使用者指派給該原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="6d2f7-106">您可以在 Microsoft 團隊系統管理中心或使用[PowerShell](teams-powershell-overview.md)管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="6d2f7-107">您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="6d2f7-108">實現類型</span><span class="sxs-lookup"><span data-stu-id="6d2f7-108">Implementation type</span></span>  |<span data-ttu-id="6d2f7-109">描述</span><span class="sxs-lookup"><span data-stu-id="6d2f7-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6d2f7-110">每個召集人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-110">Per-organizer</span></span>    |<span data-ttu-id="6d2f7-111">當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="6d2f7-112">例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="6d2f7-113">每位使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-113">Per-user</span></span>    |<span data-ttu-id="6d2f7-114">當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="6d2f7-115">例如，[**允許在頻道中立即開會**] 是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="6d2f7-116">每個召集人和每位使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="6d2f7-117">當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="6d2f7-118">例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="6d2f7-119">開啟此設定可讓會議召集人與參與者開始並停止錄製。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="6d2f7-120">根據預設，會建立名為 [全域] （組織範圍預設值）的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="6d2f7-121">貴組織中的所有使用者預設都會獲指派 [全域會議原則]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="6d2f7-122">您可以對其進行變更或建立一或多個自訂原則，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="6d2f7-123">除非您建立並指派自訂原則，否則使用者會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6d2f7-124">當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將其指派給將設定套用至其中的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2f7-125">如果使用者已啟用音訊會議授權，或使用者允許音訊會議，則 [會議詳細資料] 按鈕就會提供，會議詳細資料將無法使用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="6d2f7-126">變更或建立會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-126">Change or create a meeting policy</span></span>

<span data-ttu-id="6d2f7-127">若要變更或建立會議原則，請移至 [Microsoft Teams 系統管理中心] > **[會議] \*\* > \*\* [會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="6d2f7-128">從清單中選取原則，或選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="6d2f7-129">如果您要建立新原則，請新增原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="6d2f7-130">名稱不能包含特殊字元，且長度不可超過 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="6d2f7-131">選擇您的設定，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="6d2f7-132">例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="6d2f7-133">您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="6d2f7-134">在 [音訊與視訊]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="6d2f7-135">關閉 [允許雲端錄製]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="6d2f7-136">關閉 [允許 IP 視訊]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="6d2f7-137">在 [內容共用]\*\*\*\* 下：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="6d2f7-138">停用 [螢幕畫面分享模式]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="6d2f7-139">關閉 [允許白板]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="6d2f7-140">關閉 [允許共用記事]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="6d2f7-141">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2f7-142">一次只能為使用者指派一個會議原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="6d2f7-143">將會議原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-143">Assign a meeting policy to users</span></span>

<span data-ttu-id="6d2f7-144">若要將會議原則指派給一個使用者：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-144">To assign a meeting policy to one user:</span></span>

1. <span data-ttu-id="6d2f7-145">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6d2f7-146">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-146">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="6d2f7-147">在 [會議原則]\*\*\*\* 下，選取要指派的原則，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-147">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="6d2f7-148">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-148">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="6d2f7-149">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**使用者**]，然後搜尋使用者或篩選視圖，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-149">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="6d2f7-150">在 [ **&#x2713;** （核取符號）] 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-150">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="6d2f7-151">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713; （核取符號）。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-151">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="6d2f7-152">按一下 [**編輯設定**]，進行您想要的變更，然後按一下 [套用 **]。**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-152">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="6d2f7-153">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-153">Or, you can also do the following:</span></span>

1. <span data-ttu-id="6d2f7-154">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-154">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6d2f7-155">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-155">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="6d2f7-156">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-156">Select **Manage users**.</span></span>
4. <span data-ttu-id="6d2f7-157">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6d2f7-158">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-158">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6d2f7-159">完成新增使用者之後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-159">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2f7-160">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-160">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="6d2f7-161">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-161">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="6d2f7-162">會議原則設定</span><span class="sxs-lookup"><span data-stu-id="6d2f7-162">Meeting policy settings</span></span>

<span data-ttu-id="6d2f7-163">當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增**] 以新增原則時，您可以設定下列各項的設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-163">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="6d2f7-164">一般</span><span class="sxs-lookup"><span data-stu-id="6d2f7-164">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="6d2f7-165">音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="6d2f7-165">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="6d2f7-166">內容共用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-166">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="6d2f7-167">參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="6d2f7-167">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="6d2f7-168"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="6d2f7-168"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="6d2f7-169">會議原則設定-一般</span><span class="sxs-lookup"><span data-stu-id="6d2f7-169">Meeting policy settings - General</span></span>

- <span data-ttu-id="6d2f7-170">[允許頻道中的 [立即開會]](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="6d2f7-170">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="6d2f7-171">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="6d2f7-171">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="6d2f7-172">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="6d2f7-172">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="6d2f7-173">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="6d2f7-173">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="6d2f7-174">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="6d2f7-174">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="6d2f7-175">允許頻道中的 [立即開會]</span><span class="sxs-lookup"><span data-stu-id="6d2f7-175">Allow Meet now in channels</span></span>

<span data-ttu-id="6d2f7-176">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-176">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6d2f7-177">此設定控制使用者是否可在團隊頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-177">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="6d2f7-178">如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-178">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="6d2f7-179">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-179">The default value is True.</span></span>

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="6d2f7-181">允許 Outlook 增益集</span><span class="sxs-lookup"><span data-stu-id="6d2f7-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="6d2f7-182">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6d2f7-183">此設定控制團隊會議是否可在 Outlook 中排程（Windows、Mac、web 及行動裝置）。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="6d2f7-185">如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="6d2f7-186">例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="6d2f7-187">允許頻道會議排程</span><span class="sxs-lookup"><span data-stu-id="6d2f7-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="6d2f7-188">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6d2f7-189">此設定控制使用者是否可在團隊頻道中排程會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="6d2f7-190">如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="6d2f7-191">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-191">The default value is True.</span></span>

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="6d2f7-194">允許排程私人會議</span><span class="sxs-lookup"><span data-stu-id="6d2f7-194">Allow scheduling private meetings</span></span>

<span data-ttu-id="6d2f7-195">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-195">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6d2f7-196">此設定可控制使用者是否可以在小組中排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-196">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="6d2f7-197">如果會議不是發佈至小組中的頻道，就是私人的。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-197">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="6d2f7-198">請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-198">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="6d2f7-199">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-199">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="6d2f7-200">在私人會議中允許立即開會</span><span class="sxs-lookup"><span data-stu-id="6d2f7-200">Allow Meet now in private meetings</span></span>

<span data-ttu-id="6d2f7-201">這是針對每個使用者的原則，在會議開始之前就會套用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-201">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6d2f7-202">此設定可控制使用者是否能開始即席私人會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-202">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="6d2f7-203">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-203">The default value is True.</span></span>

<span data-ttu-id="6d2f7-204"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="6d2f7-204"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="6d2f7-205">會議原則設定-音訊 & 影片</span><span class="sxs-lookup"><span data-stu-id="6d2f7-205">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="6d2f7-206">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="6d2f7-206">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="6d2f7-207">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="6d2f7-207">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="6d2f7-208">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="6d2f7-208">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="6d2f7-209">媒體位元速率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="6d2f7-209">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="6d2f7-210">允許進行文字</span><span class="sxs-lookup"><span data-stu-id="6d2f7-210">Allow transcription</span></span>

<span data-ttu-id="6d2f7-211">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-211">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="6d2f7-212">此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-212">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="6d2f7-213">如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-213">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="6d2f7-214">開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-214">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="6d2f7-215">請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-215">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="6d2f7-217">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="6d2f7-217">Allow cloud recording</span></span>

<span data-ttu-id="6d2f7-218">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-218">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="6d2f7-219">此設定控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-219">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="6d2f7-220">如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-220">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="6d2f7-221">貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-221">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="6d2f7-222">來賓使用者無法啟動或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-222">Guest users can't start or stop the recording.</span></span> 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="6d2f7-224">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-224">Let's look at the following example.</span></span>

|<span data-ttu-id="6d2f7-225">使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-225">User</span></span> |<span data-ttu-id="6d2f7-226">會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-226">Meeting policy</span></span>  |<span data-ttu-id="6d2f7-227">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="6d2f7-227">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-228">Daniela</span><span class="sxs-lookup"><span data-stu-id="6d2f7-228">Daniela</span></span> | <span data-ttu-id="6d2f7-229">全域</span><span class="sxs-lookup"><span data-stu-id="6d2f7-229">Global</span></span>   | <span data-ttu-id="6d2f7-230">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-230">False</span></span> |
|<span data-ttu-id="6d2f7-231">Amanda</span><span class="sxs-lookup"><span data-stu-id="6d2f7-231">Amanda</span></span> | <span data-ttu-id="6d2f7-232">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6d2f7-232">Location1MeetingPolicy</span></span> | <span data-ttu-id="6d2f7-233">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-233">True</span></span>|
|<span data-ttu-id="6d2f7-234">約翰（外部使用者）</span><span class="sxs-lookup"><span data-stu-id="6d2f7-234">John (external user)</span></span> | <span data-ttu-id="6d2f7-235">不適用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-235">Not applicable</span></span> | <span data-ttu-id="6d2f7-236">不適用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-236">Not applicable</span></span>|

<span data-ttu-id="6d2f7-237">依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-237">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="6d2f7-238">您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-238">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="6d2f7-239">若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-239">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="6d2f7-240">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="6d2f7-240">Allow IP video</span></span>

<span data-ttu-id="6d2f7-241">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-241">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="6d2f7-242">影片是會議的關鍵元件。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-242">Video is a key component to meetings.</span></span> <span data-ttu-id="6d2f7-243">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-243">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="6d2f7-244">此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-244">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="6d2f7-245">在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-245">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="6d2f7-246">沒有指派任何原則的會議參與者（例如匿名及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-246">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="6d2f7-248">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-248">Let's look at the following example.</span></span>

|<span data-ttu-id="6d2f7-249">使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-249">User</span></span> |<span data-ttu-id="6d2f7-250">會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-250">Meeting policy</span></span>  |<span data-ttu-id="6d2f7-251">允許 IP 影片</span><span class="sxs-lookup"><span data-stu-id="6d2f7-251">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-252">Daniela</span><span class="sxs-lookup"><span data-stu-id="6d2f7-252">Daniela</span></span>   | <span data-ttu-id="6d2f7-253">全域</span><span class="sxs-lookup"><span data-stu-id="6d2f7-253">Global</span></span>   | <span data-ttu-id="6d2f7-254">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-254">True</span></span>        |
|<span data-ttu-id="6d2f7-255">Amanda</span><span class="sxs-lookup"><span data-stu-id="6d2f7-255">Amanda</span></span>    | <span data-ttu-id="6d2f7-256">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6d2f7-256">Location1MeetingPolicy</span></span>        | <span data-ttu-id="6d2f7-257">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-257">False</span></span>      |

<span data-ttu-id="6d2f7-258">由 Daniela 託管的會議允許開啟影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-258">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="6d2f7-259">Daniela 可以加入會議，然後開啟 [影片]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-259">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="6d2f7-260">Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-260">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="6d2f7-261">Amanda 可以查看會議中其他參與者所共用的影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-261">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="6d2f7-262">在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-262">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="6d2f7-263">這表示 Daniela 無法在 Amanda 的會議中開啟影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-263">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="6d2f7-264">如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-264">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="6d2f7-265">通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-265">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="6d2f7-266">如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-266">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="6d2f7-267">當通話連線時，Daniela 可以視需要開啟或關閉她的影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-267">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="6d2f7-268">媒體位元速率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="6d2f7-268">Media bit rate (Kbs)</span></span>

<span data-ttu-id="6d2f7-269">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-269">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-270">此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-270">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="6d2f7-271">它適用于通話或會議中的使用者的上行與下行媒體遍歷。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-271">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="6d2f7-272">此設定可讓您精細控制貴組織中的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-272">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="6d2f7-273">根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-273">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="6d2f7-274">最小值為 30 Kbps，而最大值則視會議案例而定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-274">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="6d2f7-275">若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-275">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="6d2f7-276">如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-276">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="6d2f7-277">如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-277">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="6d2f7-278">即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-278">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="6d2f7-279">會議原則設定-內容共用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-279">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="6d2f7-280">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="6d2f7-280">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="6d2f7-281">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="6d2f7-281">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="6d2f7-282">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="6d2f7-282">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="6d2f7-283">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-283">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="6d2f7-284">允許白板</span><span class="sxs-lookup"><span data-stu-id="6d2f7-284">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="6d2f7-285">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="6d2f7-285">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="6d2f7-286">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="6d2f7-286">Screen sharing mode</span></span>

<span data-ttu-id="6d2f7-287">這是每個組織單位和每個使用者原則的組合。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-287">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="6d2f7-288">此設定控制使用者的會議是否允許桌面和/或視窗共用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-288">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="6d2f7-289">沒有指派任何原則的會議參與者（例如，匿名、來賓、B2B 及同盟參與者）會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-289">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="6d2f7-290">設定值</span><span class="sxs-lookup"><span data-stu-id="6d2f7-290">Setting value</span></span> |<span data-ttu-id="6d2f7-291">行為</span><span class="sxs-lookup"><span data-stu-id="6d2f7-291">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="6d2f7-292">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-292">**Entire screen**</span></span>    | <span data-ttu-id="6d2f7-293">在會議中允許進行完整的桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-293">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="6d2f7-294">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-294">**Single application**</span></span>   | <span data-ttu-id="6d2f7-295">允許在會議中共用應用程式</span><span class="sxs-lookup"><span data-stu-id="6d2f7-295">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="6d2f7-296">**禁止**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-296">**Disabled**</span></span>     |<span data-ttu-id="6d2f7-297">在會議中關閉螢幕共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-297">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="6d2f7-298">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-298">Let's look at the following example.</span></span>

|<span data-ttu-id="6d2f7-299">使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-299">User</span></span> |<span data-ttu-id="6d2f7-300">會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-300">Meeting policy</span></span> |<span data-ttu-id="6d2f7-301">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="6d2f7-301">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-302">Daniela</span><span class="sxs-lookup"><span data-stu-id="6d2f7-302">Daniela</span></span>  | <span data-ttu-id="6d2f7-303">全域</span><span class="sxs-lookup"><span data-stu-id="6d2f7-303">Global</span></span>   | <span data-ttu-id="6d2f7-304">整個畫面</span><span class="sxs-lookup"><span data-stu-id="6d2f7-304">Entire screen</span></span> |
|<span data-ttu-id="6d2f7-305">Amanda</span><span class="sxs-lookup"><span data-stu-id="6d2f7-305">Amanda</span></span>   | <span data-ttu-id="6d2f7-306">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6d2f7-306">Location1MeetingPolicy</span></span>  | <span data-ttu-id="6d2f7-307">禁止</span><span class="sxs-lookup"><span data-stu-id="6d2f7-307">Disabled</span></span> |

<span data-ttu-id="6d2f7-308">Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-308">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="6d2f7-309">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-309">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="6d2f7-310">在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-310">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="6d2f7-311">這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-311">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="6d2f7-312">目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-312">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="6d2f7-313">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="6d2f7-313">Allow a participant to give or request control</span></span>

<span data-ttu-id="6d2f7-314">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-314">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-315">此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-315">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="6d2f7-316">若要授與控制權，請將游標暫留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-316">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="6d2f7-317">如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-317">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="6d2f7-319">如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-319">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="6d2f7-321">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-321">Let's look at the following example.</span></span>

|<span data-ttu-id="6d2f7-322">使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-322">User</span></span> |<span data-ttu-id="6d2f7-323">會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-323">Meeting policy</span></span>  |<span data-ttu-id="6d2f7-324">允許參與者授與要求控制</span><span class="sxs-lookup"><span data-stu-id="6d2f7-324">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-325">Daniela</span><span class="sxs-lookup"><span data-stu-id="6d2f7-325">Daniela</span></span>   | <span data-ttu-id="6d2f7-326">全域</span><span class="sxs-lookup"><span data-stu-id="6d2f7-326">Global</span></span>   | <span data-ttu-id="6d2f7-327">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-327">True</span></span>       |
|<span data-ttu-id="6d2f7-328">Babek</span><span class="sxs-lookup"><span data-stu-id="6d2f7-328">Babek</span></span>    | <span data-ttu-id="6d2f7-329">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6d2f7-329">Location1MeetingPolicy</span></span>        | <span data-ttu-id="6d2f7-330">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-330">False</span></span>   |

<span data-ttu-id="6d2f7-331">Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-331">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="6d2f7-332">若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-332">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2f7-333">若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-333">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="6d2f7-334">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-334">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="6d2f7-335">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-335">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="6d2f7-336">允許外部參與者授與或要求控制</span><span class="sxs-lookup"><span data-stu-id="6d2f7-336">Allow an external participant to give or request control</span></span>

<span data-ttu-id="6d2f7-337">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-337">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-338">此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-338">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="6d2f7-339">團隊會議中的外部參與者可以分類如下：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-339">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="6d2f7-340">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-340">Anonymous user</span></span>
- <span data-ttu-id="6d2f7-341">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-341">Guest users</span></span>  
- <span data-ttu-id="6d2f7-342">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-342">B2B user</span></span>
- <span data-ttu-id="6d2f7-343">聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-343">Federated user</span></span>  

<span data-ttu-id="6d2f7-344">聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-344">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="6d2f7-345">若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-345">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="6d2f7-346">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-346">Allow PowerPoint sharing</span></span>

<span data-ttu-id="6d2f7-347">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-347">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-348">此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-348">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="6d2f7-349">外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-349">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="6d2f7-350">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-350">Let's look at the following example.</span></span>

|<span data-ttu-id="6d2f7-351">使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-351">User</span></span> |<span data-ttu-id="6d2f7-352">會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-352">Meeting policy</span></span>  |<span data-ttu-id="6d2f7-353">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="6d2f7-353">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-354">Daniela</span><span class="sxs-lookup"><span data-stu-id="6d2f7-354">Daniela</span></span>   | <span data-ttu-id="6d2f7-355">全域</span><span class="sxs-lookup"><span data-stu-id="6d2f7-355">Global</span></span>   | <span data-ttu-id="6d2f7-356">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-356">True</span></span>       |
|<span data-ttu-id="6d2f7-357">Amanda</span><span class="sxs-lookup"><span data-stu-id="6d2f7-357">Amanda</span></span>   | <span data-ttu-id="6d2f7-358">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6d2f7-358">Location1MeetingPolicy</span></span>        | <span data-ttu-id="6d2f7-359">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-359">False</span></span>   |

<span data-ttu-id="6d2f7-360">Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-360">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="6d2f7-361">Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-361">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="6d2f7-362">Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-362">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="6d2f7-363">允許白板</span><span class="sxs-lookup"><span data-stu-id="6d2f7-363">Allow whiteboard</span></span>

<span data-ttu-id="6d2f7-364">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-364">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-365">此設定可控制使用者是否可以在會議中共用白板。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-365">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="6d2f7-366">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-366">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="6d2f7-367">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-367">Let's look at the following example.</span></span>

|<span data-ttu-id="6d2f7-368">使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-368">User</span></span> |<span data-ttu-id="6d2f7-369">會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-369">Meeting policy</span></span>  |<span data-ttu-id="6d2f7-370">允許白板</span><span class="sxs-lookup"><span data-stu-id="6d2f7-370">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6d2f7-371">Daniela</span><span class="sxs-lookup"><span data-stu-id="6d2f7-371">Daniela</span></span>   | <span data-ttu-id="6d2f7-372">全域</span><span class="sxs-lookup"><span data-stu-id="6d2f7-372">Global</span></span>   | <span data-ttu-id="6d2f7-373">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-373">True</span></span>       |
|<span data-ttu-id="6d2f7-374">Amanda</span><span class="sxs-lookup"><span data-stu-id="6d2f7-374">Amanda</span></span>   | <span data-ttu-id="6d2f7-375">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6d2f7-375">Location1MeetingPolicy</span></span>        | <span data-ttu-id="6d2f7-376">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-376">False</span></span>   |

<span data-ttu-id="6d2f7-377">Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-377">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="6d2f7-378">Daniela 可以共用白板，即使會議是由 Amanda 來組織。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-378">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="6d2f7-379">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="6d2f7-379">Allow shared notes</span></span>

<span data-ttu-id="6d2f7-380">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-380">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-381">此設定可控制使用者是否可以在會議中建立和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-381">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="6d2f7-382">外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-382">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="6d2f7-383">目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-383">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="6d2f7-384">我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-384">Let's look at the following example.</span></span>

|<span data-ttu-id="6d2f7-385">使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-385">User</span></span> |<span data-ttu-id="6d2f7-386">會議原則</span><span class="sxs-lookup"><span data-stu-id="6d2f7-386">Meeting policy</span></span>  |<span data-ttu-id="6d2f7-387">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="6d2f7-387">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-388">Daniela</span><span class="sxs-lookup"><span data-stu-id="6d2f7-388">Daniela</span></span>   | <span data-ttu-id="6d2f7-389">全域</span><span class="sxs-lookup"><span data-stu-id="6d2f7-389">Global</span></span>   | <span data-ttu-id="6d2f7-390">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-390">True</span></span>       |
|<span data-ttu-id="6d2f7-391">Amanda</span><span class="sxs-lookup"><span data-stu-id="6d2f7-391">Amanda</span></span>   | <span data-ttu-id="6d2f7-392">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6d2f7-392">Location1MeetingPolicy</span></span> | <span data-ttu-id="6d2f7-393">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-393">False</span></span> |

<span data-ttu-id="6d2f7-394">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-394">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="6d2f7-395">會議原則設定-參與者 & 來賓</span><span class="sxs-lookup"><span data-stu-id="6d2f7-395">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="6d2f7-396">這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-396">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="6d2f7-397">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="6d2f7-397">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="6d2f7-398">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="6d2f7-398">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="6d2f7-399">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="6d2f7-399">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="6d2f7-400">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="6d2f7-400">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="6d2f7-401">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="6d2f7-401">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="6d2f7-402">加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-402">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="6d2f7-403">如果您的群組有音訊會議，且使用它來連接，請參閱[Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-403">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="6d2f7-404">如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-404">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="6d2f7-405">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="6d2f7-405">Let anonymous people start a meeting</span></span>

<span data-ttu-id="6d2f7-406">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-406">This is a per-organizer policy.</span></span> <span data-ttu-id="6d2f7-407">此設定會控制匿名人員（包括 B2B）與同盟使用者，是否可在沒有已驗證的使用者的情況下，從出席中的組織加入使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-407">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="6d2f7-408">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-408">The default value is False.</span></span>

![螢幕擷取畫面顯示等候使用者的訊息](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="6d2f7-410">以下是在會議中有驗證使用者的情況下匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-410">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="6d2f7-411">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="6d2f7-411">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="6d2f7-412">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="6d2f7-412">Automatically admit people</span></span> |<span data-ttu-id="6d2f7-413">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="6d2f7-413">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-414">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-414">True</span></span>    | <span data-ttu-id="6d2f7-415">任何人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-415">Everyone</span></span>      | <span data-ttu-id="6d2f7-416">直接加入</span><span class="sxs-lookup"><span data-stu-id="6d2f7-416">Join directly</span></span>         |
|   | <span data-ttu-id="6d2f7-417">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-417">Everyone in your organization</span></span>       | <span data-ttu-id="6d2f7-418">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-418">Wait in lobby</span></span>        |
|   | <span data-ttu-id="6d2f7-419">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-419">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="6d2f7-420">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-420">Wait in lobby</span></span>         |
|<span data-ttu-id="6d2f7-421">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-421">False</span></span>    | <span data-ttu-id="6d2f7-422">任何人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-422">Everyone</span></span>        | <span data-ttu-id="6d2f7-423">直接加入</span><span class="sxs-lookup"><span data-stu-id="6d2f7-423">Join directly</span></span>        |
|   | <span data-ttu-id="6d2f7-424">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-424">Everyone in your organization</span></span>     | <span data-ttu-id="6d2f7-425">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-425">Wait in lobby</span></span>        |
|   | <span data-ttu-id="6d2f7-426">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-426">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="6d2f7-427">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-427">Wait in lobby</span></span>         |

<span data-ttu-id="6d2f7-428">以下是在會議中沒有經過驗證的使用者時，匿名人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-428">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="6d2f7-429">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="6d2f7-429">Let anonymous people start a meeting</span></span> |<span data-ttu-id="6d2f7-430">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="6d2f7-430">Automatically admit people</span></span>  |<span data-ttu-id="6d2f7-431">匿名人員的加入行為</span><span class="sxs-lookup"><span data-stu-id="6d2f7-431">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-432">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-432">True</span></span>    | <span data-ttu-id="6d2f7-433">任何人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-433">Everyone</span></span>      | <span data-ttu-id="6d2f7-434">直接加入</span><span class="sxs-lookup"><span data-stu-id="6d2f7-434">Join directly</span></span>         |
|   | <span data-ttu-id="6d2f7-435">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-435">Everyone in your organization</span></span>       | <span data-ttu-id="6d2f7-436">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-436">Wait in lobby</span></span>        |
|   | <span data-ttu-id="6d2f7-437">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-437">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="6d2f7-438">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-438">Wait in lobby</span></span>         |
|<span data-ttu-id="6d2f7-439">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-439">False</span></span>    | <span data-ttu-id="6d2f7-440">任何人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-440">Everyone</span></span>        | <span data-ttu-id="6d2f7-441">在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-441">Wait in lobby.</span></span> <span data-ttu-id="6d2f7-442">當第一個經過驗證的使用者加入會議時，系統會自動准許使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-442">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="6d2f7-443">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-443">Everyone in your organization</span></span>     |<span data-ttu-id="6d2f7-444">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-444">Wait in lobby</span></span>         |
|   | <span data-ttu-id="6d2f7-445">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-445">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="6d2f7-446">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-446">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="6d2f7-447">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="6d2f7-447">Automatically admit people</span></span>

<span data-ttu-id="6d2f7-448">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-448">This is a per-organizer policy.</span></span> <span data-ttu-id="6d2f7-449">此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-449">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="6d2f7-451">會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-451">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="6d2f7-452">設定值</span><span class="sxs-lookup"><span data-stu-id="6d2f7-452">Setting value</span></span>  |<span data-ttu-id="6d2f7-453">加入行為</span><span class="sxs-lookup"><span data-stu-id="6d2f7-453">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="6d2f7-454">**任何人**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-454">**Everyone**</span></span>   |<span data-ttu-id="6d2f7-455">所有會議參與者都能直接加入會議，不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-455">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="6d2f7-456">這包括經過驗證的使用者、聯盟使用者、來賓、匿名使用者，以及透過電話撥入的人員。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-456">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="6d2f7-457">**貴組織和聯盟組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-457">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="6d2f7-458">組織內經過驗證的使用者，包括來賓使用者以及來自同盟組織的使用者，直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-458">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="6d2f7-459">在大廳由手機撥入的匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-459">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="6d2f7-460">**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-460">**Everyone in your organization**</span></span>    |<span data-ttu-id="6d2f7-461">從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-461">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="6d2f7-462">在大廳以電話撥入的聯盟使用者、匿名使用者和使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-462">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span> <span data-ttu-id="6d2f7-463">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-463">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="6d2f7-464">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="6d2f7-464">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="6d2f7-465">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-465">This is a per-organizer policy.</span></span> <span data-ttu-id="6d2f7-466">此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-466">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="6d2f7-467">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-467">The default value is False.</span></span>

<span data-ttu-id="6d2f7-468">以下是透過電話撥入的人員的加入行為。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-468">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="6d2f7-469">允許撥入使用者略過大廳</span><span class="sxs-lookup"><span data-stu-id="6d2f7-469">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="6d2f7-470">自動承認人員</span><span class="sxs-lookup"><span data-stu-id="6d2f7-470">Automatically admit people</span></span>  |<span data-ttu-id="6d2f7-471">撥入之人的加入行為</span><span class="sxs-lookup"><span data-stu-id="6d2f7-471">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d2f7-472">滿足</span><span class="sxs-lookup"><span data-stu-id="6d2f7-472">True</span></span>    | <span data-ttu-id="6d2f7-473">任何人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-473">Everyone</span></span>      | <span data-ttu-id="6d2f7-474">直接加入</span><span class="sxs-lookup"><span data-stu-id="6d2f7-474">Join directly</span></span>         |
|   | <span data-ttu-id="6d2f7-475">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-475">Everyone in your organization</span></span>       | <span data-ttu-id="6d2f7-476">直接加入</span><span class="sxs-lookup"><span data-stu-id="6d2f7-476">Join directly</span></span>        |
|   | <span data-ttu-id="6d2f7-477">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-477">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="6d2f7-478">直接加入</span><span class="sxs-lookup"><span data-stu-id="6d2f7-478">Join directly</span></span>         |
|<span data-ttu-id="6d2f7-479">虛假</span><span class="sxs-lookup"><span data-stu-id="6d2f7-479">False</span></span>    | <span data-ttu-id="6d2f7-480">任何人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-480">Everyone</span></span>        | <span data-ttu-id="6d2f7-481">直接加入</span><span class="sxs-lookup"><span data-stu-id="6d2f7-481">Join directly</span></span>        |
|   | <span data-ttu-id="6d2f7-482">貴組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-482">Everyone in your organization</span></span>     |<span data-ttu-id="6d2f7-483">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-483">Wait in lobby</span></span>         |
|   | <span data-ttu-id="6d2f7-484">貴組織和聯盟組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="6d2f7-484">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="6d2f7-485">在大廳等候</span><span class="sxs-lookup"><span data-stu-id="6d2f7-485">Wait in lobby</span></span>         |


### <a name="enable-live-captions"></a><span data-ttu-id="6d2f7-486">啟用即時標題</span><span class="sxs-lookup"><span data-stu-id="6d2f7-486">Enable live captions</span></span>

<span data-ttu-id="6d2f7-487">這是針對每個使用者的原則，且適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-487">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="6d2f7-488">此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-488">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="6d2f7-490">設定值</span><span class="sxs-lookup"><span data-stu-id="6d2f7-490">Setting value</span></span> |<span data-ttu-id="6d2f7-491">行為</span><span class="sxs-lookup"><span data-stu-id="6d2f7-491">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="6d2f7-492">**已停用，但使用者可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-492">**Disabled but the user can override**</span></span>     | <span data-ttu-id="6d2f7-493">在會議期間，使用者不會自動開啟 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-493">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="6d2f7-494">使用者會看到 [溢出（**...**）] 功能表中的 [**開啟即時標題**] 選項，以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-494">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="6d2f7-495">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-495">This is the default setting.</span></span> |
|<span data-ttu-id="6d2f7-496">**禁止**</span><span class="sxs-lookup"><span data-stu-id="6d2f7-496">**Disabled**</span></span>     | <span data-ttu-id="6d2f7-497">使用者在會議期間停用 [即時] 標題。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-497">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="6d2f7-498">使用者沒有選項可將其開啟。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-498">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="6d2f7-499"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="6d2f7-499"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="6d2f7-500">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="6d2f7-500">Allow chat in meetings</span></span>

<span data-ttu-id="6d2f7-501">這是每個召集人原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-501">This is a per-organizer policy.</span></span> <span data-ttu-id="6d2f7-502">此設定控制是否允許在使用者的會議中使用會議聊天。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-502">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="6d2f7-503"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="6d2f7-503"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="6d2f7-504">會議原則設定-指定的簡報者角色模式</span><span class="sxs-lookup"><span data-stu-id="6d2f7-504">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="6d2f7-505">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-505">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-506">這項設定可讓您變更小組用戶端的 [**會議選項**] 中的 [**可以出示的人員**] 設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-506">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="6d2f7-507">此原則設定會影響所有會議，包括 [立即開會] 會議。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-507">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="6d2f7-508">[**可以出席的人員**] 設定可讓會議召集人選擇要在會議中成為簡報者的人員。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-508">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="6d2f7-509">若要深入瞭解，請參閱[在團隊會議中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)[變更團隊會議](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)與角色的參與者設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-509">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="6d2f7-510">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-510">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="6d2f7-511">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-511">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="6d2f7-512">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-512">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="6d2f7-513">若要指定 [**可以提出的人員**] 的預設值，請將**DesignatedPresenterRoleMode**參數設定為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6d2f7-513">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="6d2f7-514">**EveryoneUserOverride**：所有會議參與者都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-514">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="6d2f7-515">此為預設值。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-515">This is the default value.</span></span> <span data-ttu-id="6d2f7-516">這個參數會對應到 [小組] 中的 [**所有人**] 設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-516">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="6d2f7-517">**EveryoneInCompanyUserOverride**：組織中經過驗證的使用者，包括來賓使用者，都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-517">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="6d2f7-518">這個參數會對應到 [**我的組織**中的人員] 設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-518">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="6d2f7-519">**EveryoneInSameAndFederatedCompanyUserOverride**：組織中經過驗證的使用者，包括來賓使用者和聯盟組織的使用者，都可以是簡報者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-519">**EveryoneInSameAndFederatedCompanyUserOverride**:  Authenticated users in the organization, including guest users and users from federated organizations, can be presenters.</span></span> <span data-ttu-id="6d2f7-520">這個參數會對應到 [**我的組織中的人員] 和**[小組中受信任的組織] 設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-520">This parameter corresponds to the **People in my organization and trusted organizations** setting in Teams.</span></span>
- <span data-ttu-id="6d2f7-521">**OrganizerOnlyUserOverride**：只有會議召集人可以成為簡報者，且所有會議參與者都指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-521">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="6d2f7-522">這個參數會對應到 [團隊] 中的 [**僅自己**] 設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-522">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="6d2f7-523">請記住，在您設定預設值之後，會議召集人仍可在團隊中變更此設定，並選擇誰可以在排程的會議中出席。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-523">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="6d2f7-524">會議原則設定-會議出席情況報告</span><span class="sxs-lookup"><span data-stu-id="6d2f7-524">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="6d2f7-525">這是每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-525">This is a per-user policy.</span></span> <span data-ttu-id="6d2f7-526">此設定控制會議召集人是否可以下載[會議出席情況報告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-526">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="6d2f7-527">目前您只能使用 PowerShell 來設定此原則設定。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-527">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="6d2f7-528">您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-528">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="6d2f7-529">或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-529">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="6d2f7-530">若要讓會議召集人下載會議出席情況報告，請將**AllowEngagementReport**參數設定為 [**已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-530">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="6d2f7-531">啟用時，會在**參與者**窗格中顯示下載報告的選項。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-531">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="6d2f7-532">若要避免會議召集人下載報表，請將參數設定為 [**已停用**]。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-532">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="6d2f7-533">根據預設，此設定會停用，而且無法使用下載報表的選項。</span><span class="sxs-lookup"><span data-stu-id="6d2f7-533">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d2f7-534">相關主題</span><span class="sxs-lookup"><span data-stu-id="6d2f7-534">Related topics</span></span>

- [<span data-ttu-id="6d2f7-535">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="6d2f7-535">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6d2f7-536">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="6d2f7-536">Assign policies to your users in Teams</span></span>](assign-policies.md)
