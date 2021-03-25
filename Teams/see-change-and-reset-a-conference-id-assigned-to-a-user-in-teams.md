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
description: 瞭解如何在 Microsoft Teams 中指派會議 ID 給使用者，以及會議 ID 參數應該是什麼。
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117206"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="9af7c-103">在 Microsoft Teams 中查看並重設指派給使用者的會議 ID</span><span class="sxs-lookup"><span data-stu-id="9af7c-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="9af7c-104">在 Microsoft 365 或 Office 365 中設定音訊會議並使用 Microsoft 做為音訊會議提供者時，系統會自動將會議 ID 指派給 Microsoft Teams 使用者。</span><span class="sxs-lookup"><span data-stu-id="9af7c-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="9af7c-105">會議排程時，指派的會議 ID 會以會議邀請中送出。</span><span class="sxs-lookup"><span data-stu-id="9af7c-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="9af7c-106">使用者排程的每個會議都會獲得唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="9af7c-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="9af7c-107">雖然會自動建立會議 ID 並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是使用者不記得或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="9af7c-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="9af7c-108">您可以使用 Microsoft Teams 系統管理中心或 Windows PowerShell 來查看、變更及重設其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="9af7c-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="9af7c-109">電子郵件會以會議 ID 和預設的音訊會議電話號碼寄給使用者，或者如果您重設會議 ID，將會送出包含會議 ID 但不包含 PIN 的不同電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9af7c-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="9af7c-110">請參閱 [在 Microsoft Teams 中](reset-a-conference-id-for-a-user-in-teams.md) 重設使用者的會議 ID，以瞭解如何重設會議召集人的 PIN。</span><span class="sxs-lookup"><span data-stu-id="9af7c-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="9af7c-111">查看和重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="9af7c-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="9af7c-112">若要查看會議 ID</span><span class="sxs-lookup"><span data-stu-id="9af7c-112">To view the conference ID</span></span>

<span data-ttu-id="9af7c-113">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="9af7c-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9af7c-114">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="9af7c-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9af7c-115">按一下頁面頂端的 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="9af7c-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9af7c-116">在 **音訊會議下**，查看會議 **ID** 下的 。</span><span class="sxs-lookup"><span data-stu-id="9af7c-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9af7c-117">您可以按一下電子郵件中傳送會議資訊的連結，以包含會議 ID 和音訊電話號碼的電子郵件傳送所有會議 **資訊給使用者** 。</span><span class="sxs-lookup"><span data-stu-id="9af7c-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="9af7c-118">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9af7c-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9af7c-119">請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="9af7c-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="9af7c-120">若要重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="9af7c-120">To reset the conference ID</span></span>

<span data-ttu-id="9af7c-121">例如，如果使用者忘記會議 ID，您可以重設會議 ID。</span><span class="sxs-lookup"><span data-stu-id="9af7c-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="9af7c-122">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="9af7c-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9af7c-123">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="9af7c-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9af7c-124">按一下頁面頂端的 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="9af7c-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9af7c-125">在 **[音訊會議」** 下，按一下 **[重設會議 ID。**</span><span class="sxs-lookup"><span data-stu-id="9af7c-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="9af7c-126">在 [ **重設會議 ID>** 視窗中，按一下 [ **重設**。</span><span class="sxs-lookup"><span data-stu-id="9af7c-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="9af7c-127">系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。</span><span class="sxs-lookup"><span data-stu-id="9af7c-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="9af7c-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9af7c-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="9af7c-129">請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="9af7c-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="9af7c-130">您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="9af7c-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="9af7c-131">建立新會議 ID 或重設會議 ID 後，來電者無法使用舊的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="9af7c-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="9af7c-132">您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。</span><span class="sxs-lookup"><span data-stu-id="9af7c-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="9af7c-133">會議 ID 必須符合音訊會議橋接器上設定的數位長度。</span><span class="sxs-lookup"><span data-stu-id="9af7c-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="9af7c-134">會議 ID 中無法使用字母或特殊字元;只能使用數位。</span><span class="sxs-lookup"><span data-stu-id="9af7c-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9af7c-135">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="9af7c-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9af7c-136">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="9af7c-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9af7c-137">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="9af7c-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9af7c-138">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="9af7c-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9af7c-139">為什麼您需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9af7c-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="9af7c-140">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9af7c-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="9af7c-141">有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="9af7c-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9af7c-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="9af7c-142">Related topics</span></span>

[<span data-ttu-id="9af7c-143">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="9af7c-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)