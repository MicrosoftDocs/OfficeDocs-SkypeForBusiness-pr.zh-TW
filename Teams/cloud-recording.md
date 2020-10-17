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
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在團隊中部署雲端語音功能以錄製小組會議與群組通話以捕獲音訊、影片和螢幕共用活動的實用指導方針。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0030cdc3a7e4929435127f9c4fbe549c7a6bf20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503460"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 雲端會議錄製

在 Microsoft Teams 中，使用者可以錄製其 Teams 會議和群組通話，擷取音訊、視訊和螢幕共用的活動。 您也可以使用自動轉錄的錄製選項，便於使用者播放具有隱藏式輔助字幕的會議錄製，並在文字記錄中搜尋重要的討論項目。 錄製會在雲端進行，並儲存到 [Microsoft Stream](https://docs.microsoft.com/stream/)，使用者可以因此安全地在整個組織內共用檔案。

相關：[Teams 會議錄製使用者文件](https://aka.ms/recordmeeting)

>[!Note]
> 從使用 Microsoft Stream 到變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。 剛開始時，您可以加入這項體驗，在 11 月如果您想要繼續使用 Stream，則必須退出體驗，而在 2021 年初的某刻，我們將要求所有客戶使用商務用 OneDrive 和 SharePoint 來進行會議錄製。

> [!NOTE]
> 如需在團隊會議中使用角色的相關資訊，以及如何變更使用者的角色，請參閱 [小組會議中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 雲端會議錄製的必要條件

若要錄製小組使用者的會議，必須針對租使用者啟用 Microsoft Stream。 此外，會議召集人和啟動錄製的人員都需要符合下列必要條件：

- 使用者擁有 Office 365 E1、E3、E5、A1、A3、A5、Microsoft 365 Business Premium、商務標準版或 Business Basic<sup>1</sup>
- 使用者需要取得 Microsoft Stream<sup>2</sup>的授權 
- 使用者擁有 Microsoft Stream 上傳影片的權限
- 使用者已同意遵守由系統管理員設定 (如果有) 的公司方針
- 使用者有足夠的 Microsoft Stream 儲存空間以儲存錄製檔案
- 使用者已將 TeamsMeetingPolicy-AllowCloudRecording 設定設為 true
- 使用者在會議中不是匿名、來賓或同盟使用者
- 若要為使用者的會議啟用會議，指派給他們的小組會議原則必須將-AllowTranscription 設定設定為 true。

<sup>1</sup> 截止2020年8月20日，對於有 A1 的使用者，會議錄製檔案的存取權會在21天后到期。 如需詳細資訊，請參閱 [上傳 Microsoft 團隊會議錄製以進行串流](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording)。

<sup>2</sup> 使用者必須有授權，才能將會議上傳/下載到 Microsoft Stream，但他們不需要錄製會議的授權。 如果您想要封鎖使用者不讓他錄製 Microsoft Teams 會議，您必須授予一個將 AllowCloudRecording 設定為 $False 的 TeamsMeetingPolicy。

> [!IMPORTANT] 
> 如果您只想讓使用者錄影及下載錄製內容，則使用者不必獲派 Microsoft Stream 授權。 這會代表錄製不會儲存在 Microsoft Stream 中，而是儲存在 Azure 媒體服務 (的 AMS) 中，在刪除前會有21天的限制。 目前系統管理員並無法控制或管理此機制，包括加以刪除的能力。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>為貴組織中的使用者設定 Teams 雲端會議錄製

本節說明您可以如何設定和規劃 Teams 會議的錄製。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>針對組織中的使用者開啟 Microsoft Stream

Microsoft Stream 是以合格的 Microsoft 365 與 Office 365 訂閱或獨立服務的形式提供。  如需詳細資訊，請參閱 [Stream 授權概述](https://docs.microsoft.com/stream/license-overview)。  Microsoft Stream 現已包含在 Microsoft 365 商務版、Microsoft 365 商務標準版和 Microsoft 365 Business Basic 中。

深入瞭解如何 [在 Microsoft 365 或 Office 365 中指派授權給使用者](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) ，讓使用者可以存取 microsoft Stream。 確定沒有針對使用者封鎖 Microsoft Stream，如在 [封鎖註冊] 中定義的 [ [Microsoft stream](https://docs.microsoft.com/stream/disable-user-organization)]。

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>確定使用者已在 Microsoft Stream 中上傳視頻許可權

依預設，公司中的每個人都能在 Stream 中建立內容，只要有啟用 Stream 並指派授權給使用者。 Microsoft Stream 系統管理員可以[限制員工在 Stream 中建立內容](https://docs.microsoft.com/stream/restrict-uploaders)。 列入此限制清單的使用者將無法錄製會議。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知員工同意公司的 Microsoft Stream 指導方針

如果 Microsoft Stream 系統管理員已[設定公司指導方針原則](https://docs.microsoft.com/stream/company-policy-and-consent)，並要求員工在儲存內容之前先接受此原則，則使用者必須先接受，才能在 Microsoft Teams 中進行錄製。 在組織中推出錄製功能之前，請確認使用者已同意上述原則。

### <a name="turn-on-or-turn-off-cloud-recording"></a>開啟或關閉雲端錄製

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定 Teams 會議原則，以控制是否可以錄製使用者的會議。

在 Microsoft Teams 系統管理中心，開啟或關閉會議原則中的 [允許雲端錄製]**** 設定。 若要深入瞭解，請參閱[在 Teams 中管理會議原則](meeting-policies-in-teams.md#allow-cloud-recording)。

您可以使用 PowerShell 來設定 TeamsMeetingPolicy 中的 AllowCloudRecording 設定。 若要深入瞭解，請參閱 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

請注意，會議召集人和啟動錄製的人員都需要有錄製權限才能錄製會議。 除非您已將自訂原則指派給使用者，否則使用者會取得全域原則，預設會啟用 AllowCloudRecording。

> [!NOTE]
> 如需使用團隊角色來設定誰有權錄製會議的詳細資訊，請參閱 [小組會議中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

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
|      我想要針對大多數使用者關閉錄製，但有選擇性地啟用允許錄製的特定使用者       | <ol><li>確認 Global CsTeamsMeetingPolicy 有 AllowCloudRecording = False<li>大部分使用者都獲得 Global CsTeamsMeetingPolicy 原則或是其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = False<li>所有其他使用者都獲得其中一個 CsTeamsMeetingPolicy 原則有 AllowCloudRecording = True 的授權 <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>會議錄製內容的儲存位置

會議的錄製內容會儲存在 Microsoft Stream 雲端儲存空間。 錄製會保留，且可供查看並下載21天。 目前，如果客戶的 Teams 資料是儲存在國內，只要儲存資料的國內資料落地區域沒有提供 Microsoft Stream，客戶的 Teams 會議錄製功能就會關閉。 將來，只要客戶的 Teams 資料是儲存在國內，其會議錄製功能就會開啟，即使該國內資料落地區域沒有提供 Microsoft Stream。

當此改變生效時，會議錄製內容預設會儲存在最靠近 Microsoft Stream 的地理區域。 如果您的 Teams 資料是儲存在國內，而且您比較想將會議錄製內容儲存在國內，我們建議您先關閉會議錄製，然後在您將 Microsoft Stream 部署到您的國內資料落地區域後，再將會議錄製開啟。 若要關閉貴組織中所有使用者的功能，請關閉 Microsoft 團隊系統管理中心的 [全域團隊會議原則] 中的 [ **允許雲端錄製** ] 設定。 不過，如果您仍想要讓錄製儲存在最近的 Microsoft Stream 地理區域中，您必須同時開啟 [ **允許雲端錄製** ] 和 [在 **區域外錄製儲存空間** ]，才能進行這項變更。

若要在區域中啟用 [全域原則] 的錄製，請使用下列 Cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global – AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```


以下摘要說明在此改變生效後，當您開啟會議錄製會發生什麼情況：

|如果您開啟 [會議錄製 ...]|會議錄製內容會儲存在... |
|---|---|
|在您的國內資料派駐區域中提供 Microsoft Stream 之前 |在最接近的 Microsoft 串流區域中|
|在您的國內資料派駐區域中提供 Microsoft Stream 之後 |在您的國內資料派駐區域中|

針對尚未開啟會議錄製的新的和現有租用戶，在國內資料落地區域提供 Microsoft Stream 之後，新的錄製內容會儲存在國內。 不過，在使用 Microsoft Stream 之前啟用會議錄製的任何租使用者，在國內資料派駐區域中都可以繼續使用 Microsoft 資料流程儲存空間，即使是在國內資料派駐區域中提供 Microsoft stream 之後也一樣。

若要找出您的 Microsoft Stream 資料的儲存區域，請在 Microsoft Stream 中按一下 [?]**** (在右上角)，按一下 [關於 Microsoft Stream]****，然後按一下 [您的資料儲存位置]****。  若要深入瞭解 Microsoft Stream 儲存資料的區域，請參閱 [Microsoft Stream 常見問題集](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)。

若要深入瞭解在 Microsoft 365 或 Office 365 中跨服務儲存資料的位置，請參閱 [您的資料位於何處？](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>開啟或關閉錄製內容謄寫

此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。 如果您關閉此功能，則在播放會議錄製期間將無法使用 [ **搜尋** ] 和 [ **抄送** ] 選項。 開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。

> [!NOTE]
> 目前僅支援將小組中的語言設定為英文，且在會議中朗讀英文的使用者，才能使用該會議。 它們會與 Microsoft Stream 雲端儲存中的會議錄製一起儲存在一起。

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定 Teams 會議原則，控制啟動錄製的人員是否可以選擇謄寫會議錄製內容。

在 Microsoft Teams 系統管理中心，開啟或關閉會議原則中的 [允許謄寫]**** 設定。 若要深入瞭解，請參閱[在 Teams 中管理會議原則](meeting-policies-in-teams.md#allow-transcription)。

您可以使用 PowerShell 來設定 TeamsMeetingPolicy 中的 AllowTranscription 設定。 若要深入瞭解，請參閱 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

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

1小時錄製內容的大小為 400 MB。 請確認您瞭解錄製檔案所需的容量，並讓 Microsoft Stream 有足夠的儲存空間可使用。  閱讀 [Microsoft Stream 授權概述](https://docs.microsoft.com/stream/license-overview) ，瞭解訂閱中包含的基本儲存體，以及如何購買額外的儲存空間。

## <a name="manage-meeting-recordings"></a>管理會議錄製

會議錄製被視為租用戶擁有的內容。 如果錄製的擁有者離開公司，系統管理員可以在系統管理模式下開啟 Microsoft Stream 中的錄製影片 URL。 系統管理員可以刪除錄製內容、更新任何錄製內容的中繼資料、或變更錄製影片的權限。 深入瞭解 [Stream 中的管理功能](https://docs.microsoft.com/stream/manage-content-permissions)。

> [!NOTE]
> 如需有關管理錄製和使用者存取的其他資訊，請參閱[在 Microsoft stream 中管理使用者資料](https://docs.microsoft.com/stream/managing-user-data)和 [Microsoft Stream 中的權限和隱私權](https://docs.microsoft.com/stream/portal-permissions)。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>會議錄製的合規性與電子文件探索

會議錄製會儲存在 Microsoft Stream 中，這是 Microsoft 365 和 Office 365 與 C 相容的相容性。 為了讓合規性系統管理員能透過電子探索要求尋找 Microsoft Streams 會議或通話錄製，錄製完成訊息可在 Microsoft Teams 的合規性內容搜尋功能中找到。 合規性系統管理員可以在合規性內容搜尋預覽中的項目主旨列尋找關鍵字「錄製」，並探索組織中的會議和通話錄製。 而讓他們能夠查看所有錄製的先決條件，是必須在 Microsoft Stream 中設定他們具有系統管理員存取權。 深入瞭解[在 Stream 中指派系統管理員權限](https://docs.microsoft.com/stream/assign-administrator-user-role)。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
