---
title: 當使用者的設定在線上變更時，會商務用 Skype電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: '瞭解當使用者的電話撥入式會議設定變更時，哪些資訊會以電子郵件自動商務用 Skype Online。 '
ms.openlocfilehash: 75ed80ef7d686ecb649bc1d21f30a43fd115f1a3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237339"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="e4a90-103">當使用者的設定在線上變更時，會商務用 Skype電子郵件</span><span class="sxs-lookup"><span data-stu-id="e4a90-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="e4a90-104">如果您要在郵件中尋找自動電子郵件Microsoft Teams，請參閱當使用者的設定在 Microsoft Teams 中[變更時Microsoft Teams。](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="e4a90-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="e4a90-105">電子郵件會自動寄給使用 Microsoft 作為音訊會議[](set-up-audio-conferencing.md)提供者啟用音訊會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="e4a90-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="e4a90-106">根據預設，有四種類型的電子郵件會寄給已啟用音訊會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="e4a90-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e4a90-107">不過，如果您想要限制發送給使用者的電子郵件數量，您可以將其關閉。</span><span class="sxs-lookup"><span data-stu-id="e4a90-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="e4a90-108">當發生以下Microsoft 365 Office 365音訊會議會傳送電子郵件至使用者的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="e4a90-108">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="e4a90-109">**音訊會議授權會指派給他們，或是當您將音訊會議提供者變更為 Microsoft 時。**</span><span class="sxs-lookup"><span data-stu-id="e4a90-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="e4a90-110">此電子郵件包含會議 ID、會議的預設會議電話號碼、使用者的音訊會議 PIN，以及使用 商務用 Skype Online 會議更新工具的指示和連結，此工具是用來更新使用者的現有會議。</span><span class="sxs-lookup"><span data-stu-id="e4a90-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="e4a90-111">請參閱[指派商務用 Skype授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)[或指派 Microsoft 作為音訊會議提供者](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a90-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4a90-112">如果貴組織已啟用動態會議 ID，他們排程的所有會議都會有唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="e4a90-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="e4a90-113">您可以在貴[組織中設定音訊會議動態的 ID。](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="e4a90-113">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="e4a90-114">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="e4a90-114">Here is an example of this email:</span></span>
    
     ![商務用 Skype驗證授權](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="e4a90-116">您可以查看附加元件商務用 Skype，以[商務用 Skype更多有關授權。](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e4a90-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="e4a90-117">**使用者的會議 ID 或預設會議電話號碼會變更。**</span><span class="sxs-lookup"><span data-stu-id="e4a90-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="e4a90-118">此電子郵件包含會議 ID、預設會議電話號碼，以及使用 商務用 Skype 線上會議更新工具的指示和連結，此工具是用來更新使用者的現有會議。</span><span class="sxs-lookup"><span data-stu-id="e4a90-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="e4a90-119">但此電子郵件不包含使用者的音訊會議 PIN。</span><span class="sxs-lookup"><span data-stu-id="e4a90-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="e4a90-120">請參閱[重設使用者的會議 ID。](reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="e4a90-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4a90-121">如果貴組織已啟用動態會議 ID，他們排程的所有會議都會有唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="e4a90-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="e4a90-122">您可以在貴[組織中設定音訊會議動態的 ID。](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="e4a90-122">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="e4a90-123">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="e4a90-123">Here is an example of this email:</span></span>
    
     ![電話撥入式會議資訊已變更。](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="e4a90-125">**使用者的音訊會議 PIN 會重設。**</span><span class="sxs-lookup"><span data-stu-id="e4a90-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="e4a90-126">此電子郵件包含召集人的音訊會議 PIN、現有的會議 ID，以及使用者的預設會議電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e4a90-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="e4a90-127">請參閱 [重設音訊會議 PIN](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a90-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4a90-128">如果貴組織已啟用動態會議 ID，他們排程的所有會議都會有唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="e4a90-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="e4a90-129">您可以在貴[組織中設定音訊會議動態的 ID。](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="e4a90-129">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="e4a90-130">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="e4a90-130">Here is an example of this email:</span></span>
    
     ![電話撥入式會議 PIN 已變更。](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="e4a90-132">**使用者授權會移除，或是音訊會議提供者從 Microsoft 變更為其他提供者或無。**</span><span class="sxs-lookup"><span data-stu-id="e4a90-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="e4a90-133">從使用者移除 **音訊會議** 授權，或將使用者的音訊會議提供者從 Microsoft 變更為協力廠商音訊會議提供者，或將提供者設定為 None 時，會發生此 **情況**。</span><span class="sxs-lookup"><span data-stu-id="e4a90-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="e4a90-134">此電子郵件包含使用者使用 商務用 Skype 線上會議更新工具移除音訊會議特定資訊的指示和資訊，例如預設會議電話號碼或會議 ID。</span><span class="sxs-lookup"><span data-stu-id="e4a90-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="e4a90-135">請參閱[指派或移除 Microsoft 365 Apps 商務版。](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="e4a90-135">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="e4a90-136">以下是此電子郵件的範例：</span><span class="sxs-lookup"><span data-stu-id="e4a90-136">Here is an example of this email:</span></span>
    
     ![電話撥入式會議已關閉。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="e4a90-138">變更要寄給他們的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="e4a90-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="e4a90-139">您可以變更自動發送給使用者的電子郵件，包括電子郵件地址和包含在 From 連絡人資訊 *中的顯示名稱* 。</span><span class="sxs-lookup"><span data-stu-id="e4a90-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="e4a90-140">根據預設，電子郵件的寄件者會來自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) Cmdlet 來變更電子郵件地址和顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="e4a90-140">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span> <span data-ttu-id="e4a90-141">若要變更傳送電子郵件給使用者的電子郵件地址，您必須：</span><span class="sxs-lookup"><span data-stu-id="e4a90-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="e4a90-142">在  _SendEmailFromAddress 參數中輸入_ 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e4a90-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="e4a90-143">在  _SendEmailFromDisplayName 參數中輸入電子郵件顯示_ 名稱。</span><span class="sxs-lookup"><span data-stu-id="e4a90-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="e4a90-144">將  _SendEmailOverride 參數_ 設為  _True_。</span><span class="sxs-lookup"><span data-stu-id="e4a90-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="e4a90-145">您可以對寄給使用者的電子郵件進行變更，例如電子郵件的寄回電子郵件地址和電子郵件的顯示名稱，方式如下：</span><span class="sxs-lookup"><span data-stu-id="e4a90-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="e4a90-146">如果您想要變更電子郵件地址資訊，您必須確定您環境的輸入電子郵件政策允許來自從位址指定的自訂電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e4a90-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="e4a90-147">如果您決定要取代 From *連絡人資訊* ，您應該確認電子郵件已正確發送給使用者。</span><span class="sxs-lookup"><span data-stu-id="e4a90-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="e4a90-148">您可以與貴組織的一個使用者測試這項功能，以執行此操作。</span><span class="sxs-lookup"><span data-stu-id="e4a90-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="e4a90-149">您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) Cmdlet 來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e4a90-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="e4a90-150">如果您不希望電子郵件寄給他們，該怎麼處理？</span><span class="sxs-lookup"><span data-stu-id="e4a90-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="e4a90-151">當您停用傳送電子郵件給使用者時，即使使用者獲得授權，也不會傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e4a90-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="e4a90-152">在這種情況下，會議 ID、預設會議電話號碼，以及更重要的是，其音訊會議 PIN 不會發送給使用者。</span><span class="sxs-lookup"><span data-stu-id="e4a90-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="e4a90-153">發生此情況時，您必須傳送另一封電子郵件或打電話給使用者，告知使用者。</span><span class="sxs-lookup"><span data-stu-id="e4a90-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="e4a90-154">根據預設，電子郵件會寄給您的使用者，但如果您想要防止他們收到音訊會議電子郵件，您可以使用 商務用 Skype 系統管理中心或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e4a90-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="e4a90-155">![使用系統管理中心商務用 Skype ](../images/sfb-logo-30x30.png) **圖示商務用 Skype標誌**  </span><span class="sxs-lookup"><span data-stu-id="e4a90-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="e4a90-156">在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="e4a90-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="e4a90-157">在 **Microsoft 橋接器設定頁面上** ，選取或清除如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="e4a90-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="e4a90-158">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="e4a90-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="e4a90-159">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e4a90-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="e4a90-160">執行下列操作以停用傳送所有使用者的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="e4a90-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="e4a90-161">您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) Cmdlet 來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e4a90-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="e4a90-162">關於此電子郵件，您還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="e4a90-162">What else should you know about this email?</span></span>

- <span data-ttu-id="e4a90-163">有關啟用及停用自動傳送電子郵件給使用者的更多資訊，請參閱在音訊會議設定變更時啟用或停用 [傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a90-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="e4a90-164">有時候使用者會失去音訊資訊，而您必須能夠傳送所有音訊資訊給他們。</span><span class="sxs-lookup"><span data-stu-id="e4a90-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="e4a90-165">您可以使用系統管理中心，商務用 Skype音訊會議內容下的按一下以電子郵件傳送會議資訊。</span><span class="sxs-lookup"><span data-stu-id="e4a90-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="e4a90-166">請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a90-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="e4a90-167">不過，這項資訊不包含音訊會議 PIN。</span><span class="sxs-lookup"><span data-stu-id="e4a90-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="e4a90-168">以下是將寄給他們的此電子郵件範例：</span><span class="sxs-lookup"><span data-stu-id="e4a90-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![電話撥入式會議電子郵件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e4a90-170">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="e4a90-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e4a90-171">根據預設，電子郵件的寄件者會來自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) Cmdlet 來變更電子郵件地址和顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="e4a90-171">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span>
    
- <span data-ttu-id="e4a90-172">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="e4a90-172">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e4a90-173">您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="e4a90-173">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e4a90-174">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="e4a90-174">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e4a90-175">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4a90-175">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="e4a90-176">[使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e4a90-176">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="e4a90-177">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="e4a90-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e4a90-178">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="e4a90-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e4a90-179">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="e4a90-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e4a90-180">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e4a90-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e4a90-181">使用Windows PowerShell執行線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="e4a90-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="e4a90-182">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。</span><span class="sxs-lookup"><span data-stu-id="e4a90-182">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="e4a90-183">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 模組商務用 Skype[下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="e4a90-183">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e4a90-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="e4a90-184">Related topics</span></span>

[<span data-ttu-id="e4a90-185">啟用或停用音訊會議設定變更時傳送電子郵件的設定</span><span class="sxs-lookup"><span data-stu-id="e4a90-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="e4a90-186">傳送內含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="e4a90-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
