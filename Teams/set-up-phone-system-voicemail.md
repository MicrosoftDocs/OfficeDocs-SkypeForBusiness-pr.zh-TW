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
ms.openlocfilehash: 4f85e8db6f50becb4ae2406e84621c08507e9737
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779729"
---
# <a name="set-up-cloud-voicemail"></a>設定雲端語音信箱

本文適用于想要為企業中的每個人設定雲端語音信箱功能的[Office 365 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。

> [!NOTE]
> 雲端語音信箱支援僅在 Exchange 信箱中存放語音信箱訊息，且不支援任何協力廠商電子郵件系統。 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>僅限雲端的環境：設定雲端語音信箱

針對商務用 Skype Online 和通話方案使用者，在您指派**電話系統**授權及電話號碼之後，就會自動為使用者設定和設定雲端語音信箱。
  
1. 如果您的方案中不包含電話系統功能，您可能需要購買 [**電話系統**附加元件授權]。 您可能也需要購買 Exchange Online 授權。 請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
2. [指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[指派 Microsoft 團隊授權](assign-teams-licenses.md)，以及 Exchange Online 授權給您企業中的人員。 完成之後，他們就可以接收語音信箱訊息了！
    
3. 已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。 您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。

## <a name="phone-system-with-on-premises-environments"></a>具有內部部署環境的電話系統

下列資訊是關於設定雲端語音信箱來與內部部署通話方案環境搭配使用。
  
1. 如果您的方案中不包含電話系統功能，您可能需要購買 [**電話系統**附加元件授權]。 您也需要購買 Exchange Online 授權。 請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
2. [指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[指派 Microsoft 團隊授權](assign-teams-licenses.md)，以及 Exchange Online 授權給您企業中的人員。
    
3. 遵循針對您的使用者部署的內部部署 PSTN 呼叫解決方案的指示。 如果是雲端連接器版本，請依照[設定商務用 Skype 雲端連接器版本指南](https://technet.microsoft.com/library/mt605228.aspx)中的 [**允許使用者使用電話系統語音及語音信箱服務**] 區段中的指示進行。 針對使用商務用 Skype Server 的 PSTN 通話，請遵循[啟用企業內部部署的使用者](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)。 針對團隊直接傳送路線，請遵循設定[直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)的 [**設定電話號碼] 和 [啟用企業語音及語音信箱**] 區段。

4. 已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。 您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。

5. 語音信箱訊息是透過透過 Exchange Online 防護路由的 SMTP 傳送給使用者的 Exchange 信箱。 若要啟用成功傳遞這些郵件，請確認 exchange 連接器已在 Exchange 伺服器與 Exchange Online 防護之間正確設定;[使用連接器來設定郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。 

6. 若要啟用語音信箱功能（例如自訂問候語），以及商務用 Skype 用戶端中的視覺語音信箱，必須從 Office 365 連線至 Exchange server 信箱（透過 Exchange Web 服務）。 若要啟用此連線，您必須設定 exchange[與 Exchange Online 組織之間的 [設定 Oauth 驗證](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)] 中所述的新 Exchange Oauth 驗證通訊協定，或從 EXCHANGE 2013 CU5 或更高版本執行 exchange 混合式嚮導。 此外，您必須在商務用[Skype online 與 Exchange server 之間設定整合與 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述的商務用 skype Online 與 exchange server 之間設定整合與 oauth。 

> [!NOTE]
> 當代理人代表 delegator 接聽來電時，在雲端語音信箱中不提供通知。 使用者可以收到未接來電的通知。

## <a name="setting-voicemail-policies-in-your-organization"></a>設定組織中的語音信箱原則

> [!WARNING]
> 針對商務用 Skype 客戶，透過 Microsoft 團隊通話原則停用語音信箱，也可能會停用商務用 Skype 使用者的語音信箱服務。

預設會啟用語音語音功能，而且預設會針對所有組織和使用者停用「每個語言不過，您可以使用 [[設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) ] 和[[授與 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) ] Cmdlet 來控制它們。

貴組織中的使用者收到的語音信箱訊息是在託管 Office 365 組織的地區 transcribed。 您的租使用者主機所在的地區可能不是接收語音信箱訊息的使用者所在的地區。 若要查看您的租使用者所在的地區，請移至 [[組織設定檔](https://go.microsoft.com/fwlink/p/?linkid=2067339)] 頁面，然後按一下 [**資料位置**] 旁的 [**查看詳細**資料]。

> [!IMPORTANT]
> 您無法使用**CsOnlineVoiceMailPolicy** Cmdlet 來建立用來進行新的新原則遮罩，且無法使用**remove-CsOnlineVoiceMailPolicy** Cmdlet 來移除現有的原則實例。

您可以使用語音信箱原則管理使用者的 [使用中] 設定。 若要查看所有可用的語音信箱原則實例，您可以使用[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) Cmdlet。

 **PS C：\\> CsOnlineVoicemailPolicy**
  
![[取得 CsOnlineVoiceMailPolicy 結果] 視窗。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>關閉組織的單位

您的組織的預設設定是開啟，您可能會想要使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)停用它。 若要這樣做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>為您的組織開啟 [輸入猥褻遮罩]

預設情況下，您的組織會停用 [只提供猥褻遮罩] 功能。 如果有業務需求可啟用它，您可以使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)來啟用「轉譯猥褻遮罩」。 若要這樣做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>關閉使用者的使用者

在組織預設設定之前評估使用者原則。 例如，如果您的所有使用者都能使用語音信箱，您可以指派原則來停用授與特定使用者的[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet。

若要停用單一使用者的操作，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>為使用者開啟 [輸入猥褻遮罩]

若要針對特定的使用者啟用 [只適用于「猥褻遮罩]，您可以使用[Grant CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet，指派原則來為特定使用者啟用「轉譯猥褻遮罩]。

若要針對單一使用者啟用 [只使用「猥褻] 遮罩，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Office 365 中的語音信箱服務會緩存語音信箱原則，並每4小時更新一次快取。 所以，您所做的原則變更可能需要長達4個小時才能套用。

## <a name="help-your-users-learn-teams-voicemail-features"></a>協助您的使用者瞭解團隊語音信箱功能

我們提供下列資訊，讓您的使用者管理其語音信箱設定，以及團隊中的其他通話功能。

- [在團隊中管理您的通話設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。 本文說明如何管理所有的最終使用者團隊通話功能。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>協助使用者瞭解商務用 Skype 語音信箱功能

我們有訓練資訊和文章，可協助您的使用者成功使用商務用 Skype 語音信箱。 請將它們指向下列文章：

- [查看商務用 skype 語音信箱和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文說明如何在商務用 skype 中收聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同的速度聆聽語音信箱。

- [商務用 Skype 2016 訓練](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[以下是您在 Office 365 中使用電話系統所取得的結果](here-s-what-you-get-with-phone-system.md)

[規劃商務用 Skype 和 Exchange Server 的先決條件的移轉](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

