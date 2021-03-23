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
ms.openlocfilehash: fa30184d38822141d0f30404fb55b79eefd5d33d
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997421"
---
# <a name="set-up-cloud-voicemail"></a>設定 [雲端語音信箱]

本文適用于 Microsoft 365 或 Office 365 系統管理員[](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)，如想要為商務中每個人設定雲端語音信箱功能之系統管理員角色中所述。

> [!NOTE]
> 雲端語音信箱僅支援將語音信箱中的語音信箱訊息存入，且不支援任何協力廠商電子郵件系統。 

> [!NOTE]
> 當代理人代表委派者接聽來電時，雲端語音信箱中無法提供通知。 使用者可以接收未接來電的通知。

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>雲端環境：為線上電話系統使用者設定雲端語音信箱

針對線上電話系統使用者，在您指派電話系統授權給使用者之後，系統會自動為使用者設定和設定雲端語音信箱。 

> [!NOTE]
> 對於擁有內部部署提供電話號碼的線上商務用 Skype Phone System 使用者，您可能需要使用 [Set-CsUser -HostedVoicemail](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)$True。 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>設定 Exchange Server 信箱使用者的雲端語音信箱

下列資訊是有關將雲端語音信箱配置為與線上使用電話系統，但在 Exchange Server 上擁有信箱的使用者合作。 
  
1. 語音信箱訊息會透過透過 Exchange Online Protection 路由的 SMTP 傳送到使用者的 Exchange 信箱。 若要順利傳遞這些郵件，請確定 Exchange 連接器在 Exchange 伺服器和 Exchange Online Protection 之間已正確配置; [使用連接器設定郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。 

2. 若要啟用語音信箱功能，例如自訂商務用 Skype 用戶端的問候語和視覺語音信箱，必須透過 Exchange Web Services 從 Microsoft 365 或 Office 365 連接到 Exchange 伺服器信箱。 若要啟用此連線，您必須設定 Exchange 與 Exchange Online 組織之間設定 [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)驗證中所述的新 Exchange 組織驗證通訊協定，或執行 Exchange 2013 CU5 或更大的 Exchange 混合式精靈。 此外，您必須在商務用 Skype Online 和 Exchange 伺服器之間設定整合和在商務用 Skype Online 和 Exchange Server 之間設定整合與 OAuth 中所述的 [整合和統](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)一。 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>設定商務用 Skype Server 使用者的雲端語音信箱

若要將商務用 Skype 伺服器使用者設定為雲端語音信箱，請參閱為內部部署使用者規劃雲端 [語音信箱服務](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>在貴組織中啟用受保護的語音信箱

當某人為貴組織的使用者留下語音信箱訊息時，語音信箱會以電子郵件訊息附件形式傳送到使用者的信箱。 使用郵件流程規則來適用郵件加密，您可以防止這些語音信箱訊息轉寄給其他收件者。 當您啟用受保護的語音信箱時，使用者可以在語音信箱中通話，或在 Outlook、Outlook 網頁版或 Android 版或 iOS 版 Outlook 中開啟郵件，以聆聽受保護的語音信箱訊息。 受保護的語音信箱訊息無法于商務用 Skype 或 Microsoft Teams 中開啟。

有關郵件加密的資訊，請參閱 [電子郵件加密](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)。

若要設定受保護的語音信箱，請執行下列操作：

1. 使用具有全域系統管理員許可權的帳戶 https://admin.microsoft.com 前往並登錄。
2. 選取 **顯示全部**，然後前往 **系統管理中心**  >  **Exchange**。
3. 在 Exchange 系統管理中心中，選取 **郵件流程**  >  **規則**。
4. 選取 **+** **新增**，然後選取 **將 Office 365 郵件加密和許可權保護適用于郵件**。
5. 提供新郵件流程規則的名稱，然後在下列的下列條件中選取郵件屬性 ：包括語音  >    >  **信箱的郵件類型**。 選取 **確定**。
6. 在 **執行下列操作下**，選取 **將 Office 365** 郵件加密和許可權保護適用于郵件，然後選取選取 **其中一個**。 在 **RMS 範本下**，選取 請勿 **轉出**。 選取 **確定** ，然後 **儲存**。
    > [!NOTE]
    > 如果 **RMS 範本** 清單是空的，您必須設定郵件加密。 有關設定郵件加密的資訊，請參閱下列文章：
    > - [設定新的郵件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [建立及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [電子郵件的請勿轉轉選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>在貴組織中設定語音信箱政策

> [!WARNING]
> 針對商務用 Skype 客戶，透過 Microsoft Teams 通話政策停用語音信箱也可能停用商務用 Skype 使用者的語音信箱服務。

語音信箱文字翻譯預設為啟用，且所有組織和使用者預設會停用聽寫不全遮罩功能;不過，您可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) Cmdlet 來控制它們。

貴組織中使用者收到的語音信箱訊息會轉譯至您的 Microsoft 365 或 Office 365 組織託管地區。 您的租使用者所在的區域可能與接收語音信箱訊息的使用者所在的地區不同。 若要查看租使用者託管的地區，請前往 [組織設定檔頁面面 [](https://go.microsoft.com/fwlink/p/?linkid=2067339)，然後按一下 [**資料** 位置旁的 **[查看詳細資料**> 。

> [!IMPORTANT]
> 您無法使用 **New-CsOnlineVoiceMailPolicy** Cmdlet 建立新原則實例進行轉錄和轉錄不端遮罩，而且無法使用 **Remove-CsOnlineVoiceMailPolicy** Cmdlet 移除現有的原則實例。

您可以使用語音信箱策略管理使用者的抄寫設定。 若要查看所有可用的語音信箱策略實例，您可以使用 [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) Cmdlet。

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
  
### <a name="turning-off-transcription-for-your-organization"></a>關閉貴組織的轉錄

由於貴組織的文字翻譯預設設定為已啟用，因此您可能會想要使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)來停用此設定。 若要這麼做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>為貴組織開啟文字翻譯不全遮罩功能

根據預設，貴組織會停用文字不全遮罩功能。 如果有啟用這項功能的商業需求，您可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)啟用文字翻譯不端遮罩。 若要這麼做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>關閉使用者的轉錄

在組織預設設定之前，會先評估使用者政策。 例如，如果所有使用者已啟用語音信箱轉錄功能，您可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet 指派一個策略來停用特定使用者的轉寫功能。

若要停用單一使用者的抄寫，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>為使用者開啟文字翻譯不全遮罩

若要為特定使用者啟用文字翻譯不全遮罩，您可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet 指派原則，為特定使用者啟用轉錄不端遮罩。

若要為單一使用者啟用文字翻譯不全遮罩，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Microsoft 365 和 Office 365 中的語音信箱服務會每隔 4 小時會緩存語音信箱政策並更新該緩存。 因此，您進行的政策變更最多可能需要 4 小時才能適用。

## <a name="help-your-users-learn-teams-voicemail-features"></a>協助使用者瞭解 Teams 語音信箱功能

我們有下列資訊可讓使用者管理語音信箱設定，以及 Teams 中的其他通話功能：

- [在 Teams 中管理您的通話設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。 本文說明如何管理所有使用者 Teams 通話功能。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>協助使用者瞭解商務用 Skype 語音信箱功能

我們有訓練資訊和文章，可協助使用者順利使用商務用 Skype 語音信箱。 指向下列文章：

- [檢查商務](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)用 Skype 語音信箱和選項：本文說明如何在商務用 Skype 中聆聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同速度聆聽語音信箱。

- [商務用 Skype 2016 訓練](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[規劃商務用 Skype 和 Exchange Server 的先決條件的移轉](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
