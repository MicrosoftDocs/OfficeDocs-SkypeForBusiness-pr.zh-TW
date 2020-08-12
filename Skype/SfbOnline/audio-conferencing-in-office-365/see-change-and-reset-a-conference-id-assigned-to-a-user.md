---
title: 在商務用 Skype Online 中，查看、變更及重設指派給使用者的會議 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '瞭解如何在商務用 Skype Online 中將會議 ID 指派給使用者，以及會議 Id 參數的用途。 '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643603"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="c1660-103">在商務用 Skype Online 中查看及重設指派給使用者的會議 ID</span><span class="sxs-lookup"><span data-stu-id="c1660-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="c1660-104">如需 Microsoft 團隊中使用者會議 Id 的相關資訊，請參閱[在 Microsoft 團隊中查看及重設指派給使用者的會議 id](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="c1660-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="c1660-105">當您在 Microsoft 365 或 Office 365 中設定音訊會議，且使用 Microsoft 作為音訊會議提供者時，會議 ID 會自動指派給商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="c1660-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c1660-106">在會議排程時，指派的會議 ID 會在會議邀請中傳送。</span><span class="sxs-lookup"><span data-stu-id="c1660-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="c1660-107">使用者排程的每個會議都會指派唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="c1660-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="c1660-108">雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或是您的使用者無法記住或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="c1660-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="c1660-109">您可以使用**商務用 Skype 系統管理中心**和 Windows PowerShell 來查看、變更及重設其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="c1660-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="c1660-110">系統會傳送電子郵件給使用者，並提供會議 ID 和預設的音訊會議電話號碼; 或者，如果您重設會議 ID，就會傳送不同的電子郵件，並包含會議 ID，但不包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="c1660-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="c1660-111">如需重設會議召集人 PIN 的詳細資訊，請[移至這裡](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c1660-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="c1660-112">查看及重設會議 Id</span><span class="sxs-lookup"><span data-stu-id="c1660-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="c1660-113">若要查看會議 ID</span><span class="sxs-lookup"><span data-stu-id="c1660-113">To view the conference ID</span></span>

<span data-ttu-id="c1660-114">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="c1660-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="c1660-115">您可以查看其會議 ID 並傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="c1660-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="c1660-116">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c1660-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="c1660-117">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="c1660-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="c1660-118">在**商務用 Skype 系統管理中心** >  **音訊會議**  >  **使用者**中，選取需要會議 ID 的使用者。</span><span class="sxs-lookup"><span data-stu-id="c1660-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="c1660-119">在 [動作] 頁面中，查看 [**會議 ID**] 底下。</span><span class="sxs-lookup"><span data-stu-id="c1660-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c1660-120">您可以在 [**使用者**] 頁面上選取使用者之後，按一下 [透過**電子郵件傳送會議資訊**] 連結，在包含會議 ID 和音訊電話號碼的電子郵件中，傳送所有會議資訊給使用者。</span><span class="sxs-lookup"><span data-stu-id="c1660-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="c1660-121">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c1660-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="c1660-122">您可以使用 Windows PowerShell 來查看使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="c1660-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="c1660-123">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="c1660-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="c1660-124">若要深入瞭解 Cmdlet，請參閱[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 ) 。</span><span class="sxs-lookup"><span data-stu-id="c1660-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="c1660-125">若要重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="c1660-125">To reset the conference ID</span></span>

<span data-ttu-id="c1660-126">您可以重設使用者的會議 ID （例如忘記它）。</span><span class="sxs-lookup"><span data-stu-id="c1660-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="c1660-127">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="c1660-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="c1660-128">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c1660-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="c1660-129">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="c1660-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="c1660-130">在**商務用 Skype 系統管理中心** >  **音訊會議**  >  **使用者**的 [動作] 窗格中，按一下 [**會議 ID**] 底下的 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="c1660-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="c1660-131">在 [**重設會議 ID？** ] 視窗中，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="c1660-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="c1660-132">系統會自動建立會議 ID，並以新的會議 ID 傳送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c1660-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="c1660-133">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c1660-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="c1660-134">您可以使用 Windows PowerShell 來重設使用者的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="c1660-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="c1660-135">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="c1660-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="c1660-136">您還應該知道什麼？</span><span class="sxs-lookup"><span data-stu-id="c1660-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="c1660-137">在建立新的會議 ID 或重新設定之後，舊的會議 ID 無法由呼叫者使用。</span><span class="sxs-lookup"><span data-stu-id="c1660-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c1660-138">您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。</span><span class="sxs-lookup"><span data-stu-id="c1660-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c1660-139">使用者可以使用商務用 Skype 會議遷移工具來更新現有的會議。</span><span class="sxs-lookup"><span data-stu-id="c1660-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="c1660-140">若要瞭解如何下載、安裝及執行此工具，請參閱：[適用于商務用 skype 和 Lync 的會議更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[商務用 Skype Online、會議遷移工具 (64 位) ](https://go.microsoft.com/fwlink/?LinkID=626047)及[商務用 Skype online、會議遷移工具 (32 位) ](https://www.microsoft.com/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="c1660-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="c1660-141">若要深入瞭解 Cmdlet，請參閱[設定 get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 。</span><span class="sxs-lookup"><span data-stu-id="c1660-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="c1660-142">會議 ID 必須符合在音訊會議橋設定的位數長度。</span><span class="sxs-lookup"><span data-stu-id="c1660-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="c1660-143">您不能在會議 Id 中使用字母或特殊字元;只有數位可以使用。</span><span class="sxs-lookup"><span data-stu-id="c1660-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="c1660-144">所有音訊會議使用者的會議 ID 預設都會是9位數，且位數無法變更。</span><span class="sxs-lookup"><span data-stu-id="c1660-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c1660-145">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="c1660-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c1660-146">若要使用 Windows PowerShell，請參閱管理使用者和允許或不允許的使用者。</span><span class="sxs-lookup"><span data-stu-id="c1660-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c1660-147">在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="c1660-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c1660-148">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="c1660-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c1660-149">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="c1660-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="c1660-150">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1660-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="c1660-151">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="c1660-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c1660-152">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="c1660-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c1660-153">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="c1660-153">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="c1660-154">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="c1660-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="c1660-155">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="c1660-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="c1660-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="c1660-156">Related topics</span></span>

[<span data-ttu-id="c1660-157">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="c1660-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

