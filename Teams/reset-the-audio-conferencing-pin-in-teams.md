---
title: 重設音訊會議 PIN Microsoft Teams
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
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 重設使用者的音訊會議 PIN，並瞭解 PIN 的重要事實。
ms.openlocfilehash: 6470085fed25a83c1a8dc46ab45e8c6ea57b5603
ms.sourcegitcommit: a07040d1527692b4dbde7bd2c21994377ad0a92e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114022"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="c61d9-103">重設音訊會議 PIN Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c61d9-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="c61d9-104">PIN 是由每個已啟用音訊會議Microsoft Teams使用者所建立的數位所建立的代碼。</span><span class="sxs-lookup"><span data-stu-id="c61d9-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="c61d9-105">會議召集人會使用音訊會議 PIN 來識別他們是會議召集人，並允許他們以電話開始會議。</span><span class="sxs-lookup"><span data-stu-id="c61d9-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="c61d9-106">如果他們使用 Microsoft Teams應用程式來開始會議，則不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="c61d9-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="c61d9-107">如果使用者忘記 PIN，卻在啟用音訊會議時，無法于電子郵件中找到 PIN，系統管理員可以重設其 PIN，或重設自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="c61d9-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="c61d9-108">當經過驗證的使用者使用 Microsoft Teams App 加入時，或當召集人使用他們的 PIN 在電話上加入時，就可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="c61d9-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="c61d9-109">當會議需要 PIN 才能啟動時，使用電話加入的使用者會放在大廳，並聆聽等候音樂，直到召集人准許他們加入。</span><span class="sxs-lookup"><span data-stu-id="c61d9-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the organizer admits them.</span></span> <span data-ttu-id="c61d9-110">如果會議召集人不需要 PIN，以電話開始會議，則來電者加入會議時不會要求他們提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="c61d9-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="c61d9-111">重設使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="c61d9-111">Reset a user's PIN</span></span>

<span data-ttu-id="c61d9-112">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="c61d9-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c61d9-113">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="c61d9-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c61d9-114">按一下 **[編輯**> 。</span><span class="sxs-lookup"><span data-stu-id="c61d9-114">Click **Edit**.</span></span>

3. <span data-ttu-id="c61d9-115">在 **[音訊會議」** 下，按一下 [ **重設 PIN** 碼。</span><span class="sxs-lookup"><span data-stu-id="c61d9-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="c61d9-116">按一下 **[重設**。</span><span class="sxs-lookup"><span data-stu-id="c61d9-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="c61d9-117">讓使用者重設自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="c61d9-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="c61d9-118">讓使用者前往 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。</span><span class="sxs-lookup"><span data-stu-id="c61d9-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="c61d9-119">按一下 **[重設 PIN** 碼。</span><span class="sxs-lookup"><span data-stu-id="c61d9-119">Click **Reset PIN**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c61d9-120">針對 GCCH，請前往： https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing 。</span><span class="sxs-lookup"><span data-stu-id="c61d9-120">For GCCH go to: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing.</span></span>

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="c61d9-121">關於 PIN，您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="c61d9-121">What else should you know about PINs?</span></span>

- <span data-ttu-id="c61d9-122">為了安全，PIN 只會在 PIN 重設時顯示給系統管理員一次。</span><span class="sxs-lookup"><span data-stu-id="c61d9-122">For security purposes, the PIN is only shown to an administrator one time, when the PIN is reset.</span></span> <span data-ttu-id="c61d9-123">系統管理員重設 PIN 之後，PIN 會列為 \*\*\*\*\*\*\*\*。。</span><span class="sxs-lookup"><span data-stu-id="c61d9-123">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="c61d9-124">系統預設會啟用自動傳送電子郵件給使用者，當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c61d9-124">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="c61d9-125">但如果您已停用自動傳送電子郵件，PIN 重設電子郵件將不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="c61d9-125">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="c61d9-126">會議開始時，召集人必須允許大廳的所有 PSTN 使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="c61d9-126">When a meeting starts, the organizer needs to admit all PSTN users in the lobby to join the meeting.</span></span> <span data-ttu-id="c61d9-127">例如，如果兩個 PSTN 參與者在會議開始之前嘗試加入會議，則他們將會放在大廳中，並且會保留聆聽音樂，當會議召集人透過電話使用 PIN 加入時，會議就會開始，而召集人可以使用會議內命令 (按 \*21) 以允許大廳的所有 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="c61d9-127">For example, if two PSTN participants try to join a meeting before it has started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the organizer can use the in-meeting command (press \*21) to admit all PSTN users in the lobby.</span></span>
    
- <span data-ttu-id="c61d9-128">預設設定是不允許匿名來電者啟動會議。</span><span class="sxs-lookup"><span data-stu-id="c61d9-128">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="c61d9-129">當您啟用音訊會議的使用者時，根據預設，使用者會收到包含會議資訊及其 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c61d9-129">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="c61d9-130">使用者必須擁有 Microsoft 365 或 Office 365 信箱，因為當 PIN 重設時，會以電子郵件將新的 PIN 寄到使用者為使用者設定的主要 SMTP 位址 (別名) 。</span><span class="sxs-lookup"><span data-stu-id="c61d9-130">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="c61d9-131">當您設定音訊會議時，您可以設定組織中 PIN 所需的位數。</span><span class="sxs-lookup"><span data-stu-id="c61d9-131">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="c61d9-132">PIN 可以是 4 到 12 位數 -預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="c61d9-132">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="c61d9-133">如果您變更 PIN 長度設定，則設定只會在新產生的 PIN 上，不會適用于已啟用音訊會議的現有使用者的 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="c61d9-133">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="c61d9-134">請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c61d9-134">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="c61d9-135">根據預設，電子郵件會設定為使用者Microsoft 365或Office 365 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="c61d9-135">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="c61d9-136">您可以將電子郵件傳送至非郵件Microsoft 365非Office 365位址，例如 Hotmail 或 MSN 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c61d9-136">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="c61d9-137">您可以使用預設電子郵件地址來取代Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c61d9-137">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="c61d9-138">如果使用者在郵件或信箱中Exchange信箱，Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c61d9-138">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c61d9-139">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="c61d9-139">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c61d9-140">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="c61d9-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c61d9-141">您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="c61d9-141">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c61d9-142">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="c61d9-142">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c61d9-143">為什麼您需要使用 PowerShell Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c61d9-143">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="c61d9-144">[使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c61d9-144">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="c61d9-145">如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="c61d9-145">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c61d9-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="c61d9-146">Related topics</span></span>

[<span data-ttu-id="c61d9-147">重設使用者的會議識別碼</span><span class="sxs-lookup"><span data-stu-id="c61d9-147">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
