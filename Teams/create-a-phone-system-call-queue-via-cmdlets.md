---
title: 透過 Cmdlet 建立通話佇列
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: 瞭解如何透過 Cmdlet 設定通話佇列
ms.openlocfilehash: f00691b037e876b7236e8ab1c8e705367dece3a4
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614356"
---
# <a name="create-a-call-queue-via-cmdlets"></a>透過 Cmdlet 建立通話佇列

## <a name="assumptions"></a>假設

1. PowerShell 已安裝在您的電腦上
   - 設定您的電腦以[進行Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - 已安裝 MSTeams 模組

     ```powershell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - 已安裝 MSOnline 模組

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. 您擁有租使用者管理許可權
3. 您已購買 Microsoft Teams 電話
4. 以下所述的代理程式、通訊群組清單和 Teams 頻道已經建立

注意：以下使用的 Teams 通道 Cmdlet 是 Teams PowerShell 模組的公開預覽版本的一部分。  如需詳細資訊，請參閱 [安裝 Teams PowerShell 公開預覽](teams-powershell-install.md) ，並參閱 [Microsoft Teams PowerShell 版本資訊](teams-powershell-release-notes.md)。

已安裝 MicrosoftTeams 模組的使用者應 `Update-Module MicrosoftTeams` 確保已安裝最新版本。

## <a name="scenario"></a>案例

將會建立下列三個通話佇列：

銷售通話佇列資訊：

- 由自動語音應答正面顯示：是
- 從 PSTN 直接撥打電話：否
- 語言：美國英文
- 問候語：無
- 等候音樂：播放音訊檔案
  - 檔案名：sales-hold-in-queue-music.wav
- 接聽電話：使用者
  - Bill@contoso.com
  - Mary@contoso.com
- 會議模式：開啟
- 路由方法：Attendant
- 目前狀態型路由：關閉
- 通話專員可以選擇不接聽電話：是
- 通話專員警示時間：15
- 通話溢位處理：200
  - 重新導向至：Adele@contoso.com
- 通話逾時處理：120 秒
  - 重新導向至：Adele@contoso.com

支援通話佇列資訊：

- 由自動語音應答正面顯示：是
- 從 PSTN 直接撥打電話：否
- 語言：英文英國
- 問候語：播放音訊檔案
  - 檔案名：support-greeting.wav
- 等候音樂：播放音訊檔案
  - 檔案名：support-hold-in-queue-music.wav
- 接聽電話：支援通訊群組清單
  - Support@contoso.com
- 會議模式：開啟
- 路由方法：最長閒置時間
- 目前狀態路由：N/A – 預設為開啟，因為最長閒置時間
- 通話專員可以選擇不接聽電話：否
- 通話專員警示時間：15
- 通話溢位處理：200
  - 重新導向：支援共用語音信箱
    - 播放音訊檔案 (support-shared-voicemail-greeting.wav) 
    - 已啟用轉譯
- 通話逾時處理：45 分鐘
  - 重新導向：支援共用語音信箱
    - TTS：「很抱歉，我們一直等著您，現在正在將您的來電轉接至語音信箱」。
    - 已啟用轉譯

設施共同作業通話佇列資訊：

- 由自動語音應答正面顯示：否
- 從 PSTN 直接通話：無 (內部通話僅) 
- 語言：法文 FR
- 問候語：無
- 等候音樂：預設
- 接聽電話：小組：設施
- 撥號接聽信道：技術支援中心
  - 頻道擁有者：Fred@contoso.com
- 會議模式：開啟
- 路由方法：Round 彥宏
- 目前狀態型路由：開啟
- 通話專員可以選擇不接聽電話：否
- 通話專員警示時間：15
- 通話溢位處理：200
  - 中斷連線
- 通話逾時處理：45 分鐘
  - 中斷連線

## <a name="login"></a>登錄

系統會提示您輸入 Teams 系統管理員認證。

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="sales-queue"></a>銷售佇列

### <a name="create-audio-files"></a>建立音訊檔案

將 「d： \\ 」 取代為儲存在您電腦上 wav 檔案的路徑。

```powershell
$content = [System.IO.File]::ReadAllBytes('d:\sales-hold-in-queue-music.wav')
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
```

### <a name="get-users-id"></a>取得使用者識別碼

```powershell
$userAdeleID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity
$userSalesBillID = (Get-CsOnlineUser -Identity "sip:bill@contoso.com").Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity "sip:mary@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>取得支援的語言清單

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>建立通話佇列

```powershell
New-CsCallQueue -Name "Sales" -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID "en-US"
```

### <a name="get-license-types"></a>取得授權類型

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>建立及指派資源帳戶

注意：此處不需要電話號碼，因為自動語音應答會在通話佇列前面結束

- ApplicationID
  - 自動語音應答：ce933385-9390-45d1-9512-c8d228074e07
  - 通話佇列：11cd3e2e-fccb-42ad-ad00-878b93575e07

注意：以下所示的授權類型 (PHONESYSTEM_VIRTUALUSER) 必須是上述Get-MsolAccountSku Cmdlet 所列出的授權類型。

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Sales-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="support-queue"></a>支援佇列

### <a name="create-audio-files"></a>建立音訊檔案

將 「d： \\ 」 取代為儲存在您電腦上 wav 檔案的路徑。

```powershell
$content1 = [System.IO.File]::ReadAllBytes('d:\support-greeting.wav')
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content1).ID

$content2 = [System.IO.File]::ReadAllBytes('d:\support-hold-in-queue-music.wav')
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content2).ID

$content3 = [System.IO.File]::ReadAllBytes('d:\support-shared-voicemail-greeting.wav')
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content3).ID
```

### <a name="get-support-team-group-id"></a>取得支援小組群組識別碼

```powershell
$teamSupportID = (Get-Team -DisplayName "Support").GroupID
```

### <a name="get-list-of-supported-languages"></a>取得支援的語言清單

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>建立通話佇列

```powershell
New-CsCallQueue -Name "Support" -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID "en-US"
```

### <a name="get-license-types"></a>取得授權類型

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>建立及指派資源帳戶

注意：此處不需要電話號碼，因為自動語音應答會預先結束通話佇列

- ApplicationID
  - 自動語音應答：ce933385-9390-45d1-9512-c8d228074e07
  - 通話佇列：11cd3e2e-fccb-42ad-ad00-878b93575e07

注意：以下所示的授權類型 (PHONESYSTEM_VIRTUALUSER) 必須是上述Get-MsolAccountSku Cmdlet 所列出的授權類型。

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Support-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="facilities-collaborative-calling-queue"></a>設施共同作業通話佇列

### <a name="get-facilities-team-group-id"></a>取得設施小組群組識別碼

```powershell
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
```

### <a name="get-facilities-help-desk-team-channel-id"></a>取得設施技術支援中心小組頻道識別碼

```powershell
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
```

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>取得設施技術支援中心通道擁有者使用者識別碼

```powershell
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
```

### <a name="get-on-behalf-of-calling-resource-account-id"></a>代表撥打資源帳戶識別碼取得

```powershell
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>取得支援的語言清單

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>建立通話佇列

```powershell
New-CsCallQueue -Name "Facilities" -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID "fr-FR" -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
```

### <a name="get-license-types"></a>取得授權類型

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>建立及指派資源帳戶

**注意**：此處不需要電話號碼，因為自動語音應答會預先結束通話佇列

- ApplicationID
  - 自動語音應答：ce933385-9390-45d1-9512-c8d228074e07
  - 通話佇列：11cd3e2e-fccb-42ad-ad00-878b93575e07

注意：以下所示的授權類型 (PHONESYSTEM_VIRTUALUSER) 必須是上述Get-MsolAccountSku Cmdlet 所列出的授權類型。

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Facilities-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```
