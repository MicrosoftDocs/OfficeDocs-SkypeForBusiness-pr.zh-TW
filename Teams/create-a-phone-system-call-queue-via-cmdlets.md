---
title: 透過 Cmdlet 建立通話佇列
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 瞭解如何透過 Cmdlet 設定通話佇列
ms.openlocfilehash: 8ffbef5541a230755bb7439507e3002a5cb92462
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071106"
---
# <a name="create-a-call-queue-via-cmdlets"></a>透過 Cmdlet 建立通話佇列

## <a name="assumptions"></a>假設
1)  PowerShell 已安裝在電腦上
- 設定您的電腦Windows PowerShell [](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
- 已安裝 MSTeams 模組 ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- 已安裝 MSOnline 模組 ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  您擁有租使用者管理許可權
3)  您購買Microsoft Teams 電話
4)  已建立下列Teams的代理程式、通訊群組清單和頻道

注意：Teams通道 Cmdlet 是 PowerShell 模組的公用預覽版Teams一部分。  若要詳細資訊，請參閱安裝[PowerShell Teams](teams-powershell-install.md)預覽版，Microsoft Teams [PowerShell 版本資訊](teams-powershell-release-notes.md)。

已安裝 MicrosoftTeams 模組的使用者應確保已安裝最新版本 ````Update-Module MicrosoftTeams```` 。


## <a name="scenario"></a>案例

將會建立下列三個通話佇列：

銷售通話佇列資訊：
- 由自動助理前方：是
- 從 PSTN 直接通話：否
- 語言：英文英文
- 問候語：無
- 等候音樂：播放音訊檔案
- - 檔案名：sales-hold-in-queue-music.wav
- 通話接聽：使用者
- - Bill@contoso.com
- - Mary@contoso.com
- 會議模式：已啟動
- 路由方法：Attendant
- 目前狀態路由：關閉
- 通話代理人可以退出宣告通話：是
- 通話代理通知時間：15
- 呼叫溢出處理：200
- - 重新導向至：Adele@contoso.com
- 通話超時處理：120 秒
- - 重新導向至：Adele@contoso.com

支援通話佇列資訊：
- 由自動助理前方：是
- 從 PSTN 直接通話：否
-   語言：英文英文
-   問候語：播放音訊檔案
-   - 檔案名：support-greeting.wav
-   等候音樂：播放音訊檔案
-   - 檔案名：support-hold-in-queue-music.wav。
-   通話接聽：支援通訊群組清單
-   - Support@contoso.com
-   會議模式：已啟動
-   路由方法：最長閒置時間
-   目前狀態路由：N/A – 預設為啟用，因為最長閒置時間
-   通話代理人可以退出宣告通話：否
-   通話代理通知時間：15
-   呼叫溢出處理：200
-   - 重新導向：支援共用語音信箱
- - -   播放音訊檔案 (共用語音信箱問候語。wav) 
- - -   已啟用文字翻譯
-   通話超時處理：45 分鐘
-   - 重新導向：支援共用語音信箱
- - - TTS：「很抱歉，您一直等候，現在卻將通話轉接到語音信箱。」
- - - 已啟用文字翻譯


設施共同作業通話佇列資訊：
- 自動助理的前方：否
- 從 PSTN 直接撥打： (內部通話) 
-   語言：法文 FR
-   問候語：無
-   等候音樂：預設值
-   通話接聽：小組：設施
-   電話接聽信道：技術支援台
-   - 頻道擁有者：Fred@contoso.com
-   會議模式：已啟動
-   路由方法：Round Robin
-   目前狀態路由：On
-   通話代理人可以退出宣告通話：否
-   通話代理通知時間：15
-   呼叫溢出處理：200
-   - 中斷連線
-   通話超時處理：45 分鐘
-   - 中斷連線


## <a name="login"></a>登錄
系統會提示您輸入您的Teams認證。
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>銷售佇列
### <a name="create-audio-files"></a>建立音訊檔案
將 \\ 「d：」取代為將波浪檔案儲存在您電腦上的路徑。

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>取得使用者識別碼
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>取得支援的語言清單
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>建立通話佇列
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>取得授權類型
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>建立及指派資源帳戶
注意：電話通話佇列由自動總機前置結束，因此此處不需要號碼
- ApplicationID
- - 自動助理：ce933385-9390-45d1-9512-c8d228074e07
- - 通話佇列：11cd3e2e-fcb-42ad-ad00-878b93575e07

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>支援佇列
### <a name="create-audio-files"></a>建立音訊檔案
將 \\ 「d：」取代為將波浪檔案儲存在您電腦上的路徑。

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>取得支援小組群組識別碼
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>取得支援的語言清單
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>建立通話佇列
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>取得授權類型
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>建立及指派資源帳戶
注意：電話通話佇列是自動助理的前端，因此此處不需要號碼
- ApplicationID
- - 自動助理：ce933385-9390-45d1-9512-c8d228074e07
- - 通話佇列：11cd3e2e-fcb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>設施共同作業通話佇列
### <a name="get-facilities-team-group-id"></a>取得設施小組群組識別碼
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>取得設施服務台小組頻道識別碼
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>取得設施服務台頻道 ower 使用者識別碼
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>代表通話資源帳戶識別碼取得
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>取得支援的語言清單
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>建立通話佇列
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>取得授權類型
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>建立及指派資源帳戶
注意：電話通話佇列是自動助理的前端，因此此處不需要號碼
- ApplicationID
- - 自動助理：ce933385-9390-45d1-9512-c8d228074e07
- - 通話佇列：11cd3e2e-fcb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````