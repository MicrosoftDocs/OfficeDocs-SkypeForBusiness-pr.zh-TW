---
title: 在 Microsoft Teams 中重設使用者的會議 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 瞭解在 Microsoft Teams 中重設使用者會議 ID 的步驟，並取得會議更新和移移工具的連結。
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117641"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="5a804-103">在 Microsoft Teams 中重設使用者的會議 ID</span><span class="sxs-lookup"><span data-stu-id="5a804-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="5a804-104">動態會議 ID 會包含在會議邀請的底部，以及來電者可用來撥入會議的電話撥入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="5a804-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="5a804-105">當使用者撥打電話號碼時，會議的自動語音機會要求來電者輸入此會議 ID，以便他們參加會議。</span><span class="sxs-lookup"><span data-stu-id="5a804-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a804-106">會議 ID 會自動產生，介於 7 到 9 位數之間，且會在您為使用者啟用音訊會議時設定。</span><span class="sxs-lookup"><span data-stu-id="5a804-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="5a804-107">**不支援靜態會議 ID。**</span><span class="sxs-lookup"><span data-stu-id="5a804-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="5a804-108">為使用者重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="5a804-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="5a804-109">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="5a804-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5a804-110">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="5a804-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5a804-111">按一下 **[編輯**> 。</span><span class="sxs-lookup"><span data-stu-id="5a804-111">Click **Edit**.</span></span>

3. <span data-ttu-id="5a804-112">在 **[音訊會議>** 下，按一下 **[重設會議 ID>**。</span><span class="sxs-lookup"><span data-stu-id="5a804-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="5a804-113">在 [ **重設會議 ID>** 視窗中，按一下 [ **重設**。</span><span class="sxs-lookup"><span data-stu-id="5a804-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="5a804-114">系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。</span><span class="sxs-lookup"><span data-stu-id="5a804-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="5a804-115">根據預設，電子郵件會寄給使用者，但可以關閉。</span><span class="sxs-lookup"><span data-stu-id="5a804-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="5a804-116">重設會議 ID 之後，系統就會將一封包含新會議 ID 的電子郵件寄給使用者。</span><span class="sxs-lookup"><span data-stu-id="5a804-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="5a804-117">在許多情況下，此電子郵件會寄到主要電子郵件地址，包括其 Microsoft 365 或 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="5a804-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="5a804-118">電子郵件包含新的會議 ID、預設撥入 (電話號碼) 更新現有會議的指示。</span><span class="sxs-lookup"><span data-stu-id="5a804-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="5a804-119">我還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="5a804-119">What else should I know?</span></span>

- <span data-ttu-id="5a804-120">您可以在包含會議 ID 和撥入電話號碼的電子郵件中，針對使用者按一下音訊會議區段的 ，以電子郵件傳送會議資訊，以傳送所有 **會議資訊給使用者**。</span><span class="sxs-lookup"><span data-stu-id="5a804-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="5a804-121">它不會傳送 PIN。</span><span class="sxs-lookup"><span data-stu-id="5a804-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="5a804-122">Teams 服務會建立 7- 9 位數的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5a804-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="5a804-123">您無法變更其長度。</span><span class="sxs-lookup"><span data-stu-id="5a804-123">You can't change its length.</span></span>
    
- <span data-ttu-id="5a804-124">重設之後，您可以在會議 ID 下看到新的會議 **ID。**</span><span class="sxs-lookup"><span data-stu-id="5a804-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="5a804-125">建立新會議 ID 之後，來電者無法使用舊的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="5a804-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5a804-126">您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。</span><span class="sxs-lookup"><span data-stu-id="5a804-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5a804-127">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="5a804-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5a804-128">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="5a804-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5a804-129">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="5a804-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5a804-130">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="5a804-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5a804-131">為什麼您需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a804-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="5a804-132">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5a804-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="5a804-133">有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="5a804-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5a804-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="5a804-134">Related topics</span></span>

[<span data-ttu-id="5a804-135">重設音訊會議 PIN 碼</span><span class="sxs-lookup"><span data-stu-id="5a804-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)