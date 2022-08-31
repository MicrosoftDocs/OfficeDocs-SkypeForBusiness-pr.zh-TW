---
title: 記錄管理和轉譯的會議原則
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: 瞭解如何在 Teams 中管理會議原則設定，以進行錄製和轉譯。
ms.openlocfilehash: 57e90984cde312f1804d5d2144c82a4d252822b6
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466201"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>記錄&轉錄的會議原則設定

本文將說明 Teams 會議中錄製和轉譯的特定會議原則設定。 您可以在 [**會議**  >  **會議** 原則] 下的小組系統管理中心找到這些設定。

## <a name="transcription"></a>轉錄

這是每個召集人和個別使用者原則的組合。 此設定可控制在播放會議錄製內容期間是否提供字幕和謄寫功能。 開始錄製的人需要開啟此設定，才能使用這些功能進行錄製。

開啟此設定將建立與會議錄製內容一起儲存的文字記錄，從而在會議錄製內容中啟用 **[搜尋]**、**[CC]** 和 **[文字記錄]**。

錄製會議的轉譯目前僅支援在 Teams 會議中設定語言或說英文的使用者。

## <a name="cloud-recording"></a>雲端錄製

此設定結合了每個召集人及個別使用者的原則，並控制是否可以錄製會議。 如果參與者的原則設定已開啟，且對方是來自同一個組織的已驗證使用者，則會議召集人或另一個會議參與者就可以開始錄製。

組織外部人員 (例如，同盟和匿名使用者) 無法開始錄製。 來賓無法開始或停止錄製。

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

讓我們看看下列範例。

| 使用者                 | 會議原則         | 允許雲端錄製 |
|----------------------|------------------------|-----------------------|
| Daniela              | 全域                 | 關閉                   |
| Amanda               | Location1MeetingPolicy | 開啟                    |
| John (外部)  | 不適用         | 不適用        |

- 您無法錄製由 Daniela 召集的會議。
- 拉格無法錄製由 Daniela 召集的會議。
- 您可以錄製由「小組」召集的會議。
- Daniela 無法錄製由 10 月 2 日召集的會議。
- John 無法錄製由[匯入] 召集的會議。

若要深入了解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

## <a name="meetings-automatically-expire"></a>會議自動過期

此設定會控制會議錄製是否自動過期。 開啟此設定之後，您會得到設定預設到期時間的選項，以天數為單位。

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="來自 Teams 系統管理中心自動會議到期設定的螢幕擷取畫面。":::

此設定提供簡單的工具，可減少舊版錄製的儲存量。 OneDrive 和 SharePoint 系統會監控所有會議錄製的到期日，並自動將錄製在到期日移至回收站。

### <a name="default-expiration-time"></a>預設到期時間

所有新建立的會議錄製都會有 120 天的預設到期日;在開啟此功能後建立的所有錄製都會在建立日期後的 120 天內刪除。

> [!NOTE]
> A1 使用者的預設到期時間上限為 30 天。

#### <a name="changing-default-expiration-time"></a>變更預設到期時間

系統管理員可以在 PowerShell 或 Teams 系統管理中心編輯預設到期時間設定。 任何變更只會影響之前新建立的會議錄製內容;不會影響該日期之前建立的任何錄製。

系統管理員無法變更現有會議錄製的到期時間。 這樣做是為了保護擁有錄製內容之使用者的決定。 會議和通話都可以由此設定控制。

到期值是天數的整數。  這可以設定為：

- 最小值： **1**
- 最大值： **99999**
- 您也可以在 PowerShell 中將到期時間設定為 **-1** ，讓錄製永遠不會過期。

PowerShell 命令範例：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>合規性

您不應該依賴會議到期設定來提供法律保護，因為使用者可以修改他們所控制之任何錄製的到期日。

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>在 Microsoft Purview 中錄製到期設定和 Microsoft 365 保留原則

檔案保留優先于檔案刪除。 在保留期間完成之前，Teams 會議錄製到期原則無法刪除具有許可權保留原則的 Teams 會議錄製。 例如，如果您的 [許可權] 保留原則指出檔案將保留五年，而 Teams 會議錄製到期原則設定為 60 天，則 Teams 會議錄製到期原則會在五年後刪除錄製內容。

如果您有不同刪除日期的 Teams 會議錄製到期原則和許可權刪除原則，檔案會在兩個日期的最早日期刪除。 例如，如果您的 [許可權] 刪除原則指出檔案將在一年後刪除，而 Teams 會議錄製到期日設定為 120 天，則 Teams 會議錄製到期原則會在 120 天后刪除該檔案。

除非有禁止錄製的許可權保留原則，否則使用者可以在到期日之前手動刪除錄製內容。

### <a name="deletion-of-recordings"></a>刪除錄製內容

錄製內容通常會在到期日後的一天內刪除，但在少數情況下可能需要長達五天的時間。 檔案擁有者會在錄製到期時收到電子郵件通知，並會導向至回收站以復原錄製內容。

> [!NOTE]
> 在到期日，錄製會移至回收站，並清除到期日欄位。 如果您從回收站復原錄製內容，此功能將不會再次刪除該錄製，因為已清除到期日。

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>從 Stream (傳統版) 移轉錄製的到期日

從Stream (傳統版) 移轉的錄製不會隨附到期套件。 相反地，我們鼓勵系統管理員只移轉他們想要保留的錄製。 如需詳細資料[，請參閱Stream (傳統版) 移轉檔](/stream/streamnew/stream-classic-to-new-migration-overview)。

## <a name="store-recordings-outside-of-your-country-or-region"></a>儲存您國家或地區以外的錄製內容

此原則會控制會議記錄是否可以永久儲存在其他國家或地區。 如果已啟用，則無法移轉錄製內容。 如需有關雲端會議以及儲存錄製內容的詳細資訊，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

## <a name="related-topics"></a>相關主題

- [管理 Teams 中的會議原則](meeting-policies-overview.md)
- [在 Teams 中指派原則給使用者](policy-assignment-overview.md)
- [雲端會議錄製](cloud-recording.md)
- [管理誰可以排程會議](manage-who-can-schedule-meetings.md)
