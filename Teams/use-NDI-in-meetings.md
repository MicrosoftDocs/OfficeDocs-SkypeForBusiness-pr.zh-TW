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
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337012"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>在 Microsoft 團隊中使用 NDI®技術

 NewTek NDI® (網路裝置介面) 技術是一種連線媒體裝置的新式方案， (例如畫室式相機和混音器) 。 NDI®技術不是使用物理連線，而是透過本機內部網路（包括本機電腦）來實現連線。

NDI®技術已成為一個標準的工業方案，可為數據流製作即時內容，並在專業的廣播世界中取得重要的認識與採納。

Skype 先前已在2018中新增 NDI® out 功能至 Skype。 Microsoft 團隊使用這個功能來改善會議體驗。

NDI®技術受限於局域網，且只能看作是生產工作流程的一部分，而不是廣播方案。

## <a name="turn-on-ndi-technology"></a>開啟 NDI®技術

NDI®技術需要為使用者開啟兩個步驟。

1. 租使用者管理員必須在 CsTeamsMeetingPolicy 中啟用 ' AllowNDIStreaming」屬性。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 此變更已填入之後，使用者必須從 [**設定**] 許可權開啟其特定用戶端的 NDI®技術  >  ** **。

當使用者加入會議時，他們會看到一則訊息，通知他們正在廣播會議。 如果使用者不想納入廣播，他們將需要從會議中除去。

下圖顯示使用者在團隊會議中看到的橫幅訊息。

![他 NDI 在團隊會議中顯示的®技術橫幅。](media/NDI-disclosure.png)

橫幅有 [Microsoft 隱私權原則](https://aka.ms/teamsprivacy)的連結。

## <a name="supported-locales-and-user-types"></a>支援的區域設定和使用者類型

NDI®技術在所有地區設定中都受到支援。 下列使用者包含在 NDI®技術資料流程中，但不是所有使用者都可以存取 NDI®技術資料流程：

- 受租使用者-完整支援，根據會議原則所控制的響鈴/tenantId/userId (傳送) 
- 同盟-即使在) <sup>1</sup>上有 NDI®技術，也沒有資料流程存取 (
- Premium-無資料流程存取
- 匿名–無資料流程存取
- 來賓–無資料流程存取  

<sup>1</sup> 台裝置的 NDI®技術設定預設為開啟。 如果會議參與者使用的裝置的 NDI®技術關閉，他們必須開啟 NDI®技術。
