---
title: 開啟或關閉 Microsoft 團隊中的會議進入與結束宣告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '瞭解如何在 Microsoft 團隊會議中開啟或關閉 [進入] 和 [結束公告]。 '
ms.openlocfilehash: 8deb53145c95f9a370e894083de8e998b50fa9ae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832603"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="77e76-103">開啟或關閉 Microsoft 團隊中的會議進入與結束宣告</span><span class="sxs-lookup"><span data-stu-id="77e76-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="77e76-104">當您在 Office 365 中設定音訊會議時，您會收到音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="77e76-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="77e76-105">[會議橋] 可以包含一或多個電話號碼，供人們撥打 Microsoft 團隊會議時使用。</span><span class="sxs-lookup"><span data-stu-id="77e76-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="77e76-106">[會議橋接] 會使用電話撥入會議的使用者，接聽來電。</span><span class="sxs-lookup"><span data-stu-id="77e76-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="77e76-107">「會議橋接」會使用會議自動語音應答中的語音提示來應答來電者，然後根據您的設定，可以播放通知、要求呼叫者記錄其名稱，以及設定 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="77e76-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="77e76-108">您可以將 PIN 提供給 Microsoft 團隊會議召集人，如果他們無法使用 Microsoft 團隊 app 來啟動會議，就能讓他們開始會議。</span><span class="sxs-lookup"><span data-stu-id="77e76-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="77e76-109">不過，您可以將它設定為不需要 PIN 就能開始會議。</span><span class="sxs-lookup"><span data-stu-id="77e76-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="77e76-110">設定會議加入選項</span><span class="sxs-lookup"><span data-stu-id="77e76-110">Setting meeting join options</span></span>

<span data-ttu-id="77e76-111">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="77e76-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="77e76-112">在左側導覽中，前往 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="77e76-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="77e76-113">在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="77e76-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="77e76-114">在 [**橋設定**] 窗格中，啟用或停用**會議進入和結束通知**。</span><span class="sxs-lookup"><span data-stu-id="77e76-114">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="77e76-115">預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="77e76-115">This is selected by default.</span></span> <span data-ttu-id="77e76-116">如果您清除此選項，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="77e76-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="77e76-117">在 [**進入/結束宣告類型**] 底下，選取 [**名稱或電話號碼**] 或 [**聲音**]。</span><span class="sxs-lookup"><span data-stu-id="77e76-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="77e76-118">如果您選擇 [**名稱] 或 [電話號碼**]，請在加入會議前，啟用或停用**要求呼叫者記下其名稱**。</span><span class="sxs-lookup"><span data-stu-id="77e76-118">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="77e76-119">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="77e76-119">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="77e76-120">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="77e76-120">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="77e76-121">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="77e76-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="77e76-122">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="77e76-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="77e76-123">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="77e76-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77e76-124">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e76-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="77e76-125">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="77e76-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="77e76-126">如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="77e76-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="77e76-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="77e76-127">Related topics</span></span>

[<span data-ttu-id="77e76-128">音訊會議的常見問題</span><span class="sxs-lookup"><span data-stu-id="77e76-128">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
