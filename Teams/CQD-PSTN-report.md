---
title: 使用 CQD PSTN 直接路由報告
ms.author: serdars
author: SerdarSoysal
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
description: 使用 [Microsoft Teams通話品質儀表板 (PSTN) ) 直接路由報告來監控和疑難排解 PSTN Microsoft Teams。
ms.openlocfilehash: 18e24690fe86bf7efd511bea674c3d3d7eba3e43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635057"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>使用 CQD PSTN 直接路由報告

我們于 2020 年 3 月新增了 Microsoft Teams 通話品質儀表板 (CQD) PSTN 直接路由報告至可下載[的 Power BI](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)查詢範本 。 


CQD PSTN 直接路由報表 (CQD PSTN 直接路由報表.pbit) 可協助您瞭解 PSTN 服務的使用模式和品質。 使用此報表可監控服務使用方式、會話邊界控制器 (SBC) 、電話語音、網路參數和網路效能比詳細資料。 這項資訊可協助找出問題，包括通話中斷的原因。 例如，您將能夠查看音量何時降低，或是有多少通話受到影響，以及原因。


CQD PSTN 直接路由報告有四個區段：

  - [PSTN 概觀](#pstn-overview)

  - [服務詳細資料](#service-details)

  - [網路效能比](#network-effectiveness-ratio)

  - [網路參數](#network-parameters)

## <a name="highlights"></a>突出

1. 根據通話類型、SBC、來電和通話物件國家/地區來分析

   CQD PSTN 直接路由報告會匯總租使用者上所有 SBC 在) 年的最後 7、30 或 180 天的可靠性 (使用方式) 。 您可以根據通話類型、SBC、來電者及通話物件國家/地區來分析資料。 如果您對特定的 SBC 或國家/地區感興趣，您可以找出所選時間範圍內的趨勢變更。
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 直接路由報告中可用的篩選的螢幕擷取畫面":::
   
2. 追蹤趨勢

    趨勢分析在嘗試瞭解服務使用方式和可靠性時不可或缺。 每小時趨勢提供每日績效的密切觀察，有助於識別即時事件。 每日趨勢讓您從長期的觀點來查看服務健康情況。 必須能夠以適當的資料細微性，在兩種模式之間切換。 CQD PSTN 直接路由報告提供 6 個月趨勢概觀、7 天和 30 天每日趨勢，以及每小時趨勢，以便分析每個層級的績效。
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 直接路由報告中的趨勢圖形螢幕擷取畫面":::

3. 深入到 SBC 或使用者層級

   我們已在 CQD 中建立許多資料類別的深入深入功能，讓您快速瞭解 SBC 或使用者層級的使用方式或可靠性分配。 使用鑽取功能，您可以快速發現問題並瞭解使用者的實際影響。 CQD PSTN 直接路由報告功能會深入探討服務詳細資料與網路效能比度量。 按一下您感興趣的資料點，以深入瞭解 SBC 或使用者層級詳細資料。
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="顯示資料點上的深入功能之螢幕擷取畫面":::


## <a name="pstn-overview"></a>PSTN 概觀

CQD PSTN 直接路由報告提供下列與過去 180 天服務整體健康情況有關的資訊。
![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report1.png)

例如，如果您對透過 SBC 撥打的所有來電的整體使用狀況和健康情況感興趣，abc.bca.adatum.biz 美國作為國內國家/地區：

| **通話** | **描述**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | 您可以使用頂端的篩選向下向下切入，然後選取 ByotIn 做為通話類型、abc.bca.contoso.com 會話 Boarder 控制器，以及美國做為內部國家/地區。 |
| 2            | 過去 180 天的使用量趨勢。 您可以在服務詳細資料頁面上找到使用方式詳細資料包表。                                                                     |
| 3            | 過去 180 天內的撥號延遲、延遲、抖動和封包遺失趨勢後。 您可以在網路參數頁面上找到詳細報告。                           |
| 4            | 過去 180 天的同時通話和每日使用中使用者趨勢。 此圖表可協助您瞭解服務的最大數量。                            |
| 5            | 熱門通話結束原因影響過去 180 天的服務品質。 您可以在網路有效比率與 NER (NER) 詳細資料。                    |

## <a name="service-details"></a>服務詳細資料

此頁面提供每天的服務使用趨勢，以及使用者的意見回饋按地理位置分類。

  - **嘗試通話總數 –** 該時間範圍內的總嘗試通話次數，包括成功和失敗的通話

  - **已連接通話總數 -** 該時間範圍內已連接的通話總數

  - **總分鐘數 –** 該時間範圍內的總分鐘使用量

  - **每日使用中使用者 (DAU) –** 當天至少撥打過一通電話的每日使用中使用者計數

  - **同時通話 –** 一分鐘內同時進行中通話的最大值

  - **使用者意見-** 「我的通話評分」分數來自使用者。 3-5 視為良好的通話。 1-2 視為錯誤通話。

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report2.png)

例如：

1.  如果您看到平均通話持續時間在 2020/02/14 時降低為 0，您可以先檢查通話音量是否正常，並查看總連接通話與總通話次數之間是否有重大差異。 接著，請前往網路效能比頁面，以投資通話失敗的原因。

2.  如果您在使用者意見回饋圖上看到紅點增加，您可以前往網路效能比頁面和網路參數，查看是否有異常情況，您也可以使用 MS Service Desk 提出票證。

## <a name="network-effectiveness-ratio"></a>網路效能比

這是顯示在整體健康情況儀表板上的相同度量。 您可以在下方的每小時網路效能比和通話結束原因圖表上，檢查每小時 NER 號碼與受影響的來電詳細資料， (呼叫路線) 入/出號碼。

  - **NER** - (%) ，測量已傳送的通話數與傳送給收件者的通話數，以傳送通話。

  - **SIP 回應程式** 代碼 - 三位數的整數回應程式碼會顯示通話狀態。

  - **Microsoft 回應代碼**-從 Microsoft 元件所送出的回應代碼。

  - **描述** – 對應到 SIP 回應代碼和 Microsoft 回應代碼的原因階段。

  - **受影響的通話數** ： 在所選時間範圍內受影響的通話總數。

> ![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report3.png)
> 
例如：

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report4.png)

如果 Daily NER 在 2020/02/05 出現下拉，您可以按一下日期，其他圖表會縮放至該特定日期。

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report5.png)

從 NER 良好百分比每小時趨勢中，您可以發現 21：00 左右會發生下拉。 然後再次按一下以縮放至第 21 小時，並檢查 [影響通話詳細資料>，以查看該小時內有多少通話失敗，以及通話結束原因為何。 您可以在任何 SBC 問題上自行自找問題開始，如果問題與 SBC 沒有關聯，也可以向服務台報告。

## <a name="network-parameters"></a>網路參數

所有網路參數都是從直接路由介面到會話邊界控制器測量。 有關建議值的資訊，請參閱準備貴組織的網路[Microsoft Teams，並](prepare-network.md)查看 Customer Edge 以Microsoft Edge建議的值。

  - **抖動** – 是使用 RTCP 或 RTP 控制通訊協定在兩個端點之間計算網路傳播延遲 (的毫秒) 。

  - **封包** 遺失 – 是未送達的封包量值;這是在兩個端點之間計算。

  - 延遲 **-** (也稱為往返時間) 是訊號的接收時間長度，加上接收該訊號所花的時間長度。 此延遲時間是由訊號兩點之間的傳播時間所組成。

> ![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report6.png)

例如：

如果您看到特定日期的四個圖表 (延遲、抖動、封裝遺失率、撥號後延遲) ，例如 2020/02/14 的延遲，請按一下日期點。 而底部的每小時趨勢圖會重新顯示每小時數位。 您可以使用 MS Service Desk 檢查 SBCs 或提出票證。

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>相關主題

[使用 Power BI 分析 CQD 資料Microsoft Teams](CQD-PSTN-report.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)