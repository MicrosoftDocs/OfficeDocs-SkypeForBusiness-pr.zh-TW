---
title: 等候音樂
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 5e28aa4774d105b687551601ba89657d91a08170
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356551"
---
# <a name="music-on-hold"></a>等候音樂

當使用者Microsoft Teams從公用交換電話網絡 (PSTN) 來電時，PSTN 來電者可以聆聽選取的音樂。

播放的音樂是 Microsoft 提供的預設音樂，或是您上傳和設定自訂音樂。 作為租使用者系統管理員，您可以建立通話Teams，並將該Teams可用。 

請注意，PSTN 來電者也可以在其他情況下聆聽等候音樂;例如，當他們撥打到雲端通話佇列，或他們的通話是由使用者Microsoft Teams時。 本文提及的功能並未涵蓋或控制這些案例。 

## <a name="configure-music-on-hold"></a>設定等候音樂

若要設定等候音樂：

1.  在系統管理中心的左側導Teams，請前往 **語音>通話政策**。

2.  在管理 **政策選項卡** 上，選取其中一個現有政策或建立新策略。

3.  在 **[PSTN 通話者音樂保留狀態> 欄位中****，選取** 下拉式功能表中的 [已啟用。

您也可以使用 PowerShell 模組來設定等候音樂Teams音樂。 在 TeamsCallingPolicy 中，將 MusicOnHoldEnabledType 參數變更為啟用，然後將該策略實例授予一或多個使用者。

如果使用者Teams通話Teams將音樂保留設定為停用，則當使用者將通話設為保留Teams時，不會播放任何音樂。

## <a name="configure-custom-music"></a>設定自訂音樂

> [!NOTE]
> 此功能是公開預覽版。

除了播放預設音樂給 PSTN 來電者之外，您還可以上傳包含音樂或其他音訊內容的自訂音訊檔案，並設定該音訊檔案要播放給 PSTN 來電者。
例如，當外部 PSTN 來電者被保留時，部門或組織可能會想要播放自訂公告或自訂音樂。  

> [!NOTE]
> 您負責獨立清除及保護所有必要的許可權，以使用您的音樂或音訊檔案Microsoft Teams服務。 這可能包括所有相關權利擁有者在音訊檔案中任何音樂、音效、音訊、品牌、名稱及其他內容中的智慧財產權和其他權利。 擁有者可能包括美術家、參與者、演出者、音樂人、歌曲作者、作曲者、記錄標籤、音樂發行者、同盟、會所、版權社團、集體管理組織，以及擁有、控制或授權音樂著作權、音效、音訊和其他智慧財產權的其他任何方。

若要設定自訂音樂保留狀態，請使用 Teams PowerShell 模組 2.5.0 或更高版本中的 PowerShell Cmdlets New/Get/Set/Grant/remove-CsTeamsCallHoldPolicy 和 Import/Get/remove-CsOnlineAudioFile。


1. 請確定Teams在通話規則中，將 PSTN 來電者的 [音樂Teams保留狀態。 

2. Upload自訂音訊檔案。

3. 建立參照Teams音訊檔案的通話保留原則，並將其指派給Teams使用者。

### <a name="upload-the-custom-audio-file"></a>Upload自訂音訊檔案

自訂音樂保留的組組從上傳音訊檔案開始。 您可以使用 PowerShell Cmdlet Import-CsOnlineAudioFile來達到此目的。 以下是使用 PowerShell 介面上傳 MP3 音訊檔案的範例：

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>在通話保留Teams中參照音訊檔案

上傳音訊檔案之後，您必須在建立或設定 Teams 通話保留政策時，使用檔案的識別碼，在 Teams Teams 通話保留政策中參照該檔案。 例如：

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

建立新通話保留Teams後，您可以使用以下方法將這項Grant-CsTeamsCallHoldPolicy給使用者：

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

若要取得您上傳的音訊檔案相關資訊，請使用 Get-CsOnlineAudioFile Cmdlet。

若要移除上傳的音訊檔案，請使用 Remove-CsOnlineAudioFile Cmdlet。 移除音訊檔案之前，請檢查您不是在 TeamsCallHoldPolicy 中使用該音訊檔案。

## <a name="feature-availability"></a>功能可用性

下表指出哪些用戶端和裝置支援音樂保留和自訂音樂保留功能。 Microsoft 會繼續新增功能支援，因此請經常回來查看是否有其他可用性。


| 功能 | 桌面 <br> Windows/Mac OS | 瀏覽器 | 行動裝置 <br> iOS | 行動裝置 <br> Android | Teams 電話 |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 保留 1：1 PSTN 通話 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | 等候音樂 | 等候音樂 |
| 在 1：1 PSTN 通話中保留 [諮詢轉移> |-等候音樂<br>-保留自訂音樂 | | | | |

## <a name="restrictions"></a>限制

- 等候音樂僅適用于商業雲端。

- 只有在使用者進入 TeamsOnly 模式時，才能使用等候音樂。

- 如果已Teams使用者已啟用 Location-Based，則無法播放等候音樂給來電者。

- 上傳音訊檔案之後，您無法匯出;您只可以移除它。

- 自訂等候音樂不適用於為共用線路外觀和委派 (以及使用通話) 使用者。 標準音樂保留將會播放。

- 在某些情況下，直接路由媒體旁路通話會轉換成非媒體旁路，以播放等候音樂，通話會維持為非媒體旁路，直到通話結束。


## <a name="related-topics"></a>相關主題

- [指派策略給使用者](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)





