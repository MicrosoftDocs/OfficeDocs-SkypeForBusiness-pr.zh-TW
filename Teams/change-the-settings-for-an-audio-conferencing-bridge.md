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
description: 變更音訊會議橋接器設定，包括進入和離開通知、播放名稱或電話號碼、鈴聲，以及提示來電者錄製其名稱。
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102639"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="77e64-103">變更音訊會議橋接器的設定</span><span class="sxs-lookup"><span data-stu-id="77e64-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="77e64-104">當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到來自所謂的音訊會議橋接器的使用者電話號碼。</span><span class="sxs-lookup"><span data-stu-id="77e64-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="77e64-105">一個會議橋接器可以包含一或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="77e64-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="77e64-106">當來電者撥入會議時，會使用這些電話號碼。</span><span class="sxs-lookup"><span data-stu-id="77e64-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="77e64-107">電話號碼會包含在會議邀請或商務用 Skype Microsoft Teams底端。</span><span class="sxs-lookup"><span data-stu-id="77e64-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="77e64-108">會議橋接器會接聽來電，然後使用會議自動語音應答提示來電者，然後視您的設定播放通知、要求來電者錄製名稱，以及控制 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="77e64-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="77e64-109">PIN 會提供給會議召集人，讓他們在未使用應用程式或應用程式商務用 Skype Microsoft Teams會議。</span><span class="sxs-lookup"><span data-stu-id="77e64-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="77e64-110">只有在應用程式使用者尚未啟動會議商務用 Skype或Microsoft Teams，會議召集人才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="77e64-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="77e64-111">如果每個人都撥入會議，會議召集人必須輸入 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="77e64-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) <span data-ttu-id="77e64-113">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="77e64-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="77e64-114">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="77e64-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="77e64-115">在 [會議橋接器」 **頁面頂端** ，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="77e64-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="77e64-116">在橋接器 **設定窗格中** ，選取：</span><span class="sxs-lookup"><span data-stu-id="77e64-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="77e64-117">**會議進入和離開通知** 如果您關閉此功能，當某人進入或離開會議時，已加入會議的使用者不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="77e64-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="77e64-118">當您開啟會議 **專案並離開通知** 時，您可以選取這些選項：</span><span class="sxs-lookup"><span data-stu-id="77e64-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="77e64-119">**名稱或電話號碼** 當使用者撥入會議時，當他們加入會議時，就會播放其電話號碼。</span><span class="sxs-lookup"><span data-stu-id="77e64-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="77e64-120">**色調** 當使用者撥入會議時，當他們加入會議時，會播放音訊鈴聲。</span><span class="sxs-lookup"><span data-stu-id="77e64-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="77e64-121">**要求來電者在加入會議前先錄製他們的名稱** 如果您關閉此功能，不會要求來電者在加入會議之前先記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="77e64-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="77e64-122">若要設定會議的 PIN 長度，請在 PIN 長度清單中選取 PIN **的位數** 。</span><span class="sxs-lookup"><span data-stu-id="77e64-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="77e64-123">若要指定是否要傳送電子郵件給使用者，請啟用或停用如果使用者的音訊會議組組變更時自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="77e64-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="77e64-124">請參閱[當使用者](emails-sent-to-users-when-their-settings-change-in-teams.md)的音訊會議設定在 Microsoft Teams 中變更時自動發送給使用者的電子郵件，或當使用者在 商務用 Skype [Online 中變更其設定時商務用 Skype電子郵件](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)。</span><span class="sxs-lookup"><span data-stu-id="77e64-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="77e64-125">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="77e64-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="77e64-126">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="77e64-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="77e64-127">若要節省時間或自動化此程式，您可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77e64-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="77e64-128">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="77e64-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="77e64-129">有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="77e64-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="77e64-130">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="77e64-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77e64-131">為什麼您需要使用 PowerShell Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e64-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="77e64-132">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="77e64-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="77e64-133">Windows PowerShell比使用 Microsoft 365 系統管理中心時，在速度、簡易性及生產力方面有許多優點，例如一次對許多使用者進行設定變更。</span><span class="sxs-lookup"><span data-stu-id="77e64-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="77e64-134">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="77e64-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="77e64-135">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="77e64-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="77e64-136">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="77e64-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="77e64-137">使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="77e64-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="77e64-138">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。</span><span class="sxs-lookup"><span data-stu-id="77e64-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="77e64-139">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="77e64-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="77e64-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="77e64-140">Related topics</span></span>

[<span data-ttu-id="77e64-141">設定 Microsoft Teams 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="77e64-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="77e64-142">設定線上商務用 Skype會議</span><span class="sxs-lookup"><span data-stu-id="77e64-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)