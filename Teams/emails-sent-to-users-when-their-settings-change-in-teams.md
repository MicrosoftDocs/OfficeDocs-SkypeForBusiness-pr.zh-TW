---
title: 在 Microsoft 團隊中其設定變更時傳送給使用者的電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '瞭解在 Microsoft 團隊中, 當使用者的電話撥入式會議設定變更時, 電子郵件會自動傳送哪些資訊給使用者。 '
ms.openlocfilehash: 575b2a77f216942213fa10caf5d95761e067ef1d
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183429"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="85ae2-103">在 Microsoft 團隊中其設定變更時傳送給使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="85ae2-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="85ae2-104">電子郵件會自動傳送給已使用 Microsoft 做為音訊會議提供者[的音訊會議的](set-up-audio-conferencing-in-teams.md)使用者。</span><span class="sxs-lookup"><span data-stu-id="85ae2-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="85ae2-105">根據預設, 會傳送四種類型的電子郵件給已啟用音訊會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="85ae2-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="85ae2-106">不過, 如果您想要限制傳送給使用者的電子郵件數目, 您可以將它關閉。</span><span class="sxs-lookup"><span data-stu-id="85ae2-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="85ae2-107">Office 365 中的音訊會議會在下列情況傳送電子郵件給使用者的電子郵件:</span><span class="sxs-lookup"><span data-stu-id="85ae2-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="85ae2-108">**系統會將音訊會議授權指派給他們, 或者當您將音訊會議提供者變更為 Microsoft 時。**</span><span class="sxs-lookup"><span data-stu-id="85ae2-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="85ae2-109">此電子郵件包含會議 ID、會議的預設會議電話號碼、使用者的音訊會議 PIN, 以及使用用來更新現有會議的 [商務用 Skype Online 會議更新] 工具的指示與連結。使用者名.</span><span class="sxs-lookup"><span data-stu-id="85ae2-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="85ae2-110">請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)或[將 microsoft 指派為音訊會議提供者](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-110">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="85ae2-111">如果您的組織已啟用動態會議 Id, 他們排程的所有使用者會議都會有唯一的會議 Id。</span><span class="sxs-lookup"><span data-stu-id="85ae2-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="85ae2-112">您可以[在組織中設定音訊會議動態 id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="85ae2-113">以下是這封電子郵件的範例:</span><span class="sxs-lookup"><span data-stu-id="85ae2-113">Here is an example of this email:</span></span>

     ![商務用 Skype 驗證授權](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="85ae2-115">若要深入瞭解授權, 請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="85ae2-116">**使用者的會議 ID 或預設會議電話號碼會變更。**</span><span class="sxs-lookup"><span data-stu-id="85ae2-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="85ae2-117">此電子郵件包含會議 ID、預設會議電話號碼, 以及使用商務用 Skype Online 會議更新工具來更新使用者現有會議的指示與連結。</span><span class="sxs-lookup"><span data-stu-id="85ae2-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="85ae2-118">但此電子郵件不會包含使用者的音訊會議 PIN。</span><span class="sxs-lookup"><span data-stu-id="85ae2-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="85ae2-119">請參閱[重設使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="85ae2-120">以下是這封電子郵件的範例:</span><span class="sxs-lookup"><span data-stu-id="85ae2-120">Here is an example of this email:</span></span>

     ![電話撥入式會議資訊已變更。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="85ae2-122">**使用者的音訊會議 PIN 將會重設。**</span><span class="sxs-lookup"><span data-stu-id="85ae2-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="85ae2-123">此電子郵件包含召集人的音訊會議 PIN、現有的會議 ID, 以及使用者的預設會議電話號碼。</span><span class="sxs-lookup"><span data-stu-id="85ae2-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="85ae2-124">請參閱[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="85ae2-125">以下是這封電子郵件的範例:</span><span class="sxs-lookup"><span data-stu-id="85ae2-125">Here is an example of this email:</span></span>
    
     ![電話撥入式會議 PIN 已變更。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="85ae2-127">**使用者的授權已移除, 或音訊會議提供者從 Microsoft 變更為其他提供者或 [無]。**</span><span class="sxs-lookup"><span data-stu-id="85ae2-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="85ae2-128">當您在使用者中移除**音訊會議**授權, 或是將使用者的音訊會議提供者從 Microsoft 改為協力廠商音訊會議提供者或將提供者設定為 [**無**] 時, 就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="85ae2-128">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="85ae2-129">此電子郵件包含使用者使用商務用 Skype Online 會議更新工具來移除語音會議特定資訊 (例如預設會議電話號碼或會議 ID) 的指示與資訊。</span><span class="sxs-lookup"><span data-stu-id="85ae2-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>

    <span data-ttu-id="85ae2-130">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="85ae2-131">以下是這封電子郵件的範例:</span><span class="sxs-lookup"><span data-stu-id="85ae2-131">Here is an example of this email:</span></span>

     ![電話撥入式會議已關閉。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="85ae2-133">對傳送給他們的電子郵件訊息進行變更</span><span class="sxs-lookup"><span data-stu-id="85ae2-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="85ae2-134">您可以對自動傳送給使用者的電子郵件進行變更。</span><span class="sxs-lookup"><span data-stu-id="85ae2-134">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="85ae2-135">根據預設, 電子郵件的寄件者將是來自 Office 365, 但是您可以使用 Windows PowerShell 變更顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="85ae2-135">By default, the sender of the emails will be from Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="85ae2-136">如需詳細資訊, 請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-136">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="85ae2-137">如果您不想傳送電子郵件給他們, 該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="85ae2-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="85ae2-138">當您停用傳送電子郵件給使用者時, 即使使用者獲指派授權, 也不會傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="85ae2-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="85ae2-139">在此情況下, 會議 ID、預設會議電話號碼和其他重要的是, 其音訊會議 PIN 不會傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="85ae2-139">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="85ae2-140">發生這種情況時, 您必須透過傳送一封電子郵件或呼叫他們來通知使用者。</span><span class="sxs-lookup"><span data-stu-id="85ae2-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="85ae2-141">根據預設, 電子郵件會傳送給您的使用者, 但如果您想要防止他們接收電子郵件以進行音訊會議, 您可以使用 Microsoft 團隊或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="85ae2-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="85ae2-142">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="85ae2-142">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="85ae2-143">在左側導覽中, 前往 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="85ae2-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="85ae2-144">在 [**會議橋接**] 頁面頂端, 按一下 [**橋設定**]。</span><span class="sxs-lookup"><span data-stu-id="85ae2-144">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="85ae2-145">在 [**橋設定**] 窗格中, 如果使用者的撥入設定變更, 請啟用或停用**自動傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="85ae2-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="85ae2-146">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="85ae2-146">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="85ae2-147">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="85ae2-147">**Using Windows PowerShell**</span></span>

<span data-ttu-id="85ae2-148">如需詳細資訊, 請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="85ae2-148">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="85ae2-149">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="85ae2-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="85ae2-150">根據預設, 電子郵件的寄件者會是來自 Office 365, 但您可以使用 Windows PowerShell 變更電子郵件地址和顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="85ae2-150">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="85ae2-151">Windows PowerShell 全部說明如何管理使用者, 以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="85ae2-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="85ae2-152">在 Windows PowerShell 中, 您可以使用單一管理點來管理 Office 365, 以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="85ae2-152">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="85ae2-153">若要開始使用 Windows PowerShell, 請參閱以下主題:</span><span class="sxs-lookup"><span data-stu-id="85ae2-153">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="85ae2-154">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="85ae2-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="85ae2-155">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="85ae2-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="85ae2-156">如需有關 Windows PowerShell 的詳細資訊, 請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps), 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="85ae2-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="85ae2-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="85ae2-157">Related topics</span></span>

[<span data-ttu-id="85ae2-158">在音訊會議設定變更時啟用或停用傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="85ae2-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="85ae2-159">使用音訊會議資訊傳送電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="85ae2-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
