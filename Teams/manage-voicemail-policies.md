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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 管理使用者的語音信箱政策。
ms.openlocfilehash: 213908183c0d1dc608626272c0ea8aa5af308aff
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796900"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="27e0d-103">在貴組織中設定語音信箱政策</span><span class="sxs-lookup"><span data-stu-id="27e0d-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="27e0d-104">針對商務用 Skype，透過通話Microsoft Teams停用語音信箱也可以停用您的語音信箱服務商務用 Skype使用者。</span><span class="sxs-lookup"><span data-stu-id="27e0d-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="27e0d-105">語音信箱文字翻譯預設為啟用，且所有組織和使用者預設會停用聽寫不全遮罩功能;不過，您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 和 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet 來控制它們。</span><span class="sxs-lookup"><span data-stu-id="27e0d-105">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="27e0d-106">貴組織中使用者收到的語音信箱訊息，會于貴組織或組織Microsoft 365 Office 365轉譯。</span><span class="sxs-lookup"><span data-stu-id="27e0d-106">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="27e0d-107">您的租使用者所在的區域可能與接收語音信箱訊息的使用者所在的地區不同。</span><span class="sxs-lookup"><span data-stu-id="27e0d-107">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="27e0d-108">若要查看租使用者託管的地區，請前往 [組織設定檔頁面面 [](https://go.microsoft.com/fwlink/p/?linkid=2067339)，然後按一下 [**資料** 位置旁的 **[查看詳細資料**> 。</span><span class="sxs-lookup"><span data-stu-id="27e0d-108">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27e0d-109">您無法使用 **New-CsOnlineVoiceMailPolicy** Cmdlet 建立新原則實例進行轉錄和轉錄不全遮罩，而且無法使用 **Remove-CsOnlineVoiceMailPolicy** Cmdlet 移除現有的原則實例。</span><span class="sxs-lookup"><span data-stu-id="27e0d-109">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="27e0d-110">您可以使用語音信箱策略管理使用者的抄寫設定。</span><span class="sxs-lookup"><span data-stu-id="27e0d-110">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="27e0d-111">若要查看所有可用的語音信箱策略實例，您可以使用 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27e0d-111">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="27e0d-112">關閉貴組織的轉錄</span><span class="sxs-lookup"><span data-stu-id="27e0d-112">Turning off transcription for your organization</span></span>

<span data-ttu-id="27e0d-113">由於貴組織的文字翻譯預設設定為已啟用，因此您可能會想要使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)來停用此設定。</span><span class="sxs-lookup"><span data-stu-id="27e0d-113">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="27e0d-114">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="27e0d-114">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="27e0d-115">為貴組織開啟文字翻譯不全遮罩功能</span><span class="sxs-lookup"><span data-stu-id="27e0d-115">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="27e0d-116">根據預設，貴組織會停用文字不全遮罩功能。</span><span class="sxs-lookup"><span data-stu-id="27e0d-116">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="27e0d-117">如果有啟用這項功能的商業需求，您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)啟用文字翻譯不端遮罩。</span><span class="sxs-lookup"><span data-stu-id="27e0d-117">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="27e0d-118">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="27e0d-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="27e0d-119">關閉使用者的轉錄</span><span class="sxs-lookup"><span data-stu-id="27e0d-119">Turning off transcription for a user</span></span>

<span data-ttu-id="27e0d-120">在組織預設設定之前，會先評估使用者政策。</span><span class="sxs-lookup"><span data-stu-id="27e0d-120">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="27e0d-121">例如，如果所有使用者都已啟用語音信箱轉錄功能，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派策略來停用特定使用者的轉寫功能。</span><span class="sxs-lookup"><span data-stu-id="27e0d-121">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="27e0d-122">若要停用單一使用者的抄寫，請執行：</span><span class="sxs-lookup"><span data-stu-id="27e0d-122">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="27e0d-123">為使用者開啟文字翻譯不全遮罩功能</span><span class="sxs-lookup"><span data-stu-id="27e0d-123">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="27e0d-124">若要為特定使用者啟用文字翻譯不全遮罩，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派原則，為特定使用者啟用轉錄不端遮罩。</span><span class="sxs-lookup"><span data-stu-id="27e0d-124">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="27e0d-125">若要為單一使用者啟用文字翻譯不全遮罩，請執行：</span><span class="sxs-lookup"><span data-stu-id="27e0d-125">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="27e0d-126">語音信箱服務Microsoft 365 Office 365語音信箱政策，並每隔 6 小時更新一次。</span><span class="sxs-lookup"><span data-stu-id="27e0d-126">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="27e0d-127">因此，您進行的政策變更最多可能需要 6 小時才能適用。</span><span class="sxs-lookup"><span data-stu-id="27e0d-127">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
