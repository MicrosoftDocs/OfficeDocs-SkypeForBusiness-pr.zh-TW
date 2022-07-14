---
title: 即時活動錄製原則
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 瞭解即時活動錄製原則。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ae98255edf26843e59839192a9f20096182bfa2
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794111"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Microsoft Teams 中的即時活動錄製原則

您有幾個選項可以錄製 Microsoft Teams 即時活動。 錄製選項是使用錄製原則來設定。 本文將說明各種設定。

錄製選項是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)來設定。

## <a name="scheduling-and-option-behaviors"></a>排程和選項行為

排程即時活動錄製時，有兩個召集人選項：

- 錄製適用于製作人和簡報者

  - 錄製檔案：提供錄製檔，讓製作人和簡報者可以在活動結束後下載。

- 出席者可錄製內容

  - DVR：DVR (數位錄影機) 可讓出席者在活動期間倒帶和暫停

  - VOD：隨選影片 (VOD) 可讓出席者觀看活動結束之後

## <a name="broadcast-recording-policy-setting"></a>廣播錄製原則設定

在廣播原則中，有一個設定可讓您切換開啟或關閉即時活動的錄製。

| &nbsp;| 錄製適用于製作人和簡報者 | 出席者可錄製內容 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 永遠記錄               | 已停用並選取                                | 已啟用並已選取         |
| 召集人可以錄製或不可以錄製 | 預設已啟用和選取                  | 預設已啟用和選取   |
| 永不記錄               | 已停用且未選取                            | 已停用且未選取      |

## <a name="storage-and-persistence-behavior"></a>儲存空間與持續性行為

| 選項                                       | 狀態   | DVR                                                   | VOD                                                     | 錄製                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 出席者可錄製內容 | 選擇     | DVR 可供使用，且 Azure Media Services (AMS) 資產會儲存 180 天 | 出席者可以存取和觀看活動                     |                              |
|                                                  | 未選取 | DVR 可供使用，且 AMS 資產會儲存 180 天 | 出席者無法在活動結束後存取活動 |                              |
||已停用 (未選取) |DVR 可供使用，且會在事件後刪除 AMS 資產|出席者無法在活動結束後存取活動||
| 錄製可供製作人和簡報者使用 | 選擇     |                                                           |                                                             | 建立 MP4 並儲存 180 天 |
|                                                  | 未選取 |                                                           |                                                             | 未建立任何檔案           |

### <a name="related-topics"></a>相關主題

- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [Teams 即時活動的規劃](plan-for-teams-live-events.md)
- [在 Teams 中設定即時活動設定](configure-teams-live-events.md)
- [Teams 雲端會議錄製](../cloud-recording.md)
