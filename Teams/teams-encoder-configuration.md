---
title: Microsoft Teams 中串流處理的編碼器設定
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文將討論 Microsoft Teams 串流事件的編碼器型 RTMP 設定。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767926"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>在 Microsoft Teams 中設定即時活動串流的編碼器

Teams 會從輸出 RTMP 或 RTMPS 的各種不同編碼器接受即時摘要。 每個編碼器都不同，因此傳送至 Teams 時，請務必遵循編碼器設定的指導方針。

若要瞭解如何在 Teams 中設定即時活動，請參閱建立即時活動。 如果您已經使用已與 Teams 整合的編碼器，請閱讀有關設定 [即時串流編碼器](teams-encoder-setup.md)的資訊。

## <a name="configuration-steps"></a>設定步驟

在您使用 Teams 或 Yammer 排程即時活動並選取 **Teams Encoder** 選項之後，您就可以從會議邀請中擷取 RTMP URL 和金鑰，並使用它們將摘要傳送到 Teams 製作人 UI。

### <a name="gather-the-rtmp-information"></a>收集 RTMP 資訊

#### <a name="scheduled-in-teams"></a>在 Teams 中排程

1. 開啟 Teams 用戶端並流覽至行事 **曆**。
1. 選取已排程的即時活動，然後選取雙箭頭按鈕以查看邀請詳細資料。
1. 移至 **[詳細資料] 區段中的 RTMP** 。
1. 選 **取 [取得 RTMP** ] 連結，將 RTMP 內充 URL 複製到剪貼簿。
1. 選 **取 [取得 RTMP 鍵** ] 以將 RTMP 鍵複製到剪貼簿。

#### <a name="scheduled-in-yammer"></a>已在 Yammer 中排程

1. 流覽至已排程活動的 Yammer 社群。
1. 選取 [ **事件] 索** 引標籤以查看即將到來的排程活動。
1. 選取您要的事件以顯示詳細資料頁面。
1. 在右側的 [ **生產**] 底下，選取 **RTMP 資訊** 連結以公開 RTMP URL 和按鍵。

## <a name="encoder-setup"></a>編碼器設定

1. 收集 RTMP 資訊後，請確定您的編碼器已按照下方建議的編碼器設定正確設定。
1. 在編碼器的串流設定中輸入 RTMP URL 和 Key， (參閱製造商的特定) 檔。
1. 使用所需的音訊和視訊來源設定您的編碼器。
1. 開啟 Teams 用戶端，並以製作人身分加入現場通風孔。
1. 開始從編碼器串流到 Teams RTMP 內裝 URL。
1. 在 [Teams 製作人] 視窗中，幾秒鐘後，編碼器的 RTMP 摘要會顯示在簡報者區域中。
1. 按一下簡報者區域中的 RTMP 摘要，將其置於左側的佇列中。
1. 一旦您對摘要感到滿意，請選 **取 [傳送 Live** ] - 摘要也會出現在 [製作人] 視窗的右側。
1. 選 **取 [開始** ] 以開始串流。

## <a name="recommended-encoder-settings"></a>建議的編碼器設定

### <a name="ingest-protocols"></a>內塞通訊協定

- 單位 RTMPS 或 RTMP

### <a name="video-format"></a>視訊格式

- 編解碼器：H.264
- 設定檔：高 (層級 4.0) 
- 位元速率：最高 5 Mbps (5000 kbps) 
- 嚴格常數位元速率 (CBR) 
- Keyframe/識別碼：2 秒
  - 每一個單一的單一目錄開頭都必須有一個 IDR 框架
  - 框架速率：29.97 fps 或 30 fps
  - 解析度：1280 x 720 (720P) 
  - 交錯模式：漸進式

### <a name="audio-format"></a>音訊格式

- 編解碼器：AAC (LC) 
- 位元速率：192 kbps
- 範例速率：48 kHz 或 44.1 kHz (建議 48 kHz) 

### <a name="playback-requirements"></a>播放需求

- 音訊和視訊串流都必須存在，才能在 Teams 中播放內容。

### <a name="configuration-tips"></a>設定秘訣

- 盡可能使用硬線網際網路連線。
- 判斷頻寬需求時，必須將串流位元速率設為兩倍。 雖然這不是強制性需求，但可協助降低網路圊塞的影響。
- 使用軟體型編碼器時，請關閉任何不必要的程式。
- 開始推擠之後，請勿變更您的編碼器設定。 它對事件有負面影響，並可能導致事件不穩定。 如果您想要在活動開始之前執行此動作，您必須在 Teams 中中斷使用製作人控制項的連線，然後再次開始設定。
- 如果編碼器在即時活動期間中斷連線，請重新連線，保持持續處理常式的相同時間戳記。 任何不連續性都可能會在某些瀏覽器和裝置上造成音訊或視訊問題。
- 提供您足夠的時間來設定您的活動。 針對高規模活動，建議您在活動開始前一小時開始設定。
