---
title: 以位置為基礎的路由術語
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 瞭解與以位置為基礎之路由的相關術語與概念, 以進行直接路由。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: db6d6892c8a3bda8d30ac61d0458f252a6ac9281
ms.sourcegitcommit: 60c868155c7709df35fad23a41330483f8b59fee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2019
ms.locfileid: "36185013"
---
# <a name="location-based-routing-terminology"></a>以位置為基礎的路由術語

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

以下是在整個以位置為基礎的路由檔中使用的一些術語與概念。 建議您先熟悉這些條款與概念, 然後再深入瞭解檔。

|字詞  |說明  |
|---------|---------|
|網路區域     | 網路區域包含一個網路網站集合。 例如, 如果您的組織有許多位於印度的網站, 您可以選擇將 "印度" 指定為網路區域。        |
|網路網站    | 網路網站代表貴組織有實體場所 (例如辦公室、一組建築物或校園) 的位置。 網路網站定義為 IP 子網的集合。 針對位置路由的最佳做法是為每個具有唯一 PSTN 連線的位置建立一個單獨的網站。  每個網路網站都必須與一個網路區域建立關聯。 您可以建立可用於位置路由的網站, 或是未啟用位置式路由的網站。 例如, 您可能會想要建立未啟用位置路由的網站, 以允許啟用位置路由的使用者在漫遊到該網站時, 進行 PSTN 呼叫。 請注意, 網路網站也可以用來啟用和設定緊急通話。        |
|網路子網     |在團隊端點可以連接至網路的位置上, IP 子網必須定義並關聯至已定義的網路, 才能強制進行免付費略過。 多個子網可能會與同一個網路網站建立關聯, 但多個網站可能不會與同一個子網產生關聯。 這個子網的關聯功能可讓您以位置路由來找出端點, 以判斷是否應該允許指定的 PSTN 通話。 支援 IPv6 和 IPv4 子網。 決定團隊端點是否位於網站上時, 以位置為基礎的路由會先檢查相符的 IPv6 位址。 如果 IPv6 位址不存在, 則以位置為基礎的路由檢查 IPv4 位址。 <br><br>
|受信任的外部 IP 位址    |[受信任的外部 IP 位址] 是商業網路的網際網路外部 IP 位址。 在檢查特定網站相符前, 他們會判斷使用者的端點是否在公司網路內。 如果使用者的外部 IP 與信任清單中定義的 IP 位址相符, 則以位置為基礎的路由檢查, 以判斷使用者端點所在的內部子網。 如果使用者的外部 IP 位址與在信任清單中定義的任何 IP 位址都不相符, 則會將端點分類為未知的位置, 而對已啟用位置路由的使用者進行任何 PSTN 呼叫, 都會遭到封鎖。          |

### <a name="related-topics"></a>相關主題
- [規劃直接路由的以位置為基礎的路由](location-based-routing-plan.md)
- [設定以位置為基礎的路由的網路設定](location-based-routing-configure-network-settings.md)
- [針對直接路由啟用以位置為基礎的路由](location-based-routing-enable.md)
