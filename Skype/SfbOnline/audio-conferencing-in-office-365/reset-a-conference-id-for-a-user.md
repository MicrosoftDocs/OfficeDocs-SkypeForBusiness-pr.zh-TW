---
title: 在線上重設使用者商務用 Skype ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: '瞭解在 商務用 Skype Online 中重設使用者會議 ID 的步驟，並取得會議更新和移商務用 Skype工具的連結。 '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237769"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="e7779-103">在線上重設使用者商務用 Skype ID</span><span class="sxs-lookup"><span data-stu-id="e7779-103">Reset a conference ID for a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="e7779-104">有關在 Microsoft Teams 中重設會議 ID 的資訊，請參閱在 Microsoft Teams 中重[設Microsoft Teams。](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="e7779-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="e7779-105">動態會議 ID 會包含在會議邀請的底部，以及來電者可用來撥入會議的電話撥入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e7779-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="e7779-106">當使用者撥打電話號碼時，會議的自動語音機會要求來電者輸入此會議 ID，以便他們參加會議。</span><span class="sxs-lookup"><span data-stu-id="e7779-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7779-107">如果您的會議提供者是 Microsoft，使用者的會議 ID 會設定為 Dynamic Only。</span><span class="sxs-lookup"><span data-stu-id="e7779-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="e7779-108">這無法變更。</span><span class="sxs-lookup"><span data-stu-id="e7779-108">This cannot be changed.</span></span> <span data-ttu-id="e7779-109">系統只會針對啟用音訊會議商務用 Skype使用者自動設定會議 ID。</span><span class="sxs-lookup"><span data-stu-id="e7779-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="e7779-110">為使用者重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="e7779-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="e7779-111">在 **商務用 Skype管理** 中心中，按一下 [音訊會議使用者，選取使用者，然後在 [動作窗格的 [會議 ID> 下按一下  >  \*\*\*\*[**重設**。 </span><span class="sxs-lookup"><span data-stu-id="e7779-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="e7779-112">在 [ **重設會議 ID？ 視窗中** ，按一下 **[是**。</span><span class="sxs-lookup"><span data-stu-id="e7779-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="e7779-113">系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。</span><span class="sxs-lookup"><span data-stu-id="e7779-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="e7779-114">根據預設，電子郵件會寄給使用者，但可以關閉。</span><span class="sxs-lookup"><span data-stu-id="e7779-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7779-115">重設會議 ID 之後，系統就會將一封包含新會議 ID 的電子郵件寄給使用者。</span><span class="sxs-lookup"><span data-stu-id="e7779-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="e7779-116">在許多情況下，此電子郵件會寄到主要電子郵件地址，Microsoft 365或Office 365信箱。</span><span class="sxs-lookup"><span data-stu-id="e7779-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="e7779-117">電子郵件包含新的會議 ID、預設撥入 (電話號碼) 以及使用 商務用 Skype 更新工具更新現有會議的指示。</span><span class="sxs-lookup"><span data-stu-id="e7779-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="e7779-118">我還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="e7779-118">What else should I know?</span></span>

- <span data-ttu-id="e7779-119">您可以在包含會議 ID 和撥入電話號碼的電子郵件中，按一下動作窗格中的使用者以電子郵件傳送會議資訊，以傳送所有會議資訊給使用者。</span><span class="sxs-lookup"><span data-stu-id="e7779-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="e7779-120">它不會傳送 PIN。</span><span class="sxs-lookup"><span data-stu-id="e7779-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="e7779-121">會議 ID 會包含 7 位數，而且您無法變更在系統管理中心商務用 Skype或使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e7779-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="e7779-122">重設之後，您可以在會議 ID 下看到新的 **會議 ID。**</span><span class="sxs-lookup"><span data-stu-id="e7779-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="e7779-123">當您選取使用者頁面上的使用者時，可在音訊會議下的動作窗格底部查看音訊會議使用者的會議 **ID。** </span><span class="sxs-lookup"><span data-stu-id="e7779-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="e7779-124">建立新會議 ID 之後，來電者無法使用舊的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="e7779-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="e7779-125">您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。</span><span class="sxs-lookup"><span data-stu-id="e7779-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="e7779-126">使用者可以使用會議商務用 Skype工具來更新現有的會議。</span><span class="sxs-lookup"><span data-stu-id="e7779-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="e7779-127">若要瞭解如何下載、安裝及執行會議更新商務用 Skype，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e7779-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="e7779-128">適用于 Lync 和 lync 商務用 Skype更新工具</span><span class="sxs-lookup"><span data-stu-id="e7779-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="e7779-129">商務用 Skype線上，會議移 (64 位) </span><span class="sxs-lookup"><span data-stu-id="e7779-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="e7779-130">商務用 Skype線上，會議移 (32 位) </span><span class="sxs-lookup"><span data-stu-id="e7779-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e7779-131">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="e7779-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e7779-132">當要Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="e7779-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e7779-133">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="e7779-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e7779-134">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="e7779-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e7779-135">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="e7779-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e7779-136">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7779-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- <span data-ttu-id="e7779-137">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="e7779-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e7779-138">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="e7779-138">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="e7779-139">[使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e7779-139">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="e7779-140">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e7779-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e7779-141">使用Windows PowerShell執行線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="e7779-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="e7779-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7779-142">Related topics</span></span>

[<span data-ttu-id="e7779-143">重設音訊會議 PIN 碼</span><span class="sxs-lookup"><span data-stu-id="e7779-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
