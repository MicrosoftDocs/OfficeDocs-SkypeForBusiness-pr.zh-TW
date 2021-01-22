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
description: 變更音訊會議橋接器設定，包括進入與離開通知、播放名稱或電話號碼、鈴聲，以及提示來電者錄下他們的名稱。
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918699"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="db49e-103">變更音訊會議橋接器的設定</span><span class="sxs-lookup"><span data-stu-id="db49e-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="db49e-104">當您在 Microsoft 365 或 Office 365 中設定音訊會議時，會從所謂的音訊會議橋接器收到使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="db49e-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="db49e-105">一個會議橋接器可以包含一或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="db49e-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="db49e-106">這些電話號碼在來電者撥入會議時會使用。</span><span class="sxs-lookup"><span data-stu-id="db49e-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="db49e-107">電話號碼會包含在商務用 Skype 或 Microsoft Teams 會議邀請的底部。</span><span class="sxs-lookup"><span data-stu-id="db49e-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="db49e-108">會議橋接器會以會議自動語音應答的語音提示接聽來電並提示來電者，然後視您的設定來播放通知、要求來電者錄下他們的名稱，以及控制 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="db49e-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="db49e-109">當 PIN 不在使用商務用 Skype 或 Microsoft Teams 應用程式時，會提供給會議召集人，讓他們開始會議。</span><span class="sxs-lookup"><span data-stu-id="db49e-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="db49e-110">只有當商務用 Skype 或 Microsoft Teams 應用程式使用者尚未開始會議時，會議召集人才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="db49e-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="db49e-111">如果每個人都撥入會議，會議召集人需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="db49e-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) <span data-ttu-id="db49e-113">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="db49e-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="db49e-114">在左側流覽區中，前往 **會議**  >  **橋接器**。</span><span class="sxs-lookup"><span data-stu-id="db49e-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="db49e-115">在會議橋接器頁面 **頂端** ，按一下 [ **橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="db49e-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="db49e-116">在橋接器 **設定窗格中** ，選取：</span><span class="sxs-lookup"><span data-stu-id="db49e-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="db49e-117">**會議進入與離開通知** 如果您關閉此功能，已加入會議的使用者就不會在有人進入或離開會議時收到通知。</span><span class="sxs-lookup"><span data-stu-id="db49e-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="db49e-118">當您開啟會議進入 **與離開通知時**，您可以選取這些選項：</span><span class="sxs-lookup"><span data-stu-id="db49e-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="db49e-119">**名稱或電話號碼** 當使用者撥入會議時，就會在加入會議時播放其電話號碼。</span><span class="sxs-lookup"><span data-stu-id="db49e-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="db49e-120">**鈴聲** 當使用者撥入會議時，當他們加入會議時，會播放音訊鈴聲。</span><span class="sxs-lookup"><span data-stu-id="db49e-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="db49e-121">**要求來電者在加入會議前記錄他們的名稱** 如果您關閉此功能，系統就不會要求來電者在加入會議前記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="db49e-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="db49e-122">若要設定會議的 PIN 長度，請在 PIN 長度清單中選取 PIN 的 **位數** 。</span><span class="sxs-lookup"><span data-stu-id="db49e-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="db49e-123">若要指定是否要傳送電子郵件給使用者，請啟用或停用當使用者的音訊會議組式變更時自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="db49e-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="db49e-124">請參閱 [當使用者在 Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) 中的音訊會議設定變更時自動將電子郵件發送給使用者，或當使用者在商務用 [Skype Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 中的設定變更時，將電子郵件發送給使用者，以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="db49e-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="db49e-125">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="db49e-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="db49e-126">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="db49e-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="db49e-127">若要節省時間或將這項程式自動化，您可以使用 [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="db49e-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="db49e-128">Windows PowerShell 的用場就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="db49e-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="db49e-129">使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。</span><span class="sxs-lookup"><span data-stu-id="db49e-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="db49e-130">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="db49e-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="db49e-131">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="db49e-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="db49e-132">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="db49e-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="db49e-133">Windows PowerShell 在速度、簡化及生產力方面有許多優點，是僅用 Microsoft 365 系統管理中心所沒有的，例如當您要一次為許多使用者變更設定時。</span><span class="sxs-lookup"><span data-stu-id="db49e-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="db49e-134">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="db49e-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="db49e-135">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="db49e-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="db49e-136">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="db49e-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="db49e-137">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="db49e-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="db49e-138">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="db49e-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="db49e-139">此模組僅支援 64 位的電腦，可從商務用 Skype Online 的 Windows PowerShell 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="db49e-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="db49e-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="db49e-140">Related topics</span></span>

[<span data-ttu-id="db49e-141">設定 Microsoft Teams 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="db49e-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="db49e-142">設定商務用 Skype Online 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="db49e-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
