---
title: '[通話品質儀表板] (CQD) 中的 Stream 分類'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 瞭解如何在 Microsoft Teams 和 商務用 Skype Online 的通話品質儀表板 (CQD) 中分類串流品質。
ms.openlocfilehash: 9b17cf115759e96edbccdb85369ac42fd5861ff7
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794291"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>呼叫品質儀表板中的串流分類 (CQD) 

Microsoft Teams 和 商務用 Skype Online 的通話品質儀表板 (CQD) 可讓您深入瞭解使用 Microsoft Teams 和商務用 Skype服務進行通話的品質。 本主題提供媒體串流品質分類的詳細資訊。 若要深入瞭解 CQD 及其設定方式，請參閱 [設定通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)。

## <a name="classifier-definitions"></a>分類器定義

CQD 中的串流會根據可用關鍵品質計量的值分類為 _[良好_]、[ _不佳_] 或 [ _未分類_ ]。 用來分類串流的計量及條件會顯示在後續的資料表中。 CQD 的「不佳原因」維度可用來瞭解哪些計量負責 _不佳_ 的分類。 如需這些維度的詳細資訊，請參閱 [通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。

### <a name="audio-classifier"></a>音訊分類器

如果符合下列一或多個條件，且封包使用> 500 封包，音訊串流會標示為 _不佳_：

|度量|案例|條件|解釋|
|:-----|:-----|:-----|:-----|
|往返|所有|> 500|平均來回網路傳播時間，計算為毫秒。 [RFC3550](https://tools.ietf.org/html/rfc3550)中提供的詳細資料。|
|封包遺失率|所有|> 0.1|串流的平均封包遺失率。|
|抖動|所有|> 30|以毫秒為毫秒的串流平均抖動。|
||||

### <a name="video-classifier-due-to-freeze"></a>凍結造成的視訊分類器

視訊串流會根據產生的分類分數值來標示為 [  _良好_ ] 或 [ _不佳_ ]，以估算使用者是否遭遇凍結視訊。 此分類器僅適用于 Microsoft Teams 產品。

|步#|度量|案例|條件 |如果條件為 True，則分類 |如果條件為 False，則分類 |如果公制無法使用，則分類 |解釋 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|凍結分類器導致視訊不佳 |Is Server Pair is Client ： Server|>0.246|_可憐_|_好_|_未分類_|根據使用者體驗、凍結持續時間統計資料和整體通話體驗的組合，產生介於 0 到 1 之間的分數 |
|2|凍結分類器導致視訊不佳 |Is Server Pair is Client ： Client|>0.524|_可憐_|_好_|_未分類_|根據使用者體驗、凍結持續時間統計資料和整體通話體驗的組合，產生介於 0 到 1 之間的分數 |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>視訊分類器
視訊串流會根據下列順序的第一個可用計量值標示為 [ _良好_ ] 或 [ _不佳_ ]：

|步#|度量|條件 |如果條件為 True，則分類 |如果條件為 False，則分類 |如果公制無法使用，則分類 |解釋 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|影片本機框架遺失百分比 Avg|> 50% |_可憐_|_好_|繼續進行步驟 2|向使用者顯示的視訊框架遺失的平均百分比。 平均值包括從網路損失中復原的框架。|
|2|視訊框架速率 Avg|< 7|_可憐_|_好_|繼續進行步驟 3|視訊串流每秒收到的平均框架，計算會話的持續時間。|
|3|影片張貼 FECPLR|> 0.15|_可憐_|_好_|_未分類_|在所有視訊串流和編解碼器上套用匯總 FEC 之後的封包遺失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分類器

VBSS 串流會根據下列順序的第一個可用計量值標示為 [ _良好_ ] 或 [ _不佳_ ]：

|步# |度量 |條件 |如果條件為 True，則分類 |如果條件為 False，則分類 |如果公制無法使用，則分類 |解釋 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|影片本機框架遺失百分比 Avg|編解碼器為 NOT H264S</br>和</br>StreamDirection 已輸入</br></br>如果 FrameLoss > 50%|_可憐_|_好_|_未分類_|向使用者顯示的視訊框架遺失的平均百分比。 平均值包括從網路損失中復原的框架。 FrameLoss 僅用於分類輸入非 H264S 串流。|
|2|視訊框架速率 Avg|< 1|_可憐_|_好_|_未分類_|視訊串流每秒收到的平均框架，計算會話的持續時間。 適用于所有輸出串流和 H264S 的 StreamDirection。|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>應用程式共用分類器

如果符合下列一或多個條件，應用程式共用串流會標示為 _不佳_ ：

| 度量     | 條件 | 解釋 |
|:---        |:---       | :--- |
| 被破壞的磚總和百分比 | > 36 | 捨棄而非傳送到遠端對等 (的磚百分比，例如從 MCU 傳送到檢視器) 。 捨棄 (或破壞) 磚可能是用戶端和伺服器之間的頻寬限制所導致。 |
| AppSharing RDP 磚處理延遲平均值 | > 400 | 會議服務器 RDP 堆疊上的平均延遲以毫秒為處理磚。 |
| AppSharing 相對 OneWay 平均值 | > 1.75 | 應用程式共用串流的端點間相對單向延遲平均為秒數。 |
| | | |

## <a name="unclassified-streams"></a>未分類的串流

在 CQD 中，當互動式連線 (ICE) 連線失敗或未報告計算串流分類所需的所有計量時，串流會標示為未 _分類_ 。

若要檢查 ICE 連線失敗，請檢查「First Connectivity Ice」 和 「Second Connectivity Ice」 的尺寸是否為「失敗」值。 如果有任一值表示失敗，則串流會標示為 _[未分類]_。

如果 ICE 連線成功處理 _未分類_ 的串流，則該串流可能會被視為 _未分類，_ 因為未報告重要串流計量。 報告這些計量有幾個原因：

- **未收到 QoE 報告** ：用於分類的計量會在通話結束時傳送的 QoE 報告中報告。 例如，如果未產生此報告 (，因為某些協力廠商端點可能無法傳送 QoE) 或無法傳送 (例如，因為網路中斷) ，CQD 無法將串流分類。

  > [!TIP]
  > 您可以使用「QoE 記錄可用」維度來判斷是否收到串流的 QoE 報告。 請注意，如果從任一端點收到 QoE 報表，此維度的值會是 「True」。 兩個端點的 QoE 報表是衡量標準最準確報告的必要專案。

- **簡短通話** - 簡短通話可能沒有足夠的媒體活動來計算關鍵串流計量。 如果沒有這些計量，CQD 就無法將串流分類。

  > [!TIP]
  > 您可以使用「持續時間 (秒) 」、「工期 (分鐘) 」、「工期 5 秒或更短」和「持續時間 60 秒以上」等維度來判斷串流的持續時間。 度量「Avg 通話持續時間」也可以用來計算一組串流的平均持續時間。

- **封包使用率低** — 就像「簡短通話」案例一樣，計算關鍵串流計量需要足夠的封包使用量。 如果沒有這些計量，CQD 就無法將串流分類。
  - 當出席者加入會議聆聽簡報者，但 (大多數通話) 都將麥克風設為靜音時，就會發生常見的低封包使用情形。 在這裡，輸入到用戶端的音訊串流具有高封包使用率，而從用戶端輸出的音訊串流則幾乎無封包使用率。 串流的持續時間可能為一小時或更久，但從用戶端到伺服器的串流封包使用率很低，因為麥克風設為靜音，且 _未分類_ 的串流結果。

  > [!TIP]
  > 您可以使用「封包使用量」維度和「Avg 封包使用量」來判斷串流的封包活動。

## <a name="related-topics"></a>相關主題
[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定呼叫品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)
