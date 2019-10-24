---
title: 開啟或關閉商務用 Skype Online 中的進入與結束會議宣告
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '瞭解如何使用商務用 Skype 系統管理中心來開啟或關閉商務用 Skype Online 會議中的進入與結束公告。 '
ms.openlocfilehash: 62b3437b75e36b57bebd167f6d2e155deb31a41b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642916"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="223bf-103">開啟或關閉商務用 Skype Online 中的進入與結束會議宣告</span><span class="sxs-lookup"><span data-stu-id="223bf-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="223bf-104">如需在 Microsoft 團隊中進入與結束宣告的相關資訊，請參閱[開啟或關閉 Microsoft 團隊會議的進入與結束公告](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="223bf-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="223bf-105">當您在 Office 365 中設定音訊會議時，您會收到音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="223bf-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="223bf-106">[會議橋] 可以包含一或多個電話號碼，供人們撥入商務用 Skype 會議時使用。</span><span class="sxs-lookup"><span data-stu-id="223bf-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="223bf-107">[會議橋接] 會使用電話撥入會議的使用者，接聽來電。</span><span class="sxs-lookup"><span data-stu-id="223bf-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="223bf-108">「會議橋接」會使用會議自動語音應答中的語音提示來應答來電者，然後根據您的設定，可以播放通知、要求呼叫者記錄其名稱，以及設定 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="223bf-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="223bf-109">您可以將 PIN 提供給商務用 Skype 會議召集人，如果他們無法使用商務用 Skype app 來啟動會議，就能讓他們開始會議。</span><span class="sxs-lookup"><span data-stu-id="223bf-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="223bf-110">不過，您可以將它設定為不需要 PIN 就能開始會議。</span><span class="sxs-lookup"><span data-stu-id="223bf-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="223bf-111">設定會議加入選項</span><span class="sxs-lookup"><span data-stu-id="223bf-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="223bf-112">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="223bf-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="223bf-113">在 [**會議加入體驗**] 底下，選取或清除 [**啟用會議專案] 和 [結束通知] 以開啟**。</span><span class="sxs-lookup"><span data-stu-id="223bf-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="223bf-114">預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="223bf-114">This is selected by default.</span></span> <span data-ttu-id="223bf-115">如果您清除此選項，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="223bf-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="223bf-116">在 [**進入/結束宣告類型**] 底下，選取 [**名稱或電話號碼**] 或 [**聲音**]。</span><span class="sxs-lookup"><span data-stu-id="223bf-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="223bf-117">**在加入會議前，** 請核取或取消核取 [要求來電者] 來記錄其名稱。</span><span class="sxs-lookup"><span data-stu-id="223bf-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="223bf-118">進行變更之後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="223bf-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="223bf-119">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="223bf-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="223bf-120">若要節省時間或將這項作業自動化，您可以使用[CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="223bf-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="223bf-121">在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者以及允許或不允許的使用者。</span><span class="sxs-lookup"><span data-stu-id="223bf-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="223bf-122">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="223bf-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="223bf-123">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="223bf-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="223bf-124">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="223bf-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="223bf-125">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="223bf-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="223bf-126">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心（例如當您在一次為多位使用者進行設定變更時）。</span><span class="sxs-lookup"><span data-stu-id="223bf-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="223bf-127">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="223bf-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="223bf-128">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="223bf-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="223bf-129">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="223bf-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="223bf-130">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="223bf-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="223bf-131">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="223bf-131">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="223bf-132">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="223bf-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="223bf-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="223bf-133">Related topics</span></span>

[<span data-ttu-id="223bf-134">音訊會議常見問題</span><span class="sxs-lookup"><span data-stu-id="223bf-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
