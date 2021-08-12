---
title: '通話品質儀表板和 CQD (串流分類) '
ms.author: serdars
author: lolaj
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 瞭解如何將串流品質分類在 (電話品質儀表板) Microsoft Teams 商務用 Skype中。
ms.openlocfilehash: 595ed77fd0fa6c2fb3a9bf778ff8b94e837314da1c83acb5a099bb0c795eabe1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341149"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>通話品質儀表板和 CQD (串流分類) 

 (和 商務用 Skype Online 的通話品質儀表板) CQD Microsoft Teams 可讓您深入瞭解使用 Microsoft Teams 和 商務用 Skype 服務撥打商務用 Skype品質。 本主題提供有關媒體流品質分類的詳細資訊。 若要深入瞭解 CQD 以及如何設定，請參閱設定 [通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)。

## <a name="classifier-definitions"></a>分類器定義

CQD 中的資料流程會根據可用的關鍵品質度量值分類為良好、不佳或未分類。  用來將資料流程分類的度量和條件會顯示在後續資料表中。 CQD 的 「差因」維度可用來瞭解哪一個公制是導致 「差」 _分類_ 的原因。 有關這些維度的資訊，請參閱通話品質儀表板中可用的 [維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。

### <a name="audio-classifier"></a>音訊分類器

如果符合下列一或多個條件，音訊串流會標示為 _不佳_：

|度量|案例|條件|解釋|
|:-----|:-----|:-----|:-----|
|音訊降級平均值|有效負載描述不是 SATIN|> 1.0|串流的平均網路平均意見分數降低。 網路遺失和抖動影響接收音訊品質的多少。|
|往返|所有|> 500|以毫秒為單位計算的往返網路傳播時間平均值。 詳細資料可在 [RFC3550 中提供](https://tools.ietf.org/html/rfc3550)。|
|封包遺失率|所有|> 0.1|串流的平均封包遺失率。|
|抖動|所有|> 30|串流的平均抖動以毫秒為單位。|
|隱藏樣本平均值的比例|有效負載描述不是 SATIN|> 0.07|封包遺失修複產生的隱藏樣本的音訊框架數量與音訊框架總數之間的平均比率。|
||||

### <a name="video-classifier-due-to-freeze"></a>由於凍結而使用視像分類器

視音訊串流會 _根據_ 產生的分類器分數值標示為 [良好或不佳」，以估算使用者體驗的凍結視音訊。 此分類器僅適用于Microsoft Teams產品。

|步#|度量|案例|條件 |如果條件為 True，分類 |條件為 False 的分類 |如果公制無法使用，分類 |解釋 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|凍結分類器導致視視不佳 |Is Server Pair is Client ： Server|>0.246|_可憐_|_好_|_未分類_|根據使用者體驗、凍結持續時間統計資料和整體通話體驗的組合，產生介於 0 到 1 之間的分數 |
|2|凍結分類器導致視視不佳 |Is Server Pair is Client ： Client|>0.524|_可憐_|_好_|_未分類_|根據使用者體驗、凍結持續時間統計資料和整體通話體驗的組合，產生介於 0 到 1 之間的分數 |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>影片分類器
視訊串流會根據下列順序的第一個可用度量值標示為良好或不佳：

|步#|度量|條件 |如果條件為 True，分類 |條件為 False 的分類 |如果公制無法使用，分類 |解釋 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|影片本地框架遺失百分比平均值|> 50% |_可憐_|_好_|繼續步驟 2|顯示給使用者之影片畫面遺失的平均百分比。 平均值包括從網路損失中復原的畫面。|
|2|視音訊畫面播放速率平均值|< 7|_可憐_|_好_|繼續步驟 3|視音訊串流每秒收到的平均幀數，這是在會話期間所計算。|
|3|影片 張貼 FECPLR|> 0.15|_可憐_|_好_|_未分類_|在所有視音訊流和編解碼器上加總 FEC 之後，封包遺失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分類器

VBSS 串流會根據下列順序的第一個可用度量值，標示為良好或不佳：

|步# |度量 |條件 |如果條件為 True，分類 |條件為 False 的分類 |如果公制無法使用，分類 |解釋 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|影片本地框架遺失百分比平均值|> 50% |_可憐_|_好_|繼續步驟 2|顯示給使用者之影片畫面遺失的平均百分比。 平均值包括從網路損失中復原的畫面。|
|2|視音訊畫面播放速率平均值|< 2|_可憐_|_好_|繼續步驟 3|視音訊串流每秒收到的平均幀數，這是在會話期間所計算。|
|3|影片 張貼 FECPLR|> 0.15|_可憐_|_好_|_未分類_|在所有視音訊流和編解碼器上加總 FEC 之後，封包遺失率。|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>應用程式共用分類器

如果符合下列一或多個條件，應用程式共用流會標示為差：

| 度量     | 條件 | 解釋 |
|:---        |:---       | :--- |
| 已破壞的磚百分比總計 | > 36 | 捨棄而不是送到遠端對等 (的磚百分比，例如，從微控制器到檢視器) 。 捨棄 (或) 磚可能是由用戶端與伺服器之間的頻寬限制所導致。 |
| AppSharing RDP 磚處理延遲平均值 | > 400 | 會議服務器上 RDP Stack 上處理磚的平均延遲時間 ，以毫秒為單位。 |
| AppSharing 相對 OneWay Average | > 1.75 | 應用程式共用流的端點之間平均單向延遲 ，以秒計算。 |
| | | |

## <a name="unclassified-streams"></a>未分類的資料流程

在 CQD 中，當互動式連接建立 (ICE) 連接失敗，或計算串流分類所需的所有度量未報告時，資料流程會標示為未分類。

若要檢查 ICE 連接失敗，請檢查 "First Connectivity Ice" 和 "Second Connectivity Ice" 維度的 "FAILED" 值。 如果任一值表示失敗，則串流會標示為 _未分類_。

如果未分類資料流程的 ICE連接成功，則資料流程可能被視為未分類，因為未報告金鑰串流度量。 有一些原因可能無法報告這些度量：

- **未收到 QoE** 報告 —用於分類的度量單位會以通話結束時的 QoE 報告報告。 例如 (因為某些協力廠商端點可能無法傳送 QoE) 或無法傳送 (例如，因為網路中斷) ，CQD 就無法將資料流程分類。

  > [!TIP]
  > 「QoE 記錄可用」維度可用來判斷是否收到資料流程的 QoE 報告。 請注意，如果從任一端點收到 QoE 報表，此維度的值會為 「True」。 需要兩個端點的 QoE 報告，才能最精確地報告度量。

- **簡短通話** - 短時間通話可能沒有足夠的媒體活動，無法計算金鑰串流度量。 如果沒有這些度量，CQD 就無法將資料流程分類。

  > [!TIP]
  > 維度「持續時間 (秒) 」、「持續時間 (分鐘) 」、「持續時間 5 秒或更短」，以及「持續時間 60 秒以上」等維度可用來判斷資料流程的持續時間。 測量「Avg 通話持續時間」也可以用來計算一組資料流程的平均持續時間。

- **低封包使用量** - 就像「簡短通話」案例一樣，計算金鑰串流度量時，需要足夠的封包使用量。 如果沒有這些度量，CQD 就無法將資料流程分類。
  - 當出席者加入會議以聆聽簡報者的聲音，但從未說話時 (在大多數通話中，麥克風會靜音) 。 在此，輸入至用戶端的音訊流具有較高的封包使用率，而從用戶端輸出的音訊流則很少或沒有封包使用量。 串流持續時間可能是一小時或更長時間，但從用戶端到伺服器的串流封包使用量較低，因為麥克風已靜音，且結果為未 _分類的串_ 流。

  > [!TIP]
  > 「封包使用量」維度和「Avg 封包使用量」量值可用來判斷資料流程的封包活動。

## <a name="related-topics"></a>相關主題
[改善及監控通話品質Teams](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[Upload租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用 Power BI分析 CQD 資料](CQD-Power-BI-query-templates.md)
