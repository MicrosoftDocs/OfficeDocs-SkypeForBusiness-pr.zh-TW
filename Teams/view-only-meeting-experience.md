---
title: 僅供檢視會議體驗
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解適用於系統管理員、簡報者和出席者的 Teams 僅供檢視會議體驗
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875053"
---
# <a name="teams-view-only-meeting-experience"></a>Teams 僅供檢視會議體驗

> [!Note]
> 在 Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供僅供檢視廣播。 此功能將於 2021 年 3 月 1 日啟用，但預設為關閉。 Microsoft 365 政府社群雲端 (GCC) 中的功能將於 2021 年 3 月底開始推出。 政府社群雲端 High (GCCH) 和美國國防部 (DoD) 將於稍後推出。 如果您想要將功能設定為預設開啟，您必須在此日期之後變更預設原則。 使用 PowerShell 啟用原則 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。

> [!Note]
> 如果您的會議或網路研討會達到容量限制，Teams 將會無縫調整，以容納 10,000 人僅供檢視廣播體驗。 此外，在遠端工作數量增加的這段時間裡，到今年年底，請利用 20,000 人的更大廣播容量。

Microsoft Teams 允許最多 10,000 位出席者加入 Teams 會議。 達到主要會議的容量限制後，其他出席者將透過僅供檢視體驗加入。

第一次加入會議的出席者，直到達到會議容量限制前，都可獲得完整的 Teams 會議體驗。 他們可以分享音訊和視訊、查看分享的視訊以及參與會議聊天。

主要會議容量到達後加入的出席者將擁有僅供檢視體驗。

我們擁有完整的 Android 和 iOS 行動裝置支援，可讓出席者加入。

> [!Note]
> 目前在會議中可聊天和通話的人數限制，WW 為 300 人，而 GCC、GCC High 和 DoD 為 250 人。

對於擁有 E3/E5/A3/A5 SKU 的任何召集人，預設會停用僅供檢視體驗。 不需要進一步設定。

## <a name="disable-teams-view-only-experience"></a>停用 Teams 僅供檢視體驗

系統管理員可以使用 PowerShell 停用僅供檢視體驗。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

未來，系統管理員也可以在 Teams 系統管理中心中停用的僅供檢視體驗。

## <a name="impact-to-users"></a>對使用者的影響

使用者的體驗會根據數個因素而不同。

達到主要會議的容量限制後，如果下列任一情況成立，出席者將無法加入會議：

- 系統管理員已停用 Teams 僅供檢視體驗。
- 出席者沒有略過大廳的權限。

達到主要會議的容量限制後，會議召集人和簡報者會看到一個橫幅，通知他們已達到會議容量限制，新的出席者將加入僅供檢視會議。

  ![適用於召集者和簡報者的 Teams 用戶端和橫幅訊息](media/chat-and-banner-message.png)

達到主要會議的容量限制後，系統將在加入前的畫面上通知會議出席者他們正在以僅供檢視模式加入。

  ![Teams 加入前畫面以及顯示給參與者的訊息，告知他們將以僅供檢視模式加入](media/view-only-pre-join-screen.png)

如果有空間，使用者一律可以加入主要會議。 達到主要會議容量限制後，如果一或多位出席者離開主要會議，則主要會議會釋出容量可供加入。 加入 (或重新加入) 會議的出席者將加入主要會議，直到再次達到容量限制。 處於僅供檢視體驗的出席者無法自動升級到主要會議，且目前無法手動將他們升級到主要會議。

如果尚未設定簡報者/出席者角色，主要會議的空間會採用先到先入的原則。 達到會議容量限制後，所有其他使用者將以僅供檢視體驗加入。

## <a name="impact-to-meeting-presenters"></a>對會議簡報者的影響

對會議簡報者的限制包括：

- 您沒有僅供檢視出席者的資訊。 我們不支援僅供檢視出席者使用電子文件探索。
- 使用者看不到僅供檢視出席者。
- 您無法從會議移除僅供檢視出席者。

> [!Note]
> 出席者數只會反映會議中的人員，不會反映僅供檢視會議室中的人員。 因此，簡報者無法取得使用僅供檢視體驗的確切人數。

## <a name="experience-for-view-only-attendees"></a>僅供檢視出席者的體驗

Teams 僅供檢視體驗可讓出席者：

- 聆聽 Teams 主要會議的參與者發言。
- 觀看目前主講人的視訊摘要 (如果目前主講人有分享視訊)。
- 使用共用桌面功能查看共用的內容。

僅供檢視出席者將無法在會議中體驗下列選項：

- 如果根據設定的大廳原則或選項，出席者沒有略過大廳的權限，則無法加入會議。
- 無法使用音訊會議加入僅供檢視會議室。
- 無法使用 Microsoft Teams 會議室系統或雲端視訊 Interop (CVI) 服務加入僅供檢視會議室。
- 無法分享他們的音訊或視訊。
- 無法查看或參與會議聊天。
- 無法觀看會議參與者的視訊摘要，除非參與者是目前的主講人。
- 無法查看使用原生共用 PowerPoint 功能或個別應用程式共用 (桌面共用除外) 共用的 PowerPoint 檔案。

## <a name="view-only-feature-limitations"></a>僅供檢視功能限制

- 無論該會議的即時輔助字幕設定如何，僅供檢視出席者將一律看到即時輔助字幕。 目前僅支援英文字輔助字幕。
- 串流技術將支援僅供檢視出席者。
- 出席報告中不會包含僅供檢視出席者。
- 僅供檢視出席者將擁有單一視訊體驗。 他們可以看到目前主講人或正在共用的內容，但不能同時看到兩者。
- 我們目前不支援僅供檢視出席者使用 **圖庫**、**大型圖庫** 或 **在一起模式** 版面配置。  
- 僅供檢視出席者不會與一般出席者一樣有相同的延遲。 <sup>1</sup>

  <sup>1</sup> 僅供檢視出席者在會議中會有 30 秒的視訊和音訊延遲。  
