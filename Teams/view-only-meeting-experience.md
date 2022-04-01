---
title: 僅供檢視會議體驗
author: SerdarSoysal
ms.author: serdars
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解適用於系統管理員、簡報者和出席者的 Teams 僅供檢視會議體驗
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 032036c6f08dac76cae9ed124ffe7bc8439e4c32
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584258"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 僅供檢視會議體驗

> [!Note]
> 在 Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供僅供檢視廣播。 此功能將於 2021 年 3 月 1 日啟用，但預設為關閉。 Microsoft 365 政府社群雲端 (GCC) 中的功能將於 2021 年 3 月底開始推出。 政府社群雲端 High (GCCH) 和美國國防部 (DoD) 將於稍後推出。 如果您想要將功能設定為預設開啟，您必須在此日期之後變更預設原則。 使用 PowerShell 啟用原則 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。

> [!Note]
> 如果您的會議達到容量限制，Teams 將會無縫調整，以容納 10,000 人僅供檢視的廣播體驗。 此外，在遠端工作數量增加的這段時間裡，到今年年底，請利用 20,000 人的更大廣播容量。 網路研討會目前不支援僅供檢視的廣播體驗。

Microsoft Teams 允許最多 10,000 位出席者加入 Teams 會議。 達到主要會議的容量限制後 (即 1000 位使用者進入會議時)，其他出席者將以僅供檢視體驗加入。

先加入會議的出席者，在達到主要會議容量限制前，都可獲得完整的 Teams 會議體驗。 他們可以分享音訊和視訊、查看分享的視訊以及參與會議聊天。

主要會議容量到達後加入的出席者將擁有僅供檢視體驗。

出席者將能夠透過電腦版、Web 版和 Teams 行動版 (Android 和 iOS) 加入僅供檢視體驗。

> [!Note]
> 「主要會議」的目前容量限制或換句話說，完全互動的使用者數目為 1000 個，且包含 GCC 和網路研討會。

## <a name="teams-view-only-experience-controls"></a>Teams 僅供檢視體驗控制

您可以使用來自 [SkypeForBusiness PowerShell 模組](/powershell/module/skype/?view=skype-ps)或 [MicrosoftTeams 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)至少 2.0.0 版的 [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) Cmdlet 啟用僅供檢視體驗。

若要使用建議的 `MicrosoftTeams` 模組：

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

若要啟用僅供檢視體驗，您可以使用下列 PowerShell 程式碼片段：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

若要停用僅供檢視體驗，您也可以使用 PowerShell。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

未來，您可以在 Teams 系統管理中心啟用或停用僅供檢視體驗。

## <a name="impact-to-users"></a>對使用者的影響

使用者的體驗會根據數個因素而不同。

達到主要會議的容量限制後，如果下列任一情況成立，出席者將無法加入會議：

- 系統管理員已為召集人或整個租用戶停用 Teams 的僅供檢視體驗。
- 僅供檢視出席者無法略過大廳。 例如，如果會議的召集人選擇只讓 **我組織中的人員** 略過大廳，而組織外的出席者嘗試以僅供檢視出席者形式加入，他們將無法加入。

達到主要會議的容量限制後，會議召集人和簡報者會看到一個橫幅，通知他們新出席者將以僅供檢視參與者形式加入。

  ![給召集者和簡報者的 Teams 用戶端和橫幅訊息。](media/chat-and-banner-message.png)

達到主要會議的容量限制後，系統將在加入前的畫面上通知會議出席者他們正在以僅供檢視模式加入。

  ![Teams 加入前畫面以及給參與者的訊息，告知他們將以僅供檢視模式加入。](media/view-only-pre-join-screen.png)

如果有空間，使用者一律可以加入主要會議。 達到主要會議容量限制後，如果一或多位出席者離開主要會議，則主要會議會釋出容量可供加入。 加入 (或重新加入) 會議的出席者將加入主要會議，直到再次達到容量限制。 處於僅供檢視體驗的出席者無法自動升級到主要會議，且無法手動將他們升級到主要會議。

如果已設定簡報者和出席者角色，且簡報者在主要會議達到容量限制後嘗試加入會議，他們將以僅供檢視出席者形式加入，且具有與其他僅供檢視出席者相同的限制。 可確保所有簡報者加入主要會議的支援將於稍後推出。 一律會保證召集人擁有主要會議中的空間。

## <a name="impact-to-meeting-presenters-and-organizers"></a>對會議簡報者和召集人的影響

會議簡報者和召集人的限制包括：

- 您沒有僅供檢視出席者的資訊。 我們不支援僅供檢視出席者使用電子文件探索。
- 主要會議中的使用者看不到僅供檢視出席者。
- 您無法從會議移除僅供檢視出席者。

> [!Note]
> 出席者數只會反映主要會議中的人員，不會反映僅供檢視會議室中的人員。 因此，簡報者無法取得使用僅供檢視體驗的確切人數。

## <a name="experience-for-view-only-attendees"></a>僅供檢視出席者的體驗

Teams 僅供檢視體驗可讓出席者：

- 聆聽 Teams 主要會議的參與者發言。
- 觀看目前主講人的視訊摘要 (如果目前主講人有分享視訊)。
- 使用共用桌面或畫面分享功能查看共用的內容。

僅供檢視出席者將無法在會議中體驗下列選項：

- 如果根據設定的大廳原則或選項，出席者沒有略過大廳的權限，則無法加入會議。
- 無法使用音訊會議加入僅供檢視會議室。
- 無法使用 Microsoft Teams 會議室系統或雲端視訊 Interop (CVI) 服務加入僅供檢視會議室。
- 無法分享他們的音訊或視訊。
- 無法查看或參與會議聊天。
- 無法觀看會議參與者的視訊摘要，除非參與者是目前的主講人。
- 查看使用 PowerPoint Live 功能或個別應用程式共用 (桌面共用或螢幕畫面分享除外) 而共用的 PowerPoint 檔案。
- 在會議中舉手。
- 傳送或查看回應。
- 與整合至 Teams 會議的任何第三方應用程式互動，包括投票。
- 存取會議錄製。

## <a name="view-only-feature-limitations"></a>僅供檢視功能限制

- 僅供檢視出席者只能在桌面版和 Web 版上查看即時字幕。 目前僅支援英文字輔助字幕。
- 僅供檢視出席者無法註冊網路研討會。
- 串流技術將支援僅供檢視出席者。
- 出席報告中不會包含僅供檢視出席者。
- 僅供檢視出席者將擁有單一視訊體驗。 他們可以看到目前主講人或正在共用的內容，但不能同時看到兩者。
- 我們目前不支援僅供檢視出席者使用 **圖庫**、**大型圖庫** 或 **在一起模式** 版面配置。
- 只有下列大廳政策支援僅能觀看的出席者：'我的組織人員'、'我的組織人員與來賓'、'我的組織人員、信任的組織及來賓'，以及'所有人'。 如果您使用的大廳原則不支援僅供檢視出席者，則會拒絕僅供檢視出席者加入會議。 
- 僅供檢視出席者不會有與一般出席者相同的延遲。<sup>1</sup>

  <sup>1</sup> 僅供檢視出席者在會議中會有 30 秒的視訊和音訊延遲。  
