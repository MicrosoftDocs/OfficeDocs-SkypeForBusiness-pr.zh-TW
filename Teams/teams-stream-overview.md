---
title: Microsoft Teams 中串流處理的編碼器概觀
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
description: 本文將概略說明 Microsoft Teams 串流事件的編碼器型 RTMP 設定。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d7ea21edb6677397785367cecd3daaf9bbe513f3
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767924"
---
# <a name="live-streaming-events-in-microsoft-teams"></a>Microsoft Teams 中的即時串流活動

您可以使用貴組織的 Microsoft Teams 建立即時活動。 您可以針對各種情況排程、製作和提供即時活動，例如全公司活動、領導力更新等等。 即時串流活動可讓製作人策劃和控制向觀眾廣播的內容。

您可以使用編碼器的單一位元速率 RTMP 或 RTMPS 串流來建立、排程和執行即時活動 – 我們會處理所有轉譯，以便將適配位元速率傳遞給您的檢視者。

就像 Teams 中的任何其他影片一樣，您可以將即時活動開放給整個公司，或是限制特定群組的存取權。 這可在 Teams 內提供端對端建立和檢視體驗。

活動結束後，視訊會隨選提供，並提供智慧型功能，包括：

- 語音轉換文字和隱藏式輔助字幕。
- 文字記錄搜尋和時間代碼可讓您在影片中快速找到重要的時刻。

## <a name="live-events-in-microsoft-365"></a>Microsoft 365 中的即時活動

無論觀眾、團隊或社群位於何處，您都可以在 Teams 或 Yammer 中建立即時熱氣騰騰的活動。 出席者可以觀看高畫質 (HD) 影片，並透過仲裁型 Q&A 體驗提交問題。 跨 Microsoft 365 無縫整合，代表您可以使用 Teams 來提供高製作、工作室品質的活動。

## <a name="get-started"></a>開始使用

確保您想要能夠建立即時活動的使用者擁有建立即時事件所需的許可權。 根據預設，貴組織中的每個人都可以建立即時活動，不過 Teams 系統管理員可以限制存取權。 深入瞭解即時活動管理。

1. 在 Teams 系統管理中心的左側導覽畫面中，移至 **[會議**  >  **即時活動原則**] > [**管理原則]** 索引標籤。
1. 如果您想要：
    1. 編輯現有的預設原則，選擇 **全全組織 (預設)**。
    1. 建立新的自訂原則，選擇 **[+新增]**。
    1. 編輯自訂原則，選取原則，然後選擇 [ **編輯]**。

## <a name="monitor-your-event"></a>監控您的活動

身為製作人，您可以使用 Teams 用戶端查看觀眾摘要 (顯示在右側) 以及目前檢視活動的出席者數目。

## <a name="capabilities"></a>功能

以下是即時串流事件的功能：

|操作                                            |限制                                                               |
|-----------------------------------------------------|---------------------------------------------------------------------|
|使用外部編碼器) 在 Teams (中建立即時活動  |企業版 (E1、E3、E5) 、教育版 (A3、A5)                           |
|觀看即時活動                                     |檢視者具有檢視活動的許可權和有效的 Teams 授權 (除非事件為公開，否則不需要檢視的授權)  |
|最大解析度                                   |720p                                                                 |
|即時或即時) 中 (的並行即時活動上限 |15                                                                   |
|同時使用中檢視者                            |10000                                                                |
|即時活動的長度上限                         |4 小時                                                              |
|合作夥伴網路快取支援                      |Ive、Kollective、Riverbed、Ramp、Microsoft                          |
|其他網路快取支援                        |可能可以運作，但不支援                                        |
|出席者 DVR 控制項                                |暫停， 播放速度 (2x 追平， 1x 在即時) ， 搜尋                |
|即時輔助字幕                                   |708 字幕從編碼器傳遞                                |
|自動語音轉換文字和輔助字幕                |在事件之後處理                                            |
|互動式討論                              |從 Yammer 建立事件時透過 Yammer 提供支援           |
|Teams 批註                                       |活動結束後提供使用                                       |
|在活動) 之後的即時活動 (點選檢視        |即時的自動轉換為隨選，以在 Teams 中立即檢視和編制索引 |
|可下載的錄製                               |由擁有者處理並可在即時活動後使用               |

Teams 中的即時活動是一項高度可用的服務，您可以預期在規模上有良好的效能。 在不太可能導致需要容錯移轉的情況下，使用外部編碼的即時事件將不會有備援，而且無法復原。
