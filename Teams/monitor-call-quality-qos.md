---
title: 監控和改善 Microsoft Teams 的通話品質
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用 [服務品質] (QoS) 設定，然後在 Microsoft Teams 中使用 [通話分析] 和 [通話品質儀表板]。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac317ff6ac17a2b6a0e94c0fa5683979cb887b90
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66793240"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>監控和改善 Microsoft Teams 的通話品質

本文介紹三種可在 Microsoft Teams 中用來監視、疑難排解、管理和改善通話品質的重要工具。 

- **呼叫品質儀表板 (CQD)**：若要分析全組織的趨勢或問題，請推動效能的改善

- **通話分析**：分析個別使用者的通話和會議品質

- **服務品質 (QoS)**：排列重要網路流量的優先順序



## <a name="monitor-and-troubleshoot-call-quality"></a>監視和疑難排解通話品質
您將使用每個使用者的 **通話分析** 和 **通話品質儀表板** 來尋找並疑難排解在進行中作業期間出現的通話品質問題。 這可讓您推動整個網路的效能改進。 這兩種工具都位於 Teams 系統管理中心。

 - **通話分析會** 顯示與 Teams 中每個使用者  **_特定通話和會議_** 相關的裝置、網路和連線能力的詳細資訊。 Teams 系統管理員和技術服務專員會使用此資訊，針對特定通話中的通話品質和連線問題進行疑難排解。 若要深入瞭解，請閱讀 [設定通話分析](set-up-call-analytics.md) 和 [使用通話分析來疑難排解不佳的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **呼叫品質儀表板 (CQD)** 可讓您以 **_全網路檢視_** 整個組織的通話品質。 使用 CQD 資訊來協助您找出並修正問題。 首先， [設定 CQD](turning-on-and-using-call-quality-dashboard.md)。 然後閱讀 [管理 Teams 中的通話和會議品質](quality-of-experience-review-guide.md)。

 通話分析和 CQD 同時執行，可以獨立使用或一起使用。 例如，如果通訊支援專員判斷他們需要更多協助來疑難排解使用者的通話問題，他們會將通話向上呈報給通訊支援工程師，後者有權存取通話的其他相關資訊。 此外，通訊支援工程師會提醒網路工程師他們可能在通話分析中注意到的網站相關問題。 網路工程師會檢查 CQD，以查看整體網站相關問題是否可能是造成使用者通話問題的起因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 排定重要網路流量的優先順序
當您的使用者開始使用 Teams 進行通話和會議時，可能會遇到來電者的語音中斷或中斷通話或會議。 共用視訊可能會凍結或像素化，或完全失敗。 這是因為代表語音和視訊流量的 IP 封包遇到網路圊塞，或完全無法依序送達。 如果發生這種情況 (或是要避免) 發生這種情況，請使用 **服務品質 (QoS)**。 

使用 QoS，您可以優先處理延遲敏感的網路流量 (例如語音或視訊串流) ，允許它在較不敏感 (的流量前面「換行」，例如下載新的應用程式，另外還有一秒的下載時間並不大) 。 QoS 會使用 Windows 群組原則物件和稱為埠型存取控制清單的路由功能，識別並標記即時串流中的所有封包，這會指示您的網路提供語音、視訊和螢幕共用自己的私人網路絡頻寬。

在理想情況下，您會在內部網路上實作 QoS，並準備好推出 Teams，但您可以隨時執行。 如果您夠小，可能就不需要 QoS。

當您準備好時，請閱讀 [Microsoft Teams 中的實作服務品質 (QoS) ](QoS-in-Teams.md)。

若要使用 QoS 管理會議流量，請閱讀 [設定您要如何處理 Teams 會議的即時媒體流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[設定 CQD](turning-on-and-using-call-quality-dashboard.md)

[在 Teams 中管理通話和會議品質](quality-of-experience-review-guide.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
