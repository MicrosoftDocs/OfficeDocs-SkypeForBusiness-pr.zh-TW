---
title: 即時活動錄製政策
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 瞭解即時活動錄製政策。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615167"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Microsoft Teams 中的即時活動錄製政策

您有幾個選項可以錄製 Microsoft Teams 即時活動。 錄製選項是使用錄製策略設定。 本文將說明各種設定。

錄製選項是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy 設定](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)

## <a name="scheduling-and-option-behaviors"></a>排程和選項行為

排程即時活動錄製時，有兩個召集人選項：

- 錄製可供製作人與簡報者使用

  - 錄製檔案：提供錄製檔案，製作人與簡報者可以在活動結束後下載。

- 可供出席者錄製

  - DVR：數位視訊錄製 (DVR) 可讓出席者在活動期間倒帶和暫停

  - VOD：視訊 (VOD) 可讓出席者在活動結束後觀看

## <a name="broadcast-recording-policy-setting"></a>廣播錄製政策設定

在廣播政策中，有一個設定可以切換為開啟或關閉即時活動的錄製。

|                                 | 可供製作人與簡報者的錄製 | 錄製內容可供出席者使用 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 永遠記錄               | 已停用並選取                                | 已停用並選取         |
| 召集人可以錄製或無法錄製 | 預設為啟用且未選取                  | 預設為啟用且未選取   |
| 永不錄製               | 已停用且未選取                            | 已停用且未選取      |

當系統設定為永遠記錄 **時**，該政策頁面會選取下列選項：

![即時事件政策設定](../media/live-event-recording-policy.png "Microsoft Teams 系統管理中心即時活動原則設定的螢幕擷取畫面")

## <a name="storage-and-persistence-behavior"></a>儲存空間和持續性行為

| 選項                                       | 狀態   | Dvr                                                   | Vod                                                     | 錄製                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 製作人與簡報者可以使用錄製內容 | 選擇     | DVR 可供使用，而 AMS (Azure Media Services) 會儲存 180 天 | 出席者可以存取並觀看活動                     |                              |
|                                                  | 未選取 | DVR 可供使用，且 AMS 資產會儲存 180 天 | 活動結束後，出席者無法存取活動 |                              |
||已停用 (未選取) |DVR 可供使用，事件之後會刪除 AMS 資產|活動結束後，出席者無法存取活動||
| 製作人與簡報者可以使用錄製內容 | 選擇     |                                                           |                                                             | 建立並儲存 MP4 |
|                                                  | 未選取 |                                                           |                                                             | 未建立任何檔案           |

### <a name="related-topics"></a>相關主題

- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [Teams 即時活動的方案](plan-for-teams-live-events.md)
- [在 Teams 中設定即時活動設定](configure-teams-live-events.md)
- [Teams 雲朵會議錄製](../cloud-recording.md)
