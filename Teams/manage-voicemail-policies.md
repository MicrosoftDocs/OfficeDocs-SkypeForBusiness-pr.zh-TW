---
title: 管理語音信箱政策
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 管理使用者的語音信箱政策。
ms.openlocfilehash: 275c67cef3a318d15f030f26aa50a74a15748c03
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604422"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>在貴組織中設定語音信箱政策

> [!WARNING]
> 針對商務用 Skype，透過通話Microsoft Teams停用語音信箱，也可能停用您的語音信箱服務商務用 Skype使用者。

## <a name="voicemail-organization-defaults-for-all-users"></a>所有使用者的語音信箱組織預設值
- 語音信箱文字翻譯已啟用。
- 語音信箱語音信箱翻譯不聽障遮罩功能已停用。
- 錄製持續時間上限設定為 5 分鐘。

您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 和 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet 來控制這些預設值。

貴組織中使用者收到的語音信箱訊息會轉譯至貴組織或Microsoft 365 Office 365地區。 您的租使用者所在的區域可能與接收語音信箱訊息的使用者所在的地區不同。 若要查看租使用者託管的地區，請前往 [組織設定檔頁面面 [](https://go.microsoft.com/fwlink/p/?linkid=2067339)，然後按一下 [**資料** 位置旁的 **[查看詳細資料**> 。

> [!IMPORTANT]
> 您無法使用 **New-CsOnlineVoiceMailPolicy** Cmdlet 建立新的原則實例來進行轉錄和轉錄不端遮罩，而且您也無法使用 **Remove-CsOnlineVoiceMailPolicy** Cmdlet 移除現有的原則實例。

您可以使用語音信箱策略管理使用者的抄寫設定。 若要查看所有可用的語音信箱策略實例，您可以使用 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet。

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
  
## <a name="turning-off-transcription-for-your-organization"></a>關閉貴組織的轉錄

由於貴組織的文字翻譯預設設定為已啟用，因此您可能會想要使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)來停用此設定。 若要這麼做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>為貴組織開啟文字翻譯不全遮罩功能

根據預設，貴組織會停用文字不全遮罩功能。 如果有啟用這項功能的商業需求，您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)啟用文字翻譯不端遮罩。 若要這麼做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>變更貴組織的錄製持續時間

根據預設，貴組織的錄製長度上限為五分鐘。 如果業務需要增加或減少錄製長度上限，可以使用 [Set-CsOnlineVoicemailPolicy 來達到此目標](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)。 例如，若要將錄製時間上限設為 60 秒，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>貴組織的雙語言系統提示

根據預設，語音信箱系統提示會以使用者設定語音信箱時所選取的語言呈現給來電者。 如果商務需要以兩種語言呈現語音信箱系統提示，可以使用 [Set-CsOnlineVoicemailPolicy 完成這項操作](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)。 必須設定主要和次要語言，而且可能不同。 若要這麼做，請執行：

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>關閉使用者的轉錄

在組織預設設定之前，會先評估使用者政策。 例如，如果所有使用者都已啟用語音信箱轉錄功能，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派一個策略來停用特定使用者的轉寫功能。

若要停用單一使用者的抄寫，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>為使用者開啟文字翻譯不全遮罩功能

若要為特定使用者啟用文字翻譯不全遮罩，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派原則，為特定使用者啟用轉錄不端遮罩。

若要為單一使用者啟用文字翻譯不全遮罩，請執行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>變更使用者的錄製持續時間

您必須先使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Cmdlet 建立自訂語音信箱策略。 下列命令會建立每個使用者的線上語音信箱策略 OneMinuteVoicemailPolicy，其中 MaximumRecordingLength 設定為 60 秒，其他欄位則設為租使用者層級全域值。

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

若要將此自訂策略指派給使用者，請執行： 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>使用者需要雙語言系統提示

您必須先使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Cmdlet 建立自訂語音信箱策略。 下列命令會建立每個使用者的線上語音信箱策略 enUS-esSP-VoicemailPolicy，且 PrimarySystemPromptLanguage 設定為 en-US (英文 - 美國) ，而 SecondarySystemPromptLanguage 設為 es-SP (西班牙文 - 西班牙) 。

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

若要將此自訂策略指派給使用者，請執行： 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> Cmdlet Get-CsOnlineVoicemailPolicy目前不會返回 PrimarySystemPromptLanguage 和 SecondarySystemPromptLanguage 的值。 若要查看這些值，請修改命令，如下所示：
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> 使用 **策略名稱取代 PolicyName。**


> [!IMPORTANT]
> 語音信箱服務Microsoft 365 Office 365語音信箱政策，並每隔 6 小時更新一次。 因此，您進行的政策變更最多可能需要 6 小時才能適用。
