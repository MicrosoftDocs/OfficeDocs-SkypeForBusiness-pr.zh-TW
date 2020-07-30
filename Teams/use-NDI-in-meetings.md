---
title: 在 Microsoft 團隊中使用 NDI
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用 NDI。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522900"
---
# <a name="use-ndi-in-microsoft-teams"></a>在 Microsoft 團隊中使用 NDI

[!INCLUDE [template](includes/preview-feature.md)]

網路裝置介面（NDI）是一種連線媒體裝置（例如畫室式相機和混音器）的新式方案。 NDI 會透過本機內部網路（包括本機電腦）來啟用連線，而不是使用物理連線。

NewTek NDI®已成為一個標準的工業方案，可為數據流製作即時內容，並在專業的廣播世界中取得重要的認識與採納。

Skype 先前已在晚2018中新增 NDI Out 功能至 Skype。 Microsoft 團隊利用此功能來改善會議體驗。

NDI 受限於局域網，且只能看作是生產工作流程的一部分，而不是廣播方案。

## <a name="turn-on-ndi"></a>開啟 NDI

NDI 需要為使用者開啟兩個步驟。

1. 租使用者管理員必須啟用功能標誌 enableStreamingCallsOverNdi。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 在此變更已填入之後，使用者必須從 [**設定**] 許可權開啟其特定用戶端的 NDI  >  ** **。

當使用者加入會議時，他們會看到一則訊息，通知他們正在廣播會議。 如果使用者不想納入廣播，他們將需要從會議中除去。

下圖顯示使用者在團隊會議中看到的橫幅訊息。

![顯示在團隊會議中的 NDI 橫幅影像。](media/NDI-disclosure.png)

橫幅有[Microsoft 隱私權原則](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi)的連結。

## <a name="supported-locales-and-user-types"></a>支援的區域設定和使用者類型

NDI 在所有地區設定中都受支援。 NDI 會議支援下列使用者：

- 租使用者-完全支援，根據響鈴/tenantId/userId （由會議原則 + 功能標誌控制）提供。
- 同盟–否（即使已開啟 NDI）<sup>1</sup>
- Freemium-否（預設值）
- 匿名–否（預設值）
- 來賓–否（預設值）

<sup>1</sup>個裝置預設為開啟的 NDI 設定。 如果會議參與者使用的裝置有 NDI [關閉]，就必須開啟 NDI。
