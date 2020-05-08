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
description: 瞭解 PIN 長度與需求的參數，並瞭解如何在商務用 Skype 中設定會議的長度。
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164532"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="dbd71-103">在商務用 Skype Online 中設定音訊會議會議的 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="dbd71-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="dbd71-104">如需在 Microsoft 團隊中設定 PIN 長度的相關資訊，請參閱[在 Microsoft 團隊中設定音訊會議會議的 PIN 長度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="dbd71-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="dbd71-105">當您設定商務用 Skype 的音訊會議時，您會收到音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="dbd71-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="dbd71-106">一個會議橋接器可以包含一或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dbd71-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="dbd71-107">您所設定的電話號碼將會包含在商務用 Skype app 的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="dbd71-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="dbd71-108">音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。</span><span class="sxs-lookup"><span data-stu-id="dbd71-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="dbd71-109">它會從自動語音應答中向來電者提供語音提示，然後視您的設定而定，您可以播放通知並要求呼叫者記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="dbd71-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="dbd71-110">**Microsoft bridge 設定**可讓您變更會議通知與會議加入體驗的設定，以及設定會議召集人所使用的 pin 長度。</span><span class="sxs-lookup"><span data-stu-id="dbd71-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="dbd71-111">如果您無法使用商務用 Skype app 加入會議，會議召集人就可以使用 Pin 來啟動會議。</span><span class="sxs-lookup"><span data-stu-id="dbd71-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="dbd71-112">設定 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="dbd71-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="dbd71-113">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="dbd71-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="dbd71-114">在 [**安全性** > **PIN 長度**] 底下，選取您想要的 PIN 數位位數，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dbd71-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dbd71-115">PIN 與會議 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="dbd71-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="dbd71-116">呼叫者加入會議時，會使用會議 Id。</span><span class="sxs-lookup"><span data-stu-id="dbd71-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="dbd71-117">它們可用來識別會議。</span><span class="sxs-lookup"><span data-stu-id="dbd71-117">They are used to identify the meeting.</span></span> <span data-ttu-id="dbd71-118">PIN 是用來將來電者驗證為會議召集人。</span><span class="sxs-lookup"><span data-stu-id="dbd71-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="dbd71-119">想要進一步瞭解 PIN 設定嗎？</span><span class="sxs-lookup"><span data-stu-id="dbd71-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="dbd71-120">Pin 可能是4到12位數;預設值為5。</span><span class="sxs-lookup"><span data-stu-id="dbd71-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="dbd71-121">只有在建立 Pin 時才會使用數位。</span><span class="sxs-lookup"><span data-stu-id="dbd71-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="dbd71-122">不會使用字母和特殊字元。</span><span class="sxs-lookup"><span data-stu-id="dbd71-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="dbd71-123">只有在商務用 Skype 使用者尚未開始會議時，會議召集人才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="dbd71-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="dbd71-124">如果每個人都要撥入會議，會議召集人需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="dbd71-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="dbd71-125">PIN 安全設定會套用到與 Microsoft 橋接器相關聯的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dbd71-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="dbd71-126">它們會套用至所有使用與指定的橋接器相關聯之電話號碼的會議。</span><span class="sxs-lookup"><span data-stu-id="dbd71-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="dbd71-127">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="dbd71-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="dbd71-128">若要節省時間或將這項作業自動化，您可以使用[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dbd71-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="dbd71-129">若要將 PIN 中的位數設定為8：`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="dbd71-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="dbd71-130">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="dbd71-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="dbd71-131">在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="dbd71-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="dbd71-132">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="dbd71-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dbd71-133">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbd71-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="dbd71-134">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="dbd71-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="dbd71-135">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="dbd71-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="dbd71-136">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="dbd71-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="dbd71-137">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="dbd71-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="dbd71-138">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="dbd71-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="dbd71-139">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="dbd71-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="dbd71-140">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="dbd71-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="dbd71-141">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="dbd71-141">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="dbd71-142">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="dbd71-142">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dbd71-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dbd71-143">See also</span></span>

[<span data-ttu-id="dbd71-144">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="dbd71-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
