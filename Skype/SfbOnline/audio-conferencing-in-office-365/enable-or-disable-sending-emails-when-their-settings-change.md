---
title: 啟用或停用在線上音訊會議設定變更時傳送商務用 Skype電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: '瞭解如何啟用或停用Skype釘號變更或預設會議號碼變更等設定時，傳送電子郵件給使用者。 '
ms.openlocfilehash: f6596e3e5c52dd82f4f61ad176ae4d656a5f146c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237319"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="89996-103">啟用或停用在線上音訊會議設定變更時傳送商務用 Skype電子郵件</span><span class="sxs-lookup"><span data-stu-id="89996-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="89996-104">如果您想要啟用或停用在 Microsoft Teams 中傳送電子郵件，請參閱啟用或停用在 Microsoft Teams 中變更音訊會議設定時傳送[Microsoft Teams。](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="89996-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="89996-105">啟用音訊會議時，系統會自動以電子郵件通知使用者。</span><span class="sxs-lookup"><span data-stu-id="89996-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="89996-106">不過，有時候您可能會想要減少寄給使用者的電子郵件商務用 Skype數量。</span><span class="sxs-lookup"><span data-stu-id="89996-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="89996-107">在這種情況下，您可以停用傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="89996-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="89996-108">如果您停用傳送電子郵件，音訊會議電子郵件將不會傳送給使用者，包括使用者啟用或停用音訊會議、PIN 重設時間，以及會議 ID 和預設會議電話號碼變更時的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="89996-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="89996-109">以下是啟用音訊會議時，會寄給使用者的電子郵件範例：</span><span class="sxs-lookup"><span data-stu-id="89996-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音訊會議電子郵件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="89996-111">何時會將電子郵件寄給您的使用者？</span><span class="sxs-lookup"><span data-stu-id="89996-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="89996-112">啟用音訊會議後，會向貴組織的使用者數封電子郵件：</span><span class="sxs-lookup"><span data-stu-id="89996-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="89996-113">當 **音訊會議授權** 指派給他們時。</span><span class="sxs-lookup"><span data-stu-id="89996-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="89996-114">當您手動重設使用者的音訊會議 PIN 時。</span><span class="sxs-lookup"><span data-stu-id="89996-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="89996-115">當您手動重設使用者的會議 ID 時。</span><span class="sxs-lookup"><span data-stu-id="89996-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="89996-116">從 **這些會議中移除音訊會議** 授權時。</span><span class="sxs-lookup"><span data-stu-id="89996-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="89996-117">當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。</span><span class="sxs-lookup"><span data-stu-id="89996-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="89996-118">當使用者的音訊會議提供者變更為 Microsoft 時。</span><span class="sxs-lookup"><span data-stu-id="89996-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="89996-119">啟用或停用電子郵件，禁止將電子郵件寄給使用者</span><span class="sxs-lookup"><span data-stu-id="89996-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="89996-120">您可以使用系統管理商務用 Skype或Windows PowerShell來啟用或停用發送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="89996-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="89996-121">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="89996-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="89996-122">在 商務用 Skype **系統管理中心**，按一下左側流覽中的 [**音訊會議**> 。</span><span class="sxs-lookup"><span data-stu-id="89996-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="89996-123">在 **Microsoft 橋接器設定頁面上** ，選取或清除如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="89996-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="89996-124">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="89996-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="89996-125">您也可以使用音訊會議設定傳送電子郵件給使用者，方法是進入音訊會議使用者、選取使用者，然後按一下以  >  \*\*\*\*\*\*電子郵件傳送會議資訊\*\*。</span><span class="sxs-lookup"><span data-stu-id="89996-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="89996-126">如果您這麼做，將會送出一封電子郵件，只包含會議 ID 和會議電話號碼，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="89996-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="89996-127">請參閱 [傳送電子郵件給使用者及其音訊會議資訊](send-an-email-to-a-user-with-their-dial-in-information.md) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="89996-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="89996-128">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="89996-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="89996-129">執行下列操作以停用傳送電子郵件：</span><span class="sxs-lookup"><span data-stu-id="89996-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="89996-130">有關此 Cmdlet 的協助，請參閱 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)。</span><span class="sxs-lookup"><span data-stu-id="89996-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="89996-131">您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="89996-131">What else should you know?</span></span>

- <span data-ttu-id="89996-132">當自動電子郵件停用時，您仍可使用系統管理中心手動觸發使用會議 ID 和電話號碼商務用 Skype電子郵件。</span><span class="sxs-lookup"><span data-stu-id="89996-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="89996-133">不過，如果您這麼做，將不會包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="89996-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="89996-134">如果您想要重設音訊會議 PIN 並停用傳送電子郵件，您必須以其他方式將 PIN 傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="89996-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="89996-135">您可以使用系統管理中心或商務用 Skype來停用傳送電子郵件給使用者Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="89996-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="89996-136">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="89996-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="89996-137">您可以使用這些 Cmdlet 來節省時間或將這項功能自動化。</span><span class="sxs-lookup"><span data-stu-id="89996-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="89996-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="89996-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="89996-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="89996-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="89996-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="89996-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="89996-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="89996-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="89996-142">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="89996-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="89996-143">您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="89996-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="89996-144">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="89996-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="89996-145">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="89996-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="89996-146">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="89996-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="89996-147">Windows PowerShell比使用 Microsoft 365 系統管理中心時，在速度、簡易性及生產力方面有許多優點，例如一次對許多使用者進行設定變更。</span><span class="sxs-lookup"><span data-stu-id="89996-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="89996-148">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="89996-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="89996-149">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="89996-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="89996-150">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="89996-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="89996-151">使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="89996-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="89996-152">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。</span><span class="sxs-lookup"><span data-stu-id="89996-152">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="89996-153">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="89996-153">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="89996-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="89996-154">Related topics</span></span>

[<span data-ttu-id="89996-155">當使用者的音訊會議設定變更時，寄來的電子郵件</span><span class="sxs-lookup"><span data-stu-id="89996-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="89996-156">傳送內含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="89996-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
