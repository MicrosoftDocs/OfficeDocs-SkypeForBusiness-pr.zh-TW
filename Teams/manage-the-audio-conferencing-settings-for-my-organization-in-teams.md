---
title: 管理音訊會議設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '請參閱Microsoft Teams將電話撥入式會議授權和會議 ID 指派給使用者和其他許多電話撥入式會議設定的步驟。 '
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101089"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="ab664-103">在 Microsoft Teams 管理貴組織的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="ab664-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="ab664-104">您可以更輕鬆地在單一位置查看所有Microsoft Teams會議設定。</span><span class="sxs-lookup"><span data-stu-id="ab664-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="ab664-105">指派音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="ab664-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="ab664-106">您無法使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="ab664-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="ab664-107">您必須使用系統管理Microsoft 365中心。</span><span class="sxs-lookup"><span data-stu-id="ab664-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="ab664-108">請參閱[指派Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-108">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> 
  
 <span data-ttu-id="ab664-109">**為使用者指派授權**</span><span class="sxs-lookup"><span data-stu-id="ab664-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="ab664-110">使用公司Microsoft 365學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="ab664-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ab664-111">在系統管理中心的左側Microsoft 365，前往使用者活動使用者，然後從可用使用者清單中選取  >  使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ab664-112">如果您同時將授權指派給最多 20 個使用者，您可以使用選取視圖下拉式清單，然後選擇其中一個選項，或建立您自己的視圖。</span><span class="sxs-lookup"><span data-stu-id="ab664-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="ab664-113">然後按一下 [**編輯，\*\*\*\*下** 一步兩次，然後選取授權並 **按一下 [提交**> 。</span><span class="sxs-lookup"><span data-stu-id="ab664-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="ab664-114">在 [產品授權」 下的 [動作 **窗格**> 中，按一下 **[編輯。**</span><span class="sxs-lookup"><span data-stu-id="ab664-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="ab664-115">在 [ **產品授權>** 頁面上，開啟 **音訊會議** ，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="ab664-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="ab664-116">有關授權的更多內容，請參閱Microsoft Teams[附加元件授權。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="ab664-116">For more on licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="ab664-117">指派授權之後，Microsoft 一開始可能不會在清單中顯示為音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="ab664-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="ab664-118">如果發生這種情況，請登出系統管理中心，或按 CTRL+F5 重新啟用瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="ab664-118">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="ab664-119">啟用或停用發送給音訊會議使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="ab664-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="ab664-120">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ab664-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-121">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="ab664-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ab664-122">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="ab664-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ab664-123">在橋接器 **設定窗格中** ，啟用或停用當使用者的撥入設定變更時自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="ab664-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="ab664-124">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ab664-124">Click **Save**.</span></span>

    
<span data-ttu-id="ab664-125">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ab664-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="ab664-126">請參閱[powerShell Microsoft Teams，](/powershell/module/teams/?view=teams-ps)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ab664-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="ab664-127">重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="ab664-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="ab664-128">![使用系統管理中心Teams ](media/teams-logo-30x30.png) **圖示Microsoft Teams標誌**</span><span class="sxs-lookup"><span data-stu-id="ab664-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-129">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ab664-130">在 **[音訊會議」** 下，按一下 **[重設會議 ID。**</span><span class="sxs-lookup"><span data-stu-id="ab664-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="ab664-131">在 [ **重設會議 ID？ 視窗中** ，按一下 [ **重設**。</span><span class="sxs-lookup"><span data-stu-id="ab664-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="ab664-132">如果已啟用傳送電子郵件給使用者，系統會自動建立會議 ID，並傳送一封具有新會議 ID 的電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="ab664-133">預設會啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="ab664-133">It's enabled by default.</span></span>

<span data-ttu-id="ab664-134">請參閱[為使用者重設會議 ID。](reset-a-conference-id-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ab664-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="ab664-135">重設會議召集人的 PIN</span><span class="sxs-lookup"><span data-stu-id="ab664-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="ab664-136">使用者排程的每個會議都會獲得一個唯一的會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="ab664-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="ab664-137">雖然會自動建立會議 ID 並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是您的使用者不記得或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="ab664-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="ab664-138">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ab664-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-139">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ab664-140">在 **[音訊會議」** 下，按一下 **[重** 設 PIN 碼，然後按一下 [ **重設**。</span><span class="sxs-lookup"><span data-stu-id="ab664-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="ab664-141">當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ab664-141">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="ab664-142">但如果您已停用自動傳送電子郵件，將不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-142">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="ab664-143">PIN 在重設後只會顯示一次。</span><span class="sxs-lookup"><span data-stu-id="ab664-143">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="ab664-144">在重設後顯示 PIN 之後，PIN 不會再顯示在使用者屬性上;而是會顯示 \*\*\*\* 。</span><span class="sxs-lookup"><span data-stu-id="ab664-144">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="ab664-145">請參閱 [重設音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="ab664-146">傳送包含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="ab664-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="ab664-147">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ab664-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-148">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ab664-149">在 **[音訊會議」** 下，按一下 **[以電子郵件傳送會議資訊。**</span><span class="sxs-lookup"><span data-stu-id="ab664-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="ab664-150">當您這麼做時，音訊會議 PIN 不會發送給使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="ab664-151">請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="ab664-152">設定邀請中包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ab664-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="ab664-153">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ab664-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-154">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="ab664-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ab664-155">在 [ **音訊會議」 旁**，按一下 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="ab664-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="ab664-156">在音訊 **會議窗格中** ，您可以設定付費 **號碼** ，如果允許，也可以設定 **免付費號碼**。</span><span class="sxs-lookup"><span data-stu-id="ab664-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="ab664-157">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ab664-157">Click **Save**.</span></span>
    
<span data-ttu-id="ab664-158">請參閱 [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="ab664-159">選擇音訊會議橋接器設定</span><span class="sxs-lookup"><span data-stu-id="ab664-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="ab664-160">**設定來電者加入會議時的會議體驗**</span><span class="sxs-lookup"><span data-stu-id="ab664-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="ab664-161">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ab664-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-162">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="ab664-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ab664-163">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="ab664-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ab664-164">在橋接器 **設定窗格中** ，啟用或停用 **會議專案及離開通知**。</span><span class="sxs-lookup"><span data-stu-id="ab664-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="ab664-165">此功能預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="ab664-165">This is enabled by default.</span></span> <span data-ttu-id="ab664-166">如果您停用此選項，根據預設，已加入會議的使用者不會在有人進入或離開會議時收到通知。</span><span class="sxs-lookup"><span data-stu-id="ab664-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="ab664-167">在 **進入/離開公告類型下**，選擇 **色調** 或 **名稱或電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="ab664-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="ab664-168">如果您選擇名稱 **或電話號碼**，您也可以選擇啟用或停用要求來電者在加入會議前錄製 **其名稱**。</span><span class="sxs-lookup"><span data-stu-id="ab664-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="ab664-169">根據預設，外部參與者看不到撥入參與者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ab664-169">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="ab664-170">如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。</span><span class="sxs-lookup"><span data-stu-id="ab664-170">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>


5. <span data-ttu-id="ab664-171">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ab664-171">Click **Save**.</span></span>

    
<span data-ttu-id="ab664-172">請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="ab664-173">**設定會議的 PIN 長度**</span><span class="sxs-lookup"><span data-stu-id="ab664-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="ab664-174">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="ab664-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ab664-175">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="ab664-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ab664-176">在 [**橋接器設定>** 窗格中，在 PIN 長度清單中輸入 PIN的位數，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="ab664-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="ab664-177">PIN 必須介於 4 到 12 位數之間。</span><span class="sxs-lookup"><span data-stu-id="ab664-177">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="ab664-178">預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="ab664-178">The default is 5.</span></span>

    
<span data-ttu-id="ab664-179">請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="ab664-180">**啟用或停用電子郵件，禁止將電子郵件發送給音訊使用者**</span><span class="sxs-lookup"><span data-stu-id="ab664-180">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="ab664-181">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="ab664-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ab664-182">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="ab664-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ab664-183">在橋接器 **設定窗格中** ，啟用或停用如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="ab664-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="ab664-184">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ab664-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="ab664-185">您也可以使用音訊會議設定傳送電子郵件給使用者，方法是流覽使用者的音訊會議屬性，然後按一下以電子郵件傳送會議 **資訊**。</span><span class="sxs-lookup"><span data-stu-id="ab664-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="ab664-186">如果您這麼做，將會送出只包含會議 ID 和會議電話號碼的電子郵件，但不包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="ab664-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="ab664-187">請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="ab664-188">在音訊會議橋接器上 (主要) 次要 (次要) 替代語言</span><span class="sxs-lookup"><span data-stu-id="ab664-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="ab664-189">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ab664-189">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-190">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="ab664-190">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ab664-191">從清單中選取電話號碼，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="ab664-191">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="ab664-192">在預設語言和替代語言下選擇您想要的語言 **， (選用) 。**</span><span class="sxs-lookup"><span data-stu-id="ab664-192">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="ab664-193">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ab664-193">Click **Save**.</span></span>


<span data-ttu-id="ab664-194">請參閱 [設定音訊會議的自動語音語音處理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-194">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="ab664-195">請參閱音訊會議電話撥入號碼</span><span class="sxs-lookup"><span data-stu-id="ab664-195">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="ab664-196">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ab664-196">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ab664-197">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="ab664-197">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ab664-198">從清單中選取電話號碼，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="ab664-198">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="ab664-199">您可以在這裡：</span><span class="sxs-lookup"><span data-stu-id="ab664-199">Here you can:</span></span>
    
   - <span data-ttu-id="ab664-200">查看要用於音訊會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ab664-200">View the phone numbers that are to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="ab664-201">查看音訊會議自動語音機會使用的位置和主要語言。</span><span class="sxs-lookup"><span data-stu-id="ab664-201">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="ab664-202">請參閱 [查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ab664-202">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ab664-203">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="ab664-203">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ab664-204">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="ab664-204">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ab664-205">有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="ab664-205">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ab664-206">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="ab664-206">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ab664-207">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab664-207">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="ab664-208">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ab664-208">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="ab664-209">如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ab664-209">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="ab664-210">相關主題</span><span class="sxs-lookup"><span data-stu-id="ab664-210">Related topics</span></span>

[<span data-ttu-id="ab664-211">管理使用者的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="ab664-211">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)