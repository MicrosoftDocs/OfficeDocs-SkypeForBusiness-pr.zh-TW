---
title: 在商務用 Skype Online 中，在沒有 PIN 的情況下，在電話上啟動音訊會議
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '瞭解如何啟用或停用匿名來電者從商務用 Skype 系統管理中心加入會議，或是使用 PowerShell 腳本。 '
ms.openlocfilehash: 6eb62e2a2a295644185b3f0e6fd424749dc5bf56
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111939"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="bc005-103">在商務用 Skype Online 中，在沒有 PIN 的情況下，在電話上啟動音訊會議</span><span class="sxs-lookup"><span data-stu-id="bc005-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="bc005-104">有關在 Microsoft Teams 中啟動沒有 PIN 的音訊會議的資訊，請參閱在 Microsoft Teams 中在沒有 PIN 的情況下，在手機上啟動 [音訊會議](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="bc005-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="bc005-105">因為商務用 Skype 會議召集人尚未開始會議，因此撥入會議的使用者在會議大廳聆聽音樂可能會感到沮喪。</span><span class="sxs-lookup"><span data-stu-id="bc005-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="bc005-106">如果會議召集人預設會來電到會議，則啟動會議時必須輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="bc005-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="bc005-107">您可以設定，讓任何人都可以撥入會議，而且不會提示 PIN 開始會議。</span><span class="sxs-lookup"><span data-stu-id="bc005-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="bc005-108">您可以使用商務用 Skype 系統管理中心為單一使用者啟用或停用此設定。</span><span class="sxs-lookup"><span data-stu-id="bc005-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="bc005-109">如果有人從商務用 Skype 應用程式開始會議，會議召集人不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="bc005-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="bc005-110">只有當會議召集人以電話加入其會議時，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="bc005-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="bc005-111">當音訊使用者獲得音訊會議授權並啟用音訊會議時，會議 PIN會發送給音訊使用者。</span><span class="sxs-lookup"><span data-stu-id="bc005-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="bc005-112">請參閱 [傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md) ，其音訊會議資訊和電子郵件會在使用者的音訊會議設定變更時 [自動傳送給使用者](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="bc005-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="bc005-113">啟用或停用匿名來電者加入會議</span><span class="sxs-lookup"><span data-stu-id="bc005-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="bc005-114">在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **使用者**。</span><span class="sxs-lookup"><span data-stu-id="bc005-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="bc005-115">在清單中，選取使用者，然後按一下 [動作窗格 **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="bc005-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="bc005-116">在使用者的屬性頁面上，選取或 **清除會議選項** 下的允許未經驗證的來電 **者成為會議的第一個人。如果沒有，他們會在大廳等候，直到經過驗證的使用者加入**。</span><span class="sxs-lookup"><span data-stu-id="bc005-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="bc005-117">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="bc005-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="bc005-118">**使用 Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="bc005-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="bc005-119">執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bc005-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="bc005-120">您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="bc005-120">What else should you know?</span></span>

- <span data-ttu-id="bc005-121">如果您想要重設 PIN，請參閱重設 [音訊會議 PIN](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="bc005-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="bc005-122">如果匿名存取或不需要 PIN 來啟動會議，則停用：</span><span class="sxs-lookup"><span data-stu-id="bc005-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="bc005-123">如果會議尚未開始 (會議中還沒有人員) ：如果來電者是召集人，系統就會提示來電者;如果表示是，系統會提示他輸入 PIN，而輸入 PIN 之後，會議就會開始，而使用者將加入會議。</span><span class="sxs-lookup"><span data-stu-id="bc005-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="bc005-124">如果會議已開始 (其他人已在會議) ：來電者若是會議召集人，系統將不會提示來電者輸入 PIN;會議已開始，來電者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="bc005-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="bc005-125">如果已啟用匿名存取，或不需要 PIN 來啟動會議：</span><span class="sxs-lookup"><span data-stu-id="bc005-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="bc005-126">如果會議尚未開始 (會議中還沒有人) ：來電者若是召集人，系統將不會提示她，而且永遠不會提示她輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="bc005-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="bc005-127">由於召集人的設定設為關閉，會議將會開始，匿名來電者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="bc005-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="bc005-128">如果會議已經開始 (其他人已經在會議) ：來電者不會提示她，如果對方是召集人，而且永遠不會提示她輸入 PIN;會議已經啟動，來電者會加入。</span><span class="sxs-lookup"><span data-stu-id="bc005-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bc005-129">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="bc005-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bc005-130">若要為多個使用者節省時間或將其自動化，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bc005-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="bc005-131">在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="bc005-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bc005-132">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="bc005-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="bc005-133">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="bc005-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bc005-134">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc005-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="bc005-135">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="bc005-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="bc005-136">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次變更許多使用者的設定時。</span><span class="sxs-lookup"><span data-stu-id="bc005-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="bc005-137">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="bc005-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="bc005-138">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="bc005-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="bc005-139">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="bc005-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="bc005-140">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="bc005-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="bc005-141">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="bc005-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="bc005-142">此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="bc005-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bc005-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="bc005-143">Related topics</span></span>

[<span data-ttu-id="bc005-144">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="bc005-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)