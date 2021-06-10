---
title: 讓使用者錄製會議名稱
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解如何啟用或停用使用者是否可在加入會議時錄製其Microsoft Teams。
ms.openlocfilehash: 8b92e0d4a73cc18ceaf374f1a05102e51752c083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092691"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="07330-103">讓使用者在加入會議時記錄其Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07330-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="07330-104">當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到電話號碼和所謂的音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="07330-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="07330-105">會議橋接器可以包含一或多個電話號碼，可以是專用或共用的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="07330-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="07330-106">會議橋接器會針對使用電話撥入會議的使用者接聽電話。</span><span class="sxs-lookup"><span data-stu-id="07330-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="07330-107">會議橋接器會以自動語音應答的語音提示來接聽來電者，然後視他們的設定播放通知、要求來電者錄製其名稱，以及設定會議召集人的 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="07330-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="07330-108">PIN 會提供給會議召集人，讓他們可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="07330-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="07330-109">不過，您可以進行設定，讓會議不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="07330-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="07330-110">設定來電者是否應該錄製其名稱</span><span class="sxs-lookup"><span data-stu-id="07330-110">Set whether callers should record their name</span></span>

<span data-ttu-id="07330-111">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="07330-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="07330-112">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="07330-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="07330-113">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="07330-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="07330-114">啟用或停用 **會議專案及離開通知**。</span><span class="sxs-lookup"><span data-stu-id="07330-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="07330-115">如果啟用通知，請選擇進入 **/** 離開公告類型下的名稱或電話號碼，然後開啟要求來電者在加入會議前錄製 **其名稱。**</span><span class="sxs-lookup"><span data-stu-id="07330-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="07330-116">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="07330-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="07330-117">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="07330-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="07330-118">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="07330-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="07330-119">有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="07330-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="07330-120">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="07330-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="07330-121">為什麼您需要使用 PowerShell Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="07330-121">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="07330-122">[使用 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="07330-122">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="07330-123">如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="07330-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="07330-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="07330-124">Related topics</span></span>

[<span data-ttu-id="07330-125">嘗試或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="07330-125">Try or purchase Audio Conferencing</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)