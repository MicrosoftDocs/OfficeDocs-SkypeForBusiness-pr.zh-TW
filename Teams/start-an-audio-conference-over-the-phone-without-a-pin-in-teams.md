---
title: 在 Teams 中在沒有 PIN 的情況下，在電話上啟動音訊會議
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '瞭解如何從 Teams 系統管理中心啟用或停用匿名來電者加入會議。 '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116961"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="4df2c-103">在 Microsoft Teams 中，在沒有 PIN 的情況下，在手機上啟動音訊會議</span><span class="sxs-lookup"><span data-stu-id="4df2c-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="4df2c-104">因為 Microsoft Teams 會議召集人尚未開始會議，因此撥入會議的使用者在會議大廳聆聽音樂可能會感到沮喪。</span><span class="sxs-lookup"><span data-stu-id="4df2c-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="4df2c-105">如果會議召集人預設會來電到會議，則啟動會議時必須輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="4df2c-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="4df2c-106">您可以設定，讓任何人都可以撥入會議，而且不會提示 PIN 開始會議。</span><span class="sxs-lookup"><span data-stu-id="4df2c-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="4df2c-107">您可以使用系統管理中心為單一使用者啟用或停用此設定。</span><span class="sxs-lookup"><span data-stu-id="4df2c-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="4df2c-108">如果有人從 Microsoft Teams 應用程式開始會議，會議召集人不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="4df2c-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="4df2c-109">只有當會議召集人以電話加入其會議時，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="4df2c-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="4df2c-110">當音訊使用者獲得音訊會議授權並啟用音訊會議時，會議 PIN會發送給音訊使用者。</span><span class="sxs-lookup"><span data-stu-id="4df2c-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="4df2c-111">請參閱 [傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) ，其音訊會議資訊和電子郵件會在使用者的音訊會議設定變更時 [自動傳送給使用者](emails-sent-to-users-when-their-settings-change-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4df2c-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="4df2c-112">啟用或停用匿名來電者加入會議</span><span class="sxs-lookup"><span data-stu-id="4df2c-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="4df2c-113">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="4df2c-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4df2c-114">在左側流覽中，按一下 [ **使用者>**。</span><span class="sxs-lookup"><span data-stu-id="4df2c-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="4df2c-115">選取清單中的使用者，然後按一下頁面頂端的 [編輯。</span><span class="sxs-lookup"><span data-stu-id="4df2c-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="4df2c-116">在 [ **音訊會議」 旁**，按一下 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="4df2c-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="4df2c-117">在音訊 **會議窗格中** ，啟用或停用電話撥入 **來電者可以是會議的第一個人**。</span><span class="sxs-lookup"><span data-stu-id="4df2c-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="4df2c-118">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="4df2c-118">Click **Apply**.</span></span> 

<span data-ttu-id="4df2c-119">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4df2c-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="4df2c-120">請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="4df2c-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="4df2c-121">您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="4df2c-121">What else should you know?</span></span>

- <span data-ttu-id="4df2c-122">如果您想要重設 PIN，請參閱重設 [音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4df2c-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="4df2c-123">如果匿名存取或不需要 PIN 來啟動會議，則停用：</span><span class="sxs-lookup"><span data-stu-id="4df2c-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="4df2c-124">如果會議尚未開始 (會議中還沒有人員) ：如果來電者是召集人，系統就會提示來電者;如果表示是，系統會提示他輸入 PIN，而輸入 PIN 之後，會議就會開始，而使用者將加入會議。</span><span class="sxs-lookup"><span data-stu-id="4df2c-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="4df2c-125">如果會議已開始 (其他人已在會議) ：來電者若是會議召集人，系統將不會提示來電者輸入 PIN;會議已開始，來電者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="4df2c-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="4df2c-126">如果已啟用匿名存取，或不需要 PIN 來啟動會議：</span><span class="sxs-lookup"><span data-stu-id="4df2c-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="4df2c-127">如果會議尚未開始 (會議中還沒有人) ：來電者若是召集人，系統將不會提示她，而且永遠不會提示她輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="4df2c-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="4df2c-128">由於召集人的設定設為關閉，會議將會開始，匿名來電者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="4df2c-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="4df2c-129">如果會議已經開始 (其他人已經在會議) ：來電者不會提示她，如果對方是召集人，而且永遠不會提示她輸入 PIN;會議已經啟動，來電者會加入。</span><span class="sxs-lookup"><span data-stu-id="4df2c-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4df2c-130">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="4df2c-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4df2c-131">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="4df2c-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4df2c-132">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="4df2c-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4df2c-133">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="4df2c-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4df2c-134">為什麼您需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4df2c-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="4df2c-135">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4df2c-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="4df2c-136">有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="4df2c-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4df2c-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="4df2c-137">Related topics</span></span>

[<span data-ttu-id="4df2c-138">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="4df2c-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)