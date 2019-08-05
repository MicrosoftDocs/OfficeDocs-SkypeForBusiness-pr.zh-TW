---
title: 讓使用者在 Microsoft 團隊中加入會議時, 記錄他們的名稱
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 瞭解如何啟用或停用您的使用者在 Microsoft 團隊中加入會議時是否可以記錄他們的名稱。
ms.openlocfilehash: 44ae945b8ea17b68652e03ab3cb072e5491c5497
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183423"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="7add7-103">讓使用者在 Microsoft 團隊中加入會議時, 記錄他們的名稱</span><span class="sxs-lookup"><span data-stu-id="7add7-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="7add7-104">當您在 Office 365 中設定音訊會議時, 您將會收到電話號碼, 也就是「音訊會議橋」。</span><span class="sxs-lookup"><span data-stu-id="7add7-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="7add7-105">[會議橋] 可以包含一或多個可以是專用或共用電話號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="7add7-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="7add7-106">[會議橋接] 會使用電話撥入會議的使用者, 接聽來電。</span><span class="sxs-lookup"><span data-stu-id="7add7-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="7add7-107">「會議橋接」會從自動語音應答中向來電者提供語音提示, 然後根據其設定, 可以播放通知、要求呼叫者記錄其名稱, 以及設定會議召集人的 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="7add7-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="7add7-108">提供給會議召集人的 Pin, 讓他們可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="7add7-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="7add7-109">不過, 您可以設定它, 讓您不需要 PIN 就能開始會議。</span><span class="sxs-lookup"><span data-stu-id="7add7-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="7add7-110">設定呼叫者是否應記錄其名稱</span><span class="sxs-lookup"><span data-stu-id="7add7-110">Set whether callers should record their name</span></span>

<span data-ttu-id="7add7-111">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="7add7-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7add7-112">在左側導覽中, 前往 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="7add7-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7add7-113">在 [**會議橋接**] 頁面頂端, 按一下 [**橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="7add7-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7add7-114">啟用或停用**會議進入和結束通知**。</span><span class="sxs-lookup"><span data-stu-id="7add7-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="7add7-115">如果啟用通知, 請在 [**進入/結束通知類型**] 下選擇**名稱或電話號碼**, 然後開啟**Ask 呼叫者在加入會議前記錄他們的名稱。**</span><span class="sxs-lookup"><span data-stu-id="7add7-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="7add7-116">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7add7-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7add7-117">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="7add7-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7add7-118">Windows PowerShell 全部說明如何管理使用者, 以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="7add7-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7add7-119">在 Windows PowerShell 中, 您可以使用單一管理點來管理 Office 365, 以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="7add7-119">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7add7-120">若要開始使用 Windows PowerShell, 請參閱以下主題:</span><span class="sxs-lookup"><span data-stu-id="7add7-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7add7-121">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7add7-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7add7-122">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="7add7-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7add7-123">如需有關 Windows PowerShell 的詳細資訊, 請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps), 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7add7-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7add7-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="7add7-124">Related topics</span></span>

[<span data-ttu-id="7add7-125">在 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="7add7-125">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
