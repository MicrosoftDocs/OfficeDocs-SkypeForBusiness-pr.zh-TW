---
title: 在 Microsoft 團隊中重設音訊會議 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: '瞭解您應該瞭解的 Pin，以及如何在 Microsoft 團隊中重設它們。 '
ms.openlocfilehash: 92f0fcf0b5a5e8afe0615b54b08f0fa407c4a969
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838223"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="8f479-103">在 Microsoft 團隊中重設音訊會議 PIN</span><span class="sxs-lookup"><span data-stu-id="8f479-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="8f479-104">PIN 是由為每個啟用音訊會議的 Microsoft 團隊使用者所建立的數位組成的程式碼。</span><span class="sxs-lookup"><span data-stu-id="8f479-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="8f479-105">會議召集人會使用音訊會議 Pin 來找出他們是會議召集人，並允許他們透過電話啟動會議。</span><span class="sxs-lookup"><span data-stu-id="8f479-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="8f479-106">如果他們使用 Microsoft 團隊 app 來啟動會議，則不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="8f479-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="8f479-107">如果使用者忘記自己的 PIN，而且他們無法在啟用音訊會議時傳送給他們的電子郵件中找到它，系統管理員可以重設其 PIN，或者可以重設自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="8f479-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="8f479-108">當經過驗證的使用者使用 Microsoft 團隊應用程式加入會議，或當召集人透過電話與對方的 PIN 連線時，就可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="8f479-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="8f479-109">當會議需要 PIN 才能開始時，以手機加入的使用者將會放在大廳，並會在會議開始前聆聽音樂保留狀態。</span><span class="sxs-lookup"><span data-stu-id="8f479-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="8f479-110">如果會議召集人不需要 PIN 即可在手機上啟動會議，則不會要求呼叫者在加入會議時提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="8f479-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="8f479-111">重設使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="8f479-111">Reset a user's PIN</span></span>

<span data-ttu-id="8f479-112">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="8f479-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8f479-113">在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="8f479-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="8f479-114">按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="8f479-114">Click **Edit**.</span></span>

3. <span data-ttu-id="8f479-115">在 [**音訊會議**] 底下，按一下 [**重設 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="8f479-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="8f479-116">按一下 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="8f479-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="8f479-117">讓使用者重設自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="8f479-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="8f479-118">讓使用者移至[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。</span><span class="sxs-lookup"><span data-stu-id="8f479-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="8f479-119">按一下 [**重設 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="8f479-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="8f479-120">關於 Pin，您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="8f479-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="8f479-121">為安全起見，pin 只會在 PIN 重設時向系統管理員顯示一次。</span><span class="sxs-lookup"><span data-stu-id="8f479-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="8f479-122">由管理員重設 PIN 之後，PIN 將會列為 \* \* \* \* \* \* \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="8f479-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="8f479-123">預設會啟用自動將電子郵件傳送給使用者，當使用者啟用音訊會議或 PIN 重設時，就會收到一封電子郵件及其 PIN。</span><span class="sxs-lookup"><span data-stu-id="8f479-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="8f479-124">但如果您已停用自動傳送電子郵件，則 PIN 重設電子郵件不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="8f479-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="8f479-125">當會議開始時，大廳中的所有使用者都會自動加入該會議。</span><span class="sxs-lookup"><span data-stu-id="8f479-125">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="8f479-126">例如，如果有兩個參與者嘗試在會議開始前加入會議，則會將它們放在大廳，並在會議召集人透過電話使用其 PIN 進行加入時，會議將會啟動，且會議廳中的參與者將會加入 [會議]。</span><span class="sxs-lookup"><span data-stu-id="8f479-126">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="8f479-127">預設設定為 [不允許匿名呼叫者啟動會議]。</span><span class="sxs-lookup"><span data-stu-id="8f479-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="8f479-128">當您為使用者啟用音訊會議時，預設會傳送包含會議資訊及其 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8f479-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="8f479-129">使用者必須擁有 Office 365 信箱，因為當 PIN 重設時，新的 PIN 碼會以電子郵件傳送給使用者，以傳送給使用者設定的主要 SMTP 位址（別名）。</span><span class="sxs-lookup"><span data-stu-id="8f479-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="8f479-130">當您設定音訊會議時，您會設定貴組織中的 Pin 所需的數位。</span><span class="sxs-lookup"><span data-stu-id="8f479-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="8f479-131">Pin 可能是4到12位數，預設值是5。</span><span class="sxs-lookup"><span data-stu-id="8f479-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="8f479-132">如果您變更 [PIN 長度] 設定，此設定只會套用到新產生的針腳上，且不適用於已啟用音訊會議的現有使用者的 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="8f479-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="8f479-133">請參閱[設定音訊會議的 PIN 長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8f479-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="8f479-134">預設的電子郵件將會設定為使用者的 Office 365 主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f479-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="8f479-135">您可以傳送電子郵件至非 Office 365 位址，例如 Hotmail 或 MSN 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8f479-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="8f479-136">您可以使用 Windows PowerShell 來覆寫預設電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8f479-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="8f479-137">如果使用者在 Office 365 沒有 Exchange 信箱，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="8f479-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8f479-138">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="8f479-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="8f479-139">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="8f479-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8f479-140">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="8f479-140">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8f479-141">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="8f479-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8f479-142">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f479-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8f479-143">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="8f479-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8f479-144">如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8f479-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8f479-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f479-145">Related topics</span></span>

[<span data-ttu-id="8f479-146">重設使用者的會議識別碼</span><span class="sxs-lookup"><span data-stu-id="8f479-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
