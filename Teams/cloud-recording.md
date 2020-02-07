---
title: Teams 雲端會議錄製
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在 Microsoft 團隊中部署雲端語音功能的實用指導方針。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38981774af168c978371b06d8de6eeedd4b16644
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825601"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 雲端會議錄製

> [!IMPORTANT]
> **在將來，我們會進行設定變更**，讓團隊會議錄製功能針對其小組資料儲存在全國的客戶，即使 Microsoft Stream 無法在國內資料常駐區域中使用也一樣。 當此變更生效時，會議錄製會預設儲存在最接近的 Microsoft 串流區域中。 如果您的小組資料是儲存在國內，而且您想要將會議錄製儲存在國內，建議您先關閉會議錄製，然後再將其開啟，然後再將 Microsoft Stream 部署到您的國內區域。 若要深入瞭解，請參閱[會議錄製的儲存位置](#where-your-meeting-recordings-are-stored)。

在 Microsoft 團隊中，使用者可以記錄其小組會議與群組通話，以捕獲音訊、影片和螢幕共用活動。 您也可以使用自動轉錄的錄製選項，便於使用者播放具有隱藏式輔助字幕的會議錄製，並在文字記錄中搜尋重要的討論項目。 錄製會在雲端進行，並儲存到[Microsoft Stream](https://docs.microsoft.com/stream/)，讓使用者可以安全地在其組織中共用檔案。

相關：[團隊會議錄製最終使用者檔](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>團隊雲端會議錄製的先決條件

若要錄製小組使用者的會議，必須針對租使用者啟用 Microsoft Stream。 此外，會議召集人和開始錄製的人員也必須具備下列先決條件：

- 使用者擁有 Office 365 E1、E3、E5、A1、A3、A5、M365 Business、Business Premium 或 Business Essentials
- 使用者需要取得 Microsoft Stream<sup>1</sup>的授權 
- 使用者擁有 Microsoft Stream 上傳影片的許可權
- 使用者已在由管理員設定的情況下，同意公司指引
- 使用者在 Microsoft Stream 中擁有足夠的儲存空間，以供儲存錄製
- 使用者已將 TeamsMeetingPolicy-AllowCloudRecording 設定設為 true
- 使用者不是會議中的匿名、來賓或同盟使用者

> [!NOTE]
> 此外，若要讓啟動錄製的人選擇是否要自動將抄寫錄製，使用者的 TeamsMeetingPolicy-AllowTranscription 設定必須設定為 true。

<sup>1</sup>使用者必須有授權，才能將會議上傳/下載到 Microsoft Stream，但他們不需要有錄製會議的授權。 如果您想要封鎖使用者錄製 Microsoft 團隊會議，您必須授與 AllowCloudRecording 設定為 $False 的 TeamsMeetingPolicy。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>為組織中的使用者設定小組雲端會議錄製

本節說明如何針對錄製團隊會議進行設定和規劃。

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>為組織中的使用者啟用 Microsoft Stream

Microsoft Stream 是以符合資格的 Office 365 訂閱或獨立服務的形式提供。  如需詳細資訊，請參閱[資料流程授權概覽](https://docs.microsoft.com/stream/license-overview)。  Microsoft Stream 現已包含在 Microsoft 365 商務版、Office 365 Business Premium 和 Office 365 Business Essentials 中。

深入瞭解如何[在 Office 365 中指派授權給使用者](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，讓使用者可以存取 Microsoft Stream。 確定沒有針對使用者封鎖 Microsoft Stream，[如本文所定義。](https://docs.microsoft.com/stream/disable-user-organization)

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>確保使用者在 Microsoft Stream 中有上傳視頻許可權

根據預設，公司中的每個人都可以在串流中建立內容、啟用資料流程並指派授權給使用者。 Microsoft Stream 管理員可以限制員工在串流中[建立內容](https://docs.microsoft.com/stream/restrict-uploaders)。 在此受限制清單中的使用者將無法錄製會議。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知員工在 Microsoft Stream 中同意公司的指導方針

如果 Microsoft 串流管理員已[設定公司準則原則](https://docs.microsoft.com/stream/company-policy-and-consent)，且需要員工在儲存內容之前接受此原則，使用者必須先進行，然後才能在 Microsoft 團隊中進行錄製。 在您推出組織中的錄製功能前，請確定使用者已同意原則。

### <a name="turn-on-or-turn-off-cloud-recording"></a>開啟或關閉雲端錄製

您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定團隊會議原則，以控制使用者的會議是否可以錄製。

在 Microsoft [團隊系統管理中心] 中，開啟或關閉會議原則中的 [**允許雲端錄製**] 設定。 若要深入瞭解，請參閱[在團隊中管理會議原則](meeting-policies-in-teams.md#allow-cloud-recording)。

使用 PowerShell，您可以設定 TeamsMeetingPolicy 中的 AllowCloudRecording 設定。 若要深入瞭解，請參閱[新-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)及[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

請注意，會議召集人和錄製啟動器都需要有錄製會議的許可權。 除非您已將自訂原則指派給使用者，否則使用者會取得全域原則，預設會停用 AllowCloudRecording。

如果使用者要回退到全域原則，請使用下列 Cmdlet 來移除使用者的特定原則指派：

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要在全域原則中變更 AllowCloudRecording 的值，請使用下列 Cmdlet：

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 例子                                                                 |                                                                                                                                                                         步驟                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    我想要讓公司中的所有使用者都能錄製會議                                    |                                                                     <ol><li>確認全域 CsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>所有使用者都有具有 AllowCloudRecording = True 的全域 CsTeamsMeetingPolicy 或其中一個 CsTeamsMeetingPolicy 原則 </ol>                                                                     |
| 我想讓我的大多數使用者能夠錄製會議，但有選擇性地停用不允許錄製的特定使用者 |        <ol><li>確認 GlobalCsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>大部分的使用者都有全域 CsTeamsMeetingPolicy 或其中一個 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 原則<li>所有其他使用者都已授與 AllowCloudRecording = False 的其中一個 CsTeamsMeetingPolicy 原則</ol>         |
|                                                   我想要將錄製設為停用100%                                                   |                                                                <ol><li>確認全域 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>所有使用者都已授與 AllowCloudRecording = False 的全域 CsTeamsMeetingPolicy 或其中一個 CsTeamsMeetingPolicy 原則                                                                 |
|      我想要針對大多數使用者停用錄製，但有選擇性地啟用允許錄製的特定使用者       | <ol><li>確認全域 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>大多數的使用者都是使用 AllowCloudRecording = False 授與全域 CsTeamsMeetingPolicy 或其中一個 CsTeamsMeetingPolicy 原則<li>所有其他使用者都已授與 AllowCloudRecording = True 的其中一個 CsTeamsMeetingPolicy 原則 <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>您的會議錄製儲存位置

會議錄製會儲存在 Microsoft Stream 雲端儲存空間中。 目前，如果 Microsoft 資料流程無法在儲存資料的國內資料派駐區域中使用 Microsoft Stream，則會針對其小組資料儲存在國內的客戶關閉會議錄製功能。 將來，即使 Microsoft Stream 無法在國內資料派駐區域中使用，也會針對資料儲存在國內的客戶開啟會議錄製功能。

當此變更生效時，預設會將會議錄製儲存在 Microsoft Stream 最近的地理區域中。 如果您的小組資料是儲存在國內，而且您想要將會議錄製儲存在國內，建議您關閉此功能，然後在將 Microsoft Stream 部署到您的國內資料派駐區域之後，再將它開啟。 若要關閉貴組織中所有使用者的功能，請在 Microsoft 團隊管理中心，關閉 [全域團隊會議原則] 中的 [**允許雲端錄製**] 設定。

以下摘要顯示當您在此變更生效時開啟會議錄製時會發生的情況：

|如果您開啟 [會議錄製 ...] |已儲存會議錄製 .。。  |
|---------|---------|
|在您的國內資料派駐區域中提供 Microsoft Stream 之前    |在最接近的 Microsoft 串流區域中         |
|在您的國內資料派駐區域中提供 Microsoft Stream 之後    | 在您的國內資料派駐區域中        |

針對尚未開啟會議錄製的新與現有租使用者，在國內資料派駐區域中提供 Microsoft Stream 之後，新的錄製會儲存在國內。 不過，在使用 Microsoft Stream 之前啟用會議錄製的任何租使用者，在國內資料派駐區域中都可以繼續使用 Microsoft 資料流程儲存空間，即使在國內資料常駐區域。

若要找出儲存 Microsoft 資料流程資料的地區，請在 Microsoft Stream 中按一下 **？** 按一下右上角的 [**關於 Microsoft Stream**]，然後按一下**您的資料儲存在中**。  若要深入瞭解 Microsoft Stream 儲存資料的地區，請參閱[Microsoft 資料流程常見問題](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)。

若要深入瞭解如何在 Office 365 的各個服務中儲存資料，請參閱[您的資料位於何處？](https://products.office.com/en-us/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>開啟或關閉 [錄製會議]

當使用者記錄其小組會議時，他們可以確認在錄製會議之後是否應該自動產生記錄。 如果您已停用會議召集人與錄製發起者的「會議」功能，錄製發起者就不會取得將抄寫會議錄製的選項。

您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定團隊會議原則，以控制錄製發起者是否能取得將抄寫會議錄製的選項。

在 Microsoft [團隊系統管理中心] 中，開啟或關閉會議原則中的 [**允許**會議] 設定。 若要深入瞭解，請參閱[在團隊中管理會議原則](meeting-policies-in-teams.md#allow-transcription)。

使用 PowerShell，您可以設定 TeamsMeetingPolicy 中的 AllowTranscription 設定。 若要深入瞭解，請參閱[新-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)及[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

除非您已將自訂原則指派給使用者，否則使用者會取得全域原則，預設會停用 AllowTranscription。

若要讓使用者回到全域原則，請使用下列 Cmdlet 來移除使用者的特定原則指派：

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要在全域原則中變更 AllowCloudRecording 的值，請使用下列 Cmdlet：

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|例子|步驟 |
|---|---|
|我希望公司中的所有使用者都能在開始錄製會議時將抄寫 |<ol><li>確認全域 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>所有使用者都有具有 AllowTranscription = True 的全域 csTeamsMeetingPolicy 或其中一個 CsTeamsMeetingPolicy 原則。 </ol>|
|我想讓我的大多數使用者能夠將抄寫會議錄製，但有選擇性地停用不允許將抄寫的特定使用者 |<ol><li>確認全域 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>大部分的使用者都有全域 CsTeamsMeetingPolicy 或其中一個 AllowTranscription = True 的 CsTeamsMeetingPolicy 原則 <li>所有其他使用者都已授與 AllowTranscription = False 的其中一個 CsTeamsMeetingPolicy 原則 </ol>|
|我想要將錄製的畫面停成100% |<ol><li>確認全域 CsTeamsMeetingPolicy 具有 AllowTranscription = False <li>所有使用者都已授與 AllowTranscription = False 的全域 CsTeamsMeetingPolicy 或其中一個 CsTeamsMeetingPolicy 原則 </ol>|
|我想要針對大多數的使用者停用，但有選擇性地啟用允許將抄寫的特定使用者 |<ol><li>確認全域 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False <li>大多數的使用者都是使用 AllowCloudRecording = False 授與全域 CsTeamsMeetingPolicy 或其中一個 CsTeamsMeetingPolicy 原則 <li>所有其他使用者都已授與 AllowCloudRecording = True 的其中一個 CsTeamsMeetingPolicy 原則 </ol>|
|||

### <a name="planning-for-storage"></a>規劃儲存

1小時錄製的大小為 400 MB。 請務必瞭解錄製的檔案所需的容量，並在 Microsoft Stream 中擁有足夠的儲存空間。  閱讀本文以瞭解訂閱中包含的基本[儲存體，以及](https://docs.microsoft.com/stream/license-overview)如何購買額外的儲存空間。

## <a name="manage-meeting-recordings"></a>管理會議錄製

會議錄製被視為由租使用者擁有的內容。 如果錄製的擁有者離開公司，系統管理員可以在 [系統管理模式] 中開啟 Microsoft Stream 中的錄製影片 URL。 系統管理員可以刪除錄製、更新任何錄製的中繼資料，或變更錄製影片的許可權。 深入瞭解[資料流程中的系統管理功能](https://docs.microsoft.com/stream/manage-content-permissions)。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>相容性與 eDiscovery for 會議錄製

會議錄製會儲存在 Microsoft Stream 中，這是 Office 365 與 C-C 相容性。 若要支援針對 Microsoft 串流的會議或通話錄製所需合規性管理員的電子探索要求，錄製已完成訊息可在 Microsoft 團隊的合規性內容搜尋功能中取得。 合規性管理員可以在 [合規性內容] 搜尋預覽中尋找專案主旨行中的關鍵字「錄製」，並在組織中尋找會議和通話記錄。 若要讓他們查看所有錄製，必須在 Microsoft Stream 中以系統管理員的身分設定。 深入瞭解[在資料流程中指派系統管理員許可權](https://docs.microsoft.com/stream/assign-administrator-user-role)。

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)
