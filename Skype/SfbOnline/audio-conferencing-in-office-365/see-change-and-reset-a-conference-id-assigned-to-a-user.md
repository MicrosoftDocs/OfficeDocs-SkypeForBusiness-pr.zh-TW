---
title: 查看、變更及重設在線上版中指派給使用者商務用 Skype ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: '瞭解如何在 商務用 Skype Online 中指派會議 ID 給使用者，以及會議 ID 參數應該是什麼。 '
ms.openlocfilehash: f12982298903485d93582fae3a4f39aaed49170c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237049"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="5e77f-103">在 商務用 Skype 中查看和重設指派給使用者的會議 ID</span><span class="sxs-lookup"><span data-stu-id="5e77f-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="5e77f-104">有關使用者會議識別碼Microsoft Teams，請參閱在 Microsoft Teams 中查看[和重設指派給使用者的會議 id。](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="5e77f-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="5e77f-105">在 Microsoft 365 或 Office 365 中設定音訊會議並使用 Microsoft 做為音訊會議提供者時，系統會自動將會議 ID 指派給 商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="5e77f-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="5e77f-106">會議排程時，指派的會議 ID 會以會議邀請進行。</span><span class="sxs-lookup"><span data-stu-id="5e77f-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="5e77f-107">使用者排程的每個會議都會獲得唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5e77f-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="5e77f-108">雖然會自動建立會議 ID 並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是使用者不記得或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5e77f-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="5e77f-109">您可以使用系統 **管理商務用 Skype和** Windows PowerShell來查看、變更和重設其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5e77f-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="5e77f-110">電子郵件會以會議 ID 和預設的音訊會議電話號碼寄給使用者，或者如果您重設會議 ID，將會送出包含會議 ID 但不包含 PIN 的不同電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5e77f-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="5e77f-111">有關重設會議召集人 PIN 的資訊， [請前往這裡](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="5e77f-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="5e77f-112">查看和重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="5e77f-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="5e77f-113">若要查看會議 ID</span><span class="sxs-lookup"><span data-stu-id="5e77f-113">To view the conference ID</span></span>

<span data-ttu-id="5e77f-114">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="5e77f-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="5e77f-115">您可以查看他們的會議 ID，並將它傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="5e77f-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="5e77f-116">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="5e77f-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="5e77f-117">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="5e77f-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="5e77f-118">在 商務用 Skype **系統管理中心** >  **音訊會議**  >  **使用者中**，選取需要會議 ID 的使用者。</span><span class="sxs-lookup"><span data-stu-id="5e77f-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="5e77f-119">在動作頁面中，查看會議 **ID 下的**。</span><span class="sxs-lookup"><span data-stu-id="5e77f-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="5e77f-120">您可以在選取使用者頁面上的使用者之後，按一下透過電子郵件傳送會議資訊，以包含會議 ID 和音訊電話號碼的電子郵件傳送所有會議 **資訊給使用者**。</span><span class="sxs-lookup"><span data-stu-id="5e77f-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="5e77f-121">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5e77f-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="5e77f-122">您可以使用 Windows PowerShell來查看使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5e77f-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="5e77f-123">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="5e77f-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="5e77f-124">請參閱 [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) 以深入瞭解 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5e77f-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="5e77f-125">若要重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="5e77f-125">To reset the conference ID</span></span>

<span data-ttu-id="5e77f-126">例如，如果使用者忘記會議 ID，您可以重設會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5e77f-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="5e77f-127">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="5e77f-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="5e77f-128">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="5e77f-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="5e77f-129">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="5e77f-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="5e77f-130">在 **[商務用 Skype系統** 管理中心 >  **音訊會議使用者** 中，按一下 [會議識別碼》 下的 [動作窗格>  >  中的 [**重設**。 </span><span class="sxs-lookup"><span data-stu-id="5e77f-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="5e77f-131">在 [ **重設會議 ID？ 視窗中** ，按一下 **[是**。</span><span class="sxs-lookup"><span data-stu-id="5e77f-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="5e77f-132">系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。</span><span class="sxs-lookup"><span data-stu-id="5e77f-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="5e77f-133">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5e77f-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="5e77f-134">您可以使用會議識別碼重設使用者Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5e77f-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="5e77f-135">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="5e77f-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="5e77f-136">您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="5e77f-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="5e77f-137">建立新會議 ID 或重設會議 ID 後，來電者無法使用舊的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5e77f-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5e77f-138">您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。</span><span class="sxs-lookup"><span data-stu-id="5e77f-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="5e77f-139">使用者可以使用會議移商務用 Skype工具來更新現有的會議。</span><span class="sxs-lookup"><span data-stu-id="5e77f-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="5e77f-140">若要瞭解如何下載、安裝及執行工具，請參閱：商務用 Skype 和[Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的會議更新工具、商務用 Skype Online、會議移移工具[ (64](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 商務用 Skype Online、會議移移工具[ (32](https://www.microsoft.com/download/details.aspx?id=54079)位) 。</span><span class="sxs-lookup"><span data-stu-id="5e77f-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="5e77f-141">請參閱 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 以深入瞭解 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5e77f-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="5e77f-142">會議 ID 必須符合音訊會議橋接器上設定的數位長度。</span><span class="sxs-lookup"><span data-stu-id="5e77f-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="5e77f-143">會議 ID 中無法使用字母或特殊字元;只能使用數位。</span><span class="sxs-lookup"><span data-stu-id="5e77f-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="5e77f-144">根據預設，所有音訊會議使用者的會議 ID 為 9 位數，而且無法變更位數。</span><span class="sxs-lookup"><span data-stu-id="5e77f-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5e77f-145">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="5e77f-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5e77f-146">當要Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="5e77f-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5e77f-147">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="5e77f-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5e77f-148">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="5e77f-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="5e77f-149">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="5e77f-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="5e77f-150">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e77f-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="5e77f-151">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="5e77f-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5e77f-152">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="5e77f-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="5e77f-153">[使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5e77f-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="5e77f-154">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5e77f-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="5e77f-155">使用Windows PowerShell執行線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="5e77f-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="5e77f-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="5e77f-156">Related topics</span></span>

[<span data-ttu-id="5e77f-157">嘗試或購買音訊會議Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="5e77f-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
