---
title: 音訊會議設定變更時的電子郵件選項
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
- seo-marvel-mar2020
description: '瞭解如何啟用或停用Skype釘號變更或預設會議號碼變更等設定時，將電子郵件傳送給使用者Microsoft Teams。 '
ms.openlocfilehash: 17c2864703eafa2c70709da0381f870abba58ad0
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004165"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="8c1c7-103">啟用或停用在音訊會議設定變更時傳送Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c1c7-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="8c1c7-104">啟用音訊會議時，系統會自動以電子郵件通知使用者。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="8c1c7-105">不過，有時候您可能會想要減少寄給使用者的電子郵件Microsoft Teams數量。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="8c1c7-106">在這種情況下，您可以停用傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="8c1c7-107">如果您停用傳送電子郵件，音訊會議電子郵件將不會傳送給使用者，包括使用者啟用或停用音訊會議、PIN 重設時間，以及會議 ID 和預設會議電話號碼變更時的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="8c1c7-108">以下是啟用音訊會議時，會寄給使用者的電子郵件範例：</span><span class="sxs-lookup"><span data-stu-id="8c1c7-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音訊會議電子郵件訊息範例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="8c1c7-110">何時會將電子郵件寄給您的使用者？</span><span class="sxs-lookup"><span data-stu-id="8c1c7-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="8c1c7-111">啟用音訊會議後，會向貴組織的使用者數封電子郵件：</span><span class="sxs-lookup"><span data-stu-id="8c1c7-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="8c1c7-112">當 **音訊會議授權** 指派給他們時。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="8c1c7-113">當您手動重設使用者的音訊會議 PIN 時。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="8c1c7-114">當您手動重設使用者的會議 ID 時。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="8c1c7-115">從 **這些會議中移除音訊會議** 授權時。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="8c1c7-116">當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="8c1c7-117">當使用者的音訊會議提供者變更為 Microsoft 時。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="8c1c7-118">啟用或停用電子郵件，禁止將電子郵件寄給使用者</span><span class="sxs-lookup"><span data-stu-id="8c1c7-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="8c1c7-119">您可以使用電子郵件Microsoft Teams或Windows PowerShell來啟用或停用發送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="8c1c7-120">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="8c1c7-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8c1c7-121">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="8c1c7-122">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="8c1c7-123">在橋接器 **設定窗格中** ，啟用或停用在使用者的撥入設定變更時自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="8c1c7-124">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="8c1c7-125">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8c1c7-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="8c1c7-126">您也可以使用 PowerShell 模組Microsoft Teams並執行：</span><span class="sxs-lookup"><span data-stu-id="8c1c7-126">You can also use the Microsoft Teams PowerShell module and run:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

<span data-ttu-id="8c1c7-127">您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-127">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="8c1c7-128">請參閱[powerShell Microsoft Teams，](/powershell/module/teams/?view=teams-ps)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-128">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8c1c7-129">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="8c1c7-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="8c1c7-130">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8c1c7-131">有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8c1c7-132">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="8c1c7-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8c1c7-133">為什麼您需要使用 PowerShell Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c1c7-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="8c1c7-134">[使用 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="8c1c7-134">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="8c1c7-135">如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="8c1c7-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="8c1c7-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="8c1c7-136">Related topics</span></span>

[<span data-ttu-id="8c1c7-137">當使用者的音訊會議設定變更時，寄來的電子郵件</span><span class="sxs-lookup"><span data-stu-id="8c1c7-137">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="8c1c7-138">傳送內含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="8c1c7-138">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
