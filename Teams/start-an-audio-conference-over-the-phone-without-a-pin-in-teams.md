---
title: 在沒有 Microsoft 團隊中的 PIN 的情況下，透過電話啟動音訊會議
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
description: '瞭解如何啟用或停用匿名呼叫者從 [小組] 管理中心加入會議。 '
ms.openlocfilehash: 87588bc8edfcc4d50b5589339f92f56829ec38ef
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837913"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="8a737-103">在沒有 Microsoft 團隊中的 PIN 的情況下，透過電話啟動音訊會議</span><span class="sxs-lookup"><span data-stu-id="8a737-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="8a737-104">因為 Microsoft 團隊會議召集人還沒有啟動會議，所以撥入會議的使用者可能會不想要在會議的大廳聆聽音樂中舉行。</span><span class="sxs-lookup"><span data-stu-id="8a737-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="8a737-105">如果會議召集人撥入會議，預設會需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="8a737-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="8a737-106">您可以設定它，讓任何人都能撥入會議，而不會提示您輸入 PIN 以啟動會議。</span><span class="sxs-lookup"><span data-stu-id="8a737-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="8a737-107">您可以使用系統管理中心來針對單一使用者啟用或停用此設定。</span><span class="sxs-lookup"><span data-stu-id="8a737-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="8a737-108">如果某人從 Microsoft 團隊 app 開始會議，則會議召集人不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="8a737-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="8a737-109">只有在會議召集人在手機上加入會議時，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="8a737-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="8a737-110">當使用者指派**音訊會議**授權，且已啟用音訊會議時，會議的 PIN 會傳送給音訊使用者。</span><span class="sxs-lookup"><span data-stu-id="8a737-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="8a737-111">請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)，以及[在其音訊會議設定變更時自動傳送給使用者的電子](emails-sent-to-users-when-their-settings-change-in-teams.md)郵件。</span><span class="sxs-lookup"><span data-stu-id="8a737-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="8a737-112">啟用或停用匿名呼叫者加入會議</span><span class="sxs-lookup"><span data-stu-id="8a737-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="8a737-113">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="8a737-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8a737-114">在左側導覽中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="8a737-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="8a737-115">在清單中選取使用者，然後按一下頁面頂端的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="8a737-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="8a737-116">按一下 [**音訊會議**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="8a737-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="8a737-117">在 [**音訊會議**] 窗格中，啟用或停**用撥入呼叫者可以是會議中的第一個人員**。</span><span class="sxs-lookup"><span data-stu-id="8a737-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="8a737-118">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="8a737-118">Click **Apply**.</span></span> 

<span data-ttu-id="8a737-119">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8a737-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="8a737-120">如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="8a737-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="8a737-121">您還應該知道什麼？</span><span class="sxs-lookup"><span data-stu-id="8a737-121">What else should you know?</span></span>

- <span data-ttu-id="8a737-122">如果您想要重設 PIN，請參閱[重設音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8a737-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="8a737-123">如果您使用匿名存取，或不需要 PIN 即可開始會議，則會停用：</span><span class="sxs-lookup"><span data-stu-id="8a737-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="8a737-124">如果會議尚未開始（在會議中還沒有任何人）：如果您是召集人，系統會提示來電者;如果他說是，系統會提示您輸入 PIN，然後在輸入 PIN 之後，會議就會開始，且使用者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="8a737-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="8a737-125">如果會議已開始（其他人已在會議中）：如果他是召集人，則不會提示來電者，且系統不會提示您輸入 PIN;會議已啟動，且呼叫者會加入該會議。</span><span class="sxs-lookup"><span data-stu-id="8a737-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="8a737-126">如果啟用匿名存取，或不需要 PIN 即可開始會議，則會啟用：</span><span class="sxs-lookup"><span data-stu-id="8a737-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="8a737-127">如果會議尚未開始（在會議中還沒有任何人）：如果她是召集人，系統不會提示來電者，而且系統不會提示您輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="8a737-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="8a737-128">因為召集人的設定設為 [關閉]，所以會議會啟動，而匿名呼叫者將會加入會議。</span><span class="sxs-lookup"><span data-stu-id="8a737-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="8a737-129">如果會議已開始（其他人已在會議中）：如果她是召集人，系統不會提示來電者，而她將不會收到 PIN 提示; 會議已開始，且呼叫者會加入該會議。</span><span class="sxs-lookup"><span data-stu-id="8a737-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8a737-130">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="8a737-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="8a737-131">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="8a737-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8a737-132">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="8a737-132">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8a737-133">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="8a737-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8a737-134">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a737-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8a737-135">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="8a737-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8a737-136">如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8a737-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8a737-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="8a737-137">Related topics</span></span>

[<span data-ttu-id="8a737-138">試用或購買 Office 365 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="8a737-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
