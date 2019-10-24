---
title: 在商務用 Skype Online 中不使用 PIN 在手機上啟動音訊會議
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '瞭解如何從商務用 Skype 系統管理中心或使用 PowerShell 腳本，來啟用或停用匿名呼叫者加入會議。 '
ms.openlocfilehash: 1cdcbd2f610c3d60ba2fb4e554823d410fd4ae8f
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642483"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="246a9-103">在商務用 Skype Online 中不使用 PIN 在手機上啟動音訊會議</span><span class="sxs-lookup"><span data-stu-id="246a9-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="246a9-104">如需在 Microsoft 團隊中不使用 PIN 來啟動音訊會議的相關資訊，請參閱透過[沒有 pin 的 Microsoft 團隊在手機上啟動音訊會議](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="246a9-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="246a9-105">因為商務用 Skype 會議召集人尚未開始會議，所以撥入會議的使用者可能會不想要在會議的大廳聆聽音樂中舉行。</span><span class="sxs-lookup"><span data-stu-id="246a9-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="246a9-106">如果會議召集人撥入會議，預設會需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="246a9-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="246a9-107">您可以設定它，讓任何人都能撥入會議，而不會提示您輸入 PIN 以啟動會議。</span><span class="sxs-lookup"><span data-stu-id="246a9-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="246a9-108">您可以使用商務用 Skype 系統管理中心來針對單一使用者啟用或停用此設定。</span><span class="sxs-lookup"><span data-stu-id="246a9-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="246a9-109">如果某人從商務用 Skype app 開始會議，則會議召集人不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="246a9-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="246a9-110">只有在會議召集人在手機上加入會議時，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="246a9-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="246a9-111">當使用者指派**音訊會議**授權，且已啟用音訊會議時，會議的 PIN 會傳送給音訊使用者。</span><span class="sxs-lookup"><span data-stu-id="246a9-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="246a9-112">請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)，以及[在其音訊會議設定變更時自動傳送給使用者的電子](emails-sent-to-users-when-their-settings-change.md)郵件。</span><span class="sxs-lookup"><span data-stu-id="246a9-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="246a9-113">啟用或停用匿名呼叫者加入會議</span><span class="sxs-lookup"><span data-stu-id="246a9-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="246a9-114">在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議** > **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="246a9-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="246a9-115">在清單中，選取使用者，然後在 [動作] 窗格中，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="246a9-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="246a9-116">在使用者的 [屬性] 頁面的 [**會議選項**] 底下，選取或清除 [**允許未驗證的呼叫者成為會議中的第一位人員]。如果不是，則會在大廳等候，直到經過驗證的使用者加入為止**。</span><span class="sxs-lookup"><span data-stu-id="246a9-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="246a9-117">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="246a9-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="246a9-118">**使用 Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="246a9-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="246a9-119">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="246a9-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="246a9-120">您還應該知道什麼？</span><span class="sxs-lookup"><span data-stu-id="246a9-120">What else should you know?</span></span>

- <span data-ttu-id="246a9-121">如果您想要重設 PIN，請參閱[重設音訊會議 PIN](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="246a9-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="246a9-122">如果您使用匿名存取，或不需要 PIN 即可開始會議，則會停用：</span><span class="sxs-lookup"><span data-stu-id="246a9-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="246a9-123">如果會議尚未開始（在會議中還沒有任何人）：如果您是召集人，系統會提示來電者;如果他說是，系統會提示您輸入 PIN，然後在輸入 PIN 之後，會議就會開始，且使用者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="246a9-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="246a9-124">如果會議已開始（其他人已在會議中）：如果他是召集人，則不會提示來電者，且系統不會提示您輸入 PIN;會議已啟動，且呼叫者會加入該會議。</span><span class="sxs-lookup"><span data-stu-id="246a9-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="246a9-125">如果啟用匿名存取，或不需要 PIN 即可開始會議，則會啟用：</span><span class="sxs-lookup"><span data-stu-id="246a9-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="246a9-126">如果會議尚未開始（在會議中還沒有任何人）：如果她是召集人，系統不會提示來電者，而且系統不會提示您輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="246a9-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="246a9-127">因為召集人的設定設為 [關閉]，所以會議會啟動，而匿名呼叫者將會加入會議。</span><span class="sxs-lookup"><span data-stu-id="246a9-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="246a9-128">如果會議已開始（其他人已在會議中）：如果她是召集人，系統不會提示來電者，而她將不會收到 PIN 提示; 會議已開始，且呼叫者會加入該會議。</span><span class="sxs-lookup"><span data-stu-id="246a9-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="246a9-129">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="246a9-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="246a9-130">若要節省時間或將這項作業自動化給一個以上的使用者，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="246a9-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="246a9-131">在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者以及允許或不允許的使用者。</span><span class="sxs-lookup"><span data-stu-id="246a9-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="246a9-132">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="246a9-132">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="246a9-133">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="246a9-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="246a9-134">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="246a9-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="246a9-135">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="246a9-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="246a9-136">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="246a9-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="246a9-137">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="246a9-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="246a9-138">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="246a9-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="246a9-139">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="246a9-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="246a9-140">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="246a9-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="246a9-141">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="246a9-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="246a9-142">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="246a9-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="246a9-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="246a9-143">Related topics</span></span>

[<span data-ttu-id="246a9-144">在 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="246a9-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
