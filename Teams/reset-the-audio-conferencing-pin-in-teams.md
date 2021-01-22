---
title: 在 Microsoft Teams 中重設音訊會議 PIN
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
description: 瞭解如何在 Microsoft Teams 中重設使用者的音訊會議 PIN，以及瞭解 PIN 的重要資訊。
ms.openlocfilehash: cf660331bebfe32fe1809067570e316449c12a22
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918979"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="dfd17-103">在 Microsoft Teams 中重設音訊會議 PIN</span><span class="sxs-lookup"><span data-stu-id="dfd17-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="dfd17-104">PIN 是由數位所建立的代碼，會針對每個啟用音訊會議功能的 Microsoft Teams 使用者建立。</span><span class="sxs-lookup"><span data-stu-id="dfd17-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="dfd17-105">會議召集人會使用音訊會議 PIN，識別他們為會議召集人，並允許他們使用電話開始會議。</span><span class="sxs-lookup"><span data-stu-id="dfd17-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="dfd17-106">如果他們使用 Microsoft Teams 應用程式來開始會議，則不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="dfd17-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="dfd17-107">如果使用者忘記 PIN，而且在可以使用音訊會議時所寄給他們的電子郵件中找不到 PIN，系統管理員可以重設他們的 PIN，或重設自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="dfd17-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="dfd17-108">當已驗證的使用者使用 Microsoft Teams 應用程式加入，或當會議召集人使用 PIN 使用電話加入時，就可以召開會議。</span><span class="sxs-lookup"><span data-stu-id="dfd17-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="dfd17-109">當會議需要 PIN 才能開始時，以電話加入的使用者將會被安置在大廳等候，並且保留通話時聆聽音樂，直到會議召開。</span><span class="sxs-lookup"><span data-stu-id="dfd17-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="dfd17-110">如果會議召集人不需要 PIN，只要使用電話啟動會議，那麼當來電者加入會議時，系統就不會要求他們提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="dfd17-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="dfd17-111">重設使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="dfd17-111">Reset a user's PIN</span></span>

<span data-ttu-id="dfd17-112">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="dfd17-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="dfd17-113">在左側導覽中，按一下 **[使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="dfd17-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="dfd17-114">按一下 **[編輯**。</span><span class="sxs-lookup"><span data-stu-id="dfd17-114">Click **Edit**.</span></span>

3. <span data-ttu-id="dfd17-115">在 **[音訊會議> 下**，按一下 [**重設 PIN。**</span><span class="sxs-lookup"><span data-stu-id="dfd17-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="dfd17-116">按一下 [ **重設**。</span><span class="sxs-lookup"><span data-stu-id="dfd17-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="dfd17-117">讓使用者重設自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="dfd17-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="dfd17-118">讓使用者前往 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。</span><span class="sxs-lookup"><span data-stu-id="dfd17-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="dfd17-119">按一下 [ **重設 PIN** 碼。</span><span class="sxs-lookup"><span data-stu-id="dfd17-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="dfd17-120">您應該知道有關 PIN 還有哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="dfd17-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="dfd17-121">基於安全性的參考資料，重設 PIN 時，PIN 只會向管理員顯示一次。</span><span class="sxs-lookup"><span data-stu-id="dfd17-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="dfd17-122">系統管理員重設 PIN 之後，PIN 就會列為 \*\*\*\*\*\*。。</span><span class="sxs-lookup"><span data-stu-id="dfd17-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="dfd17-123">系統預設會啟用自動傳送電子郵件給使用者，而且使用者可以使用音訊會議或 PIN 重設時，也會收到一封包含 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="dfd17-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="dfd17-124">但是如果您停用了自動傳送電子郵件的設定，PIN 重設電子郵件將不會傳送給使用者，您必須手動傳送 PIN 資訊給使用者。</span><span class="sxs-lookup"><span data-stu-id="dfd17-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="dfd17-125">會議開始時，大廳的所有使用者都會自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="dfd17-125">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="dfd17-126">例如，如果有兩位參與者嘗試在會議開始之前加入會議，他們會被放在大廳等候，並且保留通話時聆聽音樂，當會議召集人透過電話使用 PIN 加入時，會議就會開始，而大廳等候的參與者也會加入會議。</span><span class="sxs-lookup"><span data-stu-id="dfd17-126">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="dfd17-127">預設設定是不允許匿名來電者啟動會議。</span><span class="sxs-lookup"><span data-stu-id="dfd17-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="dfd17-128">當您允許使用者使用音訊會議時，根據預設，使用者會收到包含會議資訊和 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="dfd17-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="dfd17-129">使用者必須擁有 Microsoft 365 或 Office 365 信箱，因為 PIN 重設之後，新的 PIN 會以電子郵件，寄給使用者為使用者設定的主要 SMTP 位址 (別名) 。</span><span class="sxs-lookup"><span data-stu-id="dfd17-129">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="dfd17-130">當您設定音訊會議時，會設定貴組織中 PIN 所需的位數。</span><span class="sxs-lookup"><span data-stu-id="dfd17-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="dfd17-131">PIN 可以是 4 到 12 位數 - 預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="dfd17-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="dfd17-132">如果您變更了 PIN 長度設定，此設定只會新產生的 PIN 上，不會針對啟用音訊會議的現有使用者，將之用於 PIN 設定。</span><span class="sxs-lookup"><span data-stu-id="dfd17-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="dfd17-133">請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd17-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="dfd17-134">根據預設，電子郵件會設定為使用者的 Microsoft 365 或 Office 365 主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="dfd17-134">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="dfd17-135">您可以傳送電子郵件至非 Microsoft 365 或非 Office 365 位址 ，例如 Hotmail 或 MSN 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="dfd17-135">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="dfd17-136">您可以使用 Windows PowerShell 來取代預設的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="dfd17-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="dfd17-137">如果使用者在 Microsoft 365 或 Office 365 中沒有 Exchange 信箱，這項功能就很實用。</span><span class="sxs-lookup"><span data-stu-id="dfd17-137">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="dfd17-138">想要進一瞭解更多 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="dfd17-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="dfd17-139">Windows PowerShell 的用場就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="dfd17-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="dfd17-140">使用 Windows PowerShell，您可以使用單點管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。</span><span class="sxs-lookup"><span data-stu-id="dfd17-140">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="dfd17-141">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="dfd17-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dfd17-142">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfd17-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="dfd17-143">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="dfd17-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="dfd17-144">有關 Windows PowerShell 詳細資訊，請參閱 [Microsoft Teams PowerShell 參照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 以進一詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dfd17-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dfd17-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="dfd17-145">Related topics</span></span>

[<span data-ttu-id="dfd17-146">重設使用者的會議識別碼</span><span class="sxs-lookup"><span data-stu-id="dfd17-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
