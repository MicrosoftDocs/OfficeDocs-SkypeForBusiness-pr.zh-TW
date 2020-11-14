---
title: 設定雲端語音信箱
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
description: '瞭解如何為您的使用者設定雲端語音信箱。 '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031069"
---
# <a name="set-up-cloud-voicemail"></a>設定雲端語音信箱

本文適用于 Microsoft 365 或 Office 365 系統管理員，如想要為企業中的每個人設定雲端語音信箱功能的系統 [管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 所述。

> [!NOTE]
> 雲端語音信箱支援僅在 Exchange 信箱中存放語音信箱訊息，且不支援任何協力廠商電子郵件系統。 

> [!NOTE]
> 當代理人代表 delegator 接聽來電時，在雲端語音信箱中不提供通知。 使用者可以收到未接來電的通知。

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>僅限雲端的環境：為線上電話系統使用者設定雲端語音信箱

對於線上電話系統使用者，在您指派 **電話系統** 授權給使用者之後，系統會自動為使用者設定和設定雲端語音信箱。 

> [!NOTE]
> 針對使用內部部署提供電話號碼的線上商務用 Skype 電話系統使用者，您可能需要使用 [move-csuser-HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)啟用託管的語音信箱。 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>針對 Exchange Server 信箱使用者設定雲端語音信箱

下列資訊是關於設定雲端語音信箱，以與線上使用電話系統但其信箱在 Exchange 伺服器上的使用者搭配使用。 
  
1. 語音信箱訊息是透過透過 Exchange Online 防護路由的 SMTP 傳送給使用者的 Exchange 信箱。 若要啟用成功傳遞這些郵件，請確認 exchange 連接器已在 Exchange 伺服器與 Exchange Online 防護之間正確設定; [使用連接器來設定郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。 

2. 若要啟用語音信箱功能（例如在商務用 Skype 用戶端中自訂問候語和視覺語音信箱），必須從 Microsoft 365 或 Office 365 連線至 Exchange server 信箱。 若要啟用此連線，您必須設定 exchange [與 Exchange Online 組織之間的 [設定 Oauth 驗證](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)] 中所述的新 Exchange Oauth 驗證通訊協定，或從 EXCHANGE 2013 CU5 或更高版本執行 exchange 混合式嚮導。 此外，您必須在商務用 [Skype online 與 Exchange server 之間設定整合與 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述的商務用 skype Online 與 exchange server 之間設定整合與 oauth。 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>針對商務用 Skype Server 使用者設定雲端語音信箱

若要為雲端語音信箱設定商務用 Skype server 使用者，請參閱 [規劃雲端語音信箱服務給內部部署使用者](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>在組織中啟用受保護的語音信箱

當有人在您的組織中為使用者留下語音信箱訊息時，語音信箱會以電子郵件附件的形式傳送到使用者的信箱。 使用郵件流程規則來套用郵件加密，您可以防止將這些語音信箱訊息轉寄給其他收件者。 當您啟用受保護的語音信箱時，使用者可以撥入其語音信箱信箱，或開啟 Outlook、Outlook 網頁版或 Android 版 Outlook 中的郵件，以聆聽受保護的語音信箱訊息。 受保護的語音信箱訊息無法在商務用 Skype 中開啟。

如需郵件加密的詳細資訊，請參閱 [電子郵件加密](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)。

若要設定受保護的語音信箱，請執行下列動作：

1. 移至 https://admin.microsoft.com 並使用具有全域管理員許可權的帳戶登入。
2. 選取 [ **全部顯示** ]，然後移至 [ **管理員中心** ]  >  **Exchange** 。
3. 在 Exchange Admin Center 中，選取 [ **郵件流程**  >  **規則** ]。
4. 選取 [ **+** **新增** ]，然後選取 [ **將 Office 365 郵件加密及版權保護] 套用至郵件** 。
5. 提供新郵件流程規則的名稱，然後在 [套用 **此規則** ] 底下，選取 **[** 郵件內容]，  >  **其中包含 [**  >  **語音信箱** ] 這類訊息。 選取 **[確定]** 。
6. 在 **[執行下列** 動作] 底下，選取 **[將 Office 365 郵件加密與版權保護] 給郵件** ，然後選取 [ **選取一個** ]。 在 [ **RMS 範本** ] 底下，選取 [ **不要轉寄** ]。 選取 **[確定]** ，然後選取 [ **儲存** ]。
    > [!NOTE]
    > 如果 **RMS 範本** 清單是空的，您必須設定郵件加密。 如需設定郵件加密的詳細資訊，請參閱下列文章：
    > - [設定新的郵件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [設定及管理 Azure 資訊保護範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [電子郵件的 [不要轉寄] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>設定組織中的語音信箱原則

> [!WARNING]
> 針對商務用 Skype 客戶，透過 Microsoft 團隊通話原則停用語音信箱，也可能會停用商務用 Skype 使用者的語音信箱服務。

預設會啟用語音語音功能，而且預設會針對所有組織和使用者停用「每個語言不過，您可以使用 [ [設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) ] 和 [[授與 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) ] Cmdlet 來控制它們。

貴組織中的使用者收到的語音信箱訊息是在託管 Microsoft 365 或 Office 365 組織的地區 transcribed。 您的租使用者主機所在的地區可能不是接收語音信箱訊息的使用者所在的地區。 若要查看您的租使用者所在的地區，請移至 [ [組織設定檔](https://go.microsoft.com/fwlink/p/?linkid=2067339)] 頁面，然後按一下 [ **資料位置** ] 旁的 [ **查看詳細** 資料]。

> [!IMPORTANT]
> 您無法使用 **CsOnlineVoiceMailPolicy** Cmdlet 來建立用來進行新的新原則遮罩，且無法使用 **remove-CsOnlineVoiceMailPolicy** Cmdlet 來移除現有的原則實例。

您可以使用語音信箱原則管理使用者的 [使用中] 設定。 若要查看所有可用的語音信箱原則實例，您可以使用 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) Cmdlet。

 **PS C： \\> CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy 結果] 視窗。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>關閉組織的單位

您的組織的預設設定是開啟，您可能會想要使用 [ [設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)停用它。 若要這樣做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>為您的組織開啟 [輸入猥褻遮罩]

預設情況下，您的組織會停用 [只提供猥褻遮罩] 功能。 如果有業務需求可啟用它，您可以使用 [ [設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)來啟用「轉譯猥褻遮罩」。 若要這樣做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>關閉使用者的使用者

在組織預設設定之前評估使用者原則。 例如，如果您的所有使用者都能使用語音信箱，您可以指派原則來停用授與特定使用者的 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet。

若要停用單一使用者的操作，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>為使用者開啟 [輸入猥褻遮罩]

若要針對特定的使用者啟用 [只適用于「猥褻遮罩]，您可以使用 [Grant CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet，指派原則來為特定使用者啟用「轉譯猥褻遮罩]。

若要針對單一使用者啟用 [只使用「猥褻] 遮罩，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Microsoft 365 和 Office 365 中的語音信箱服務會緩存語音信箱原則，並每4小時更新一次快取。 所以，您所做的原則變更可能需要長達4個小時才能套用。

## <a name="help-your-users-learn-teams-voicemail-features"></a>協助您的使用者瞭解團隊語音信箱功能

我們提供下列資訊，讓您的使用者管理其語音信箱設定，以及團隊中的其他通話功能。

- [在團隊中管理您的通話設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。 本文說明如何管理所有的最終使用者團隊通話功能。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>協助使用者瞭解商務用 Skype 語音信箱功能

我們有訓練資訊和文章，可協助您的使用者成功使用商務用 Skype 語音信箱。 請將它們指向下列文章：

- [查看商務用 skype 語音信箱和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文說明如何在商務用 skype 中收聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同的速度聆聽語音信箱。

- [商務用 Skype 2016 訓練](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[規劃商務用 Skype 和 Exchange Server 的先決條件的移轉](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
