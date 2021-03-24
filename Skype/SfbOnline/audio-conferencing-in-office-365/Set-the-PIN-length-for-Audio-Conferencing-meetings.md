---
title: 在商務用 Skype Online 中設定音訊會議會議的 PIN 長度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: 瞭解 PIN 長度和需求的參數，並瞭解如何在商務用 Skype 中設定會議長度。
ms.openlocfilehash: a2acaad15712621c33b275e914263f6781178d9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100789"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="96914-103">在商務用 Skype Online 中設定音訊會議會議的 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="96914-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="96914-104">有關在 Microsoft Teams 中設定 PIN 長度的資訊，請參閱在 Microsoft Teams 中設定音訊會議會議的 [PIN 長度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="96914-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="96914-105">當您為商務用 Skype 設定音訊會議時，您將獲得音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="96914-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="96914-106">一個會議橋接器可以包含一或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="96914-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="96914-107">您設定的電話號碼會包含在商務用 Skype 應用程式的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="96914-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="96914-108">音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。</span><span class="sxs-lookup"><span data-stu-id="96914-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="96914-109">它會使用自動語音應答的語音提示來接聽來電者，然後視您的設定播放通知，並要求來電者錄製其名稱。</span><span class="sxs-lookup"><span data-stu-id="96914-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="96914-110">**Microsoft 橋接器** 設定允許您變更會議通知和會議加入體驗的設定，並設定會議召集人所使用的 PIN 長度。</span><span class="sxs-lookup"><span data-stu-id="96914-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="96914-111">如果會議召集人無法使用商務用 Skype 應用程式加入會議，請使用 PIN 開始會議。</span><span class="sxs-lookup"><span data-stu-id="96914-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="96914-112">設定 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="96914-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="96914-113">在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **Microsoft 橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="96914-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="96914-114">在 **[安全性** PIN 長度圖》 下，選取要用於 PIN 的位數，  >  然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="96914-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="96914-115">PIN 與會議 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="96914-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="96914-116">當來電者加入會議時，會使用會議 ID。</span><span class="sxs-lookup"><span data-stu-id="96914-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="96914-117">它們是用來識別會議。</span><span class="sxs-lookup"><span data-stu-id="96914-117">They are used to identify the meeting.</span></span> <span data-ttu-id="96914-118">PIN 是用來驗證來電者為會議召集人。</span><span class="sxs-lookup"><span data-stu-id="96914-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="96914-119">想要進一瞭解 PIN 設定嗎？</span><span class="sxs-lookup"><span data-stu-id="96914-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="96914-120">PIN 可以是 4 到 12 位數;預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="96914-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="96914-121">數位只有在建立 PIN 時才能使用。</span><span class="sxs-lookup"><span data-stu-id="96914-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="96914-122">不會使用字母和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="96914-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="96914-123">只有當商務用 Skype 使用者尚未開始會議時，會議召集人才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="96914-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="96914-124">如果每個人都撥入會議，會議召集人必須輸入 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="96914-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="96914-125">PIN 安全性設定會適用于與 Microsoft 橋接器相關聯的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="96914-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="96914-126">這些將會適用于使用與特定橋接器相關聯的電話號碼的所有會議。</span><span class="sxs-lookup"><span data-stu-id="96914-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="96914-127">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="96914-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="96914-128">若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96914-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="96914-129">若要將 PIN 中的位數設為 8：  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="96914-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="96914-130">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="96914-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="96914-131">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="96914-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="96914-132">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="96914-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="96914-133">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="96914-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="96914-134">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="96914-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="96914-135">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如一次變更許多使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="96914-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="96914-136">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="96914-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="96914-137">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="96914-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="96914-138">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="96914-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="96914-139">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="96914-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="96914-140">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="96914-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="96914-141">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="96914-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="96914-142">此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="96914-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96914-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="96914-143">See also</span></span>

[<span data-ttu-id="96914-144">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="96914-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)