---
title: 開啟或關閉線上會議進入商務用 Skype公告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: '瞭解如何使用系統管理中心在線上商務用 Skype開啟或關閉商務用 Skype公告。 '
ms.openlocfilehash: f097563ca8dce47277a44573f2af66ed7f1539dd
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237569"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="11f9b-103">開啟或關閉線上會議進入商務用 Skype公告</span><span class="sxs-lookup"><span data-stu-id="11f9b-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="11f9b-104">有關在 Microsoft Teams 中進入和離開公告的資訊，請參閱在 Microsoft Teams 中開啟[或關閉進入和Microsoft Teams。](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)</span><span class="sxs-lookup"><span data-stu-id="11f9b-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="11f9b-105">當您在 Microsoft 365 或 Office 365 中設定音訊會議時，會取得音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="11f9b-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="11f9b-106">會議橋接器可以包含一或多個電話號碼，使用者會使用該電話號碼商務用 Skype會議。</span><span class="sxs-lookup"><span data-stu-id="11f9b-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="11f9b-107">會議橋接器會針對使用電話撥入會議的使用者接聽電話。</span><span class="sxs-lookup"><span data-stu-id="11f9b-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="11f9b-108">會議橋接器會使用來自會議自動語音應答的語音提示來接聽來電者，然後視您的設定播放通知、要求來電者錄製其名稱，以及設定 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="11f9b-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="11f9b-109">PIN 會提供給會議商務用 Skype，如果會議召集人無法使用應用程式啟動會議，可以商務用 Skype會議。</span><span class="sxs-lookup"><span data-stu-id="11f9b-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="11f9b-110">不過，您可以將其設定為不需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="11f9b-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="11f9b-111">設定會議加入選項</span><span class="sxs-lookup"><span data-stu-id="11f9b-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="11f9b-112">在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="11f9b-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="11f9b-113">在 **會議加入體驗下**，選取或清除啟用會議進入和離開 **通知以開啟**。</span><span class="sxs-lookup"><span data-stu-id="11f9b-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="11f9b-114">這是預設選取的。</span><span class="sxs-lookup"><span data-stu-id="11f9b-114">This is selected by default.</span></span> <span data-ttu-id="11f9b-115">如果您清除，當某人進入或離開會議時，已加入會議的使用者不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="11f9b-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="11f9b-116">在 **進入/離開公告類型下**，選取名稱 **或電話號碼** 或 **語音**。</span><span class="sxs-lookup"><span data-stu-id="11f9b-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="11f9b-117">檢查或取消勾選 **要求來電者在加入會議前先錄製他們的名稱**。</span><span class="sxs-lookup"><span data-stu-id="11f9b-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="11f9b-118">進行變更之後，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="11f9b-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="11f9b-119">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="11f9b-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="11f9b-120">若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11f9b-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="11f9b-121">當涉及Windows PowerShell商務用 Skype，商務用 Skype是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="11f9b-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="11f9b-122">您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="11f9b-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="11f9b-123">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="11f9b-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="11f9b-124">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="11f9b-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="11f9b-125">[使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="11f9b-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="11f9b-126">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="11f9b-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="11f9b-127">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="11f9b-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="11f9b-128">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="11f9b-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="11f9b-129">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="11f9b-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="11f9b-130">使用Windows PowerShell執行線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="11f9b-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="11f9b-131">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。</span><span class="sxs-lookup"><span data-stu-id="11f9b-131">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="11f9b-132">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 模組商務用 Skype[下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="11f9b-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="11f9b-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="11f9b-133">Related topics</span></span>

[<span data-ttu-id="11f9b-134">音訊會議的常見問題</span><span class="sxs-lookup"><span data-stu-id="11f9b-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
