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
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910055"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="8e800-103">在組織中設定語音信箱政策</span><span class="sxs-lookup"><span data-stu-id="8e800-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="8e800-104">針對商務用 Skype，透過通話Microsoft Teams停用語音信箱，也可能停用您的語音信箱服務商務用 Skype使用者。</span><span class="sxs-lookup"><span data-stu-id="8e800-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="8e800-105">所有使用者的語音信箱組織預設值</span><span class="sxs-lookup"><span data-stu-id="8e800-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="8e800-106">語音信箱文字翻譯已啟用。</span><span class="sxs-lookup"><span data-stu-id="8e800-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="8e800-107">語音信箱語音信箱聽寫不聽的遮罩功能已停用。</span><span class="sxs-lookup"><span data-stu-id="8e800-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="8e800-108">錄製持續時間上限設定為 5 分鐘。</span><span class="sxs-lookup"><span data-stu-id="8e800-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="8e800-109">您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 和 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet 控制這些預設值。</span><span class="sxs-lookup"><span data-stu-id="8e800-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="8e800-110">貴組織中使用者收到的語音信箱訊息會轉譯至貴組織或Microsoft 365 Office 365的地區。</span><span class="sxs-lookup"><span data-stu-id="8e800-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="8e800-111">您的租使用者所在的區域可能與接收語音信箱訊息的使用者所在的地區不同。</span><span class="sxs-lookup"><span data-stu-id="8e800-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="8e800-112">若要查看租使用者託管的地區，請前往 [組織設定檔頁面面 [](https://go.microsoft.com/fwlink/p/?linkid=2067339)，然後按一下 [**資料** 位置旁的 **[查看詳細資料**> 。</span><span class="sxs-lookup"><span data-stu-id="8e800-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e800-113">您無法使用 **New-CsOnlineVoiceMailPolicy** Cmdlet 建立新原則實例進行轉錄和轉錄不全遮罩，而且無法使用 **Remove-CsOnlineVoiceMailPolicy** Cmdlet 移除現有的原則實例。</span><span class="sxs-lookup"><span data-stu-id="8e800-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="8e800-114">您可以使用語音信箱策略管理使用者的抄寫設定。</span><span class="sxs-lookup"><span data-stu-id="8e800-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="8e800-115">若要查看所有可用的語音信箱策略實例，您可以使用 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8e800-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="8e800-116">關閉貴組織的轉錄</span><span class="sxs-lookup"><span data-stu-id="8e800-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="8e800-117">由於貴組織的文字翻譯預設設定為已啟用，因此您可能會想要使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)來停用。</span><span class="sxs-lookup"><span data-stu-id="8e800-117">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="8e800-118">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="8e800-119">為貴組織開啟文字翻譯不全遮罩功能</span><span class="sxs-lookup"><span data-stu-id="8e800-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="8e800-120">根據預設，貴組織會停用文字不全遮罩功能。</span><span class="sxs-lookup"><span data-stu-id="8e800-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="8e800-121">如果有啟用這項功能的商業需求，您可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)啟用文字翻譯不端遮罩。</span><span class="sxs-lookup"><span data-stu-id="8e800-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="8e800-122">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="8e800-123">變更貴組織的錄製持續時間</span><span class="sxs-lookup"><span data-stu-id="8e800-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="8e800-124">根據預設，貴組織的錄製長度上限為五分鐘。</span><span class="sxs-lookup"><span data-stu-id="8e800-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="8e800-125">如果業務需要增加或減少錄製長度上限，可以使用 [Set-CsOnlineVoicemailPolicy 來達到此目標](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)。</span><span class="sxs-lookup"><span data-stu-id="8e800-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="8e800-126">例如，若要將錄製時間上限設為 60 秒，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="8e800-127">貴組織的雙語言系統提示</span><span class="sxs-lookup"><span data-stu-id="8e800-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="8e800-128">根據預設，語音信箱系統提示會以使用者設定語音信箱時所選取的語言呈現給來電者。</span><span class="sxs-lookup"><span data-stu-id="8e800-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="8e800-129">如果商務需要以兩種語言呈現語音信箱系統提示，可以使用 [Set-CsOnlineVoicemailPolicy 完成這項操作](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)。</span><span class="sxs-lookup"><span data-stu-id="8e800-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="8e800-130">必須設定主要和次要語言，而且可能不同。</span><span class="sxs-lookup"><span data-stu-id="8e800-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="8e800-131">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="8e800-132">關閉使用者的轉錄</span><span class="sxs-lookup"><span data-stu-id="8e800-132">Turning off transcription for a user</span></span>

<span data-ttu-id="8e800-133">在組織預設設定之前，會先評估使用者政策。</span><span class="sxs-lookup"><span data-stu-id="8e800-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="8e800-134">例如，如果所有使用者都已啟用語音信箱轉錄功能，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派策略來停用特定使用者的轉寫功能。</span><span class="sxs-lookup"><span data-stu-id="8e800-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="8e800-135">若要停用單一使用者的抄寫，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="8e800-136">為使用者開啟文字翻譯不全遮罩功能</span><span class="sxs-lookup"><span data-stu-id="8e800-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="8e800-137">若要為特定使用者啟用文字翻譯不全遮罩，您可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) Cmdlet 指派原則，為特定使用者啟用轉錄不全遮罩。</span><span class="sxs-lookup"><span data-stu-id="8e800-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="8e800-138">若要為單一使用者啟用文字翻譯不全遮罩，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="8e800-139">變更使用者的錄製持續時間</span><span class="sxs-lookup"><span data-stu-id="8e800-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="8e800-140">您必須先使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Cmdlet 建立自訂語音信箱策略。</span><span class="sxs-lookup"><span data-stu-id="8e800-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="8e800-141">下列命令會建立每個使用者的線上語音信箱策略 OneMinuteVoicemailPolicy，其中 MaximumRecordingLength 設定為 60 秒，其他欄位則設為租使用者層級全域值。</span><span class="sxs-lookup"><span data-stu-id="8e800-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="8e800-142">若要將此自訂策略指派給使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="8e800-143">使用者需要雙語言系統提示</span><span class="sxs-lookup"><span data-stu-id="8e800-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="8e800-144">您必須先使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Cmdlet 建立自訂語音信箱策略。</span><span class="sxs-lookup"><span data-stu-id="8e800-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="8e800-145">下列命令會建立每個使用者的線上語音信箱策略 enUS-esSP-VoicemailPolicy，且 PrimarySystemPromptLanguage 設定為 en-US (英文 - 美國) ，而 SecondarySystemPromptLanguage 設為 es-SP (西班牙文 - 西班牙) 。</span><span class="sxs-lookup"><span data-stu-id="8e800-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="8e800-146">若要將此自訂策略指派給使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="8e800-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="8e800-147">Cmdlet Get-CsOnlineVoicemailPolicy目前不會返回 PrimarySystemPromptLanguage 和 SecondarySystemPromptLanguage 的值。</span><span class="sxs-lookup"><span data-stu-id="8e800-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="8e800-148">若要查看這些值，請修改命令，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e800-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="8e800-149">使用 **策略名稱取代 PolicyName。**</span><span class="sxs-lookup"><span data-stu-id="8e800-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8e800-150">語音信箱服務Microsoft 365 Office 365語音信箱政策，並每隔 6 小時更新一次。</span><span class="sxs-lookup"><span data-stu-id="8e800-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="8e800-151">因此，您進行的政策變更最多可能需要 6 小時才能適用。</span><span class="sxs-lookup"><span data-stu-id="8e800-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
