---
title: 開啟或關閉會議在 Teams
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
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在會議或會議開啟或Microsoft Teams公告。
ms.openlocfilehash: 6be1c6dc86d8088b5ddb54b2141a10172ba13cc5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121331"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="f14fc-103">開啟或關閉會議在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f14fc-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="f14fc-104">當您在會議或Microsoft 365中Office 365音訊會議時，會取得音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="f14fc-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="f14fc-105">會議橋接器可以包含一或多個電話號碼，使用者會使用該電話號碼來Microsoft Teams會議。</span><span class="sxs-lookup"><span data-stu-id="f14fc-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="f14fc-106">會議橋接器會針對使用電話撥入會議的使用者接聽電話。</span><span class="sxs-lookup"><span data-stu-id="f14fc-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="f14fc-107">會議橋接器會從會議自動語音應答接聽來電者語音提示，然後視您的設定播放通知、要求來電者錄製其名稱，以及設定 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="f14fc-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="f14fc-108">PIN 會提供給會議Microsoft Teams，如果會議召集人無法使用應用程式啟動會議，可以Microsoft Teams會議。</span><span class="sxs-lookup"><span data-stu-id="f14fc-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="f14fc-109">不過，您可以將其設定為不需要 PIN 才能開始會議。</span><span class="sxs-lookup"><span data-stu-id="f14fc-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="f14fc-110">設定會議加入選項</span><span class="sxs-lookup"><span data-stu-id="f14fc-110">Setting meeting join options</span></span>

<span data-ttu-id="f14fc-111">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="f14fc-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="f14fc-112">您必須是 Teams 服務系統管理員才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="f14fc-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="f14fc-113">請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。</span><span class="sxs-lookup"><span data-stu-id="f14fc-113">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="f14fc-114">登入系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f14fc-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="f14fc-115">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="f14fc-116">在 [會議橋接器 **」** 頁面頂端，按一下 [**橋接器** 設定。</span><span class="sxs-lookup"><span data-stu-id="f14fc-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="f14fc-117">在橋接器 **設定窗格中** ，啟用或停用 **會議專案及離開通知**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="f14fc-118">這是預設選取的。</span><span class="sxs-lookup"><span data-stu-id="f14fc-118">This is selected by default.</span></span> <span data-ttu-id="f14fc-119">如果您清除，當某人進入或離開會議時，已加入會議的使用者將不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="f14fc-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="f14fc-120">在 **進入/離開公告類型下**，選取名稱 **或電話號碼** 或 **語音**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f14fc-121">根據預設，外部參與者看不到撥入參與者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f14fc-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="f14fc-122">如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。</span><span class="sxs-lookup"><span data-stu-id="f14fc-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="f14fc-123">如果您選擇名稱 **或電話號碼**，請啟用或停用要求來電者在加入會議前 **記錄其名稱**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="f14fc-124">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f14fc-125">想要進一Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f14fc-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="f14fc-126">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="f14fc-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f14fc-127">有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="f14fc-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f14fc-128">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="f14fc-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="f14fc-129">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f14fc-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="f14fc-130">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f14fc-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="f14fc-131">如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f14fc-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f14fc-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="f14fc-132">Related topics</span></span>

[<span data-ttu-id="f14fc-133">音訊會議的常見問題</span><span class="sxs-lookup"><span data-stu-id="f14fc-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)