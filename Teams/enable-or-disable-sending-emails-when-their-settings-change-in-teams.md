---
title: 啟用或停用 Microsoft 團隊中的音訊會議設定變更時傳送電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: '瞭解如何啟用或停用 Skype 將電子郵件傳送給使用者，例如 pin 變更或 Microsoft 團隊中的預設會議號碼變更等設定。 '
ms.openlocfilehash: 3bb4b09cf1e60edcb9ffb4f4fdb981a9fd6ea0ae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836803"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="f3e44-103">啟用或停用 Microsoft 團隊中的音訊會議設定變更時傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="f3e44-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="f3e44-104">當使用者啟用音訊會議時，系統會自動透過電子郵件收到通知。</span><span class="sxs-lookup"><span data-stu-id="f3e44-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="f3e44-105">不過，有時您可能會想要減少傳送給 Microsoft 團隊使用者的電子郵件數目。</span><span class="sxs-lookup"><span data-stu-id="f3e44-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="f3e44-106">在這種情況下，您可以停用傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f3e44-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="f3e44-107">如果您停用傳送電子郵件，語音會議電子郵件不會傳送給您的使用者，包括使用者在音訊會議中啟用或停用的電子郵件、其 PIN 重設時，以及會議 ID 和預設會議電話號碼的變更.</span><span class="sxs-lookup"><span data-stu-id="f3e44-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="f3e44-108">以下是在啟用音訊會議時傳送給使用者的電子郵件範例：</span><span class="sxs-lookup"><span data-stu-id="f3e44-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音訊會議電子郵件訊息範例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="f3e44-110">何時要傳送電子郵件給使用者？</span><span class="sxs-lookup"><span data-stu-id="f3e44-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="f3e44-111">在啟用音訊會議之後，會有幾封電子郵件會傳送給貴組織中的使用者：</span><span class="sxs-lookup"><span data-stu-id="f3e44-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="f3e44-112">將**音訊會議**授權指派給他們時。</span><span class="sxs-lookup"><span data-stu-id="f3e44-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="f3e44-113">當您手動重設使用者的音訊會議 PIN 時。</span><span class="sxs-lookup"><span data-stu-id="f3e44-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="f3e44-114">手動重設使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="f3e44-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="f3e44-115">從他們移除**音訊會議**授權時。</span><span class="sxs-lookup"><span data-stu-id="f3e44-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="f3e44-116">當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或 [**無**] 時。</span><span class="sxs-lookup"><span data-stu-id="f3e44-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="f3e44-117">當使用者的音訊會議提供者變更為 Microsoft 時。</span><span class="sxs-lookup"><span data-stu-id="f3e44-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="f3e44-118">啟用或停用傳送電子郵件給使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="f3e44-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="f3e44-119">您可以使用 Microsoft 團隊或 Windows PowerShell 來啟用或停用傳送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f3e44-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="f3e44-120">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="f3e44-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f3e44-121">在左側導覽中，前往 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="f3e44-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f3e44-122">在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="f3e44-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="f3e44-123">在 [**橋設定**] 窗格中，如果使用者的撥入設定變更，請啟用或停用**自動傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="f3e44-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="f3e44-124">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f3e44-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="f3e44-125">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3e44-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="f3e44-126">如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="f3e44-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f3e44-127">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="f3e44-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f3e44-128">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="f3e44-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f3e44-129">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="f3e44-129">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f3e44-130">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="f3e44-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f3e44-131">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3e44-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f3e44-132">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="f3e44-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f3e44-133">如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f3e44-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="f3e44-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="f3e44-134">Related topics</span></span>

[<span data-ttu-id="f3e44-135">在使用者的音訊會議設定變更時傳送給使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="f3e44-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="f3e44-136">傳送內含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="f3e44-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


