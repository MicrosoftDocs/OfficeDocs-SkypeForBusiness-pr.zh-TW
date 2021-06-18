---
title: 在設定變更時傳送給使用者的電子郵件
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
description: '瞭解當使用者的電話撥入式會議設定變更時，哪些資訊會以電子郵件自動Microsoft Teams。 '
ms.openlocfilehash: 590d2b9431950464aab051b73a70a1c30e6a55ad
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004205"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="945dd-103">當使用者的設定變更時，會以電子郵件Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="945dd-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="945dd-104">電子郵件會自動寄給使用 Microsoft 作為音訊會議[](set-up-audio-conferencing-in-teams.md)提供者啟用音訊會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="945dd-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="945dd-105">根據預設，有四種類型的電子郵件會寄給啟用音訊會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="945dd-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="945dd-106">不過，如果您想要限制發送給使用者的電子郵件數量，您可以將其關閉。</span><span class="sxs-lookup"><span data-stu-id="945dd-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="945dd-107">當發生以下Microsoft 365 Office 365音訊會議會傳送電子郵件至使用者的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="945dd-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="945dd-108">**音訊會議授權會指派給他們，或是當您將音訊會議提供者變更為 Microsoft 時。**</span><span class="sxs-lookup"><span data-stu-id="945dd-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="945dd-109">此電子郵件包含會議 ID、會議的預設會議電話號碼、使用者的音訊會議 PIN，以及使用 商務用 Skype Online 會議更新工具的指示和連結，此工具是用來更新使用者的現有會議。</span><span class="sxs-lookup"><span data-stu-id="945dd-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="945dd-110">請參閱[指派Microsoft Teams附加元件授權或](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)指派 Microsoft[做為音訊會議提供者](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="945dd-110">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="945dd-111">如果貴組織已啟用動態會議 ID，他們排程的所有會議都會有唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="945dd-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="945dd-112">您可以在貴[組織中設定音訊會議動態的 ID。](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)</span><span class="sxs-lookup"><span data-stu-id="945dd-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="945dd-113">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="945dd-113">Here is an example of this email:</span></span>

     ![商務用 Skype驗證授權](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="945dd-115">若要進一瞭解授權，請參閱Microsoft Teams[附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="945dd-115">To find out more about licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="945dd-116">**使用者的會議 ID 或預設會議電話號碼會變更。**</span><span class="sxs-lookup"><span data-stu-id="945dd-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="945dd-117">此電子郵件包含會議 ID、預設會議電話號碼，以及使用 商務用 Skype 線上會議更新工具的指示和連結，此工具是用來更新使用者的現有會議。</span><span class="sxs-lookup"><span data-stu-id="945dd-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="945dd-118">但此電子郵件不包含使用者的音訊會議 PIN。</span><span class="sxs-lookup"><span data-stu-id="945dd-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="945dd-119">請參閱[為使用者重設會議 ID。](reset-a-conference-id-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="945dd-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="945dd-120">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="945dd-120">Here is an example of this email:</span></span>

     ![電話撥入式會議資訊已變更。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="945dd-122">**使用者的音訊會議 PIN 會重設。**</span><span class="sxs-lookup"><span data-stu-id="945dd-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="945dd-123">此電子郵件包含召集人的音訊會議 PIN、現有的會議 ID，以及使用者的預設會議電話號碼。</span><span class="sxs-lookup"><span data-stu-id="945dd-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="945dd-124">請參閱 [重設音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="945dd-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="945dd-125">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="945dd-125">Here is an example of this email:</span></span>
    
     ![電話撥入式會議 PIN 已變更。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="945dd-127">**使用者授權會移除，或是音訊會議提供者從 Microsoft 變更為其他提供者或無。**</span><span class="sxs-lookup"><span data-stu-id="945dd-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="945dd-128">從使用者移除 **音訊會議授權** ，或將音訊會議提供者設定為 None 時，會發生 **此情況**。</span><span class="sxs-lookup"><span data-stu-id="945dd-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="945dd-129">請參閱[指派或移除商務Microsoft 365授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="945dd-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="945dd-130">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="945dd-130">Here is an example of this email:</span></span>

     ![電話撥入式會議已關閉。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="945dd-132">變更要寄給他們的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="945dd-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="945dd-133">您可以變更自動發送給使用者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="945dd-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="945dd-134">根據預設，電子郵件的寄件者會來自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="945dd-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="945dd-135">請參閱[powerShell Microsoft Teams，](/powershell/module/teams/?view=teams-ps)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="945dd-135">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="945dd-136">如果您不希望電子郵件寄給他們，該怎麼處理？</span><span class="sxs-lookup"><span data-stu-id="945dd-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="945dd-137">當您停用傳送電子郵件給使用者時，即使使用者獲得授權，也不會傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="945dd-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="945dd-138">在這種情況下，會議 ID、預設會議電話號碼，以及更重要的是，其音訊會議 PIN 不會發送給使用者。</span><span class="sxs-lookup"><span data-stu-id="945dd-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="945dd-139">發生此情況時，您必須傳送另一封電子郵件或打電話給使用者，告知使用者。</span><span class="sxs-lookup"><span data-stu-id="945dd-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="945dd-140">根據預設，電子郵件會寄給您的使用者，但如果您想要防止他們收到音訊會議的電子郵件，您可以使用 Microsoft Teams 或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="945dd-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="945dd-141">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="945dd-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="945dd-142">在左側流覽中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="945dd-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="945dd-143">在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。</span><span class="sxs-lookup"><span data-stu-id="945dd-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="945dd-144">在橋接器 **設定窗格中** ，啟用或停用在使用者的撥入設定變更時自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="945dd-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="945dd-145">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="945dd-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="945dd-146">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="945dd-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="945dd-147">您也可以使用 PowerShell 模組Microsoft Teams並執行：</span><span class="sxs-lookup"><span data-stu-id="945dd-147">You can also use the Microsoft Teams PowerShell module and run:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

<span data-ttu-id="945dd-148">您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="945dd-148">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="945dd-149">請參閱[powerShell Microsoft Teams，](/powershell/module/teams/?view=teams-ps)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="945dd-149">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="945dd-150">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="945dd-150">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="945dd-151">根據預設，電子郵件的寄件者會來自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 變更電子郵件地址和Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="945dd-151">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="945dd-152">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="945dd-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="945dd-153">有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="945dd-153">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="945dd-154">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="945dd-154">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="945dd-155">為什麼您需要使用 PowerShell Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="945dd-155">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="945dd-156">[使用 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="945dd-156">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="945dd-157">如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="945dd-157">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="945dd-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="945dd-158">Related topics</span></span>

[<span data-ttu-id="945dd-159">啟用或停用音訊會議設定變更時傳送電子郵件的設定</span><span class="sxs-lookup"><span data-stu-id="945dd-159">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="945dd-160">傳送內含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="945dd-160">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
