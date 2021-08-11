---
title: 在 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eebbea6ce5d632d38e94465f05fd9f60a3300a4e060106e7ba2f6218433c5e8b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335813"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>在 ® 使用 NDI Microsoft Teams

 NewTek NDI® (網路裝置介面) 技術是連接媒體裝置的新解決方案， (例如工作室相機和混頻) 。 NDI 技術可®內部網路 ，包括本機電腦上，而非使用實體連接。

NDI®技術已成為為數據流製作即時內容的標準產業解決方案，並獲得了專業廣播業界的顯著認知和採用。

Skype 2018 ®新增 NDI Skype功能。 Microsoft Teams使用這項功能來改善會議體驗。

NDI®僅限本地網路，只應視為生產工作流程的一部分，而非廣播解決方案。

## <a name="turn-on-ndi-technology"></a>開啟 NDI®技術

NDI®使用者需要開啟兩個步驟。

1. 租使用者系統管理員必須在 CsTeamsMeetingPolicy 中啟用 'AllowNDIStreaming' 屬性。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 完成此變更之後，使用者必須開啟其特定用戶端的 NDI®技術，設定  >  **許可權**。

當使用者加入會議時，會看到一則訊息，通知他們會議正在廣播中。 如果使用者不想包含在廣播中，則需要從會議刪除。

下圖顯示使用者在會議或會議Teams訊息。

![he NDI®顯示于會議Teams技術橫幅。](media/NDI-disclosure.png)

橫幅有 Microsoft [隱私權政策的連結](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®只會啟用每個會話。 下次登入時，使用者必須先啟用它，才能使用 NDI®。

## <a name="supported-locales-and-user-types"></a>支援的地區設置和使用者類型

NDI®支援所有地區。 下列使用者包含在 NDI®技術流中，但並非所有使用者都可以存取 NDI®技術流：

- 租使用者內 – 完全支援，根據 Ring/tenantId/userId (由會議策略) 
- 聯合 – 即使<sup>1</sup> (有 NDI®，也) 存取
- 進階版 - 沒有串流存取
- 匿名 – 沒有串流存取
- 來賓 – 沒有串流存取  

<sup>1</sup> 裝置預設為® NDI®技術設定。 如果會議參與者使用具有 NDI®關閉的裝置，他們必須開啟 NDI® 技術。
