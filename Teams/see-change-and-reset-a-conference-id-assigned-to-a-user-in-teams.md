---
title: 查看、變更及重設使用者的會議 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 瞭解如何將會議 ID 指派給 Microsoft 團隊中的使用者，以及會議 Id 參數的用途。
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691149"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="a1324-103">在 Microsoft 團隊中查看及重設指派給使用者的會議 ID</span><span class="sxs-lookup"><span data-stu-id="a1324-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="a1324-104">當您在 Microsoft 365 或 Office 365 中設定音訊會議，且使用 Microsoft 作為音訊會議提供者時，會自動將會議 ID 指派給 Microsoft 團隊使用者。</span><span class="sxs-lookup"><span data-stu-id="a1324-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="a1324-105">在會議排程時，指派的會議 ID 會在會議邀請中傳送。</span><span class="sxs-lookup"><span data-stu-id="a1324-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="a1324-106">使用者排程的每個會議都會指派唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="a1324-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="a1324-107">雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或是您的使用者無法記住或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="a1324-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="a1324-108">您可以使用 Microsoft 團隊系統管理中心或 Windows PowerShell 來查看、變更及重設其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="a1324-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="a1324-109">系統會傳送電子郵件給使用者，並提供會議 ID 和預設的音訊會議電話號碼; 或者，如果您重設會議 ID，就會傳送不同的電子郵件，並包含會議 ID，但不包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="a1324-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="a1324-110">如需如何重設會議召集人的 PIN 的詳細資訊，請參閱[重設為 Microsoft 團隊使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md) 。</span><span class="sxs-lookup"><span data-stu-id="a1324-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="a1324-111">查看及重設會議 Id</span><span class="sxs-lookup"><span data-stu-id="a1324-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="a1324-112">若要查看會議 ID</span><span class="sxs-lookup"><span data-stu-id="a1324-112">To view the conference ID</span></span>

<span data-ttu-id="a1324-113">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="a1324-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a1324-114">在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="a1324-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a1324-115">按一下頁面頂端的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a1324-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a1324-116">在 [**音訊會議**] 下，查看 [**會議 ID**] 底下。</span><span class="sxs-lookup"><span data-stu-id="a1324-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a1324-117">您可以按一下 [透過**電子郵件傳送會議資訊**] 連結，在包含會議 ID 和音訊電話號碼的電子郵件中傳送所有會議資訊給使用者。</span><span class="sxs-lookup"><span data-stu-id="a1324-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="a1324-118">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a1324-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a1324-119">如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="a1324-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="a1324-120">若要重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="a1324-120">To reset the conference ID</span></span>

<span data-ttu-id="a1324-121">您可以重設使用者的會議 ID （例如忘記它）。</span><span class="sxs-lookup"><span data-stu-id="a1324-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="a1324-122">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="a1324-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a1324-123">在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="a1324-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a1324-124">按一下頁面頂端的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a1324-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a1324-125">在 [**音訊會議**] 底下，按一下 [**重設會議 ID**]。</span><span class="sxs-lookup"><span data-stu-id="a1324-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="a1324-126">在 [**重設會議 ID** ] 視窗中，按一下 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="a1324-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="a1324-127">系統會自動建立會議 ID，並以新的會議 ID 傳送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a1324-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="a1324-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a1324-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a1324-129">如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="a1324-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="a1324-130">您還應該知道什麼？</span><span class="sxs-lookup"><span data-stu-id="a1324-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="a1324-131">在建立新的會議 ID 或重新設定之後，舊的會議 ID 無法由呼叫者使用。</span><span class="sxs-lookup"><span data-stu-id="a1324-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a1324-132">您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。</span><span class="sxs-lookup"><span data-stu-id="a1324-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="a1324-133">會議 ID 必須符合在音訊會議橋設定的位數長度。</span><span class="sxs-lookup"><span data-stu-id="a1324-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="a1324-134">您不能在會議 Id 中使用字母或特殊字元;只有數位可以使用。</span><span class="sxs-lookup"><span data-stu-id="a1324-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a1324-135">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="a1324-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a1324-136">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="a1324-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a1324-137">在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="a1324-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a1324-138">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="a1324-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a1324-139">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1324-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a1324-140">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a1324-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a1324-141">如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a1324-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a1324-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="a1324-142">Related topics</span></span>

[<span data-ttu-id="a1324-143">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="a1324-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
