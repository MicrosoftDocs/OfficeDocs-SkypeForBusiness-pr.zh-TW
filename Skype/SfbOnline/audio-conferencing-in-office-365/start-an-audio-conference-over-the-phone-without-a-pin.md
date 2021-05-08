---
title: 在線上啟動沒有 PIN 的商務用 Skype會議
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
description: '瞭解如何啟用或停用匿名來電者從系統管理中心商務用 Skype使用 PowerShell 腳本加入會議。 '
ms.openlocfilehash: 655f61c449554a9044095a5b8ef8bd8ef2940bc4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237589"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="5fb4a-103">在線上啟動沒有 PIN 的商務用 Skype會議</span><span class="sxs-lookup"><span data-stu-id="5fb4a-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="5fb4a-104">有關在沒有 PIN 的情況下Microsoft Teams音訊會議的資訊，請參閱在 Microsoft Teams 中在沒有 PIN 的情況下[，在手機上Microsoft Teams。](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)</span><span class="sxs-lookup"><span data-stu-id="5fb4a-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="5fb4a-105">撥入會議的使用者在會議大廳中聆聽音樂可能會令人感到沮喪，因為會議商務用 Skype尚未開始會議。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="5fb4a-106">如果會議召集人預設會來電到會議，則啟動會議時必須輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="5fb4a-107">您可以設定，讓任何人都可以撥入會議，而且不會提示 PIN 開始會議。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="5fb4a-108">您可以使用系統管理商務用 Skype，為單一使用者啟用或停用此設定。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="5fb4a-109">如果有人從應用程式啟動會議，會議召集人不需要 PIN 商務用 Skype PIN。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="5fb4a-110">只有當會議召集人以電話加入其會議時，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="5fb4a-111">當音訊使用者獲得音訊會議授權並啟用音訊會議時，會議 PIN會發送給音訊使用者。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="5fb4a-112">請參閱 [傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md) ，其音訊會議資訊和電子郵件會在使用者的音訊會議設定變更時 [自動傳送給使用者](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="5fb4a-113">啟用或停用匿名來電者加入會議</span><span class="sxs-lookup"><span data-stu-id="5fb4a-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="5fb4a-114">在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議**  >  **使用者**。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="5fb4a-115">在清單中，選取使用者，然後按一下 [動作窗格 **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="5fb4a-116">在使用者的屬性頁面上， **選取或清除** 會議選項下的允許未經驗證的來電 **者成為會議的第一個人。如果沒有，則他們會在大廳等候，直到經過驗證的使用者加入**。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="5fb4a-117">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="5fb4a-118">**使用 Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="5fb4a-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="5fb4a-119">執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5fb4a-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="5fb4a-120">您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="5fb4a-120">What else should you know?</span></span>

- <span data-ttu-id="5fb4a-121">如果您想要重設 PIN，請參閱重設 [音訊會議 PIN](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="5fb4a-122">如果匿名存取或不需要 PIN 來啟動會議，則停用：</span><span class="sxs-lookup"><span data-stu-id="5fb4a-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="5fb4a-123">如果會議尚未開始 (會議中還沒有人員) ：如果來電者是召集人，系統就會提示來電者;如果表示是，系統會提示他輸入 PIN，而輸入 PIN 之後，會議就會開始，而使用者將加入會議。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="5fb4a-124">如果會議已經開始 (其他人已在會議) ：來電者若是會議召集人，系統將不會提示來電者輸入 PIN;會議已開始，來電者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="5fb4a-125">如果已啟用匿名存取，或不需要 PIN 來啟動會議：</span><span class="sxs-lookup"><span data-stu-id="5fb4a-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="5fb4a-126">如果會議尚未開始 (會議中還沒有人) ：來電者若是召集人，系統將不會提示她，而且永遠不會提示她輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="5fb4a-127">由於召集人的設定設為關閉，會議將會開始，匿名來電者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="5fb4a-128">如果會議已開始 (其他人已經在會議) ：來電者不會提示她成為召集人，而且永遠不會提示她輸入 PIN;會議已經啟動，來電者會加入。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5fb4a-129">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="5fb4a-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5fb4a-130">若要為多個使用者節省時間或將其自動化，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="5fb4a-131">當涉及Windows PowerShell商務用 Skype，商務用 Skype是管理使用者，以及使用者允許或不允許執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5fb4a-132">您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5fb4a-133">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="5fb4a-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5fb4a-134">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fb4a-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="5fb4a-135">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5fb4a-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="5fb4a-136">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如一次變更許多使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="5fb4a-137">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="5fb4a-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5fb4a-138">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="5fb4a-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="5fb4a-139">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5fb4a-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5fb4a-140">使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="5fb4a-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="5fb4a-141">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。</span><span class="sxs-lookup"><span data-stu-id="5fb4a-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="5fb4a-142">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="5fb4a-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5fb4a-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="5fb4a-143">Related topics</span></span>

[<span data-ttu-id="5fb4a-144">嘗試或購買音訊會議Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="5fb4a-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
