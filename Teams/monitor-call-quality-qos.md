---
title: 在 Microsoft 團隊中實施 QoS 及監視通話分析
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jambirk
description: 使用 [服務品質 (QoS)] 設定, 然後在 Microsoft 團隊中呼叫分析和通話品質儀表板。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77730db17e900951f0fe1a60b7c0ae2ccdbfbc5b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181245"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>在 Microsoft 團隊中實施 QoS 及監視通話品質

## <a name="get-started"></a>快速入門

當您的使用者開始使用團隊撥打電話和召開會議時, 他們可能會遇到來電或 chopping 通話或會議的問題。 共用影片可能會凍結或像素化, 或完全失敗。 這是因為 IP 資料包所代表的語音和影片通信量遇到網路擁塞, 而不是順序讀出或根本無法進行。 有幾種方法可以在它們出現表面並防止其傳回 (主要是服務品質 (QoS)) 時, 找出這些問題。

**[服務品質 (QoS)** ] 是一種允許即時網路流量 (例如語音或視頻串流), 可讓您在不太敏感的通信量 (例如下載新的 app, 增加額外的下載沒太大的交易。 QoS 會使用 Windows 群組原則物件和路由功能 (稱為埠的存取控制清單) 來識別及標記即時資料流中的所有資料包, 這可協助您的網路提供語音、影片和螢幕共用來傳送自己的專用部分網路頻寬。

 現在, 我們只是說它是透過郵件傳送信件的方式: 如果您傳送 it 書籍的速度非常快, 且有足夠的功能, 如果您將它傳送給第一個課程, 就能以更快的速度傳送它, 而且如果您傳送 it 優先順序郵件, 它會在兩天內取得。 當然的網路比郵件執行的速度更快, 但仍會執行 true, 因為速度對於某些應用程式來說非常重要, 而且對其他人而言並不重要。 這個主旨本身在本質上是非常複雜且難以理解, 但它會在使用者體驗上帶來巨大的差異, 因此需要提前進行投資與精力。 已閱讀[[在 Microsoft 團隊中實施服務品質 (QoS)](QoS-in-Teams.md) ], 以取得更詳細的討論。

理想的做法是, 在您的內部網路上實施 QoS, 而不是設定小組, 但如果足夠小, 就可以選用。 這可讓延遲式的語音及視頻流量在其他流量前優先。 您可以在[Microsoft 團隊系統管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)的所有[用戶端裝置](QoS-in-Teams-clients.md), 以及您網路中的交換器與路由器上, 執行這項優先順序。

[[**通話分析] 和 [通話品質儀表板**](difference-between-call-analytics-and-call-quality-dashboard.md)] 可用來找出並疑難排解在進行中的作業時所帶來的問題。  

[**通話分析**] 會顯示與 Microsoft 團隊或商務用 Skype 帳戶中每位使用者的***特定通話與會議***相關的裝置、網路及連線性的詳細資訊。 如果您是 Office 365 系統管理員, 您可以使用呼叫分析來針對特定通話中遇到的通話品質和連線問題進行疑難排解。 這可協助您找出並消除問題。

**通話品質儀表板 (CQD)** 的設計目的是協助系統管理員和網路工程師優化其***網路***, 不會分析和疑難排解單一通話。 CQD 會將焦點從特定的使用者轉移, 以查看整個組織的匯總資訊。 這也可以協助您找出並消除問題。

## <a name="related-topics"></a>相關主題

[在 Microsoft 團隊中實現服務品質 (QoS)](QoS-in-Teams.md)

[影片: 通話品質概覽](https://aka.ms/teams-quality)

[設定通話分析](set-up-call-analytics.md)

[使用呼叫分析來排查不佳的通話品質問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[開啟並使用通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)

[通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流程分類](stream-classification-in-call-quality-dashboard.md)