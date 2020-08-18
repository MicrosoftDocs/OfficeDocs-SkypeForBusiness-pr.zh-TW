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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '請參閱 Microsoft 團隊步驟，將電話撥入式會議授權及會議 ID 指派給使用者和許多其他電話撥入式會議設定。 '
ms.openlocfilehash: 8a01be430e8c3993325c5ef6759e520664a21e55
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788767"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="310be-103">在 Microsoft 團隊中管理貴組織的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="310be-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="310be-104">在單一位置查看 Microsoft 團隊的所有音訊會議設定可能會更容易。</span><span class="sxs-lookup"><span data-stu-id="310be-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="310be-105">指派音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="310be-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="310be-106">您無法使用團隊指派授權。</span><span class="sxs-lookup"><span data-stu-id="310be-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="310be-107">您必須使用 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="310be-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="310be-108">請參閱 [指派 Microsoft 團隊附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="310be-108">See [Assign Microsoft Teams add-on licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span> 
  
 <span data-ttu-id="310be-109">**指派使用者的授權**</span><span class="sxs-lookup"><span data-stu-id="310be-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="310be-110">使用您的公司或學校帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="310be-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="310be-111">在**Microsoft 365 系統管理中心**的左導覽中，前往 [**使用者**作用中的  >  **使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="310be-112">如果您要同時指派授權給20個以上的使用者，您可以使用 [ **選取視圖** ] 下拉式清單，然後選擇其中一個選項，或建立您自己的 [視圖]。</span><span class="sxs-lookup"><span data-stu-id="310be-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="310be-113">然後按一下**Edit**[編輯 **]，接著**兩次，選取授權，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="310be-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="310be-114">在 [ **產品授權**] 底下的 [動作] 窗格中，按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="310be-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="310be-115">在 [ **產品授權** ] 頁面上，開啟 [ **音訊會議** ]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="310be-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="310be-116">如需授權的詳細資訊，請參閱 [Microsoft 團隊附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="310be-116">For more on licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="310be-117">指派授權之後，Microsoft 可能不會在清單中以音訊會議提供者的形式開始。</span><span class="sxs-lookup"><span data-stu-id="310be-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="310be-118">如果發生這種情況，請登出系統管理中心，或按 CTRL + F5 重新整理瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="310be-118">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="310be-119">啟用或停用傳送給音訊會議使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="310be-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="310be-120">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="310be-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-121">在左側導覽中，前往 [**會議**  >  **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="310be-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="310be-122">在 [ **會議橋接** ] 頁面頂端，按一下 [ **橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="310be-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="310be-123">在 [ **橋設定** ] 窗格中，如果使用者的撥入設定變更，請啟用或停用 **自動傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="310be-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="310be-124">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="310be-124">Click **Save**.</span></span>

    
<span data-ttu-id="310be-125">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="310be-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="310be-126">如需詳細資訊，請參閱 [Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 。</span><span class="sxs-lookup"><span data-stu-id="310be-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="310be-127">重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="310be-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="310be-128">![](media/teams-logo-30x30.png)**使用 Microsoft [團隊管理中心**] 顯示小組標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="310be-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-129">在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="310be-130">在 [ **音訊會議**] 底下，按一下 [ **重設會議 ID**]。</span><span class="sxs-lookup"><span data-stu-id="310be-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="310be-131">在 [ **重設會議 ID？** ] 視窗中，按一下 [ **重設**]。</span><span class="sxs-lookup"><span data-stu-id="310be-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="310be-132">如果已啟用傳送電子郵件給您的使用者，系統會自動建立會議 ID，並以新的會議 ID 傳送電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="310be-133">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="310be-133">It's enabled by default.</span></span>

<span data-ttu-id="310be-134">請參閱 [重設使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="310be-135">重設會議召集人的 PIN</span><span class="sxs-lookup"><span data-stu-id="310be-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="310be-136">使用者排程的每個會議都會指派唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="310be-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="310be-137">雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或者您的使用者無法記住或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="310be-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="310be-138">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="310be-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-139">在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="310be-140">在 [ **音訊會議**] 底下，按一下 [ **重設 PIN**]，然後按一下 [ **重設**]。</span><span class="sxs-lookup"><span data-stu-id="310be-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="310be-141">當使用者啟用音訊會議或 PIN 重設時，會收到一封電子郵件及其 PIN。</span><span class="sxs-lookup"><span data-stu-id="310be-141">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="310be-142">但如果您已停用自動傳送電子郵件，就不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-142">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="310be-143">PIN 只會在重定後顯示一次。</span><span class="sxs-lookup"><span data-stu-id="310be-143">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="310be-144">在重設之後，PIN 就不會再顯示在使用者屬性上;相反，\* \* \* \* \* 將會顯示。</span><span class="sxs-lookup"><span data-stu-id="310be-144">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="310be-145">請參閱 [重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="310be-146">使用音訊會議資訊傳送電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="310be-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="310be-147">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="310be-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-148">在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="310be-149">在 [ **音訊會議**] 底下，按一下 [ **以電子郵件傳送會議資訊**]。</span><span class="sxs-lookup"><span data-stu-id="310be-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="310be-150">當您這麼做時，音訊會議 PIN 不會傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="310be-151">請參閱 [使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="310be-152">設定邀請中包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="310be-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="310be-153">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="310be-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-154">在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="310be-155">按一下 [ **音訊會議**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="310be-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="310be-156">在 [ **音訊會議** ] 窗格中，您可以設定 **付費電話號碼** ，並在允許的情況下 **撥打免費電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="310be-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="310be-157">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="310be-157">Click **Save**.</span></span>
    
<span data-ttu-id="310be-158">請參閱 [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="310be-159">選擇 [音訊會議橋] 設定</span><span class="sxs-lookup"><span data-stu-id="310be-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="310be-160">**設定呼叫者加入會議時的會議體驗**</span><span class="sxs-lookup"><span data-stu-id="310be-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="310be-161">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="310be-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-162">在左側導覽中，前往 [**會議**  >  **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="310be-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="310be-163">在 [ **會議橋接** ] 頁面頂端，按一下 [ **橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="310be-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="310be-164">在 [ **橋設定** ] 窗格中，啟用或停用 **會議進入和結束通知**。</span><span class="sxs-lookup"><span data-stu-id="310be-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="310be-165">預設會啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="310be-165">This is enabled by default.</span></span> <span data-ttu-id="310be-166">如果您停用此選項，當有人進入或離開會議時，預設已加入會議的使用者將不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="310be-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="310be-167">在 [ **進入/結束宣告類型**] 底下，選擇 [ **聲調** ] 或 [姓名] **或 [電話號碼**]。</span><span class="sxs-lookup"><span data-stu-id="310be-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="310be-168">如果您選擇 [ **名稱] 或 [電話號碼**]，您也可以在加入會議前，選擇要啟用或停用 **要求呼叫者記錄其名稱**。</span><span class="sxs-lookup"><span data-stu-id="310be-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="310be-169">根據預設，外部參與者看不到撥入參與者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="310be-169">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="310be-170">如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型]\*\*\*\* 的 [音調]\*\*\*\* (這可避免 Teams 將號碼朗讀出來)。</span><span class="sxs-lookup"><span data-stu-id="310be-170">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>


5. <span data-ttu-id="310be-171">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="310be-171">Click **Save**.</span></span>

    
<span data-ttu-id="310be-172">請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="310be-173">**設定會議的 PIN 長度**</span><span class="sxs-lookup"><span data-stu-id="310be-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="310be-174">在左側導覽中，前往 [**會議**  >  **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="310be-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="310be-175">在 [ **會議橋接** ] 頁面頂端，按一下 [ **橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="310be-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="310be-176">在 [ **橋接器設定** ] 窗格中，于 [ **pin 長度** ] 清單中輸入您想要的 pin 位數，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="310be-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="310be-177">PIN 必須在4到12位數之間。</span><span class="sxs-lookup"><span data-stu-id="310be-177">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="310be-178">預設值為5。</span><span class="sxs-lookup"><span data-stu-id="310be-178">The default is 5.</span></span>

    
<span data-ttu-id="310be-179">請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="310be-180">**啟用或停用傳送電子郵件給音訊使用者的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="310be-180">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="310be-181">在左側導覽中，前往 [**會議**  >  **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="310be-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="310be-182">在 [ **會議橋接** ] 頁面頂端，按一下 [ **橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="310be-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="310be-183">在橋接器的 [ **設定** ] 窗格中，啟用或停用 [ **自動傳送電子郵件給使用者] （如果他們的音訊會議設定變更**）。</span><span class="sxs-lookup"><span data-stu-id="310be-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="310be-184">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="310be-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="310be-185">您也可以移至使用者的音訊會議屬性，然後按一下 [ **以電子郵件傳送會議資訊**]，透過音訊會議設定傳送電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="310be-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="310be-186">如果您這樣做，就會傳送一封電子郵件，其中只包含會議 ID 和會議電話號碼，但不會包含該 PIN。</span><span class="sxs-lookup"><span data-stu-id="310be-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="310be-187">請參閱 [使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="310be-188">在音訊會議橋中查看和設定主要 (預設) 與次要 (備用) 語言</span><span class="sxs-lookup"><span data-stu-id="310be-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="310be-189">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="310be-189">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-190">在左側導覽中，前往 [**會議**  >  **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="310be-190">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="310be-191">從清單中選取電話號碼，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="310be-191">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="310be-192">在 [ **預設語言** ] 下選擇您想要的語言，並在 [ \*\*替代語言] (選擇性) \*\*。</span><span class="sxs-lookup"><span data-stu-id="310be-192">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="310be-193">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="310be-193">Click **Save**.</span></span>


<span data-ttu-id="310be-194">請參閱 [設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-194">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="310be-195">請參閱音訊會議撥入號碼</span><span class="sxs-lookup"><span data-stu-id="310be-195">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="310be-196">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="310be-196">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="310be-197">在左側導覽中，前往 [**會議**  >  **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="310be-197">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="310be-198">從清單中選取電話號碼，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="310be-198">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="310be-199">您可以在這裡進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="310be-199">Here you can:</span></span>
    
   - <span data-ttu-id="310be-200">查看要用於音訊會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="310be-200">View the phone numbers that are to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="310be-201">查看音訊會議自動語音應答將使用的位置和主要語言。</span><span class="sxs-lookup"><span data-stu-id="310be-201">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="310be-202">請參閱 [音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="310be-202">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="310be-203">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="310be-203">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="310be-204">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="310be-204">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="310be-205">在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="310be-205">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="310be-206">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="310be-206">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="310be-207">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="310be-207">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="310be-208">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="310be-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="310be-209">如需有關 Windows PowerShell 的詳細資訊，請參閱 [Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) ，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="310be-209">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="310be-210">相關主題</span><span class="sxs-lookup"><span data-stu-id="310be-210">Related topics</span></span>

[<span data-ttu-id="310be-211">管理使用者的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="310be-211">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


