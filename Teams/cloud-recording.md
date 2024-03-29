---
title: Teams 雲端會議錄製
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
- highpri
ms.reviewer: nakulm
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: 在 Teams 中部署雲端語音功能的實用指引，以錄製 Teams 會議和群組通話，以擷取音訊、視訊和螢幕畫面分享活動。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 281a8997e3020b229ce8b34919177c1f6f2318c9
ms.sourcegitcommit: 73b13cd8a79ba1724b9fb79c8356a7cacafb7dd3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2022
ms.locfileid: "68965745"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 雲端會議錄製

在 Microsoft Teams 中，使用者可以錄製其 Teams 會議和群組通話，擷取音訊、視訊和螢幕共用的活動。 您也可以使用自動謄寫功能的錄製選項，便於使用者播放具有隱藏式輔助字幕的會議錄製，並在文字記錄中檢視重要的討論項目。 錄製會在雲端進行，並儲存到 OneDrive 或 SharePoint Online，讓使用者可以在整個組織安全地共用內容。

錄製會議時，系統會自動：

- 上傳至 OneDrive 或 SharePoint
- 已將權限授予受邀參加會議之人員
- 在會議聊天中的連結
- 針對 Teams 行事曆中的會議之錄製和文字記錄索引標籤
- 已新增到整個 Microsoft 365 的各種檔案清單：與我共用、office.com、建議、最近等等。
- 已針對 Microsoft 365 搜尋編制索引

相關：[Teams 會議錄製使用者文件](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> 從使用 Microsoft Stream (傳統版) 變更為使用 OneDrive 和 SharePoint 進行會議錄製，這將會在 2021 年 8 月自動發生。 如需詳細資訊，請參閱[使用 OneDrive 和 SharePoint 或 Stream 進行會議錄製](tmr-meeting-recording-change.md)。

> [!NOTE]
> 如需有關在 Teams 會議中使用角色，以及如何變更使用者角色的詳細資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。 針對即時活動錄製選項，請參閱 [Teams 中的即時活動錄製原則](teams-live-events/live-events-recording-policies.md)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 雲端會議錄製的必要條件

若要錄製 Teams 使用者的會議，必須為租用戶啟用 OneDrive 和 SharePoint。 此外，會議召集人和啟動錄製的人員都需要符合下列必要條件：

- 使用者在 OneDrive 中有足夠的儲存空間，可儲存非頻道會議錄製內容。

- Teams 的頻道在 SharePoint 中有足夠的儲存空間，可儲存頻道會議錄製內容。

- 使用者已 `CsTeamsMeetingPolicy -AllowCloudRecording` 設定設為 True，以便錄製會議和群組通話。

- 使用者已 `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` 設定設為 True，以便錄製會議和一對一通話。

- 使用者在會議中不是匿名、來賓或同盟使用者。

- 若要啟用使用者會議的謄寫功能，指派給使用者的 Teams 會議原則必須將 `-AllowTranscription` 設定設為 True。

- 若要啟用儲存頻道會議錄製，因此讓頻道成員無法編輯或下載錄製內容，必須將 `CSTeamsMeetingPolicy -ChannelRecordingDownload` 設定設為封鎖。

> [!IMPORTANT]
>
> 如果您希望使用者僅可錄製並下載錄製內容，使用者便不需要啟用 OneDrive 或 SharePoint。 這表示系統不會將錄製內容儲存在 OneDrive 或 SharePoint 中，而是會儲存在暫時的 Teams 儲存空間，並在限時 21 天後遭到刪除。 這是目前系統管理員所無法控制、管理或刪除的事項。
>
> 如需 [ 有關暫時的會議錄製儲存運作方式的詳細資訊](#temp-storage)，請參閱以下。  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>為貴組織中的使用者設定 Teams 雲端會議錄製

本節說明您可以如何透過 [Teams 會議原則](policy-assignment-overview.md) 設定和規劃 Teams 會議的錄製內容。

### <a name="turn-on-or-turn-off-cloud-recording"></a>開啟或關閉雲端錄製

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定 Teams 會議原則，以控制是否可以錄製使用者的會議。

在 Microsoft Teams 系統管理中心，開啟或關閉會議原則中的 **[雲端錄製]** 設定。 若要深入瞭解，請參閱 [音訊和視訊的會議原則設定](meetings-policies-recording-and-transcription.md#cloud-recording)。

您可以使用 PowerShell 來設定 TeamsMeetingPolicy 中的 AllowCloudRecording 設定。 若要深入瞭解，請參閱 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

請注意，會議召集人和啟動錄製的人員都需要有錄製權限才能錄製會議。 除非您已指派自訂原則給使用者，否則使用者會獲得 Global (全域) 原則，也就是預設啟用 AllowCloudRecording。

> [!NOTE]
> 如需使用 Teams 角色以設定誰有權限錄製會議的詳細資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

若要讓使用者回到 Global 原則，請使用下列 Cmdlet 來移除使用者的特定原則指派：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要變更 Global 原則中的 AllowCloudRecording 值，請使用下列 Cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|案例|步驟|
|--|--|
| 我想要讓公司中的所有使用者都能錄製他們的會議。 | <ol><li>確認 Global CsTeamsMeetingPolicy 具有 AllowCloudRecording = True。<li>所有使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具備 AllowCloudRecording = True。</ol> |
| 我想讓我的大部分使用者都能錄製其會議，但可以選擇性地停用特定使用者, 不讓其進行錄製。 | <ol><li>確認 GlobalCsTeamsMeetingPolicy 原則具備 AllowCloudRecording = True。<li>大部分使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具備 AllowCloudRecording = True。<li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則具有 AllowCloudRecording = False 的授權。</ol> |
| 我想要 100% 停用錄製。 | <ol><li>確認 Global CsTeamsMeetingPolicy 具有 AllowCloudRecording = False。<li>所有使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具備 AllowCloudRecording = False。 |
| 我想讓大部分使用者不能錄製會議，但我能選擇性地啟用特定使用者允許他進行錄製。 | <ol><li>確認 Global CsTeamsMeetingPolicy 具有 AllowCloudRecording = False。<li>大部分使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具備 AllowCloudRecording = False。<li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則具備 AllowCloudRecording = True 的授權。 <ol> |

<a name="bd-channel"></a>
> [!NOTE]
> 如果啟用 Teams 原則合規性錄製之外部租使用者的 Teams 使用者加入會議或在租使用者上通話，則不論您租使用者開啟或關閉雲端式錄製，其他租使用者都會基於合規性目的錄製該會議/通話。 如果其他租使用者的使用者不應擷取錄製內容，建議您將屬於您租使用者中會議一部分的簡報者從會議中移除。 如需有關 Teams 上原則合規性錄製的詳細資訊，請參 [閱 Teams 原則型錄製簡介，以通話&會議](teams-recording-policy.md)。

### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>封鎖或允許下載頻道會議錄製內容

此設定可控制頻道會議是否會儲存至頻道中的「錄製內容」資料夾或「錄製內容\僅供檢視」資料夾。 此設定適用於選取頻道會議記錄的使用者原則。

此設定有兩個值：

- **允許** (預設值)—將頻道會議錄製內容儲存到頻道中的「錄製內容」資料夾。 錄製內容檔案的權限將會以 Channel SharePoint 權限為依據。 這和為頻道上傳的其他任何檔案相同。

- **封鎖** (預設值)—將頻道會議錄製內容儲存到頻道中的「錄製內容\僅供檢視」資料夾。 頻道擁有者將擁有此資料夾中錄製內容的完整權限，但頻道成員將擁有讀取存取權但沒有下載功能。

您可以使用 PowerShell 來設定 TeamsMeetingPolicy 中的 ChannelRecordingDownload 設定。 若要深入瞭解，請參閱 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

除非您已指派自訂原則給使用者，否則使用者會獲得 Global (全域) 原則，也就是設為預設允許 ChannelRecordingDownload。

若要讓使用者回到全域原則，請使用下列 Cmdlet 以移除使用者的特定原則指派：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要變更全域原則中的 ChannelRecordingDownload 值，請使用下列 Cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> ChannelRecordingDownload 設定僅適用於 Microsoft Teams PowerShell 模組版本 2.4.1-預覽或更新版本。 若要下載模組的最新預覽版本，請使用此命令：
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>開啟或關閉錄製內容謄寫

此設定可控制在播放會議錄製內容期間是否提供字幕和謄寫功能。 開始錄製的人需要開啟此設定，才能使用這些功能進行錄製。
  
開啟此設定將建立與會議錄製內容一起儲存的文字記錄，從而在會議錄製內容中啟用 **[搜尋]**、**[CC]** 和 **[文字記錄]**。

> [!NOTE]
> 錄製會議謄寫目前僅支援英文 (美國)、英文 (加拿大)、英文 (印度)、英文 (英國)、英文 (澳洲)、英文 (紐西蘭)、阿拉伯文 (阿拉伯聯合大公國)、阿拉伯文 (沙烏地阿拉伯)、中文 (簡體，中國)、中文 (繁體，香港特別行政區)、中文 (繁體，台灣)、捷克文 (捷克)、丹麥文 (丹麥)、荷蘭文 (比利時)、荷蘭文 (荷蘭)、法文 (加拿大)、法文 (法國)、芬蘭文 (芬蘭)、德文 (德國)、希臘文 (希臘)、希伯來文(以色列)、印地文 (印度)、匈牙利文 (匈牙利)、義大利文 (義大利)、日文 (日本)、韓文(韓國)、挪威文 (挪威)、波蘭文 (波蘭)、葡萄牙文 (巴西)、葡萄牙文 (葡萄牙)、羅馬尼亞文 (羅馬尼亞)、俄文 (俄羅斯)、斯洛伐克文 (斯洛伐克)、西班牙文 (墨西哥)、西班牙文 (西班牙)、瑞典文 (瑞典)、泰文 (泰國)、土耳其文 (土耳其)、烏克蘭文 (烏克蘭)、越南文 (越南)。 這些會議記錄會和 OneDrive 和 SharePoint 雲端儲存空間中的會議錄製內容一起儲存。

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定 Teams 會議原則，控制啟動錄製的人員是否可以選擇謄寫會議錄製內容。

在 Microsoft Teams 系統管理中心，開啟或關閉會議原則中的 [允許謄寫] 設定。 若要深入瞭解，請參閱 [音訊和視訊的會議原則設定](meetings-policies-recording-and-transcription.md#transcription)。

您可以使用 PowerShell 來設定 TeamsMeetingPolicy 中的 AllowTranscription 設定。 若要深入瞭解，請參閱 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

除非您已指派自訂原則給使用者，否則使用者會獲得 Global (全域 ) 原則，也就是預設停用 AllowTranscription。

若要讓使用者回到 Global 原則，請使用下列 Cmdlet 來移除使用者的特定原則指派：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要變更 Global 原則中的 AllowCloudRecording 值，請使用下列 Cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

|案例|步驟 |
|---|---|
|我想要讓公司中的所有使用者都能在啟動錄製會議時謄寫。 |<ol><li>確認 Global CsTeamsMeetingPolicy 具有 AllowTranscription = True。 <li>所有使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具有 AllowTranscription = True。 </ol>|
|我想讓我的大部分使用者都能謄寫其會議錄製，但可以選擇性地停用特定使用者不讓他進行謄寫。 |<ol><li>確認 Global CsTeamsMeetingPolicy 具有 AllowTranscription = True。 <li>大部分使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具有 AllowTranscription = True。 <li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則具有 AllowTranscription = False 的授權。 </ol>|
|我想要 100% 停用錄製內容謄寫。 |<ol><li>確認 Global CsTeamsMeetingPolicy 具有 AllowTranscription = False。 <li>所有使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具有 AllowTranscription = False。 </ol>|
|我想讓大部分使用者不能謄寫，但我能選擇性地啟用特定使用者允許他進行謄寫。 |<ol><li>確認 Global CsTeamsMeetingPolicy 具有 AllowCloudRecording = False。 <li>大部分使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則具備 AllowCloudRecording = False。 <li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則具備 AllowCloudRecording = True 的授權。 </ol>|

### <a name="terms-of-use-acceptance"></a>接受使用規定

如果您的組織具有一個會議錄製原則，是您想要使用者在錄製會議之前要接受的原則，請使用 [Azure Active Directory 使用規定](/azure/active-directory/conditional-access/terms-of-use) \(部分機器翻譯\) 功能。 此功能可讓您的使用者先接受貴組織的使用規定原則，再取得 Microsoft Teams 的存取權。 此功能並不是按一下錄製按鈕的特定功能，而是與使用整體 Teams 或其他 Microsoft 365 應用程式相關的功能。 我們的建議是將您的會議錄製資訊新增至使用 Teams 或 Microsoft 365 的整體使用規定。

### <a name="set-a-custom-privacy-policy-url"></a>設定自訂隱私權原則 URL

系統管理員可以使用貴組織的自訂連結來更新 Teams 錄製和謄寫隱私權原則 URL。 您可使用下列步驟在 [Azure AD 系統管理中心](https://aad.portal.azure.com)來完成這項作業:

1. 登入 Azure AD 系統管理中心。
1. 移至 **Azure Active Directory** > **屬性**。
1. 更新 **隱私權聲明 URL**，並包含您的隱私權原則連結。

> [!NOTE]
> 如果您已經更新組織的此欄位，則不需要進行任何變更。

新增隱私權原則 URL 之後，預設 Teams 會議錄製和謄寫隱私權聲明將會以貴組織提供的新 URL 取代。

> [!NOTE]
> 加入由貴組織所主持之 Teams 會議的匿名、來賓和聯盟使用者，仍將擁有預設的 Teams 會議錄製和謄寫隱私權原則。

## <a name="permissions-and-storage"></a>權限與共用

這些會議記錄會儲存在 OneDrive 和 SharePoint 雲端儲存空間中。 位置和權限取決於會議類型和使用者在會議中的角色。 以下列出套用至錄製的預設權限，對影片錄製檔案具有完整編輯權限的使用者可以變更此權限，並視需要稍後與其他人共用。

### <a name="non-channel-meetings"></a>非頻道會議

- 錄製內容會儲存在名為 [**錄製內容**] 的資料夾中，這位於點擊錄製之使用者的 OneDrive 中。 

  範例：*recorder's OneDrive* / **錄製**

- 受邀參加會議的人 (外部使用者除外) 將會自動獲得錄製檔案的權限，且具備檢視存取權但無法下載。

- 會議擁有者和按一下記錄的人員會取得完整的編輯權限，以及變更權限並與其他人員共用。

### <a name="channel-meetings"></a>頻道會議

如果將 `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` 設定為允許 (預設值)：

- 錄製內容會儲存在 Teams 網站文件庫中，一個名為 **錄製內容** 的資料夾中。

  範例：*Teams 名稱 - 頻道名稱* / **檔** / **錄製**

- 按一下 [錄製] 的該名成員擁有完整的錄製權限。

- 每個其他成員的權限都是以 Channel SharePoint 權限為基礎。

如果將 `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` 設定為封鎖：

- 錄製內容會儲存在 Teams 網站文件庫中，在一個名為 **錄製內容/僅供檢視** 的資料夾中。 

  範例：*Teams 名稱 - 僅限頻道名稱* / **檔/錄製/檢視**

- 頻道擁有者將擁有此資料夾中錄製內容的完整編輯和下載權限。

- 頻道成員將僅能檢視存取，但無法下載。

如需特定會議類型的詳細資訊，請參閱下表：

| 會議類型  | 是誰按了一下 [錄製]？| 錄製內容在哪裡？ | 誰可以存取？ R/W、R 或共用  |
|-------------|-----------------------|------------------------|------------------------|
|與內部派對進行一對一通話             |呼叫者                 |呼叫者的 OneDrive 帳戶                        |呼叫者為擁有者，且擁有完整權限。 <br /><br />被呼叫者 (如果在同一個租用戶中) 擁有唯讀存取權。 沒有共用存取權。 <br /><br /> 被呼叫者 (如果在其他租用戶中) 沒有存取權。 呼叫者必須將它分享給被呼叫者。|
|與內部派對進行一對一通話             |被呼叫者                 |被呼叫者的 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整權限。 <br /><br />被呼叫者 (如果在同一個租用戶中擁有唯讀存取權。 沒有共用存取權。 <br /><br />呼叫者 (如果在其他租用戶中) 沒有存取權。 被呼叫者必須將它分享給呼叫者。|
|與外部通話進行一對一通話             |呼叫者                 |呼叫者的 OneDrive 帳戶                        |呼叫者為擁有者，且擁有完整權限。<br /> <br />被呼叫者沒有存取權。 呼叫者必須將它分享給被呼叫者。|
|與外部通話進行一對一通話             |被呼叫者                 |被呼叫者的 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整權限。<br /><br />呼叫者沒有存取權。 被呼叫者必須將它分享給呼叫者。|
|群組通話                                 |通話的任何成員 |按一下 [錄製] 之 OneDrive 帳戶的群組成員  |按一下 [錄製] 的成員擁有完整的權限。 <br /><br /> 來自相同租用戶的其他成員擁有讀取權限。 <br /><br /> 來自其他租用戶的其他群組成員沒有權限。|
|Adhoc/Scheduled 會議                    |召集人              |召集人的 OneDrive 帳戶                     |召集人擁有完整的錄製權限。 <br /><br /> 會議的所有其他成員擁有讀取存取權，但沒有下載功能。|
|Adhoc/Scheduled 會議                    |其他會議成員   |按一下 [錄製] 的會議成員                                  |按一下 [錄製] 的成員擁有完整的錄製權限。 <br /><br />召集人有編輯權限並可以共用。<br /><br /> 所有其他的會議成員擁有讀取存取權，但沒有下載功能。|
|與外部參與者的 Adhoc/Scheduled 會議|召集人              |召集人的 OneDrive 帳戶                     |召集人擁有完整的錄製權限。<br /> <br /> 會議的所有其他成員 (與召集人來自相同的租用戶) 擁有讀取存取權，但沒有下載功能。 <br /><br /> 所有其他外部成員皆沒有存取權，而召集人必須與他們公用。|
|與外部參與者的 Adhoc/Scheduled 會議|其他會議成員   |按一下 [錄製] 的成員                                  |按一下 [錄製] 的成員擁有完整的錄製權限。 召集人有編輯權限並可以共用。 <br /><br /> 會議的所有其他成員 (與召集人來自相同的租用戶) 擁有讀取存取權，但沒有下載功能。 <br /><br />所有其他外部成員皆沒有存取權，而召集人必須與他們公用。|
|頻道會議                            |頻道成員         |適用於該頻道的 Teams SharePoint 位置                   |如果將 Set-CsTeamsMeetingPolicy -ChannelRecordingDownload 設為允許 (預設) 使用者 (在 [錄製] 上按一下的成員) 擁有錄製的編輯權限。 每個其他成員的權限都是以 Channel SharePoint 權限為基礎。<Br><Br>如果將 Set-CsTeamsMeetingPolicy -ChannelRecordingDownload 設為 [封鎖]，頻道擁有者將擁有此錄製內容的完整權限，但頻道成員則是擁有讀取存取權但沒有下載功能。|

<a name="temp-storage"></a>

### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>無法上傳到 OneDrive 和 SharePoint 時的暫存空間

如果會議錄製內容無法上傳到 OneDrive 和 SharePoint，此檔案在刪除之前，可暫時從 Teams 下載 (為期 21 天)。 目前系統管理員無法控制或管理此機制，包括將其刪除的能力。

會議錄製可能會中止在暫存空間中的原因如下：

- 對於非頻道會議，若錄製內容的使用者沒有 OneDrive 或其 OneDrive 已達到儲存空間配額
- 對於頻道會議，若 SharePoint 網站已達到其儲存空間配額或尚未佈建該網站
- 如果已啟用特定的 OneDrive 和 SharePoint 原則，則會限制使用者上傳檔案的能力 (若使用非特定 IP 範圍等)。

適用於此的錄製保留為暫存空間，其會受到聊天訊息本身的影響。 因此，刪除會議錄製的原始聊天訊息將會阻止使用者存取錄製內容。 有兩個案例可能會影響此情況：

- **使用者手動刪除聊天訊息**－在此案例中，當原始訊息消失時，使用者將無法再存取錄製內容，也無法再進行其他的下載。 不過，錄製內容本身可能仍保留在 Microsoft 的內部系統中一段時間 (不超過原定的 21 天期間)。

- **錄製聊天訊息已遭聊天保留原則刪除** - 暫存空間的錄製內容會直接繫結至聊天保留原則。 因此，雖然 Teams 暫存空間上的錄製內容在刪除前會預設保留 21 天，但是如果聊天訊息在 21 天期間之內刪除，此錄製內容將因為聊天訊息保留原則而遭刪除。 在此之後，無法復原錄製內容。

### <a name="planning-for-storage"></a>規劃儲存空間

1小時錄製內容的大小為 400 MB。 請確認您了解錄製檔案所需的容量，並讓 OneDrive 和 SharePoint 有足夠的儲存空間可供使用。  請閱讀[設定 OneDrive 的預設儲存空間](/onedrive/set-default-storage-space)和[管理 SharePoint 網站儲存空間限制](/sharepoint/manage-site-collection-storage-limits)，以了解訂閱中所包含的基本儲存空間，以及如何購買額外的儲存空間。
  
## <a name="manage-meeting-recordings"></a>管理會議錄製

會議錄製會以影片檔案儲存在 OneDrive 和 SharePoint 中，並遵循這些平台提供的管理和控管選項。 如需詳細資訊，請參閱 [SharePoint 控管概觀](/sharepoint/governance-overview)。

對於非頻道會議，其錄製內容會儲存在錄製者的 OneDrive 中，因此在員工離職後處理擁有權和保留時，將遵循一般 [OneDrive 和 SharePoint 流程](/onedrive/retention-and-deletion#the-onedrive-deletion-process)的規定。

會議錄製的預設到期時間為 120 天。 您可以關閉 [會議自動過期] 設定或變更預設到期時間。 深入瞭解 [會議錄製自動過期](meetings-policies-recording-and-transcription.md#meetings-automatically-expire)。

## <a name="closed-captions-for-recordings"></a>錄製內容的隱藏式輔助字幕

只有當使用者在錄製時已開啟謄寫功能，才能在播放期間使用 Teams 會議錄製的隱藏式輔助字幕。 系統管理員必須 [經由原則將錄製謄寫功能開啟](#turn-on-or-turn-off-recording-transcription)，以確保他們的使用者可以選擇錄製會議及謄寫功能。

Captions help create inclusive content for viewers of all abilities. As an owner, you can hide captions on the meeting recording, although the meeting transcript will still be available on Teams unless you delete it there.

目前錄製影片檔案的隱藏式字幕會連結到 Teams 會議字幕。 在大部分情況下，此連結在檔案的存留時間內維持不變，但如果影片檔案是在同一個 OneDrive 或 SharePoint 網站中複製，則此連結可能會失效，可能會導致在複製的影片檔案上無法提供字幕。

日後若在 Teams 中的文字記錄與錄製內容之間的連結出現任何變更，都會在這裡和訊息中心通知中釐清。 如果我們之後做出任何變更，我們會確保錄製時間不到 60 天的檔案將會議的文字記錄顯示爲輔助字幕。

> [!NOTE]
> GCC 尚未提供會議謄寫功能。

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>會議錄製的 eDiscovery 與合規性

### <a name="ediscovery"></a>電子文件探索

會議錄製內容會儲存在 OneDrive 和 SharePoint 中，這兩者均符合 Microsoft 365 和 Office 365 層級-D 規範。 為支援對會議或通話錄製有興趣的合規性系統管理員之電子文件探索要求，[錄製已完成] 的訊息可在 Microsoft Teams 的合規性內容搜尋功能中使用。 合規性系統管理員可以在合規性內容搜尋預覽中的項目主旨列尋找關鍵字「錄製」，並探索組織中的會議和通話錄製。

此外，您也可以透過 eDiscovery 搜尋 SharePoint 和 OneDrive 上的檔案，找到會議錄製影片檔案。

若要深入了解 eDiscovery，請參閱文章 [適用於 Microsoft 365 的 eDiscovery 解決方案](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>保留原則

您可以透過 ProgID 屬性，將自動保留標籤套用至僅鎖定 Teams 會議錄製影片檔案。 如需詳細資訊，請參閱 [如何將保留標籤自動套用至 Teams 會議錄製](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings)。

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Microsoft Purview 資料外洩防護 (DLP) 原則

您也可以使用 ProgID 屬性，將 DLP 原則套用至會議錄製檔案。 在 SharePoint 和 OneDrive 中的檔案之 DLP 規則中，可將條件設定為：

- Document property = *ProgID*
- Value = *Media.Meeting*

若要深入了解 DLP，請參閱文章 [深入了解資料外洩防護](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="meeting-recording-diagnostic-tools"></a>會議錄製診斷工具

### <a name="user-cannot-record-meetings"></a>使用者無法錄製會議

如果您是系統管理員，您可以使用下列診斷工具來驗證使用者已正確設定以在 Teams 中錄製會議：

1. 選取 **[執行測試]** 以在 Microsoft 365 系統管理中心填入診斷。

   > [!div class="nextstepaction"]
   > [執行測試：會議錄製](https://aka.ms/MeetingRecordingDiag)

2. 在執行診斷窗格中，在 **[使用者名稱或電子郵件]** 欄位中輸入無法記錄會議之使用者的電子郵件，然後選取 **[執行測試]**。

3. 測試會傳回解決任何租用戶或原則設定的最佳後續步驟，以驗證使用者已正確設定以在 Teams 中錄製會議。
  
### <a name="meeting-record-is-missing"></a>會議記錄遺失

如果您是系統管理員，您可以使用下列診斷工具來驗證會議錄製是否成功完成，且已根據會議識別碼和錄製開始時間上傳至 Stream 或 OneDrive：

1. 選取 **[執行測試]** 以在 Microsoft 365 系統管理中心填入診斷。

   > [!div class="nextstepaction"]
   > [執行測試：遺失會議錄製](https://aka.ms/MissingRecordingDiag)

2. 在 [執行診斷] 窗格中，在 **會議的 URL** 中輸入錄製欄位 (通常會在會議邀請) 以及會議日期的 [ **會議記錄時間？** ] 欄位中，然後選取 [ **執行測試]**。

3. 測試會驗證會議錄製是否成功完成，且已上傳到 Stream 或 OneDrive。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
