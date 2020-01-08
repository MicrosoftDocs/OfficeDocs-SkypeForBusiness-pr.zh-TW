---
title: 在商務用 Skype Online 中重設音訊會議 PIN
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '瞭解關於 Pin 的資訊，以及如何在商務用 Skype Online 中重設。 '
ms.openlocfilehash: a00c36475059a05bb7cf3a9057920b63a09e9a43
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962691"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="76044-103">在商務用 Skype Online 中重設音訊會議 PIN</span><span class="sxs-lookup"><span data-stu-id="76044-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="76044-104">如需在 Microsoft 團隊中重設音訊會議 pin 的相關資訊，請參閱[重設 Microsoft 團隊中的音訊會議 PIN 碼](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="76044-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="76044-105">PIN 是由為已啟用音訊會議的每個商務用 Skype 使用者所建立的數位組成的程式碼。</span><span class="sxs-lookup"><span data-stu-id="76044-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="76044-106">會議召集人會使用音訊會議 Pin 來找出他們是會議召集人，並允許他們透過電話啟動會議。</span><span class="sxs-lookup"><span data-stu-id="76044-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="76044-107">如果他們使用商務用 Skype 應用程式來啟動會議，則不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="76044-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="76044-108">如果使用者忘記自己的 PIN，而且他們無法在啟用音訊會議時傳送給他們的電子郵件中找到它，系統管理員可以重設其 PIN，或者可以重設自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="76044-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="76044-109">當經過驗證的使用者使用商務用 Skype app 加入，或當召集人透過電話與對方的 PIN 連線時，就可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="76044-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="76044-110">當會議需要 PIN 才能開始時，以手機加入的使用者將會放在大廳，並會在會議開始前聆聽音樂保留狀態。</span><span class="sxs-lookup"><span data-stu-id="76044-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="76044-111">如果會議召集人不需要 PIN 即可在手機上啟動會議，則不會要求呼叫者在加入會議時提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="76044-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="76044-112">重設使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="76044-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="76044-113">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="76044-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="76044-114">移至 [系統管理中心] >**商務用 Skype**，然後在左側導覽中，按一下 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="76044-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="76044-115">按一下 [**使用者**]，選取您要重設 PIN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="76044-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="76044-116">在 [動作] 窗格的 [**釘**選] 底下，按一下 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="76044-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="76044-117">讓使用者重設自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="76044-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="76044-118">使用者可以使用 [**電話撥入式會議**] 頁面上的 [**重設 pin** ] 選項來重設 pin。</span><span class="sxs-lookup"><span data-stu-id="76044-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="76044-119">您可以透過下列三種方式之一來存取此頁面：</span><span class="sxs-lookup"><span data-stu-id="76044-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="76044-120">在瀏覽器中，移[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)至。</span><span class="sxs-lookup"><span data-stu-id="76044-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="76044-121">在商務用 Skype 中，按一下 [**選項**] 旁的 [**顯示功能表**] 箭號，然後按一下 [**工具** > **電話撥入式會議設定**]。</span><span class="sxs-lookup"><span data-stu-id="76044-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="76044-122">在商務用 Skype 中，按一下 [**選項**]，按一下左側功能表中的 [**來電轉接**]，然後在 [**其他通話設定**] 區段中，按一下 [**線上編輯設定**]。</span><span class="sxs-lookup"><span data-stu-id="76044-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="76044-123">關於 Pin，您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="76044-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="76044-124">為安全起見，pin 只會在 PIN 重設時向系統管理員顯示一次。</span><span class="sxs-lookup"><span data-stu-id="76044-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="76044-125">由管理員重設 PIN 之後，當**商務用 Skype 系統管理中心**以及在 Windows PowerShell 中使用 CsCsOnlineDialInConfencingUser 時，pin 將會列為 \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="76044-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="76044-126">預設會啟用自動將電子郵件傳送給使用者，當使用者啟用音訊會議或 PIN 重設時，就會收到一封電子郵件及其 PIN。</span><span class="sxs-lookup"><span data-stu-id="76044-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="76044-127">但如果您已停用自動傳送電子郵件，則 PIN 重設電子郵件不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="76044-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="76044-128">當會議開始時，大廳中的所有使用者都會自動加入該會議。</span><span class="sxs-lookup"><span data-stu-id="76044-128">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="76044-129">例如，如果有兩個參與者嘗試在會議開始前加入會議，則會將它們放在大廳，並在會議召集人透過電話使用其 PIN 進行加入時，會議將會啟動，且會議廳中的參與者將會加入 [會議]。</span><span class="sxs-lookup"><span data-stu-id="76044-129">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="76044-130">預設設定為 [不允許匿名呼叫者啟動會議]。</span><span class="sxs-lookup"><span data-stu-id="76044-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="76044-131">當您為使用者啟用音訊會議時，預設會傳送包含會議資訊及其 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="76044-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="76044-132">使用者必須擁有 Office 365 信箱，因為當 PIN 重設時，新的 PIN 碼會以電子郵件傳送給使用者，以傳送給使用者設定的主要 SMTP 位址（別名）。</span><span class="sxs-lookup"><span data-stu-id="76044-132">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="76044-133">當您設定音訊會議時，您會設定貴組織中的 Pin 所需的數位。</span><span class="sxs-lookup"><span data-stu-id="76044-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="76044-134">Pin 可能是4到12位數，預設值是5。</span><span class="sxs-lookup"><span data-stu-id="76044-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="76044-135">如果您變更 [PIN 長度] 設定，此設定只會套用到新產生的針腳上，且不適用於已啟用音訊會議的現有使用者的 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="76044-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="76044-136">請參閱[設定音訊會議的 PIN 長度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="76044-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="76044-137">預設的電子郵件將會設定為使用者的 Office 365 主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="76044-137">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="76044-138">您可以傳送電子郵件至非 Office 365 位址，例如 Hotmail 或 MSN 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="76044-138">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="76044-139">您可以使用 Windows PowerShell 來覆寫預設電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="76044-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="76044-140">如果使用者在 Office 365 沒有 Exchange 信箱，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="76044-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="76044-141">若要覆寫傳送電子郵件的預設使用者位址，租使用者系統管理員可以使用下列 Cmdlet： Get-csonlinedialinconferencinguser-amos。大理石-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com"。</span><span class="sxs-lookup"><span data-stu-id="76044-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="76044-142">SendEmail 參數是覆寫使用者的電子郵件地址所必需的。</span><span class="sxs-lookup"><span data-stu-id="76044-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="76044-143">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="76044-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="76044-144">若要節省時間或將這項作業自動化，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76044-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="76044-145">您可以執行下列動作，為 Amos 大理石設定 PIN：</span><span class="sxs-lookup"><span data-stu-id="76044-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="76044-146">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="76044-146">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="76044-147">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="76044-147">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="76044-148">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="76044-148">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="76044-149">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="76044-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="76044-150">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="76044-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="76044-151">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="76044-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="76044-152">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="76044-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="76044-153">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="76044-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="76044-154">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="76044-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="76044-155">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="76044-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="76044-156">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="76044-156">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="76044-157">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="76044-157">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="76044-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="76044-158">Related topics</span></span>

[<span data-ttu-id="76044-159">重設使用者的會議識別碼</span><span class="sxs-lookup"><span data-stu-id="76044-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
