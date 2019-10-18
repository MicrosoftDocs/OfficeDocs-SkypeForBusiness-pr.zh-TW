---
title: 通話品質儀表板中的資料流程分類
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 瞭解如何在 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板中分類資料流程品質。
ms.openlocfilehash: a64a3169087c6a485cd129e2e2214e773ef0c33c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569992"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>通話品質儀表板中的資料流程分類

Microsoft 團隊和商務用 Skype Online 的通話品質儀表板（CQD）可讓您深入瞭解使用 Microsoft 團隊和商務用 Skype 服務所進行的通話品質。 本主題提供媒體資料流程品質分類的詳細資訊。 若要深入瞭解 CQD 及如何啟用它，請參閱[開啟和使用通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)。

## <a name="classifier-definitions"></a>分類器定義

CQD 中的資料流程會根據可用的主要品質度量單位的值，分類為_良好_、_較差_或未_分類_。 在後續的資料表中，會顯示用於分類資料流程的度量值與條件。 CQD 的 "到期之處" 維度可供您瞭解哪個指標負責分類不_佳_。 如需這些尺寸的詳細資訊，請參閱[通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。

### <a name="audio-classifier"></a>音訊分類器

如果符合下列一或多個條件，音訊資料流程會標示為_差_：

|衡量|條件|簡要|
|:-----|:-----|:-----|
|音訊品質平均|> 1。0|資料流程的平均網路平均觀點。 網路遺失和抖動的多少會影響收到的音訊品質。|
|往返行程|> 500|平均往返行程網路傳播時間，以毫秒計算。 [RFC3550](https://tools.ietf.org/html/rfc3550)中提供的詳細資料。|
|資料包遺失率|> 0。1|資料流程的平均資料包遺失率。|
|抖動|> 30|資料流程的平均抖動（以毫秒為單位）。|
|隱藏平均樣本的比率|> 0.07|音訊幀數的平均比率，由資料包遺失修複產生的隱藏範例，到音訊畫面總數目。|
||||

### <a name="video-classifier"></a>視頻分類器

根據以下順序，在第一個可用指標的值上，將影片資料流程標示為_良好_或_差_：

|循序漸進#|衡量|條件 |分類 if 條件為 True |分類 if 條件為 False |無法使用分類 if 指標 |簡要 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|sr-1|影片局部畫面損失平均百分比|> 50% |_表現_|_良好_|繼續進行步驟2|顯示給使用者的影片畫面平均百分比。 Average 包括從網路損失中復原的框架。|
|pplx-2|影片畫面播放速率 Avg|< 7|_表現_|_良好_|繼續進行步驟3|每秒針對影片資料流程所收到的平均幀數（在會話期間計算）。|
|3|影片文章 FECPLR|> 0.15|_表現_|_良好_|_未_|在所有的視頻資料流程和編解碼器中，將 FEC 套用到已匯總的資料包遺失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分類器

根據以下順序，根據第一個可用指標的值，將 VBSS 串流標示為_良好_或_差_：

|循序漸進# |衡量 |條件 |分類 if 條件為 True |分類 if 條件為 False |無法使用分類 if 指標 |簡要 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sr-1|影片局部畫面損失平均百分比|> 50% |_表現_|_良好_|繼續進行步驟2|顯示給使用者的影片畫面平均百分比。 Average 包括從網路損失中復原的框架。|
|pplx-2|影片畫面播放速率 Avg|< 2|_表現_|_良好_|繼續進行步驟3|每秒針對影片資料流程所收到的平均幀數（在會話期間計算）。|
|3|影片文章 FECPLR|> 0.15|_表現_|_良好_|_未_|在所有的視頻資料流程和編解碼器中，將 FEC 套用到已匯總的資料包遺失率。|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>應用程式共用分類器

如果符合下列一或多個條件，應用程式共用資料流程會標示為不_佳_：

| 衡量     | 條件 | 簡要 |
|:---        |:---       | :--- |
| Spoiled 磚百分比總計 | > 36 | 已放棄而不是傳送到遠端對等（例如，從 MCU 移至檢視器）的磚百分比。 捨棄（或 spoiled）磚可能是由用戶端與伺服器之間的頻寬限制所造成。 |
| AppSharing RDP 磚處理延遲平均值 | > 400 | 在會議服務器上的 RDP 堆疊中處理磚的平均延遲（以毫秒為單位）。 |
| AppSharing 相對單向平均值 | > 1.75 | 應用程式共用資料流程在端點之間的平均相對單向延遲（以秒為單位）。 |
| | | |

## <a name="unclassified-streams"></a>未分類資料流程

在 CQD 中，如果互動式連線建立（ICE）連線失敗，或未報告計算資料流程分類所需的所有衡量標準，資料流程會標示為未_分類_。

若要檢查 ICE 連線失敗，請檢查「第一個連通性 Ice」和「第二個連通性 Ice」的維度，看看「失敗」的值。 如果其中一個值代表失敗，該資料流程會標示為未_分類_。

如果未_分類_資料流程的 ICE 連線成功，則該資料流程可能會被視為未_分類_，因為未報告主要資料流程度量單位。 下列幾個原因可能不會報告這些指標：

- **未收到 QoE 報告**：用於分類的度量單位會在通話結束時傳送的 QoE 報告中報告。 如果未產生此報告（例如，由於某些協力廠商端點可能無法傳送 QoE）或無法傳送（例如，由於網路中斷），CQD 無法將資料流程分類。

> [!TIP]
> 您可以使用「QoE 記錄可用」維度來判斷是否已收到資料流程的 QoE 報告。 請注意，如果 QoE 報告是從任一端點接收，此維度的值會是 "True"。 您必須使用兩個端點的 QoE 報告，才能精確報告指標。

- **短通話**：短時間的通話可能沒有足夠的媒體活動來計算金鑰資料流程度量單位。 若沒有這些指標，CQD 就無法將資料流程分類。

> [!TIP]
> [持續時間（秒）]、"Duration （分鐘）"、"持續時間5秒或更短" 以及 [持續時間60秒或更多] 可用於決定資料流程的持續時間。 [平均通話持續時間] 度量單位也可以用來計算一組資料流程的平均持續時間。

- **低資料包利用率**（例如「短通話」案例）需要足夠的資料包利用率，才能計算重要資料流程度量單位。 若沒有這些指標，CQD 就無法將資料流程分類。
  - 常見的低資料包利用率案例會在出席者加入會議來收聽簡報者，但不會在說話時（麥克風在大部分通話中為靜音）。 在這裡，入站至用戶端的音訊資料流程具有高資料包利用率，而從用戶端輸出的音訊資料流程幾乎沒有資料包利用率。 資料流程的持續時間可能是一個小時或更長，但從用戶端到伺服器的資料流程中的資料包利用率較低，因為麥克風已靜音，且未_分類_的資料流程結果。

> [!TIP]
> [資料包利用率] 維度和 "Avg Packet 利用率" 測量值可用來判斷資料流程的資料包活動。

## <a name="related-topics"></a>相關主題

[開啟並使用通話品質儀表板（CQD）](turning-on-and-using-call-quality-dashboard.md)

[通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用呼叫分析來排查不佳的通話品質問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)
