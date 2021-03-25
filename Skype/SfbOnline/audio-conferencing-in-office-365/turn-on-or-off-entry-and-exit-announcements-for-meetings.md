---
title: 在商務用 Skype Online 中開啟或關閉會議進入和離開公告
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
description: '瞭解如何使用商務用 Skype 系統管理中心在商務用 Skype Online 會議開啟或關閉進入和離開公告。 '
ms.openlocfilehash: 5165facfdc4de040b24b199cd99a1bb42565a76b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111929"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="1983f-103">在商務用 Skype Online 中開啟或關閉會議進入和離開公告</span><span class="sxs-lookup"><span data-stu-id="1983f-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="1983f-104">有關 Microsoft Teams 中的進入和退出公告的資訊，請參閱開啟或關閉 Microsoft Teams 會議進入 [或退出公告](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="1983f-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="1983f-105">當您在 Microsoft 365 或 Office 365 中設定音訊會議時，會取得音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="1983f-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="1983f-106">會議橋接器可以包含一或多個電話號碼，供人員用於撥打商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="1983f-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="1983f-107">會議橋接器會針對使用電話撥入會議的使用者接聽電話。</span><span class="sxs-lookup"><span data-stu-id="1983f-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="1983f-108">會議橋接器會從會議自動語音應答接聽來電者語音提示，然後視您的設定播放通知、要求來電者錄製其名稱，以及設定 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="1983f-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="1983f-109">PIN 會提供給商務用 Skype 會議召集人，而且如果他們無法使用商務用 Skype 應用程式開始會議，就可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="1983f-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="1983f-110">不過，您可以將其設定為不需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="1983f-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="1983f-111">設定會議加入選項</span><span class="sxs-lookup"><span data-stu-id="1983f-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="1983f-112">在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **Microsoft 橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="1983f-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="1983f-113">在 **會議加入體驗下**，選取或清除啟用會議進入和離開 **通知以開啟**。</span><span class="sxs-lookup"><span data-stu-id="1983f-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="1983f-114">這是預設選取的。</span><span class="sxs-lookup"><span data-stu-id="1983f-114">This is selected by default.</span></span> <span data-ttu-id="1983f-115">如果您清除，當某人進入或離開會議時，已加入會議的使用者不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="1983f-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="1983f-116">在 **進入/離開公告類型下**，選取名稱 **或電話號碼** 或 **語音**。</span><span class="sxs-lookup"><span data-stu-id="1983f-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="1983f-117">檢查或取消勾選 **要求來電者在加入會議前先錄製他們的名稱**。</span><span class="sxs-lookup"><span data-stu-id="1983f-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="1983f-118">進行變更後，按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="1983f-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1983f-119">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="1983f-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1983f-120">若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1983f-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="1983f-121">在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="1983f-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1983f-122">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="1983f-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1983f-123">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="1983f-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1983f-124">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1983f-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="1983f-125">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1983f-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="1983f-126">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次變更許多使用者的設定時。</span><span class="sxs-lookup"><span data-stu-id="1983f-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="1983f-127">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="1983f-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1983f-128">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="1983f-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1983f-129">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1983f-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1983f-130">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="1983f-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="1983f-131">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="1983f-131">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="1983f-132">此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="1983f-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1983f-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="1983f-133">Related topics</span></span>

[<span data-ttu-id="1983f-134">音訊會議的常見問題</span><span class="sxs-lookup"><span data-stu-id="1983f-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)