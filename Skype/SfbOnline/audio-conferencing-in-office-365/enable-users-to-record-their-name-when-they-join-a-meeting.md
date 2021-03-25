---
title: 允許使用者在商務用 Skype Online 中加入會議時記錄其名稱
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 瞭解如何啟用或停用使用者加入商務用 Skype Online 會議時是否可以錄製其名稱。
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114239"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="d06ff-103">允許使用者在商務用 Skype Online 中加入會議時記錄其名稱</span><span class="sxs-lookup"><span data-stu-id="d06ff-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="d06ff-104">如果您想要允許使用者在 Teams 中記錄其名稱，請參閱允許使用者在 Microsoft Teams 中加入會議時記錄 [其名稱](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="d06ff-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="d06ff-105">當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到電話號碼和所謂的音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="d06ff-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="d06ff-106">會議橋接器可以包含一或多個電話號碼，可以是專用或共用的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d06ff-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="d06ff-107">會議橋接器會針對使用電話撥入會議的使用者接聽電話。</span><span class="sxs-lookup"><span data-stu-id="d06ff-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="d06ff-108">會議橋接器會以自動語音應答的語音提示來接聽來電者，然後視他們的設定播放通知、要求來電者錄製其名稱，以及設定會議召集人的 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="d06ff-108">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="d06ff-109">PIN 會提供給會議召集人，讓他們可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="d06ff-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="d06ff-110">不過，您可以進行設定，讓會議不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="d06ff-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="d06ff-111">設定來電者是否應該錄製其名稱</span><span class="sxs-lookup"><span data-stu-id="d06ff-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="d06ff-112">在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **Microsoft 橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="d06ff-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="d06ff-113">在 **會議加入體驗下**，請參閱標示為啟用會議 **進入和離開通知的核取方塊**。</span><span class="sxs-lookup"><span data-stu-id="d06ff-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="d06ff-114">**已選取** 來電者在進入會議之前，會要求他們先記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="d06ff-114">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="d06ff-115">這是預設選取的。</span><span class="sxs-lookup"><span data-stu-id="d06ff-115">This is selected by default.</span></span>
    
   - <span data-ttu-id="d06ff-116">**已清除** 來電者在進入會議之前，不會被要求記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="d06ff-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="d06ff-117">進行變更之後，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="d06ff-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d06ff-118">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="d06ff-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d06ff-119">若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d06ff-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="d06ff-120">Windows PowerShell 就是管理使用者，以及允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="d06ff-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="d06ff-121">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="d06ff-121">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d06ff-122">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="d06ff-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d06ff-123">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d06ff-123">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="d06ff-124">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d06ff-124">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="d06ff-125">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="d06ff-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d06ff-126">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="d06ff-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d06ff-127">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="d06ff-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="d06ff-128">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="d06ff-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="d06ff-129">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="d06ff-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="d06ff-130">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="d06ff-130">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="d06ff-131">此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="d06ff-131">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d06ff-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="d06ff-132">Related topics</span></span>

[<span data-ttu-id="d06ff-133">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="d06ff-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)