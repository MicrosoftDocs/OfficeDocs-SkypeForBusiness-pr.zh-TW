---
title: 以電子郵件將使用者的音訊會議資訊電子郵件
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
description: 瞭解如何在 Microsoft Teams 中傳送包含其音訊會議資訊Microsoft Teams。
ms.openlocfilehash: 13c566884c5bc3e8d5de873696541c4b88fcb271
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004195"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="7062c-103">將電子郵件傳送給使用者，並將他們的音訊會議資訊傳送Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7062c-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="7062c-104">有時候Microsoft Teams使用者可能需要您傳送音訊會議資訊給他們。</span><span class="sxs-lookup"><span data-stu-id="7062c-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="7062c-105">您可以按一下使用者屬性下的透過 **電子郵件** 傳送會議資訊，以執行此操作。</span><span class="sxs-lookup"><span data-stu-id="7062c-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="7062c-106">當您傳送此電子郵件時，它會包含所有音訊會議資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="7062c-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="7062c-107">使用者的會議電話或撥入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="7062c-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="7062c-108">使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="7062c-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="7062c-109">以下是所寄電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="7062c-109">Here is an example of the email that is sent:</span></span>
  
![電話撥入式會議電子郵件訊息範例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="7062c-111">傳送包含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="7062c-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) <span data-ttu-id="7062c-113">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="7062c-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="7062c-114">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="7062c-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7062c-115">按一下頁面頂端的 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="7062c-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="7062c-116">在 **[音訊會議」** 下，按一下 **[以電子郵件傳送會議資訊。**</span><span class="sxs-lookup"><span data-stu-id="7062c-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>

## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="7062c-117">關於此電子郵件，您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="7062c-117">What else should you know about this email?</span></span>

- <span data-ttu-id="7062c-118">啟用音訊會議後，會向貴組織的使用者數封電子郵件：</span><span class="sxs-lookup"><span data-stu-id="7062c-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="7062c-119">當 **音訊會議授權** 指派給他們時。</span><span class="sxs-lookup"><span data-stu-id="7062c-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="7062c-120">當您手動重設使用者的音訊會議 PIN 時。</span><span class="sxs-lookup"><span data-stu-id="7062c-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="7062c-121">當您手動重設使用者的會議 ID 時。</span><span class="sxs-lookup"><span data-stu-id="7062c-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="7062c-122">移除 **音訊會議** 授權時。</span><span class="sxs-lookup"><span data-stu-id="7062c-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="7062c-123">當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。</span><span class="sxs-lookup"><span data-stu-id="7062c-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="7062c-124">當使用者的音訊會議提供者變更為 Microsoft 時。</span><span class="sxs-lookup"><span data-stu-id="7062c-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7062c-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="7062c-125">Related topics</span></span>

[<span data-ttu-id="7062c-126">嘗試或購買音訊會議Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="7062c-126">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
