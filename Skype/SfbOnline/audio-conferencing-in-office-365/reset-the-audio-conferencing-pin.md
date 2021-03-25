---
title: 重設商務用 Skype Online 的音訊會議 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: '瞭解您應該瞭解哪些 PIN，以及如何在商務用 Skype Online 中重設 PIN。 '
ms.openlocfilehash: 4b042775a5a0525099c0116d7d55d0092f560cdf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114199"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="63f5a-103">重設商務用 Skype Online 的音訊會議 PIN</span><span class="sxs-lookup"><span data-stu-id="63f5a-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="63f5a-104">有關在 Microsoft Teams 中重設音訊會議 PIN 的資訊，請參閱重設 Microsoft Teams 中的音訊[會議 PIN。](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)</span><span class="sxs-lookup"><span data-stu-id="63f5a-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="63f5a-105">PIN 是由每個已啟用音訊會議功能的商務用 Skype 使用者所建立的數位所建立的代碼所建立。</span><span class="sxs-lookup"><span data-stu-id="63f5a-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="63f5a-106">會議召集人會使用音訊會議 PIN 來識別他們是會議召集人，並允許他們以電話開始會議。</span><span class="sxs-lookup"><span data-stu-id="63f5a-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="63f5a-107">如果他們使用商務用 Skype 應用程式來開始會議，則不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="63f5a-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="63f5a-108">如果使用者忘記 PIN，卻在啟用音訊會議時，無法于電子郵件中找到 PIN，系統管理員可以重設其 PIN，或重設自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="63f5a-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="63f5a-109">當經過驗證的使用者使用商務用 Skype App 加入會議，或當召集人使用其 PIN 在電話上加入時，就可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="63f5a-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="63f5a-110">當會議需要 PIN 才能啟動時，使用電話加入的使用者會放在大廳，並聆聽等候音樂，直到會議開始。</span><span class="sxs-lookup"><span data-stu-id="63f5a-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="63f5a-111">如果會議召集人不需要 PIN，以在電話上開始會議，則來電者加入會議時不會要求他們提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="63f5a-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="63f5a-112">重設使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="63f5a-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="63f5a-113">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="63f5a-113">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="63f5a-114">前往商務用 Skype >系統管理 **中心**，然後按一下左側流覽中的 [ **音訊會議**> 。</span><span class="sxs-lookup"><span data-stu-id="63f5a-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="63f5a-115">按一下 **[使用者**」，選取要重設 PIN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="63f5a-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="63f5a-116">在 [動作窗格的 **PIN** 中，按一下 [ **重設**。</span><span class="sxs-lookup"><span data-stu-id="63f5a-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="63f5a-117">讓使用者重設自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="63f5a-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="63f5a-118">使用者可以使用電話撥入式會議頁面上的重設 **PIN** **選項來重設 PIN。**</span><span class="sxs-lookup"><span data-stu-id="63f5a-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="63f5a-119">您可以用三種方式之一存取此頁面：</span><span class="sxs-lookup"><span data-stu-id="63f5a-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="63f5a-120">在瀏覽器中，前往 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) 。</span><span class="sxs-lookup"><span data-stu-id="63f5a-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="63f5a-121">在商務用 Skype 中，按一下 [選項圖旁的顯示功能表箭號，然後按一下 [工具  >  **電話撥入會議設定**> 。</span><span class="sxs-lookup"><span data-stu-id="63f5a-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="63f5a-122">在商務用 Skype中，按一下 [選項>，按一下左側功能表中的 [呼叫轉轉>，然後在 [其他通話設定> 區段，按一下 **[線上編輯設定**> 。 </span><span class="sxs-lookup"><span data-stu-id="63f5a-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="63f5a-123">關於 PIN，您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="63f5a-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="63f5a-124">基於安全性目的，PIN 只會在 PIN 重設時一次顯示給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="63f5a-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="63f5a-125">系統管理員重設 PIN 之後，PIN 就會在商務用 Skype 系統管理中心列為\*\*\*\*\*\*\*\*\*\*，以及當 PIN 在 Windows PowerShell 中使用Get-CsCsOnlineDialInConfencingUser結果中。</span><span class="sxs-lookup"><span data-stu-id="63f5a-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="63f5a-126">系統預設會啟用自動傳送電子郵件給使用者，當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="63f5a-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="63f5a-127">但如果您已停用自動傳送電子郵件，PIN 重設電子郵件將不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="63f5a-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="63f5a-128">會議開始時，大廳中的所有使用者都會自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="63f5a-128">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="63f5a-129">例如，如果兩位參與者在會議開始之前嘗試加入會議，則他們會放在大廳，並保留聆聽音樂，而當會議召集人透過電話使用 PIN 加入時，會議就會開始，而大廳中的參與者會加入會議。</span><span class="sxs-lookup"><span data-stu-id="63f5a-129">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="63f5a-130">預設設定是不允許匿名來電者啟動會議。</span><span class="sxs-lookup"><span data-stu-id="63f5a-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="63f5a-131">當您啟用音訊會議的使用者時，根據預設，系統會送出包含會議資訊及其 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="63f5a-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="63f5a-132">使用者必須擁有 Microsoft 365 或 Office 365 信箱，因為當 PIN 重設時，會以電子郵件將新的 PIN 寄到使用者為使用者設定的主要 SMTP 位址 (別名) 。</span><span class="sxs-lookup"><span data-stu-id="63f5a-132">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="63f5a-133">當您設定音訊會議時，您可以設定組織中 PIN 所需的位數。</span><span class="sxs-lookup"><span data-stu-id="63f5a-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="63f5a-134">PIN 可以是 4 到 12 位數 -預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="63f5a-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="63f5a-135">如果您變更 PIN 長度設定，則設定只會在新產生的 PIN 上，不會適用于已啟用音訊會議的現有使用者的 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="63f5a-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="63f5a-136">請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="63f5a-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="63f5a-137">根據預設，電子郵件會設定為使用者的 Microsoft 365 或 Office 365 主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="63f5a-137">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="63f5a-138">您可以傳送電子郵件至非 Microsoft 365 或非 Office 365 位址，例如 Hotmail 或 MSN 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="63f5a-138">You can send an email to a non-Microsoft 365 or non-Office 365 address, such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="63f5a-139">您可以使用 Windows PowerShell 來取代預設電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="63f5a-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="63f5a-140">如果使用者在 Microsoft 365 或 Office 365 中沒有 Exchange 信箱，這項功能會很有用。</span><span class="sxs-lookup"><span data-stu-id="63f5a-140">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>
    
- <span data-ttu-id="63f5a-141">若要取代傳送電子郵件的預設使用者位址，租使用者系統管理員可以使用下列 Cmdlet：Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com"。</span><span class="sxs-lookup"><span data-stu-id="63f5a-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="63f5a-142">要取代使用者的電子郵件地址，需要 SendEmail 參數。</span><span class="sxs-lookup"><span data-stu-id="63f5a-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="63f5a-143">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="63f5a-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="63f5a-144">若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63f5a-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="63f5a-145">您可以進行以下操作來設定 Amos Marble 的 PIN：</span><span class="sxs-lookup"><span data-stu-id="63f5a-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="63f5a-146">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="63f5a-146">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="63f5a-147">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="63f5a-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="63f5a-148">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="63f5a-148">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="63f5a-149">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="63f5a-149">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="63f5a-150">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="63f5a-150">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="63f5a-151">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如一次變更許多使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="63f5a-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="63f5a-152">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="63f5a-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="63f5a-153">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="63f5a-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="63f5a-154">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="63f5a-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="63f5a-155">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="63f5a-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="63f5a-156">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="63f5a-156">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="63f5a-157">此模組僅支援 64 位電腦，可從商務用 Skype Online 版 Windows PowerShell 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="63f5a-157">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="63f5a-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="63f5a-158">Related topics</span></span>

[<span data-ttu-id="63f5a-159">重設使用者的會議識別碼</span><span class="sxs-lookup"><span data-stu-id="63f5a-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)