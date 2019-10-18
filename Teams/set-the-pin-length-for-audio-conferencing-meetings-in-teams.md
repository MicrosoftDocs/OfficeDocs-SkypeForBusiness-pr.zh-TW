---
title: 在 Microsoft 團隊中設定音訊會議會議的 PIN 長度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 瞭解 PIN 長度與需求的參數，並瞭解如何在 Microsoft 團隊中設定會議的長度。
ms.openlocfilehash: 50c6ffe31e673dc7573ebb27f0eeb2ca78a30918
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571268"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="171a4-103">在 Microsoft 團隊中設定音訊會議會議的 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="171a4-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="171a4-104">當您為 Microsoft 團隊設定音訊會議時，您將會收到音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="171a4-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="171a4-105">[會議橋] 可以包含一或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="171a4-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="171a4-106">您所設定的電話號碼將會包含在 Microsoft 團隊 app 的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="171a4-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="171a4-107">[音訊會議橋接] 會針對使用電話撥入會議的人員接聽來電。</span><span class="sxs-lookup"><span data-stu-id="171a4-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="171a4-108">它會從自動語音應答中向來電者提供語音提示，然後視您的設定而定，您可以播放通知並要求呼叫者記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="171a4-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="171a4-109">**Microsoft bridge 設定**可讓您變更會議通知與會議加入體驗的設定，以及設定會議召集人所使用的 pin 長度。</span><span class="sxs-lookup"><span data-stu-id="171a4-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="171a4-110">如果會議召集人無法使用 Microsoft 團隊 app 加入會議，請使用 Pin 來啟動會議。</span><span class="sxs-lookup"><span data-stu-id="171a4-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="171a4-111">設定 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="171a4-111">Setting the PIN length</span></span>

<span data-ttu-id="171a4-112">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="171a4-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="171a4-113">在左側導覽中，前往 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="171a4-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="171a4-114">在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="171a4-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="171a4-115">在 [**橋接器設定**] 窗格的 [ **PIN 長度**] 底下，選取您想要的 PIN 數位位數。</span><span class="sxs-lookup"><span data-stu-id="171a4-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="171a4-116">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="171a4-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="171a4-117">PIN 與會議 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="171a4-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="171a4-118">呼叫者加入會議時，會使用會議 Id。</span><span class="sxs-lookup"><span data-stu-id="171a4-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="171a4-119">它們可用來識別會議。</span><span class="sxs-lookup"><span data-stu-id="171a4-119">They are used to identify the meeting.</span></span> <span data-ttu-id="171a4-120">PIN 是用來將來電者驗證為會議召集人。</span><span class="sxs-lookup"><span data-stu-id="171a4-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="171a4-121">想要進一步瞭解 PIN 設定嗎？</span><span class="sxs-lookup"><span data-stu-id="171a4-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="171a4-122">Pin 可能是4到12位數;預設值為5。</span><span class="sxs-lookup"><span data-stu-id="171a4-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="171a4-123">只有在建立 Pin 時才會使用數位。</span><span class="sxs-lookup"><span data-stu-id="171a4-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="171a4-124">不會使用字母和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="171a4-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="171a4-125">只有在 Microsoft 團隊使用者尚未開始會議時，會議召集人才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="171a4-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="171a4-126">如果每個人都要撥入會議，會議召集人需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="171a4-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="171a4-127">PIN 安全設定會套用到與 Microsoft 橋接器相關聯的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="171a4-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="171a4-128">它們會套用至所有使用與指定的橋接器相關聯之電話號碼的會議。</span><span class="sxs-lookup"><span data-stu-id="171a4-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="171a4-129">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="171a4-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="171a4-130">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="171a4-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="171a4-131">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="171a4-131">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="171a4-132">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="171a4-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="171a4-133">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="171a4-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="171a4-134">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="171a4-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="171a4-135">如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="171a4-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="171a4-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="171a4-136">Related topics</span></span>

[<span data-ttu-id="171a4-137">在 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="171a4-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
