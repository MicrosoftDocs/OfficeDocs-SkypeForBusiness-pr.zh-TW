---
title: 透過電子郵件傳送使用者的音訊會議資訊
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft 團隊中傳送電子郵件給使用者的音訊會議資訊。
ms.openlocfilehash: d1cab63d9e89bb62254a838de708c022ef0b0993
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905605"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="422ef-103">在 Microsoft 團隊中傳送電子郵件給使用者的音訊會議資訊</span><span class="sxs-lookup"><span data-stu-id="422ef-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="422ef-104">有時候，Microsoft 團隊使用者可能需要您傳送其音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="422ef-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="422ef-105">您可以按一下使用者屬性底下的 [透過**電子郵件傳送會議資訊**] 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="422ef-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="422ef-106">傳送此電子郵件時，它會包含所有音訊會議資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="422ef-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="422ef-107">使用者的會議電話或撥入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="422ef-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="422ef-108">使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="422ef-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="422ef-109">以下是傳送的電子郵件範例：</span><span class="sxs-lookup"><span data-stu-id="422ef-109">Here is an example of the email that is sent:</span></span>
  
![電話撥入式會議電子郵件訊息範例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="422ef-111">使用音訊會議資訊傳送電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="422ef-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) <span data-ttu-id="422ef-113">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="422ef-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="422ef-114">在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="422ef-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="422ef-115">按一下頁面頂端的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="422ef-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="422ef-116">在 [**音訊會議**] 底下，按一下 [**以電子郵件傳送會議資訊**]。</span><span class="sxs-lookup"><span data-stu-id="422ef-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="422ef-117">關於此電子郵件，您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="422ef-117">What else should you know about this email?</span></span>

- <span data-ttu-id="422ef-118">在啟用音訊會議之後，會有幾封電子郵件會傳送給貴組織中的使用者：</span><span class="sxs-lookup"><span data-stu-id="422ef-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="422ef-119">將**音訊會議**授權指派給他們時。</span><span class="sxs-lookup"><span data-stu-id="422ef-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="422ef-120">當您手動重設使用者的音訊會議 PIN 時。</span><span class="sxs-lookup"><span data-stu-id="422ef-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="422ef-121">手動重設使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="422ef-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="422ef-122">從他們移除**音訊會議**授權時。</span><span class="sxs-lookup"><span data-stu-id="422ef-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="422ef-123">當使用者的音訊會議提供者從 Microsoft 變更為另一提供者或 [**無**] 時。</span><span class="sxs-lookup"><span data-stu-id="422ef-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="422ef-124">當使用者的音訊會議提供者變更為 Microsoft 時。</span><span class="sxs-lookup"><span data-stu-id="422ef-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="422ef-125">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="422ef-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="422ef-126">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="422ef-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="422ef-127">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="422ef-127">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="422ef-128">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="422ef-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="422ef-129">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="422ef-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="422ef-130">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="422ef-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="422ef-131">如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="422ef-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="422ef-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="422ef-132">Related topics</span></span>

[<span data-ttu-id="422ef-133">試用或購買 Office 365 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="422ef-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
