---
title: 在 Microsoft 團隊中重設使用者的會議 ID
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
description: 瞭解在 Microsoft 團隊中重設使用者的會議 ID，以及取得會議更新與遷移工具的連結的步驟。
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662123"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="2e122-103">在 Microsoft 團隊中重設使用者的會議 ID</span><span class="sxs-lookup"><span data-stu-id="2e122-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="2e122-104">[動態會議 ID] 包含在會議邀請的底部，以及撥入電話號碼，可供呼叫者用來撥入會議。</span><span class="sxs-lookup"><span data-stu-id="2e122-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="2e122-105">當使用者撥打電話號碼時，會議的自動回應會要求來電者輸入此會議 ID，才能出席會議。</span><span class="sxs-lookup"><span data-stu-id="2e122-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e122-106">會議 Id 會自動產生，在7-9 位數之間，且在您啟用使用者的音訊會議時進行設定。</span><span class="sxs-lookup"><span data-stu-id="2e122-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="2e122-107">**不支援靜態的會議 Id。**</span><span class="sxs-lookup"><span data-stu-id="2e122-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="2e122-108">重設使用者的會議 ID</span><span class="sxs-lookup"><span data-stu-id="2e122-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="2e122-109">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="2e122-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2e122-110">在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="2e122-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="2e122-111">按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2e122-111">Click **Edit**.</span></span>

3. <span data-ttu-id="2e122-112">在 [ **音訊會議** ] 底下，按一下 [ **重設會議 ID**]。</span><span class="sxs-lookup"><span data-stu-id="2e122-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="2e122-113">在 [ **重設會議 ID** ] 視窗中，按一下 [ **重設**]。</span><span class="sxs-lookup"><span data-stu-id="2e122-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="2e122-114">系統會自動建立會議 ID，並以新的會議 ID 傳送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="2e122-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="2e122-115">根據預設，電子郵件會傳送給使用者，但您可以關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="2e122-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="2e122-116">在您重設會議 ID 之後，具有新會議 ID 的電子郵件將會傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="2e122-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="2e122-117">此電子郵件將會傳送至主要電子郵件地址，在許多情況下，也會傳送到他們的 Microsoft 365 或 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="2e122-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="2e122-118">電子郵件包含新的會議 ID、預設的撥入電話號碼 (s) ，以及更新現有會議的指示。</span><span class="sxs-lookup"><span data-stu-id="2e122-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="2e122-119">我還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="2e122-119">What else should I know?</span></span>

- <span data-ttu-id="2e122-120">您可以在包含會議 ID 和撥入電話號碼的電子郵件中，將所有會議資訊傳送給使用者，方法是在 [**音訊會議**] 區段中，按一下 [**以電子郵件傳送會議資訊**]。</span><span class="sxs-lookup"><span data-stu-id="2e122-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="2e122-121">它不會傳送 PIN。</span><span class="sxs-lookup"><span data-stu-id="2e122-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="2e122-122">[團隊服務] 會建立 7-9 位數的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="2e122-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="2e122-123">您無法變更它的長度。</span><span class="sxs-lookup"><span data-stu-id="2e122-123">You can't change its length.</span></span>
    
- <span data-ttu-id="2e122-124">重設之後，您可以在 [ **會議 id**] 底下看到新的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="2e122-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="2e122-125">在建立新的會議 ID 之後，不能讓呼叫者使用舊的會議 id。</span><span class="sxs-lookup"><span data-stu-id="2e122-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="2e122-126">您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。</span><span class="sxs-lookup"><span data-stu-id="2e122-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2e122-127">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="2e122-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="2e122-128">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="2e122-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2e122-129">在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="2e122-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2e122-130">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="2e122-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2e122-131">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e122-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2e122-132">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="2e122-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="2e122-133">如需有關 Windows PowerShell 的詳細資訊，請參閱 [Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) ，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2e122-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="2e122-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="2e122-134">Related topics</span></span>

[<span data-ttu-id="2e122-135">重設音訊會議 PIN 碼</span><span class="sxs-lookup"><span data-stu-id="2e122-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
