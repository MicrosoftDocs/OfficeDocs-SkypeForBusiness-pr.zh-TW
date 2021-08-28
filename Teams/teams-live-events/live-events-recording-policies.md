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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 瞭解即時活動錄製政策。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bd9f800ed85d994f797c5e49d64ae0e84f90885c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613452"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>即時活動錄製Microsoft Teams

您有幾個錄製即時活動Microsoft Teams選項。 錄製選項是使用錄製策略來設定。 本文將說明各種設定。

錄製選項是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy 來設定](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)。

## <a name="scheduling-and-option-behaviors"></a>排程和選項行為

排程即時活動錄製時，有兩個召集人選項：

- 錄製者與簡報者可以使用錄製

  - 錄製檔案：提供錄製檔案，製作者和簡報者可在活動結束後下載。

- 出席者可以使用錄製

  - DVR：DVR (DVR) 可讓出席者在活動期間倒帶和暫停

  - VOD：視訊 (VOD) 可讓出席者在活動結束後觀看

## <a name="broadcast-recording-policy-setting"></a>廣播錄製政策設定

在廣播政策中，您可以切換設定來開啟或關閉即時活動的錄製。

| &nbsp;| 錄製者與簡報者可以使用錄製 | 出席者可以使用錄製 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 永遠錄製               | 已停用並選取                                | 已啟用並選取         |
| 召集人可以錄製或無法錄製 | 預設為啟用和選取                  | 預設為啟用和選取   |
| 永不錄製               | 已停用且未選取                            | 已停用且未選取      |

## <a name="storage-and-persistence-behavior"></a>儲存體和持續性行為

| 選項                                       | 狀態   | DVR                                                   | VOD                                                     | 錄製                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 出席者可以使用錄製 | 選擇     | DVR 可供使用，AZURE 媒體服務 (AMS) 資產儲存 180 天 | 出席者可以存取並觀看活動                     |                              |
|                                                  | 未選取 | DVR 可供使用，且 AMS 資產儲存 180 天 | 活動結束後，出席者無法存取活動 |                              |
||已停用 (未選取) |DVR 可供使用，事件之後會刪除 AMS 資產|活動結束後，出席者無法存取活動||
| 錄製者與簡報者可以使用錄製 | 選擇     |                                                           |                                                             | 已建立並儲存 MP4 |
|                                                  | 未選取 |                                                           |                                                             | 未建立檔案           |

### <a name="related-topics"></a>相關主題

- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [Teams 即時活動的方案](plan-for-teams-live-events.md)
- [在 Teams 中設定即時活動設定](configure-teams-live-events.md)
- [Teams雲會議錄製](../cloud-recording.md)
