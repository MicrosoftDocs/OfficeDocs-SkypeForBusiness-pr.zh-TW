---
title: 變更音訊會議橋接器的設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 變更音訊會議橋設定，包括進入與結束通知、播放姓名或電話號碼、鈴聲，以及提示來電者記下其名稱。
ms.openlocfilehash: 48028ccb3f2a0664f9fa724ec91e1dfc0177326f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780342"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="52c24-103">變更音訊會議橋接器的設定</span><span class="sxs-lookup"><span data-stu-id="52c24-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="52c24-104">當您在 Office 365 中設定音訊會議時，您將會收到「音訊會議橋」的電話號碼供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="52c24-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="52c24-105">一個會議橋接器可以包含一或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="52c24-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="52c24-106">當來電者撥入會議時，會用到這些電話號碼。</span><span class="sxs-lookup"><span data-stu-id="52c24-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="52c24-107">電話號碼包含在商務用 Skype 或 Microsoft 團隊會議邀請的底部。</span><span class="sxs-lookup"><span data-stu-id="52c24-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="52c24-108">[會議橋接] 會使用會議自動語音應答接聽來電，並使用語音提示提示來電者，然後根據您的設定，您可以播放通知、要求呼叫者記錄其名稱，以及控制 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="52c24-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="52c24-109">當使用者不是使用商務用 Skype 或 Microsoft 團隊 app 時，會為會議召集人提供 Pin，讓他們可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="52c24-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="52c24-110">只有在商務用 Skype 或 Microsoft 團隊 app 使用者尚未開始會議時，會議召集人才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="52c24-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="52c24-111">如果每個人都要撥入會議，會議召集人需要 PIN 才能啟動會議。</span><span class="sxs-lookup"><span data-stu-id="52c24-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) <span data-ttu-id="52c24-113">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="52c24-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="52c24-114">在左側導覽中，前往 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="52c24-115">在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="52c24-116">在 [**橋接器設定**] 窗格中，選取：</span><span class="sxs-lookup"><span data-stu-id="52c24-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="52c24-117">**會議進入與結束通知**如果您關閉此功能，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="52c24-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="52c24-118">當您開啟**會議進入和結束通知**時，您可以選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="52c24-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="52c24-119">**姓名或電話號碼**當使用者撥入會議時，系統會在他們加入會議時播放他們的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="52c24-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="52c24-120">**聲音**當使用者撥入會議時，會在他們加入會議時播放音訊音調。</span><span class="sxs-lookup"><span data-stu-id="52c24-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="52c24-121">**要求呼叫者在加入會議前記錄他們的名稱**如果您關閉此功能，不會要求來電者在加入會議前記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="52c24-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="52c24-122">若要設定會議的 PIN 長度，請在 [ **pin 長度**] 清單中，選取您想要的 pin 數位位數。</span><span class="sxs-lookup"><span data-stu-id="52c24-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="52c24-123">若要指定是否要傳送電子郵件給使用者，請啟用或停用 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定變更**）。</span><span class="sxs-lookup"><span data-stu-id="52c24-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="52c24-124">當[電子郵件的音訊會議設定在](emails-sent-to-users-when-their-settings-change-in-teams.md)[商務用 Skype Online 中的設定變更時](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，請參閱自動傳送給使用者的電子郵件，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="52c24-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="52c24-125">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52c24-125">Click **Save**.</span></span> 


## <a name="an-icon-showing-the-skype-for-business-logo--using-the-skype-for-business-admin-center"></a>![顯示商務用 Skype 標誌的圖示](media/sfb-logo-30x30.png)  <span data-ttu-id="52c24-127">使用商務用 Skype 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="52c24-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="52c24-128">**設定呼叫者加入會議時的會議體驗**</span><span class="sxs-lookup"><span data-stu-id="52c24-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="52c24-129">在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="52c24-130">在 [ **Microsoft 橋接器設定**] 頁面的 [**會議加入體驗**] 底下，選取：</span><span class="sxs-lookup"><span data-stu-id="52c24-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="52c24-131">[**啟用會議專案] 和 [結束通知] 以開啟**預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="52c24-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="52c24-132">如果您清除該核取方塊，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="52c24-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="52c24-133">當您選取 [**啟用會議進入] 和**[結束通知] 時，您可以從 [**進入/** 結束通知類型] 清單中選取這些選項：</span><span class="sxs-lookup"><span data-stu-id="52c24-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="52c24-134">**姓名或電話號碼**當使用者撥入會議時，系統會在他們加入會議時播放他們的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="52c24-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="52c24-135">**聲音**當使用者撥入會議時，會在他們加入會議時播放音訊音調。</span><span class="sxs-lookup"><span data-stu-id="52c24-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="52c24-136">**要求呼叫者在加入會議前記錄他們的名稱**預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="52c24-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="52c24-137">如果您清除該核取方塊，則不會要求呼叫者在加入會議前記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="52c24-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="52c24-138">進行變更之後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="52c24-139">**設定會議的 PIN 長度**</span><span class="sxs-lookup"><span data-stu-id="52c24-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="52c24-140">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="52c24-140">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="52c24-141">移至**Microsoft 365 管理中心** > **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="52c24-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="52c24-142">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="52c24-143">在 [ **Microsoft 橋接器設定**] 頁面的 [**安全性**] 底下，于 [ **pin 長度**] 清單中輸入您想要的 pin 數位位數，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="52c24-144">PIN 必須在4到12位數之間。</span><span class="sxs-lookup"><span data-stu-id="52c24-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="52c24-145">**選取是否要傳送電子郵件給您的使用者**</span><span class="sxs-lookup"><span data-stu-id="52c24-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="52c24-146">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="52c24-146">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="52c24-147">移至**Microsoft 365 管理中心** > **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="52c24-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="52c24-148">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="52c24-149">在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**如果使用者的撥入資訊變更，則自動傳送電子郵件給使用者**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="52c24-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="52c24-150">當[電子郵件的音訊會議設定在](emails-sent-to-users-when-their-settings-change-in-teams.md)[商務用 Skype Online 中的設定變更時](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，請參閱自動傳送給使用者的電子郵件，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="52c24-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="52c24-151">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="52c24-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="52c24-152">若要節省時間或自動執行此程式，您可以使用[CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="52c24-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="52c24-153">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="52c24-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="52c24-154">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="52c24-154">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="52c24-155">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="52c24-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="52c24-156">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="52c24-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="52c24-157">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="52c24-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="52c24-158">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="52c24-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="52c24-159">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="52c24-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="52c24-160">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="52c24-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="52c24-161">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="52c24-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="52c24-162">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="52c24-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="52c24-163">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="52c24-163">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="52c24-164">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="52c24-164">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="52c24-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="52c24-165">Related topics</span></span>

[<span data-ttu-id="52c24-166">設定 Microsoft Teams 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="52c24-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="52c24-167">在商務用 Skype Online 中設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="52c24-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
