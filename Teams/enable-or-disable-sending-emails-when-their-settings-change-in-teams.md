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
description: '瞭解如何啟用或停用 Skype 在 Microsoft Teams 中的釘釘變更或預設會議號碼變更等設定時傳送電子郵件給使用者。 '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092701"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="d9ba1-103">啟用或停用在 Microsoft Teams 中音訊會議設定變更時傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d9ba1-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="d9ba1-104">使用者啟用音訊會議時，會自動收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="d9ba1-105">不過，有時候您可能會想要減少寄給 Microsoft Teams 使用者的電子郵件數量。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="d9ba1-106">在這種情況下，您可以停用傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="d9ba1-107">如果您停用傳送電子郵件，音訊會議電子郵件將不會傳送給使用者，包括使用者啟用或停用音訊會議、PIN 重設時間，以及會議 ID 和預設會議電話號碼變更時的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="d9ba1-108">以下是啟用音訊會議時，會寄給使用者的電子郵件範例：</span><span class="sxs-lookup"><span data-stu-id="d9ba1-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音訊會議電子郵件訊息範例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="d9ba1-110">何時會將電子郵件寄給您的使用者？</span><span class="sxs-lookup"><span data-stu-id="d9ba1-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="d9ba1-111">啟用音訊會議後，會向貴組織的使用者數封電子郵件：</span><span class="sxs-lookup"><span data-stu-id="d9ba1-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="d9ba1-112">當 **音訊會議授權** 指派給他們時。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="d9ba1-113">當您手動重設使用者的音訊會議 PIN 時。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="d9ba1-114">當您手動重設使用者的會議 ID 時。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="d9ba1-115">從 **音訊會議授權** 中移除時。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="d9ba1-116">當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="d9ba1-117">當使用者的音訊會議提供者變更為 Microsoft 時。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="d9ba1-118">啟用或停用電子郵件，禁止將電子郵件寄給使用者</span><span class="sxs-lookup"><span data-stu-id="d9ba1-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="d9ba1-119">您可以使用 Microsoft Teams 或 Windows PowerShell 啟用或停用發送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="d9ba1-120">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="d9ba1-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d9ba1-121">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d9ba1-122">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="d9ba1-123">在橋接器 **設定窗格中** ，啟用或停用在使用者的撥入設定變更時自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="d9ba1-124">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="d9ba1-125">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d9ba1-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="d9ba1-126">請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d9ba1-127">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="d9ba1-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d9ba1-128">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d9ba1-129">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d9ba1-130">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="d9ba1-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d9ba1-131">為什麼您需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9ba1-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="d9ba1-132">[使用 Windows PowerShell 管理 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d9ba1-132">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="d9ba1-133">有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="d9ba1-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="d9ba1-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="d9ba1-134">Related topics</span></span>

[<span data-ttu-id="d9ba1-135">當使用者的音訊會議設定變更時，寄來的電子郵件</span><span class="sxs-lookup"><span data-stu-id="d9ba1-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="d9ba1-136">傳送內含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="d9ba1-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)