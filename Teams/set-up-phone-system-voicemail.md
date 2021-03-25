---
title: 設定 [雲端語音信箱]
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '瞭解如何為使用者設定雲端語音信箱。 '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117061"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="a3528-103">設定 [雲端語音信箱]</span><span class="sxs-lookup"><span data-stu-id="a3528-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="a3528-104">本文適用于 Microsoft 365 或 Office 365 系統管理員[](/microsoft-365/admin/add-users/about-admin-roles)，如想要為商務中的每個人設定雲端語音信箱功能之系統管理員角色中所述。</span><span class="sxs-lookup"><span data-stu-id="a3528-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="a3528-105">雲端語音信箱僅支援將語音信箱中的語音信箱訊息存入，且不支援任何協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="a3528-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="a3528-106">當代理人代表委派者接聽來電時，雲端語音信箱中無法提供通知。</span><span class="sxs-lookup"><span data-stu-id="a3528-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="a3528-107">使用者可以接收未接來電的通知。</span><span class="sxs-lookup"><span data-stu-id="a3528-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="a3528-108">雲端環境：為線上電話系統使用者設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a3528-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="a3528-109">針對線上電話系統使用者，在您指派電話系統授權給使用者之後，系統會自動為使用者設定和設定雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a3528-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="a3528-110">對於提供內部部署電話號碼的線上商務用 Skype Phone System 使用者，您可能需要啟用 [Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)$True。</span><span class="sxs-lookup"><span data-stu-id="a3528-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="a3528-111">設定 Exchange Server 信箱使用者的雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a3528-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="a3528-112">下列資訊是有關將雲端語音信箱配置為與線上使用電話系統，但在 Exchange Server 上擁有信箱的使用者合作。</span><span class="sxs-lookup"><span data-stu-id="a3528-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="a3528-113">語音信箱訊息會透過透過 Exchange Online Protection 路由的 SMTP 傳送到使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="a3528-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="a3528-114">若要順利傳遞這些郵件，請確定 Exchange 連接器在 Exchange 伺服器和 Exchange Online Protection 之間已正確配置; [使用連接器設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="a3528-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="a3528-115">若要啟用語音信箱功能，例如自訂商務用 Skype 用戶端的問候語和視覺語音信箱，必須透過 Exchange Web Services 從 Microsoft 365 或 Office 365 連接到 Exchange 伺服器信箱。</span><span class="sxs-lookup"><span data-stu-id="a3528-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="a3528-116">若要啟用此連線，您必須設定 Exchange 與 Exchange Online 組織之間設定 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述的新 Exchange 組織驗證通訊協定，或執行 Exchange 2013 CU5 或更大的 Exchange 混合式精靈。</span><span class="sxs-lookup"><span data-stu-id="a3528-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="a3528-117">此外，您必須在商務用 Skype Online 和 Exchange 伺服器之間設定整合和在商務用 Skype Online 和 Exchange Server 之間設定整合與 OAuth 中所述的 [整合和統](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)一。</span><span class="sxs-lookup"><span data-stu-id="a3528-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="a3528-118">設定商務用 Skype Server 使用者的雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a3528-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="a3528-119">若要為雲端語音信箱設定商務用 Skype 伺服器使用者，請參閱為內部部署使用者規劃雲端 [語音信箱服務](/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="a3528-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="a3528-120">在貴組織中啟用受保護的語音信箱</span><span class="sxs-lookup"><span data-stu-id="a3528-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="a3528-121">當某人為貴組織的使用者留下語音信箱訊息時，語音信箱會以電子郵件訊息附件形式傳送到使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="a3528-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="a3528-122">您可以使用郵件流程規則來申請郵件加密，以防止這些語音信箱訊息轉寄給其他收件者。</span><span class="sxs-lookup"><span data-stu-id="a3528-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="a3528-123">當您啟用受保護的語音信箱時，使用者可以在語音信箱中通話，或在 Outlook、Outlook 網頁版或 Android 版或 iOS 版 Outlook 中開啟郵件，以聆聽受保護的語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="a3528-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="a3528-124">受保護的語音信箱訊息無法于商務用 Skype 或 Microsoft Teams 中開啟。</span><span class="sxs-lookup"><span data-stu-id="a3528-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="a3528-125">有關郵件加密的資訊，請參閱 [電子郵件加密](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="a3528-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="a3528-126">若要設定受保護的語音信箱，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a3528-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="a3528-127">使用 https://admin.microsoft.com 具有全域系統管理員許可權的帳戶前往並登錄。</span><span class="sxs-lookup"><span data-stu-id="a3528-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="a3528-128">選取 **顯示全部**，然後前往 **系統管理中心**  >  **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="a3528-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="a3528-129">在 Exchange 系統管理中心中，選取 **郵件流程**  >  **規則**。</span><span class="sxs-lookup"><span data-stu-id="a3528-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="a3528-130">選取 **+** **新增**，然後選取 **將 Office 365 郵件加密和許可權保護適用于郵件**。</span><span class="sxs-lookup"><span data-stu-id="a3528-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="a3528-131">提供新郵件流程規則的名稱，然後在下列的下列條件中選取郵件屬性 ：包括  >    >  **語音信箱的郵件類型**。</span><span class="sxs-lookup"><span data-stu-id="a3528-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="a3528-132">選取 **確定**。</span><span class="sxs-lookup"><span data-stu-id="a3528-132">Select **OK**.</span></span>
6. <span data-ttu-id="a3528-133">在 **執行下列操作下**，選取 **將 Office 365** 郵件加密和許可權保護適用于郵件，然後選取選取 **其中一個**。</span><span class="sxs-lookup"><span data-stu-id="a3528-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="a3528-134">在 **RMS 範本下**，選取 **不要轉出**。</span><span class="sxs-lookup"><span data-stu-id="a3528-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="a3528-135">選取 **確定** ，然後 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="a3528-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="a3528-136">如果 **RMS 範本** 清單是空的，您必須設定郵件加密。</span><span class="sxs-lookup"><span data-stu-id="a3528-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="a3528-137">有關設定郵件加密的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a3528-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="a3528-138">設定新的郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="a3528-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="a3528-139">為 Azure 資訊保護組組及管理範本</span><span class="sxs-lookup"><span data-stu-id="a3528-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="a3528-140">電子郵件的請勿轉轉選項</span><span class="sxs-lookup"><span data-stu-id="a3528-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="a3528-141">在組織中設定語音信箱政策</span><span class="sxs-lookup"><span data-stu-id="a3528-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="a3528-142">針對商務用 Skype 客戶，透過 Microsoft Teams 通話政策停用語音信箱也可能停用商務用 Skype 使用者的語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="a3528-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="a3528-143">語音信箱文字翻譯預設為啟用，且所有組織和使用者預設會停用聽寫不全遮罩功能;不過，您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 和 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet 來控制它們。</span><span class="sxs-lookup"><span data-stu-id="a3528-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="a3528-144">貴組織中使用者收到的語音信箱訊息會轉譯至您的 Microsoft 365 或 Office 365 組織託管地區。</span><span class="sxs-lookup"><span data-stu-id="a3528-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="a3528-145">您的租使用者所在的區域可能與接收語音信箱訊息的使用者所在的地區不同。</span><span class="sxs-lookup"><span data-stu-id="a3528-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="a3528-146">若要查看租使用者託管的地區，請前往 [組織設定檔頁面面 [](https://go.microsoft.com/fwlink/p/?linkid=2067339)，然後按一下 [**資料** 位置旁的 **[查看詳細資料**> 。</span><span class="sxs-lookup"><span data-stu-id="a3528-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3528-147">您無法使用 **New-CsOnlineVoiceMailPolicy** Cmdlet 建立新原則實例進行轉錄和轉錄不端遮罩，而且無法使用 **Remove-CsOnlineVoiceMailPolicy** Cmdlet 移除現有的原則實例。</span><span class="sxs-lookup"><span data-stu-id="a3528-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="a3528-148">您可以使用語音信箱策略管理使用者的抄寫設定。</span><span class="sxs-lookup"><span data-stu-id="a3528-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="a3528-149">若要查看所有可用的語音信箱策略實例，您可以使用 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3528-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="a3528-150">關閉貴組織的轉錄</span><span class="sxs-lookup"><span data-stu-id="a3528-150">Turning off transcription for your organization</span></span>

<span data-ttu-id="a3528-151">由於貴組織的文字翻譯預設設定為已啟用，因此您可能會想要使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)來停用。</span><span class="sxs-lookup"><span data-stu-id="a3528-151">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="a3528-152">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="a3528-152">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="a3528-153">為貴組織開啟文字翻譯不全遮罩功能</span><span class="sxs-lookup"><span data-stu-id="a3528-153">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="a3528-154">根據預設，貴組織會停用文字不全遮罩功能。</span><span class="sxs-lookup"><span data-stu-id="a3528-154">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="a3528-155">如果有啟用這項功能的商業需求，您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)啟用文字翻譯不端遮罩。</span><span class="sxs-lookup"><span data-stu-id="a3528-155">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="a3528-156">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="a3528-156">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="a3528-157">關閉使用者的轉錄</span><span class="sxs-lookup"><span data-stu-id="a3528-157">Turning off transcription for a user</span></span>

<span data-ttu-id="a3528-158">在組織預設設定之前，會先評估使用者政策。</span><span class="sxs-lookup"><span data-stu-id="a3528-158">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="a3528-159">例如，如果所有使用者都已啟用語音信箱轉錄功能，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派策略來停用特定使用者的轉寫功能。</span><span class="sxs-lookup"><span data-stu-id="a3528-159">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="a3528-160">若要停用單一使用者的抄寫，請執行：</span><span class="sxs-lookup"><span data-stu-id="a3528-160">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="a3528-161">為使用者開啟文字翻譯不全遮罩功能</span><span class="sxs-lookup"><span data-stu-id="a3528-161">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="a3528-162">若要為特定使用者啟用文字翻譯不全遮罩，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派原則，為特定使用者啟用轉錄不全遮罩。</span><span class="sxs-lookup"><span data-stu-id="a3528-162">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="a3528-163">若要為單一使用者啟用文字翻譯不全遮罩，請執行：</span><span class="sxs-lookup"><span data-stu-id="a3528-163">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="a3528-164">Microsoft 365 和 Office 365 中的語音信箱服務會每隔 4 小時會緩存語音信箱政策並更新該緩存。</span><span class="sxs-lookup"><span data-stu-id="a3528-164">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="a3528-165">因此，您進行的政策變更最多可能需要 4 小時才能適用。</span><span class="sxs-lookup"><span data-stu-id="a3528-165">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="a3528-166">協助使用者瞭解 Teams 語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="a3528-166">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="a3528-167">我們針對您的使用者在 Teams 中管理語音信箱設定及其他通話功能，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a3528-167">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="a3528-168">[在 Teams 中管理您的通話設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="a3528-168">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="a3528-169">本文將說明如何管理所有使用者 Teams 通話功能。</span><span class="sxs-lookup"><span data-stu-id="a3528-169">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="a3528-170">協助使用者瞭解商務用 Skype 語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="a3528-170">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="a3528-171">我們有訓練資訊和文章，可協助使用者順利使用商務用 Skype 語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a3528-171">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="a3528-172">指向下列文章：</span><span class="sxs-lookup"><span data-stu-id="a3528-172">Point them to the following articles:</span></span>

- <span data-ttu-id="a3528-173">[檢查商務](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)用 Skype 語音信箱和選項：本文說明如何在商務用 Skype 中聆聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同速度聆聽語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a3528-173">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="a3528-174">商務用 Skype 2016 訓練</span><span class="sxs-lookup"><span data-stu-id="a3528-174">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="a3528-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="a3528-175">Related topics</span></span>
[<span data-ttu-id="a3528-176">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="a3528-176">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="a3528-177">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="a3528-177">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="a3528-178">規劃商務用 Skype 和 Exchange Server 的先決條件的移轉</span><span class="sxs-lookup"><span data-stu-id="a3528-178">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)