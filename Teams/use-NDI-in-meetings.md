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
ms.openlocfilehash: 2a9eed33ba105584379f207697c27e8d6bd6cde5
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359180"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>在 ®使用 NDI Microsoft Teams

 NewTek NDI® (網路裝置介面) 技術是連接媒體裝置的新解決方案， (例如工作室相機和混頻) 。 NDI 技術可®內部網路 ，包括本機電腦上，而非使用實體連接。

NDI®技術已成為為數據流製作即時內容的標準產業解決方案，並獲得了專業廣播界的重要認知和採用。

Skype 2018 ®新增 NDI Skype功能。 Microsoft Teams此功能來改善會議體驗。

NDI®僅限本地網路，只應視為生產工作流程的一部分，而非廣播解決方案。

## <a name="turn-on-ndi-technology"></a>開啟 NDI®技術

NDI®使用者需要開啟兩個步驟。

1. 租使用者系統管理員必須讓使用者開啟其會議策略的 NDI。 您可以在系統管理入口網站中個別Teams，或透過 csTeamsMeetingPolicy 中的 _AllowNDIStreaming_ 屬性Teams PowerShell 進行這項操作。

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. 完成此變更之後，使用者必須開啟 NDI®特定用戶端的技術，設定  >  **許可權**。

為使用者及其特定用戶端開啟後，使用者可以透過溢出功能表開啟 NDI，然後選取 「透過 NDI 廣播」。

啟動 NDI 並讓端點訂閱 NDI 提要之後，他們會看到一則訊息，通知他們會議正在廣播。 如果使用者不想包含在廣播中，則需要從會議刪除。

下圖顯示使用者在會議或會議Teams訊息。

![he NDI®顯示于會議Teams技術橫幅。](media/NDI-disclosure.png)

橫幅有 Microsoft [隱私權政策的連結](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®只會啟用每個會話。 在下次的會議上，使用者必須先啟用它，才能使用 NDI®。

## <a name="supported-locales-and-user-types"></a>支援的地區設置和使用者類型

NDI®支援所有地區。

使用 NDI 的存取權是由嘗試啟用此功能的使用者的會議策略所決定。 針對最安全的解決方案，請勿將 NDI 策略開啟為全域設定。
