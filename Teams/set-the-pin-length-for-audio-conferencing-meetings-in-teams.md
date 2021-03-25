---
title: 設定音訊會議的 PIN 碼長度
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解 PIN 長度和需求的參數，並瞭解如何在 Microsoft Teams 中設定會議長度。
ms.openlocfilehash: 68dc1f3ea5508dc88bc168a5f3fbed837bbee04f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117161"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="ff15b-103">在 Microsoft Teams 中設定音訊會議會議的 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="ff15b-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="ff15b-104">當您為 Microsoft Teams 設定音訊會議時，將會取得音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="ff15b-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="ff15b-105">一個會議橋接器可以包含一或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ff15b-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="ff15b-106">您設定的電話號碼會包含在 Microsoft Teams 應用程式的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="ff15b-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="ff15b-107">音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。</span><span class="sxs-lookup"><span data-stu-id="ff15b-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="ff15b-108">它以自動語音應答的語音提示回答來電者，然後視您的設定播放通知，並要求來電者錄製其名稱。</span><span class="sxs-lookup"><span data-stu-id="ff15b-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="ff15b-109">**Microsoft 橋接器** 設定允許您變更會議通知和會議加入體驗的設定，並設定會議召集人所使用的 PIN 長度。</span><span class="sxs-lookup"><span data-stu-id="ff15b-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="ff15b-110">如果會議召集人無法使用 Microsoft Teams 應用程式加入會議，請使用 PIN 開始會議。</span><span class="sxs-lookup"><span data-stu-id="ff15b-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="ff15b-111">設定 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="ff15b-111">Setting the PIN length</span></span>

<span data-ttu-id="ff15b-112">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ff15b-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ff15b-113">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="ff15b-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ff15b-114">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="ff15b-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="ff15b-115">在橋接器 **設定窗格中** 的 **PIN 長度** 下，選取 PIN 的位數。</span><span class="sxs-lookup"><span data-stu-id="ff15b-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="ff15b-116">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ff15b-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ff15b-117">PIN 與會議 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="ff15b-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="ff15b-118">當來電者加入會議時，會使用會議 ID。</span><span class="sxs-lookup"><span data-stu-id="ff15b-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="ff15b-119">它們是用來識別會議。</span><span class="sxs-lookup"><span data-stu-id="ff15b-119">They are used to identify the meeting.</span></span> <span data-ttu-id="ff15b-120">PIN 是用來驗證來電者為會議召集人。</span><span class="sxs-lookup"><span data-stu-id="ff15b-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="ff15b-121">想要進一瞭解 PIN 設定嗎？</span><span class="sxs-lookup"><span data-stu-id="ff15b-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="ff15b-122">PIN 可以是 4 到 12 位數;預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="ff15b-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="ff15b-123">數位只有在建立 PIN 時才能使用。</span><span class="sxs-lookup"><span data-stu-id="ff15b-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="ff15b-124">不會使用字母和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="ff15b-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="ff15b-125">只有當 Microsoft Teams 使用者尚未開始會議時，會議召集人才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="ff15b-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="ff15b-126">如果每個人都撥入會議，會議召集人必須輸入 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="ff15b-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="ff15b-127">PIN 安全性設定會適用于與 Microsoft 橋接器相關聯的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ff15b-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="ff15b-128">這些將會適用于使用與特定橋接器相關聯的電話號碼的所有會議。</span><span class="sxs-lookup"><span data-stu-id="ff15b-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ff15b-129">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="ff15b-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ff15b-130">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="ff15b-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ff15b-131">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="ff15b-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ff15b-132">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="ff15b-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ff15b-133">為什麼您需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff15b-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="ff15b-134">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ff15b-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="ff15b-135">有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ff15b-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="ff15b-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="ff15b-136">Related topics</span></span>

[<span data-ttu-id="ff15b-137">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="ff15b-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)