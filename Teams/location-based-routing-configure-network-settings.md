---
title: 設定網路設定-以位置為基礎的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對直接路由建立及設定以位置為基礎的路由的網路區域、網站和子網。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8025467a0581c95a40551244948a8e6b7c0ecbc8
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372053"
---
# <a name="configure-network-settings-for-location-based-routing"></a>設定依位置路由的網路設定

如果您尚未這麼做，請參閱[直接路由的 [規劃位置] 路由](location-based-routing-plan.md)，以查看在設定位置式路由的網路設定之前，您必須採取的其他步驟。

本文說明如何設定以位置為基礎的路由的網路設定。 在貴組織中部署手機系統直接路由之後，接下來的步驟是建立及設定網路區域、網路網站和網路子網。

## <a name="define-network-regions"></a>定義網路區域

網路區域包含網路網站的集合，以及跨多個地理區域互連網路的各個部分。 如需如何設定網路區域的步驟，請移至[管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。

## <a name="define-network-sites"></a>定義網路網站

網路網站代表貴組織有實體場所（例如辦公室、一組建築物或校園）的位置。 您必須將拓撲中的每個網路網站與網路區域建立關聯。 如需如何設定網路網站的步驟，請參閱[在團隊中管理雲端功能的網路拓撲](manage-your-network-topology.md)。

針對位置路由的最佳做法是為每個具有唯一 PSTN 連線的位置建立一個單獨的網站。 您可以建立可用於位置路由的網站，或是未啟用位置式路由的網站。 例如，您可能會想要建立未啟用位置路由的網站，以允許啟用位置路由的使用者在漫遊到該網站時，進行 PSTN 呼叫。

## <a name="define-network-subnets"></a>定義網路子網

每個子網都必須與特定的網路網站相關聯。 您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。 如需如何設定網路子網的步驟，請移至[管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。

對於以位置為基礎的路由，小組端點可以連接至網路的位置上的 IP 子網必須定義並與已定義的網路建立關聯，才能強制進行免付費旁路。 這個子網的關聯功能可讓您以位置路由來找出端點，以判斷是否應該允許指定的 PSTN 通話。 支援 IPv6 和 IPv4 子網。 決定團隊端點是否位於網站上時，以位置為基礎的路由會先檢查相符的 IPv6 位址。 如果 IPv6 位址不存在，則以位置為基礎的路由檢查 IPv4 位址。

## <a name="define-trusted-ip-addresses-external-subnets"></a>定義信任的 IP 位址（外部子網）

[信任的 IP 位址] 是商業網路的網際網路外部 IP 位址，用來判斷使用者的端點是否在商業網路內。 如需如何設定信任的 IP 位址的步驟，請移至[管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。

如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中的 IP 位址相符，則以位置為基礎的路由檢查，以判斷使用者端點所在的內部子網。 如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中定義的任何 IP 位址都不相符，則會將端點分類為 [未知位置]，而且會封鎖對已啟用位置路由的使用者的任何 PSTN 呼叫。

## <a name="next-steps"></a>後續步驟

移至 [[啟用直接路由的以位置為基礎的路由](location-based-routing-enable.md)]。

## <a name="related-topics"></a>相關主題

- [小組中雲端語音功能的網路設定](cloud-voice-network-settings.md)
