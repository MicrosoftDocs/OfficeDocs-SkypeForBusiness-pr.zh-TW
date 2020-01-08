---
title: 在商務用 Skype Online 中的音訊會議設定變更時啟用或停用傳送電子郵件
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '瞭解如何在設定例如 pin 變更或預設會議號碼變更時，啟用或停用 Skype 將電子郵件傳送給使用者。 '
ms.openlocfilehash: d4947012e98c45e108a2cc8d9f84bb4f16a24d3c
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962711"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="78993-103">在商務用 Skype Online 中的音訊會議設定變更時啟用或停用傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="78993-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="78993-104">如果您想要啟用或停用 Microsoft 團隊傳送電子郵件，請參閱[在 Microsoft 團隊中的音訊會議設定變更時啟用或停用傳送電子郵件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="78993-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="78993-105">當使用者啟用音訊會議時，系統會自動透過電子郵件收到通知。</span><span class="sxs-lookup"><span data-stu-id="78993-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="78993-106">不過，您可能會想要減少傳送到商務用 Skype 使用者的電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="78993-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="78993-107">在這種情況下，您可以停用傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="78993-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="78993-108">如果您停用傳送電子郵件，語音會議電子郵件不會傳送給您的使用者，包括使用者在音訊會議中啟用或停用的電子郵件、其 PIN 重設時，以及會議 ID 和預設會議電話號碼的變更.</span><span class="sxs-lookup"><span data-stu-id="78993-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="78993-109">以下是在啟用音訊會議時傳送給使用者的電子郵件範例：</span><span class="sxs-lookup"><span data-stu-id="78993-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音訊會議電子郵件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="78993-111">何時要傳送電子郵件給使用者？</span><span class="sxs-lookup"><span data-stu-id="78993-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="78993-112">在啟用音訊會議之後，會有幾封電子郵件會傳送給貴組織中的使用者：</span><span class="sxs-lookup"><span data-stu-id="78993-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="78993-113">將**音訊會議**授權指派給他們時。</span><span class="sxs-lookup"><span data-stu-id="78993-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="78993-114">當您手動重設使用者的音訊會議 PIN 時。</span><span class="sxs-lookup"><span data-stu-id="78993-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="78993-115">手動重設使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="78993-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="78993-116">從他們移除**音訊會議**授權時。</span><span class="sxs-lookup"><span data-stu-id="78993-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="78993-117">當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或 [**無**] 時。</span><span class="sxs-lookup"><span data-stu-id="78993-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="78993-118">當使用者的音訊會議提供者變更為 Microsoft 時。</span><span class="sxs-lookup"><span data-stu-id="78993-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="78993-119">啟用或停用傳送電子郵件給使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="78993-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="78993-120">您可以使用商務用 Skype 系統管理中心或 Windows PowerShell 來啟用或停用傳送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="78993-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="78993-121">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="78993-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="78993-122">在**商務用 Skype 系統管理中心**的左導覽中，按一下 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="78993-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="78993-123">在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定已變更**）。</span><span class="sxs-lookup"><span data-stu-id="78993-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="78993-124">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="78993-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="78993-125">您也可以移至 [**音訊會議** > ]**使用者**、選取使用者，然後按一下 [透過**電子郵件傳送會議資訊**]，將電子郵件傳送給具有音訊會議設定的使用者。</span><span class="sxs-lookup"><span data-stu-id="78993-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="78993-126">如果您這樣做，就會傳送一封電子郵件，只包含會議 ID 與會議電話號碼，但不包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="78993-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="78993-127">如需詳細資訊，請參閱[傳送電子郵件給使用者的音訊會議資訊](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="78993-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="78993-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="78993-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="78993-129">執行下列動作以停用傳送電子郵件：</span><span class="sxs-lookup"><span data-stu-id="78993-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="78993-130">如需此 Cmdlet 的說明，請參閱[設定 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。</span><span class="sxs-lookup"><span data-stu-id="78993-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="78993-131">您還應該知道什麼？</span><span class="sxs-lookup"><span data-stu-id="78993-131">What else should you know?</span></span>

- <span data-ttu-id="78993-132">當自動電子郵件停用時，您仍然可以使用商務用 Skype 系統管理中心，手動觸發傳送含有會議 ID 和電話號碼的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="78993-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="78993-133">不過，如果您這麼做，就不會包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="78993-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="78993-134">如果您想要重設音訊會議 PIN，且已停用 [傳送電子郵件]，您必須以另一種方式將其傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="78993-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="78993-135">您可以使用商務用 Skype 系統管理中心或 Windows PowerShell 來停用您的使用者傳送電子郵件給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="78993-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="78993-136">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="78993-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="78993-137">您可以使用這些 Cmdlet 來節省時間或將這項作業自動化。</span><span class="sxs-lookup"><span data-stu-id="78993-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="78993-138">CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="78993-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="78993-139">移除-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="78993-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="78993-140">CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="78993-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="78993-141">CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="78993-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="78993-142">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="78993-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="78993-143">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="78993-143">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="78993-144">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="78993-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="78993-145">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="78993-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="78993-146">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="78993-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="78993-147">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="78993-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="78993-148">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="78993-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="78993-149">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="78993-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="78993-150">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="78993-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="78993-151">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="78993-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="78993-152">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="78993-152">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="78993-153">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="78993-153">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="78993-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="78993-154">Related topics</span></span>

[<span data-ttu-id="78993-155">在使用者的音訊會議設定變更時傳送給使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="78993-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="78993-156">傳送內含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="78993-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


