---
title: 使用 CQD PSTN 直接路由報表
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: 使用 Microsoft Teams 通話品質儀表板 (CQD) ) PSTN 直接路由報告來監控和疑難排解 Microsoft Teams 中的 PSTN 通話。
ms.openlocfilehash: 8d6e971adc3cd7e4ec9b4038356e744d4451146f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789888"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>使用 CQD PSTN 直接路由報表

我們在 2020 年 3 月新增了 Microsoft Teams 通話品質儀表板 (CQD) PSTN 直接路由報告至可下載 [的 Power BI 查詢 CQD 範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 


CQD PSTN 直接路由報告 (CQD PSTN 直接路由報告.pbit) 協助您瞭解 PSTN 服務的使用模式和品質。 使用此報告來監控服務使用量、會話框線控制器 (SBC) 的相關資訊、電話語音服務、網路參數和網路有效性比例詳細資料。 此資訊可協助您找出問題，包括中斷通話的原因。 例如，您可以查看降低音量的時機、受影響的通話數，以及原因為何。


CQD PSTN 直接路由報告有四個區段：

  - [PSTN 概觀](#pstn-overview)

  - [服務詳細資料](#service-details)

  - [網路有效性比例](#network-effectiveness-ratio)

  - [網路參數](#network-parameters)

## <a name="highlights"></a>突出

1. 依通話類型、SBC、來電者和來電者國家/地區進行分析

   CQD PSTN 直接路由報告會匯總租使用者過去 7、30 天或 180 天內所有 SB 的可靠性與使用量計量， (6 個月) 。 您可以依通話類型、SBC、來電者及來電者國家/地區來分析資料。 如果您對特定 SBC 或國家/地區感興趣，您可以識別所選時間範圍內的趨勢變化。
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 直接路由報表中可用篩選的螢幕擷取畫面。":::
   
2. 追蹤趨勢

    在嘗試瞭解服務使用量和可靠性時，趨勢分析是不可或缺的。 每小時趨勢可以仔細查看每日效能，以協助識別即時事件。 每日趨勢可讓您從長期的觀點查看服務健康情況。 請務必能夠使用適當的資料細度在這兩種模式之間切換。 CQD PSTN 直接路由報表提供 6 個月趨勢概觀、每天 7 天和 30 天的趨勢，以及每小時的趨勢，讓您可以分析每個層級的效能。
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 直接路由報表中趨勢圖的螢幕擷取畫面。":::

3. 切入至 SBC 或使用者層級

   我們已在 CQD 中針對許多資料類別建置切入功能，可讓您快速瞭解 SBC 或使用者層級的使用方式或可靠性分配。 您可以使用切入功能快速找出問題，並瞭解實際的使用者影響。 CQD PSTN 直接路由報告功能會切入服務詳細資料和網路有效率指派。 按一下您感興趣的資料點，深入瞭解 SBC 或使用者層級的詳細資料。
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="螢幕擷取畫面顯示資料點上的切入功能。":::


## <a name="pstn-overview"></a>PSTN 概觀

CQD PSTN 直接路由報告提供下列資訊，與過去 180 天服務的整體健康情況相關。
![螢幕擷取畫面：PSTN CQD 報告。](media/CQD-PSTN-report1.png)

例如，如果您對於透過 SBC abc.bca.adatum.biz 以及美國國內國家/地區的所有輸入通話整體使用方式和健康情況感興趣：

| **圖說文字** | **描述**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | 您可以使用頂端的篩選器向下切入，然後選取 ByotIn 做為通話類型，abc.bca.contoso.com 為會話版面控制器，而美國則為內部國家/地區。 |
| 2            | 過去 180 天的使用趨勢。 您可以在 [服務詳細資料] 頁面上找到使用詳細資料包告。                                                                     |
| 3            | 過去 180 天的電話撥號延遲、延遲、抖動和封包遺失趨勢。 您可以在 [網路參數] 頁面上找到詳細報告。                           |
| 4            | 過去 180 天的並行通話和每日作用中使用者趨勢。 此圖表可協助您瞭解服務的最大磁片區。                            |
| 5            | 前通話結束原因影響過去 180 天的服務品質。 您可以在 [網路效率比率] (NER) 頁面上找到服務健康情況的詳細資料。                    |

## <a name="service-details"></a>服務詳細資料

本頁依地理位置提供每天的服務使用趨勢和使用者意見反應明細。

  - **通話總數 –** 該時間範圍內的嘗試通話總數，包括成功和失敗的通話

  - **連線通話總數 -** 該時間範圍內的連線通話總數

  - **總分鐘數 –** 該時間範圍內的總分鐘數使用量

  - **每日作用中使用者 (DAU) –** 當天至少撥打一次連線通話的每日作用中使用者數目

  - **並行通話 –** 一分鐘內同時進行中通話的上限

  - **使用者意見反應 –** 「為我的通話評分」分數來自使用者。 3-5 被視為一個好通話。 1-2 會視為不正常通話。

![螢幕擷取畫面：PSTN CQD 報告。](media/CQD-PSTN-report2.png)

例如：

1.  如果您看到平均通話持續時間在 2020/02/14 降為 0，您可以先檢查通話音量看起來是否正常，並查看連線總通話和總通話量之間是否有很大的差異。 然後移至 [網路有效性比例] 頁面，以根據通話失敗原因進行投資。

2.  如果您在使用者意見反應對應上看到增加的紅點，您可以移至 [網路有效性比例] 頁面和 [網路參數]，查看是否有任何異常，您可以使用 MS Service Desk 提出票證。

## <a name="network-effectiveness-ratio"></a>網路有效性比例

這與 [整體健康情況] 儀表板上顯示的度量相同。 您可以在下方的 [每小時網路有效性比例] 和 [通話結束原因] 圖表上，針對通話路線 (連入/輸出) ，檢查每小時 NER 號碼與受影響的通話詳細資料。

  - **NER** - (%) 網路的能力是藉由測量來電的傳送次數與傳送給收件者的來電數目。

  - **SIP 回應代碼**-三位數整數回應碼會顯示通話狀態。

  - 從 Microsoft 元件傳送的 **Microsoft 回應代碼**-A 回應碼。

  - **描述** – 對應至 SIP 回應碼和 Microsoft 回應碼的原因階段。

  - **受影響的通話數** 目 ： 在選取的時間範圍內，電話總數受到影響。

> ![螢幕擷取畫面：PSTN CQD 報告。](media/CQD-PSTN-report3.png)
> 
例如：

![螢幕擷取畫面：PSTN CQD 報告。](media/CQD-PSTN-report4.png)

如果 Daily NER 在 2020/02/02/02 下滑，您可以按一下日期，其他圖表就會縮放到該特定日期。

![螢幕擷取畫面：PSTN CQD 報告。](media/CQD-PSTN-report5.png)

從 NER 良好百分比每小時趨勢中，您可以找到 21：00 左右的下滑趨勢。 然後再按一下以縮放至小時 21，並查看 [中斷的通話詳細資料]，以查看該小時內有多少通電話失敗，以及通話結束的原因為何。 您可以從在任何 SBC 問題上進行自我疑難排解，或在問題與 SBC 無關時回報給服務台。

## <a name="network-parameters"></a>網路參數

所有網路參數都是從直接路由介面測量到會話框線控制器。 如需建議值的相關資訊，請參閱 [準備貴組織的 Microsoft Teams 網路](prepare-network.md)，並查看客戶 Edge 至 Microsoft Edge 建議的值。

  - **抖動** – 使用 RTCP (RTP 控制通訊協定) ，在兩個端點之間計算網路傳播延遲時間變化的毫秒度量值。

  - **封包遺失** – 是無法送達的封包量值;它會在兩個端點之間計算。

  - **延遲** - (也稱為來回時間) 是訊號傳送所需的時間長度，加上接收訊號所花費的時間長度。 此時間延遲包含訊號兩點之間的傳播時間。

> ![螢幕擷取畫面：PSTN CQD 報告。](media/CQD-PSTN-report6.png)

例如：

如果您看到特定日期的四個圖表 (延遲、抖動、封裝遺失率、轉盤延遲後) 的任一圖表上出現尖峰，例如，02/14/2020 上的延遲，請按一下日期點。 底部的每小時趨勢圖會重新整理以顯示每小時的數位。 您可以使用 MS 服務台檢查 SB 或提高票證。

![螢幕擷取畫面：PSTN CQD 報告。](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>相關主題

[使用 Power BI 來分析 Microsoft Teams 的 CQD 資料](CQD-PSTN-report.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)