---
title: 監控並改善通話品質Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 在 QoS 設定 (服務品質) ，然後在 Microsoft Teams 中使用通話分析與通話品質儀表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 82edaaa1458897365cf5857837610070bb43137d385d73d084e73db9e6d6f82f
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "58190986"
---
# <a name="microsoft-teams-monitor-and-improve-call-quality"></a>Microsoft Teams：監控並改善通話品質

本文介紹三種可用於監控、疑難排解、管理和改善通話品質的重要Microsoft Teams。 

- **通話品質儀表板 (CQD) ：** 若要分析全組織的趨勢或問題，請推動改善績效

- **通話分析**：分析個別使用者的通話和會議品質

- **QoS (服務品質：)** 重要網路流量的優先順序



## <a name="monitor-and-troubleshoot-call-quality"></a>監控和疑難排解通話品質
您將使用每個使用者的通話分析與通話品質 **儀表板**，尋找及疑難排解在進行中作業期間所出現之通話品質問題。 這可讓您在整個網路中推動提升績效。 這兩個工具都位於Teams中心。

 - **通話分析** 會顯示與特定通話和會議相關的裝置、網路和連接的詳細資訊，Teams。 **** Teams系統管理員和技術支援人員會使用這項資訊來疑難排解特定通話中的通話品質與連接問題。 若要深入瞭解，請參閱 [設定通話分析](set-up-call-analytics.md) 及使用通話分析來疑難排解 [通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **通話品質儀表板 (CQD)** 提供您整個組織的通話品質 **** 全網路視圖。 使用 CQD 資訊來説明您找出並修正問題。 首先， [設定 CQD](turning-on-and-using-call-quality-dashboard.md)。 然後閱讀[管理通話和會議品質Teams。](quality-of-experience-review-guide.md)

 通話分析與 CQD 同時執行，可以獨立或一起使用。 例如，如果通訊支援專家決定需要更多協助來疑難排解使用者的通話問題，他們會將通話升級至通訊支援工程師，而該工程師可以存取通話的其他相關資訊。 因此，通訊支援工程師會通知網路工程師在通話分析中發現可能的網站相關問題。 網路工程師會檢查 CQD，查看整體網站相關問題是否可能是造成使用者通話問題的原因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 排定重要網路流量的優先順序
當使用者開始使用Teams電話和會議時，他們可能會遇到來電者的語音中斷或中斷通話或會議。 共用影片可能會凍結或像素化，或完全失敗。 這是因為代表語音和視音訊流量的 IP 封包遇到網路擠塞，且到達順序不一或完全中斷。 如果發生此 (或防止其發生于第一) ，請使用服務品質 (**QoS) 。** 

使用 QoS，您可以排定延遲敏感性網路流量的優先順序 (例如語音或視音訊流) ，讓流量在較不敏感的流量前面 (例如下載新應用程式 ，而額外下載第二秒並不重要) 。 QoS 會使用 Windows 群組原則物件和稱為埠式存取控制清單的路由功能，來識別並標記即時資料流中的所有封包，這項功能會指示您的網路提供語音、視像和螢幕共用自己的私人網路絡頻寬。

在理想情況下，您將在內部網路上執行 QoS，同時準備推出Teams，但您隨時可以執行。 如果您夠小，您可能不需要 QoS。

準備就緒時，請參閱在 (中) [QoS Microsoft Teams。](QoS-in-Teams.md)

若要使用 QoS 管理會議流量，請參閱設定要如何處理即時媒體流量，Teams[會議](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[設定 CQD](turning-on-and-using-call-quality-dashboard.md)

[管理通話和會議品質Teams](quality-of-experience-review-guide.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
