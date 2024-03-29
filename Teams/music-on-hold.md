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
ms.custom: ''
description: 瞭解如何在電話系統中管理音樂保留功能。
ms.openlocfilehash: 9e2a2aa352a1fd65955b35d4175b831653c694cb
ms.sourcegitcommit: 52450514880fe72af0d0b2fab1419eadfc3a583f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2022
ms.locfileid: "68499447"
---
# <a name="music-on-hold"></a>等候音樂

當 Microsoft Teams 使用者將來電保留時，來電者可以聆聽選取的音樂。

播放的音樂是 Microsoft 提供的預設音樂，或您上傳和設定的自訂音樂。 身為租使用者系統管理員，您可以建立 Teams 通話原則並將原則指派給 Teams 使用者，藉此設定等候音樂是否可供使用。

Microsoft Teams 通話案例中提供的預設音樂不含貴組織支付的任何版稅。

請注意，在其他情況下，來電者也可以聆聽「等候音樂」;例如，當他們撥入雲端通話佇列，或是通話被 Microsoft Teams 使用者駐留時。 這些案例不受本文所提及的功能涵蓋或控制。

## <a name="configure-music-on-hold"></a>設定等候音樂

若要設定等候音樂：

1. 在 Teams 系統管理中心的左側導覽中，移至 **語音>通話原則**。

2. 在 [ **管理原則] 索** 引標籤上，選取其中一個現有原則或建立新原則。

3. 在 **[PSTN 來電者的音樂保留** ] 欄位中，選取下拉式功能表中的 [ **已啟用** ]。

您也可以使用 Teams PowerShell 模組來設定等候音樂。 在 TeamsCallingPolicy 中，將 MusicOnHoldEnabledType 參數變更為 [已啟用]，然後將該原則實例授與一或多個使用者。

如果 Teams 使用者的 Teams 通話原則將 [等候音樂] 設為 [停用]，則當 Teams 使用者將通話設為保留時，將不會播放任何音樂。

## <a name="configure-custom-music"></a>設定自訂音樂

除了播放預設音樂給來電者之外，您還可以上傳含有音樂或其他音訊內容的自訂音訊檔案，並設定要對來電者播放該音訊檔案。
例如，當外部 PSTN 來電者被保留時，部門或組織可能會想要播放自訂公告或自訂音樂。

設定是使用通話保留原則完成。

> [!NOTE]
> 您必須負責獨立清除及保護搭配 Microsoft Teams 服務使用任何音樂或音訊檔案的所有必要權利和許可權。 這可能包括所有相關權利持有者在音訊檔案中的任何音樂、音效、音訊、品牌、名稱及其他內容中的智慧財產權和其他權利。 持有者可能包括演出者、演出者、演出者、專輯、作曲者、記錄標籤、音樂發行者、專輯、同盟、權利召集人、集體管理組織，以及任何其他擁有、控制或授權音樂著作權、音效、音訊及其他智慧財產權的物件。

### <a name="use-the-teams-admin-center"></a>使用 Teams 系統管理中心
您可以使用 Teams 系統管理中心建立或編輯通話保留原則，為使用者設定自訂音樂保留。

若要設定新的通話保留原則：

1. 在 Teams 系統管理中心，移至 **語音**  >  **通話保留原則**。

2. 選取 [ **新增] 索引卷** 標。

3. 為原則命名和描述。

4. 選 **取 [上傳檔案** ] 以上傳自訂音樂音訊檔案。

5. 選取 **套用**。

### <a name="assign-a-custom-call-hold-policy-to-users"></a>指派自訂的通話保留原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>使用 PowerShell
若要設定保留自訂音樂，請使用 Teams PowerShell 模組 3.0.0 或更新版本中的 PowerShell Cmdlet New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy 和 Import/Get/Remove/Export-CsOnlineAudioFile。

如需支援的音訊格式和檔案大小上限，請參閱 [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. 確定 Teams 使用者在 Teams 通話原則中將 PSTN 來電者的音樂設為 [已啟用]。 

2. 上傳自訂音訊檔案。

3. 建立參照自訂音訊檔案的 Teams 通話保留原則，並將它指派給 Teams 使用者。

### <a name="upload-the-custom-audio-file"></a>上傳自訂音訊檔案

「保留自訂音樂」的設定是從上傳音訊檔案開始。 您使用 PowerShell Cmdlet [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) 做為此目的。

以下顯示使用 Windows PowerShell 5.1 上傳 MP3 音訊檔案的範例。 如需其他範例，請參閱 [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)。

```PowerShell
C:\> $content = [System.IO.File]::ReadAllBytes('C:\tmp\customMoH1.mp3')
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>在 Teams 通話保留原則中參照音訊檔案

上傳音訊檔案之後，您必須在建立或設定 Teams 通話保留原則時，使用檔案識別碼，在 Teams 通話保留原則中參照檔案。 例如：

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

建立新的 Teams 通話保留原則之後，您可以使用下列Grant-CsTeamsCallHoldPolicy將該原則授與使用者：

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

若要取得上傳音訊檔案的相關資訊，請使用Get-CsOnlineAudioFile Cmdlet。

若要移除上傳的音訊檔案，請使用Remove-CsOnlineAudioFile Cmdlet。 移除音訊檔案之前，請檢查您是否在 Teams 中使用該音訊檔案CallHoldPolicy。

若要匯出上傳的音訊檔案，請使用Export-CsOnlineAudioFile Cmdlet。

## <a name="feature-availability"></a>功能可用性

下表指出哪些用戶端和裝置支援等候音樂和保留自訂音樂的功能。 Microsoft 會繼續新增功能支援，因此請經常回來查看其他可用性。

| 功能 | 桌面 <br> Windows/Mac OS | 瀏覽器 | 行動裝置 <br> iOS | 行動裝置 <br> Android | Teams Phone |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 按住 1：1 PSTN 通話 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 |
| 按住 1 對 1 Teams 通話 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 |
| 按住 1：1 PSTN 通話的 [轉接] | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | | |
| 在 1：1 Teams 通話中保留轉接 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂| | | |
| 在 1：1 PSTN 通話中保留移轉天數 |-等候音樂<br>-保留自訂音樂 || -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 |
| 在 1：1 Teams 通話中按住移轉 |-等候音樂<br>-保留自訂音樂 || -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 | -等候音樂<br>-保留自訂音樂 |

## <a name="restrictions"></a>限制

- 等候音樂僅適用于商業和 GCC 雲端實例。

- 只有當使用者處於 TeamsOnly 模式時，才能使用等候音樂。

- 如果已啟用稱為 Teams 的使用者進行Location-Based路由，則只會對來電者播放標準的「等候音樂」。

- 設定共用行外觀 (委派) 及使用「通話駐留」的使用者無法使用「保留自訂音樂」。 將會播放標準的等候音樂。

- 在某些情況下，直接路由媒體略過通話將會轉換為非媒體略過，以便在保留時播放音樂，而通話會保留為非媒體略過，直到通話終止為止。

## <a name="related-topics"></a>相關主題

- [指派原則給使用者](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
