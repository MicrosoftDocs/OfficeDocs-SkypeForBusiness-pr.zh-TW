---
title: 使用 CQD PSTN Direct 路由報告
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 CQD PSTN Direct 路由報告來監控並疑難排解 Microsoft 團隊中的 PSTN 通話。
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559422"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>使用 CQD PSTN Direct 路由報告

我們已在2020年3月新增 CQD PSTN Direct 路由報告，以供您下載[的 POWER BI 查詢範本 FOR CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 


CQD PSTN Direct 路由報告可協助客戶瞭解有關您的 SBC、電話語音、網路參數及網路效能比率的使用模式與品質的資訊services. 此資訊可協助您找出問題，包括中斷通話的原因。 例如，您可以知道何時放下音量，有多少通話會依原因而受到影響。

CQD PSTN Direct 路由報告有四個區段：

  - [PSTN 概述](#pstn-overview)

  - [服務詳細資料](#service-details)

  - [網路效能比率](#network-effectiveness-ratio)

  - [網路參數](#network-parameters)

## <a name="pstn-overview"></a>PSTN 概述

CQD PSTN Direct 路由報告提供下列與服務的整體健康情況相關的資訊（在過去的180天內）。
![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report1.png)

例如，如果您對透過 SBC abc.bca.adatum.biz 進行的所有撥出電話的整體使用量和健康情況感興趣，我們就是內部國家/地區：

| **撥出** | **描述**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | 您可以使用上方的篩選來向下切入，然後選取 [ByotIn] 作為 [呼叫類型]、abc.bca.contoso.com [會話 Boarder 控制器]，以及 [美國] 作為內部國家/地區。 |
| pplx-2            | 過去180天的使用量趨勢。 您可以在服務詳細資料頁面找到使用狀況詳細資料包告。                                                                     |
| 3            | 過去180天后的撥號延遲、延遲、抖動及資料包遺失趨勢。 您可以在 [網路參數] 頁面上找到 [詳細資料包表]。                           |
| 4            | 過去180天的同時通話和每日作用中使用者趨勢。 此圖表可協助您瞭解服務的最大數量。                            |
| 500            | 上個通話結束原因在過去的180天中受影響的服務品質。 您可以在 [網路有效比率（NER）] 頁面上找到服務健康情況詳細資料。                    |

## <a name="service-details"></a>服務詳細資料

此頁面提供每天的服務使用趨勢，以及依地理位置的使用者意見反應細分。

  - **總嘗試通話–** 總嘗試在該時間範圍內呼叫，包括成功和失敗的通話

  - **已連線的通話總數-** 該時間範圍內的連線通話總數

  - **總分鐘數–** 該時間範圍內的總分鐘使用量

  - **每日作用中的使用者（DAU）-** 一天中至少進行一個連線通話的每日作用中使用者計數

  - **同時通話–** 一分鐘內同時進行中的通話最大值

  - **使用者意見反應–**「對我的通話打分」分數來自使用者。 3-5 被視為良好的通話。 1-2 被視為不正確的呼叫。

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report2.png)

例如：

1.  如果您在02/14/2020 看到 [平均通話持續時間] 為0，您可以先檢查通話量看起來是否正常，並查看總的連線通話與總嘗試通話之間是否有很大的差異。 然後移至 [網路效能比率] 頁面，以投資撥打電話失敗的原因。

2.  如果您在 [使用者意見反應圖] 中看到增加紅色斑點，您可以移至 [網路效能比率] 頁面和 [網路] 參數，查看是否有任何不確定，您可以使用 MS 服務台來提升票證。

## <a name="network-effectiveness-ratio"></a>網路效能比率

這就是顯示在整體健康情況儀表板上的相同指標。 您可以在每小時網路效能比率中，查看含有受影響通話路線的每小時 NER 數的通話指示（入站/出站），並在下方加上通話結束原因圖表。

  - **NER** -功能（%）透過測量傳送給收件者的呼叫數與傳送給收件者的呼叫次數來傳送通話的網路。

  - **SIP 回應程式碼**-三位數的整數回應代碼會顯示通話狀態。

  - **Microsoft 回應代碼**-從 Microsoft 元件發出回應代碼。

  - **描述**：與 SIP 回應代碼及 Microsoft 回應程式碼相對應的原因階段。

  - **受影響的通話數量**-在所選時間範圍內，通話總數量會受到影響。

> ![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report3.png)
> 
例如：

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report4.png)

如果 [每日 NER] 在02/05/2020 上有一個 dip，您可以按一下日期，其他圖表就會縮放至該特定日期。

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report5.png)

從 NER 良好的每小時趨勢，您可以找出在21:00 周圍發生的 dip。 然後再次按一下以調整為小時21，並查看受影響的通話詳細資料，查看該小時內的通話失敗多少，以及通話結束的原因。 如果問題不與 SBC 有關，您可以從任何 SBC 問題或向服務台取得報告，開始進行自我疑難排解。

## <a name="network-parameters"></a>網路參數

所有網路參數都是從直接路由介面到會話邊界控制器的測量。 如需建議值的相關資訊，請參閱為[Microsoft 團隊準備貴組織的網路](prepare-network.md)，並查看客戶邊緣至 microsoft Edge 的建議值。

  - **抖動**：是在使用 RTCP （RTP 控制通訊協定）的兩個端點之間計算之網路傳播延遲時間變化的毫秒測量。

  - **資料包遺失**-是一種無法送達資料包的量度，它是在兩個端點之間計算。

  - **滯後**時間（也稱為往返行程時間）是傳送信號所需的時間長度，加上接收該信號所需的確認時間長度。 此時間延遲是由兩個信號點之間的傳播時間所組成。

> ![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report6.png)

例如：

如果您在四個圖表的任何一個（延遲、抖動、套件遺失率、Post 延遲）中看到一個峰值，請在02/14/2020 上按一下該日期點。 而底部的每小時趨勢圖將會重新整理，以顯示小時數。 您可以檢查 SBCs，或使用 MS 服務台來提升票證。

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>相關主題

[使用 Power BI 來分析 Microsoft 團隊的 CQD 資料](CQD-PSTN-report.md)