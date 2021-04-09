---
title: Teams 雲端會議錄製
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
localization_priority: Priority
f1.keywords:
- NOCSH
description: 在 Teams 中部署雲端語音功能的實用指引，以錄製 Teams 會議和群組通話，以擷取音訊、視訊和螢幕畫面分享活動。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e5c23c362d9d425c163a46dde93c6daa3c593a92
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617775"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 雲端會議錄製

在 Microsoft Teams 中，使用者可以錄製其 Teams 會議和群組通話，擷取音訊、視訊和螢幕共用的活動。 您也可以使用自動轉錄的錄製選項，便於使用者播放具有隱藏式輔助字幕的會議錄製，並在文字記錄中搜尋重要的討論項目。 錄製會在雲端進行，並儲存到 [Microsoft Stream](/stream/)，使用者可以因此安全地在整個組織內共用檔案。

相關：[Teams 會議錄製使用者文件](https://aka.ms/recordmeeting)

>[!Note]
> 從使用 Microsoft Stream 到變更為使用商務用 OneDrive 和 SharePoint 來進行會議錄製，將會採取階段性的方式。 如需每個階段的詳細資訊，請參閱[使用商務用 OneDrive 和 SharePoint 或 Stream 進行會議錄製](tmr-meeting-recording-change.md)。

> [!NOTE]
> 如需有關在 Teams 會議中使用角色，以及如何變更使用者角色的詳細資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。 針對即時活動錄製選項，請參閱 [Teams 中的即時活動錄製原則](teams-live-events/live-events-recording-policies.md)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 雲端會議錄製的必要條件

若要錄製 Teams 使用者的會議，必須啟用該租用戶的 Microsoft Stream。 此外，會議召集人和啟動錄製的人員都需要符合下列必要條件：

- 使用者有 Office 365 E1、E3、E5、A1、A3、A5、Microsoft 365 商務進階版、商務標準版或商務基本版<sup>1</sup>
- 使用者已同意遵守由系統管理員設定 (如果有) 的公司方針
- 使用者有足夠的 Microsoft Stream 儲存空間以儲存錄製檔案
- 使用者已將 CsTeamsMeetingPolicy -AllowCloudRecording 設定設為 True，以便錄製會議和群組通話
- 使用者已將 CsTeamsCallingPolicy -AllowCloudRecordingForCalls 設定設為 True，以便錄製 1:1 通話
- 使用者在會議中不是匿名、來賓或同盟使用者
- 若要啟用使用者會議謄寫，指派給使用者的 Teams 會議原則必須將 -AllowTranscription 設定設為 True。

<sup>1</sup> 在 2020 年 8 月 20 日時，A1 使用者的會議錄製檔案存取權將在 21 天後到期。 如需詳細資訊，請參閱[將 Microsoft Teams 會議錄製內容上傳至 Stream](/stream/portal-upload-teams-meeting-recording)。

> [!IMPORTANT] 
>
> 如果您只想讓使用者錄影及下載錄製內容，則使用者不必獲派 Microsoft Stream 授權。 這表示錄製內容不會儲存在 Microsoft Stream 中，而是會儲存在 Teams 非同步媒體服務 (AMS) 中，並會在限時 21 天後遭到刪除。 目前系統管理員並無法控制或管理此機制，包括加以刪除的能力。
>
> 另請注意，對於 AMS 上的錄製，錄製保留會受到聊天訊息本身的影響。 因此，刪除原始 AMS 錄製聊天訊息將會讓使用者無法存取錄製內容。 有兩個案例可能會影響此情況：
> 
> - 使用者手動刪除聊天訊息
> 
>   在此案例中，當原始訊息消失時，使用者將無法再存取錄製內容，也無法再進行進一步的下載。 不過，錄製內容本身可能仍保留在 Microsoft 的內部系統中一段時間 (不超過原始的 21 天期間)。
> 
> - 錄製聊天訊息已由聊天保留原則刪除
> 
>   AMS 錄製會直接繫結至聊天保留原則。 因此，雖然 AMS 上的錄製在刪除前預設會保留 21 天，但是如果聊天訊息在 21 天期間之前刪除，由於聊天訊息保留原則，也會刪除錄製內容。 在此之後，無法復原錄製內容。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>為貴組織中的使用者設定 Teams 雲端會議錄製

本節說明您可以如何設定和規劃 Teams 會議的錄製。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>為組織中的使用者開啟 Microsoft Stream

Microsoft Stream 可做為合格 Microsoft 365 和 Office 365 訂閱或獨立服務的一部分。  如需詳細資訊，請參閱 [Stream 授權概述](/stream/license-overview)。  Microsoft Stream 現已加入 Microsoft 365 商務版、Microsoft 365 商務標準版和 Microsoft 365 商務基本版。

深入瞭解如何[在 Microsoft 365 或 Office 365 中指派授權給使用者](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便讓使用者能夠存取 Microsoft Stream。 請確認 Microsoft Stream 沒有封鎖使用者，如[封鎖 Microsoft Stream 的註冊](/stream/disable-user-organization)中所定義。

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>確保使用者有在 Microsoft Stream 上傳影片的權限

依預設，公司中的每個人都能在 Stream 中建立內容，只要有啟用 Stream 並指派授權給使用者。 Microsoft Stream 系統管理員可以[限制員工在 Stream 中建立內容](https://docs.microsoft.com/stream/restrict-uploaders)。 此受限制清單中的使用者仍然可以錄製會議，不過，他們的錄製內容將不會傳送到 Stream。 這些錄製內容將會暫時儲存在 AMS 上 21 天。 在此期間，必須先下載錄製內容，才能在 21 天結束時刪除。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知員工同意公司的 Microsoft Stream 指導方針

如果 Microsoft Stream 系統管理員已[設定公司指導方針原則](/stream/company-policy-and-consent)，並要求員工在儲存內容之前先接受此原則，則使用者必須先接受，才能在 Microsoft Teams 中進行錄製。 在組織中推出錄製功能之前，請確認使用者已同意上述原則。

### <a name="turn-on-or-turn-off-cloud-recording"></a>開啟或關閉雲端錄製

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定 Teams 會議原則，以控制是否可以錄製使用者的會議。

在 Microsoft Teams 系統管理中心，開啟或關閉會議原則中的 [允許雲端錄製] 設定。 若要深入瞭解，請參閱[音訊和視訊的會議原則設定](meeting-policies-audio-and-video.md#allow-cloud-recording)。

您可以使用 PowerShell 來設定 TeamsMeetingPolicy 中的 AllowCloudRecording 設定。 若要深入瞭解，請參閱 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

請注意，會議召集人和啟動錄製的人員都需要有錄製權限才能錄製會議。 除非您已指派自訂原則給使用者，否則使用者會獲得 Global (全域) 原則，也就是預設啟用 AllowCloudRecording。

> [!NOTE]
> 如需使用 Teams 角色以設定誰有權限錄製會議的詳細資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

若要讓使用者回到 Global 原則，請使用下列 Cmdlet 來移除使用者的特定原則指派：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要變更 Global 原則中的 AllowCloudRecording 值，請使用下列 Cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```

</br>
</br>


|                                                                 案例                                                                 |                                                                                                                                                                         步驟                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    我想要讓公司中的所有使用者都能錄製他們的會議                                    |                                                                     <ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowCloudRecording = True<li>所有使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = True </ol>                                                                     |
| 我想讓大部分使用者能錄製會議，但我能選擇性地停用特定使用者不允許他進行錄製 |        <ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowCloudRecording = True<li>大部分使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = True<li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = False 的授權</ol>         |
|                                                   我想要 100% 停用錄製                                                   |                                                                <ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowCloudRecording = False<li>所有使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = False                                                                 |
|      我想讓大部分使用者不能錄製會議，但我能選擇性地啟用特定使用者允許他進行錄製       | <ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowCloudRecording = False<li>大部分使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = False<li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = True 的授權 <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |

#### <a name="where-your-meeting-recordings-are-stored"></a>會議錄製內容的儲存位置

會議的錄製內容會儲存在 Microsoft Stream 雲端儲存空間。 目前，如果客戶的 Teams 資料是儲存在國內，只要儲存資料的國內資料落地區域沒有提供 Microsoft Stream，客戶的 Teams 會議錄製功能就會關閉。 只要客戶的 Teams 資料是儲存在國內，其會議錄製功能就會開啟，即使該國內資料落地區域沒有提供 Microsoft Stream。 可以藉由允許錄製內容儲存在 Microsoft Stream 最靠近的地理區域，來完成此操作。 

如果您的 Teams 資料是儲存在國內，而且您比較想將會議錄製內容儲存在國內，我們建議您先關閉會議錄製，然後在您將 Microsoft Stream 部署到您的國內資料落地區域後，再將會議錄製開啟。 若要為貴組織中所有使用者關閉這個功能，請在 Microsoft Teams 系統管理中心的全域 Teams 會議原則中，關閉 [**允許雲端錄製**] 設定。 不過，如果您仍然想要讓錄製內容儲存在 Microsoft Stream 最靠近的地理區域，您必須在這項變更發生之前，同時開啟 [**允許雲端錄製**] 和 [**允許在區域外部儲存錄製內容**]。

若要在全域原則中啟用區域錄製，請使用下列 Cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```

以下摘要說明在此改變生效後，當您開啟會議錄製會發生什麼情況：

|如果您開啟會議錄製...|會議錄製內容會儲存在... |
|---|---|
|在您的國內資料落地區域提供 Microsoft Stream 之前 |在最靠近的 Microsoft Stream 區域|
|在您的國內資料落地區域提供 Microsoft Stream 之後 |在您的國內資料落地區域|

針對尚未開啟會議錄製的新的和現有租用戶，在國內資料落地區域提供 Microsoft Stream 之後，新的錄製內容會儲存在國內。 不過，在國內資料落地區域提供 Microsoft Stream 之前就啟用會議錄製的任何租用戶，將會繼續使用 Microsoft Stream 儲存空間來存放現有和新的錄製內容，即使國內資料落地區域提供 Microsoft Stream 之後。

若要找出您的 Microsoft Stream 資料的儲存區域，請在 Microsoft Stream 中按一下 [?] (在右上角)，按一下 [關於 Microsoft Stream]，然後按一下 [您的資料儲存位置]。  若要深入瞭解 Microsoft Stream 儲存資料的區域，請參閱 [Microsoft Stream 常見問題集](/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)。

若要深入瞭解 Microsoft 365 或 Office 365 中跨服務資料的儲存位置，請參閱[您的資料位於何處?](https://products.office.com/where-is-your-data-located?rtc=1)。

### <a name="turn-on-or-turn-off-recording-transcription"></a>開啟或關閉錄製內容謄寫

此設定可控制在播放會議錄製內容期間是否提供字幕和謄寫功能。 如果您關閉此功能，則 [**錄製**] 和 [**CC**] 選項在播放會議錄製內容期間無法使用。 開始錄製的人員需要開啟此設定，讓錄製也包含謄寫。

> [!NOTE]
> 目前僅針對將 Teams 語言設定為英文的使用者，以及在會議中使用英文時，才支援錄製會議的謄寫功能。 這些設定會與會議錄製內容一起儲存在 Microsoft Stream 雲端儲存空間。

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定 Teams 會議原則，控制啟動錄製的人員是否可以選擇謄寫會議錄製內容。

在 Microsoft Teams 系統管理中心，開啟或關閉會議原則中的 [允許謄寫] 設定。 若要深入瞭解，請參閱[音訊和視訊的會議原則設定](meeting-policies-audio-and-video.md#allow-transcription)。

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

</br>
</br>

|案例|步驟 |
|---|---|
|我想要讓公司中的所有使用者都能在啟動錄製會議時謄寫 |<ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowTranscription = True <li>所有使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowTranscription = True </ol>|
|我想讓大部分使用者能謄寫會議錄製內容，但我能選擇性地停用特定使用者不允許他進行謄寫 |<ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowTranscription = True <li>大部分使用者都擁有 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowTranscription = True <li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則有 AllowTranscription = False 的授權 </ol>|
|我想要 100% 停用錄製內容謄寫 |<ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowTranscription = False <li>所有使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowTranscription = False </ol>|
|我想讓大部分使用者不能謄寫，但我能選擇性地啟用特定使用者允許他進行謄寫 |<ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowCloudRecording = False <li>大部分使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = False <li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = True 的授權 </ol>|
|||

### <a name="planning-for-storage"></a>規劃儲存空間

1小時錄製內容的大小為 400 MB。 請確認您瞭解錄製檔案所需的容量，並讓 Microsoft Stream 有足夠的儲存空間可使用。  如需瞭解訂閱中包含的基本儲存空間，以及如何購買額外儲存空間，請參閱 [Microsoft Stream 授權概觀](/stream/license-overview)。

## <a name="manage-meeting-recordings"></a>管理會議錄製

會議錄製被視為租用戶擁有的內容。 如果錄製的擁有者離開公司，系統管理員可以在系統管理模式下開啟 Microsoft Stream 中的錄製影片 URL。 系統管理員可以刪除錄製內容、更新任何錄製內容的中繼資料、或變更錄製影片的權限。 深入瞭解 [Stream 中的管理功能](/stream/manage-content-permissions)。

> [!NOTE]
> 如需有關管理錄製和使用者存取的其他資訊，請參閱[在 Microsoft stream 中管理使用者資料](/stream/managing-user-data)和 [Microsoft Stream 中的權限和隱私權](/stream/portal-permissions)。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>會議錄製的合規性與電子文件探索

會議錄製內容會儲存在與 Microsoft 365 和 Office 365 Tier-C 相容的 Microsoft Stream 中。 為了讓合規性系統管理員能透過電子探索要求尋找 Microsoft Streams 會議或通話錄製，錄製完成訊息可在 Microsoft Teams 的合規性內容搜尋功能中找到。 合規性系統管理員可以在合規性內容搜尋預覽中的項目主旨列尋找關鍵字「錄製」，並探索組織中的會議和通話錄製。 而讓他們能夠查看所有錄製的先決條件，是必須在 Microsoft Stream 中設定他們具有系統管理員存取權。 深入瞭解[在 Stream 中指派系統管理員權限](/stream/assign-administrator-user-role)。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)