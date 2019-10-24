---
title: 讓使用者在商務用 Skype Online 中加入會議時，記錄他們的名稱
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 瞭解如何啟用或停用您的使用者在商務用 Skype Online 中加入會議時，是否可以記錄他們的名稱。
ms.openlocfilehash: 19fad95c0775663db799a59da159ed145aedda6b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642859"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="86111-103">讓使用者在商務用 Skype Online 中加入會議時，記錄他們的名稱</span><span class="sxs-lookup"><span data-stu-id="86111-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="86111-104">如果您想要允許使用者在小組中記錄他們的名稱，請參閱在[Microsoft 團隊中加入會議時，讓使用者記錄其名稱](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="86111-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="86111-105">當您在 Office 365 中設定音訊會議時，您將會收到電話號碼，也就是「音訊會議橋」。</span><span class="sxs-lookup"><span data-stu-id="86111-105">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="86111-106">[會議橋] 可以包含一或多個可以是專用或共用電話號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="86111-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="86111-107">[會議橋接] 會使用電話撥入會議的使用者，接聽來電。</span><span class="sxs-lookup"><span data-stu-id="86111-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="86111-108">「會議橋接」會從自動語音應答中向來電者提供語音提示，然後根據其設定，可以播放通知、要求呼叫者記錄其名稱，以及設定會議召集人的 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="86111-108">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="86111-109">提供給會議召集人的 Pin，讓他們可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="86111-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="86111-110">不過，您可以設定它，讓您不需要 PIN 就能開始會議。</span><span class="sxs-lookup"><span data-stu-id="86111-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="86111-111">設定呼叫者是否應記錄其名稱</span><span class="sxs-lookup"><span data-stu-id="86111-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="86111-112">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="86111-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="86111-113">在 [**會議加入體驗**] 底下，請參閱標示為 [**啟用會議專案] 和**[結束通知] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="86111-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="86111-114">**選取**來電者進入會議前，系統會要求呼叫者先記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="86111-114">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="86111-115">預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="86111-115">This is selected by default.</span></span>
    
   - <span data-ttu-id="86111-116">已**清除**在進入會議前，不會要求來電者記下其名稱。</span><span class="sxs-lookup"><span data-stu-id="86111-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="86111-117">進行變更之後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="86111-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="86111-118">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="86111-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="86111-119">若要節省時間或將這項作業自動化，您可以使用[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86111-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="86111-120">Windows PowerShell 全部說明如何管理使用者，以及使用者可以執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="86111-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="86111-121">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="86111-121">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="86111-122">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="86111-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="86111-123">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="86111-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="86111-124">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="86111-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="86111-125">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="86111-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="86111-126">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="86111-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="86111-127">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="86111-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="86111-128">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="86111-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="86111-129">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="86111-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="86111-130">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="86111-130">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="86111-131">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="86111-131">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="86111-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="86111-132">Related topics</span></span>

[<span data-ttu-id="86111-133">在 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="86111-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
