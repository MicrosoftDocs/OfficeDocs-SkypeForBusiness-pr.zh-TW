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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a82174fd09106f623bcf0f9a03a99c2978253ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615109"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>在 ® 使用 NDI Microsoft Teams

 NewTek NDI® (網路裝置介面) 技術是連接媒體裝置的新解決方案 (例如工作室相機和混合器) 。 NDI 技術不是使用實體®而是可啟用本機內部網路上的連接，包括本機電腦上。

NDI®技術已成為製作資料流程即時內容的標準產業解決方案，並獲得了專業廣播界的重要認知和採用。

Skype 2018 ®新增 NDI Skype功能。 Microsoft Teams使用這項功能來改善會議體驗。

NDI®僅限本地網路，只應視為生產工作流程的一部分，而非廣播解決方案。

## <a name="turn-on-ndi-technology"></a>開啟 NDI®技術

NDI®使用者需要開啟兩個步驟。

1. 租使用者系統管理員必須讓使用者開啟其會議策略的 NDI。 您可以在系統管理入口網站中個別Teams，或透過 CsTeamsMeetingPolicy 中的 _AllowNDIStreaming_ 屬性Teams PowerShell 進行這項操作。

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. 完成此變更之後，使用者必須針對其特定用戶端開啟 NDI®技術，設定  >  **許可權**。

為使用者及其特定用戶端開啟後，使用者可以透過溢出功能表開啟 NDI，然後選取 「透過 NDI 廣播」。

啟動 NDI 並讓端點訂閱 NDI 提要之後，他們會看到一則訊息，通知他們會議正在廣播。 如果使用者不想包含在廣播中，則需要從會議刪除。

下圖顯示使用者在會議或會議Teams訊息。

![he NDI®技術橫幅，顯示在Teams會議。](media/NDI-disclosure.png)

橫幅有 Microsoft [隱私權政策的連結](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®只會啟用每個會話。 在下次的會議上，使用者必須先啟用它，才能使用 NDI®。

## <a name="supported-locales-and-user-types"></a>支援的地區設置和使用者類型

所有®都支援 NDI®技術。

使用 NDI 的存取權是由嘗試啟用此功能的使用者的會議策略所決定。 針對最安全的解決方案，請勿將 NDI 策略開啟為全域設定。
