---
title: 監視並改善 Microsoft Teams 的通話品質
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用服務品質 (QoS) 設定，然後在 Microsoft Teams 中呼叫分析和通話品質儀表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed9bab3ad0cde91bc8faa4298956b07f73438e823e3e3c110ce09610fee5e7c0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286262"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>監視並改善 Microsoft Teams 的通話品質

本文介紹三個主要工具，您可以用來監視、疑難排解、管理及提高 Microsoft Teams 中的通話品質。 

- **通話品質儀表板 (CQD)**：分析整個組織的趨勢或問題，提高效能的增強功能

- **通話分析**：分析個別使用者的通話和會議品質

- **服務品質 (QoS)**：優先順序重要的網路流量



## <a name="monitor-and-troubleshoot-call-quality"></a>監視及疑難排解通話品質
您將使用每一位使用者的 **呼叫分析** 和 **通話品質儀表板** ，尋找及疑難排解進行中作業時所產生的通話品質問題。 這可讓您促進整個網路的效能增強。 這兩個工具都位於 Teams 系統管理中心。

 - 「**呼叫分析**」顯示與 Teams 中每位使用者之 **_特定通話和會議_** 相關之裝置、網路及連線能力的詳細資訊。 Teams 系統管理員和支援人員代理程式會使用此資訊來疑難排解特定通話中的通話品質和連線問題。 若要深入瞭解，請參閱 [設定通話分析](set-up-call-analytics.md) 和 [使用呼叫分析來疑難排解通話品質不良](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **通話品質儀表板 (CQD)** 可讓您在整個組織中查看通話品質的整個 **_網路_** 。 使用 CQD 資訊可協助您找出並修正問題。 首先， [設定 CQD](turning-on-and-using-call-quality-dashboard.md)。 然後[在 Teams 中讀取 [管理通話和會議品質](quality-of-experience-review-guide.md)]。

 通話分析和 CQD 會平行執行，且可以個別使用，也可以一起使用。 例如，如果通訊支援專家判斷他們需要進一步協助疑難排解使用者的通話問題，他們會將通話提升至通訊支援工程師，該工程師可以存取有關通話的其他資訊。 接下來，通訊支援工程師會提醒網路工程師可能會在通話分析中注意到的網站相關問題。 網路工程師會檢查 CQD，以查看整體網站相關問題是否可能是導致使用者呼叫問題的原因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 來設定重要網路流量的優先順序
當您的使用者開始使用 Teams 用於通話和會議時，他們可能會遇到來電者的語音中斷或削減通話或會議。 共用影片可能會凍結或像素化，或完全失敗。 這是因為表示語音和影片流量遇到網路擁塞，但未達到順序的 IP 封包。 如果發生這種情況 (或是避免其第一次發生) ，請使用 [ **服務品質 (QoS)**。 

透過 QoS，您可以將延遲敏感的網路流量劃分成 (例如，語音或影片資料流程) ，讓其「在敏感程度較低的流量之前進行線上切削」 (（如下載新的應用程式），在下載新的應用程式時，將不會有很大的交易) 。 QoS 會使用 Windows 群組原則物件和稱為埠型存取控制清單的路由功能來識別及標記即時資料流中的所有封包，這會指示您的網路提供語音、影片和螢幕共用自己專屬的網路頻寬。

理想狀況下，您會在內部網路上實施 QoS，而準備好推出 Teams，但您可以隨時執行。 如果您很小，您可能不需要 QoS。

當您準備好時，請參閱[執行服務品質 (QoS) Microsoft Teams](QoS-in-Teams.md)。

若要使用 QoS 來管理會議流量，請參閱[設定您要如何處理 Teams 會議的即時媒體流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[設定 CQD](turning-on-and-using-call-quality-dashboard.md)

[在 Teams 中管理通話和會議品質](quality-of-experience-review-guide.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)