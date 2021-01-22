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
f1.keywords:
- NOCSH
description: 在 Teams 中部署雲端語音功能的實用指南，以錄製 Teams 會議和群組通話以捕獲音訊、視視和螢幕共用活動。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 40fad38d8c77d8194d2bf24a451fb9438f10c586
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918969"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 雲端會議錄製

在 Microsoft Teams 中，使用者可以錄製其 Teams 會議和群組通話，擷取音訊、視訊和螢幕共用的活動。 您也可以使用自動轉錄的錄製選項，便於使用者播放具有隱藏式輔助字幕的會議錄製，並在文字記錄中搜尋重要的討論項目。 錄製會在雲端進行，並儲存到 [Microsoft Stream](https://docs.microsoft.com/stream/)，使用者可以因此安全地在整個組織內共用檔案。

相關：[Teams 會議錄製使用者文件](https://aka.ms/recordmeeting)

>[!Note]
> 從使用 Microsoft Stream 到變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。剛開始時，您可以加入這項體驗，在 11 月如果您想要繼續使用 Stream，則必須退出體驗，而在 2021 年初的某刻，我們將要求所有客戶使用商務用 OneDrive 和 SharePoint 來進行會議錄製。

> [!NOTE]
> 有關在 Teams 會議使用角色，以及如何變更使用者角色的資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 雲端會議錄製的必要條件

若要錄製 Teams 使用者的會議，必須針對租使用者啟用 Microsoft Stream。 此外，會議召集人和啟動錄製的人員都需要符合下列必要條件：

- 使用者擁有 Office 365 E1、E3、E5、A1、A3、A5、Microsoft 365 商務進版、商務標準版或商務基本<sup>版 1</sup>
- 使用者已同意遵守由系統管理員設定 (如果有) 的公司方針
- 使用者有足夠的 Microsoft Stream 儲存空間以儲存錄製檔案
- 使用者將 CsTeamsMeetingPolicy -AllowCloudRecording 設定設為 True，以錄製會議和群組通話
- 使用者將 CsTeamsCallingPolicy -AllowCloudRecordingForCalls 設定設為 True，以錄製 1：1 通話
- 使用者在會議中不是匿名、來賓或同盟使用者
- 若要啟用使用者會議抄寫功能，他們指派的 Teams 會議政策必須將 -AllowTranscription 設定設為 True。

<sup>1</sup> 從 2020 年 8 月 20 日開始，A1 使用者對會議錄製檔案的存取權將在 21 天后過期。 詳細資訊請參閱上傳[Microsoft Teams 會議錄製內容至 Stream。](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording)

> [!IMPORTANT] 
> 如果您只想讓使用者錄影及下載錄製內容，則使用者不必獲派 Microsoft Stream 授權。 這表示錄製內容不是儲存在 Microsoft Stream 中，而是儲存在 Async Media Services (AMS) ，在刪除前有 21 天的限制。 目前系統管理員並無法控制或管理此機制，包括加以刪除的能力。

> [!IMPORTANT]
> 此外，針對 AMS 上的錄製，錄製保留會受到聊天訊息本身的影響。 因此，如果刪除原始的 AMS 錄製聊天訊息，使用者將無法存取錄製內容。 有兩種案例可能會影響到此情況。 1) 使用者手動刪除聊天訊息 - 在此情境中，由於原始訊息消失，使用者將無法再存取錄製內容，也無法再進一步下載。 不過，錄製本身可能仍在 Microsoft 內部系統中保留一段時間， (超過原始的 21 天期間) 。 2) 聊天訊息會由聊天保留原則刪除 - AMS 錄製會直接系結到聊天保留政策。 因此，雖然 AMS 上的錄製預設會保留 21 天，再遭到刪除，但如果在 21 天期限前刪除聊天訊息，由於聊天訊息保留政策，也會一併刪除錄製內容。 之後沒有任何方法可以復原錄製內容。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>為貴組織中的使用者設定 Teams 雲端會議錄製

本節說明您可以如何設定和規劃 Teams 會議的錄製。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>為組織的使用者開啟 Microsoft Stream

Microsoft Stream 屬於合格的 Microsoft 365 和 Office 365 訂閱，或作為獨立服務的一部分提供。  如需詳細資訊，請參閱 [Stream 授權概述](https://docs.microsoft.com/stream/license-overview)。  Microsoft Stream 現在包含在 Microsoft 365 商務版、Microsoft 365 商務標準版和 Microsoft 365 商務基本版中。

深入瞭解如何在 [Microsoft 365 或 Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) 中指派授權給使用者，讓使用者能夠存取 Microsoft Stream。 確保使用者不會封鎖 Microsoft Stream，如 Microsoft Stream 的封鎖[註冊中定義。](https://docs.microsoft.com/stream/disable-user-organization)

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>確認使用者在 Microsoft Stream 中擁有上傳影片許可權

依預設，公司中的每個人都能在 Stream 中建立內容，只要有啟用 Stream 並指派授權給使用者。 Microsoft Stream 系統管理員可以[限制員工在 Stream 中建立內容](https://docs.microsoft.com/stream/restrict-uploaders)。 列入此限制清單的使用者將無法錄製會議。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知員工同意公司的 Microsoft Stream 指導方針

如果 Microsoft Stream 系統管理員已[設定公司指導方針原則](https://docs.microsoft.com/stream/company-policy-and-consent)，並要求員工在儲存內容之前先接受此原則，則使用者必須先接受，才能在 Microsoft Teams 中進行錄製。 在組織中推出錄製功能之前，請確認使用者已同意上述原則。

### <a name="turn-on-or-turn-off-cloud-recording"></a>開啟或關閉雲端錄製

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定 Teams 會議原則，以控制是否可以錄製使用者的會議。

在 Microsoft Teams 系統管理中心，開啟或關閉會議原則中的 [允許雲端錄製] 設定。 若要深入瞭解，請參閱[在 Teams 中管理會議原則](meeting-policies-in-teams.md#allow-cloud-recording)。

您可以使用 PowerShell 來設定 TeamsMeetingPolicy 中的 AllowCloudRecording 設定。 若要深入瞭解，請參閱 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

請注意，會議召集人和啟動錄製的人員都需要有錄製權限才能錄製會議。 除非您已指派自訂策略給使用者，否則使用者會取得全域原則，此全域原則預設會啟用 AllowCloudRecording。

> [!NOTE]
> 有關使用 Teams 角色來設定誰具有錄製會議的許可權，請參閱 Teams[會議的角色。](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)

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
|      我想要針對大多數的使用者關閉錄製，但選擇性地讓允許錄製的特定使用者       | <ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowCloudRecording = False<li>大部分使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = False<li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = True 的授權 <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>會議錄製內容的儲存位置

會議的錄製內容會儲存在 Microsoft Stream 雲端儲存空間。 目前，如果客戶的 Teams 資料是儲存在國內，只要儲存資料的國內資料落地區域沒有提供 Microsoft Stream，客戶的 Teams 會議錄製功能就會關閉。 會議錄製功能可以針對其資料應該儲存在國內的客戶開啟，即使 Microsoft Stream 不適用於國內資料儲存地區。 您可以允許錄製儲存在 Microsoft Stream 最近的地理區域，以完成這項操作。 

如果您的 Teams 資料是儲存在國內，而且您比較想將會議錄製內容儲存在國內，我們建議您先關閉會議錄製，然後在您將 Microsoft Stream 部署到您的國內資料落地區域後，再將會議錄製開啟。 若要關閉貴組織中所有使用者的功能，請關閉 Microsoft Teams 系統管理中心的全域 Teams 會議政策中的允許雲端錄製設定。 不過，如果您仍想要啟用錄製以儲存于 Microsoft Stream 最近的地理區域，您必須先開啟允許雲端錄製和允許區域外儲存空間，才能進行這項變更。

若要在全域原則中啟用區域內錄製，請使用下列 Cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true

Here's a summary of what happens when you turn on meeting recording when this change takes effect:

|If you turn on meeting recordings...|Meeting recordings are stored... |
|---|---|
|Before Microsoft Stream is available in your in-country data residency region |In the nearest Microsoft Stream region|
|After Microsoft Stream is available in your in-country data residency region |In your in-country data residency region|

For new and existing tenants that haven't yet turned on meeting recording, new recordings are stored in-country after Microsoft Stream is available in the in-country data residency region. However, any tenant that enables meeting recording before Microsoft Stream is available in the in-country data residency region will continue to use the Microsoft Stream storage for existing and new recordings, even after Microsoft Stream is available in the in-country data residency region.

To find the region where your Microsoft Stream data is stored, in Microsoft Stream, click **?** in the upper-right corner, click **About Microsoft Stream**, and then click **Your data is stored in**.  To learn more about the regions where Microsoft Stream stores data, see [Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

To learn more about where data is stored across services in Microsoft 365 or Office 365, see [Where is your data located?](https://products.office.com/where-is-your-data-located?rtc=1)

### Turn on or turn off recording transcription

This setting controls whether captions and transcription features are available during playback of meeting recordings. If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording. The person who started the recording needs this setting turned on so that the recording also includes transcription.

> [!NOTE]
> That transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting. They are stored together with the meeting recordings in Microsoft Stream cloud storage.

You can use the Microsoft Teams admin center or PowerShell to set a Teams meeting policy to control whether the recording initiator gets a choice to transcribe the meeting recording.

In the Microsoft Teams admin center, turn on or turn off the **Allow transcription** setting in the meeting policy. To learn more, see [Manage meeting policies in Teams](meeting-policies-in-teams.md#allow-transcription).

Using PowerShell, you configure the AllowTranscription setting in TeamsMeetingPolicy. To learn more, see [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Unless you have assigned a custom policy to the users, users get the Global policy, which has AllowTranscription disabled by default.

For a user to fall back to Global policy, use the following cmdlet to remove a specific policy assignment for a user:

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

1小時錄製內容的大小為 400 MB。 請確認您瞭解錄製檔案所需的容量，並讓 Microsoft Stream 有足夠的儲存空間可使用。  閱讀 [Microsoft Stream 授權概觀](https://docs.microsoft.com/stream/license-overview) ，以瞭解訂閱中包含的基本儲存空間，以及如何購買額外的儲存空間。

## <a name="manage-meeting-recordings"></a>管理會議錄製

會議錄製被視為租用戶擁有的內容。 如果錄製的擁有者離開公司，系統管理員可以在系統管理模式下開啟 Microsoft Stream 中的錄製影片 URL。 系統管理員可以刪除錄製內容、更新任何錄製內容的中繼資料、或變更錄製影片的權限。 深入瞭解 [Stream 中的管理功能](https://docs.microsoft.com/stream/manage-content-permissions)。

> [!NOTE]
> 如需有關管理錄製和使用者存取的其他資訊，請參閱[在 Microsoft stream 中管理使用者資料](https://docs.microsoft.com/stream/managing-user-data)和 [Microsoft Stream 中的權限和隱私權](https://docs.microsoft.com/stream/portal-permissions)。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>會議錄製的合規性與電子文件探索

會議錄製會儲存在 Microsoft Stream 中，這符合 Microsoft 365 和 Office 365 Tier-C 規範。 為了讓合規性系統管理員能透過電子探索要求尋找 Microsoft Streams 會議或通話錄製，錄製完成訊息可在 Microsoft Teams 的合規性內容搜尋功能中找到。 合規性系統管理員可以在合規性內容搜尋預覽中的項目主旨列尋找關鍵字「錄製」，並探索組織中的會議和通話錄製。 而讓他們能夠查看所有錄製的先決條件，是必須在 Microsoft Stream 中設定他們具有系統管理員存取權。 深入瞭解[在 Stream 中指派系統管理員權限](https://docs.microsoft.com/stream/assign-administrator-user-role)。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
