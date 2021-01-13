---
title: 設定網路設定-以位置為基礎的路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何建立及設定網路區域、網站和子網，以進行直接路由 Location-Based 路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822943"
---
# <a name="configure-network-settings-for-location-based-routing"></a>設定依位置路由的網路設定

如果您還沒有這麼做，請參閱 [直接路由 Location-Based 路由](location-based-routing-plan.md) ，以查看在設定 Location-Based 路由的網路設定之前必須採取的其他步驟。

本文說明如何設定 Location-Based 路由的網路設定。 在貴組織中部署手機系統直接路由之後，接下來的步驟是建立及設定網路區域、網路網站和網路子網。

## <a name="define-network-regions"></a>定義網路區域

網路區域包含網路網站的集合，以及跨多個地理區域互連網路的各個部分。 如需如何設定網路區域的步驟，請移至 [管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。

## <a name="define-network-sites"></a>定義網路網站

網路網站代表貴組織有實體場所（例如辦公室、一組建築物或校園）的位置。 您必須將拓撲中的每個網路網站與網路區域建立關聯。 如需如何設定網路網站的步驟，請參閱 [在團隊中管理雲端功能的網路拓撲](manage-your-network-topology.md)。

Location-Based 路由的最佳做法是為每個具有唯一 PSTN 連線的位置建立一個單獨的網站。 您可以建立可用於 Location-Based 路由的網站，或未啟用 Location-Based 傳送功能的網站。 例如，您可能會想要建立未啟用 Location-Based 路由的網站，以允許已啟用 Location-Based 路由的使用者在漫遊到該網站時，進行 PSTN 呼叫。

## <a name="define-network-subnets"></a>定義網路子網

每個子網都必須與特定的網路網站相關聯。 您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。 如需如何設定網路子網的步驟，請移至  [管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。

在 Location-Based 路由中，小組端點可以連線到網路的位置上，必須定義 IP 子網，並將其與已定義的網路建立關聯，才能強制進行免付費旁路。 這個子網的關聯功能可讓 Location-Based 路由來尋找地理位置上的端點，以判斷是否應該允許特定的 PSTN 通話。 支援 IPv6 和 IPv4 子網。 決定團隊端點是否位於網站時，請 Location-Based 路由首先檢查是否有相符的 IPv6 位址。 如果 IPv6 位址不存在，請 Location-Based 路由檢查來尋找 IPv4 位址。

## <a name="define-trusted-ip-addresses-external-subnets"></a>在外部子網 (定義信任的 IP 位址) 

[信任的 IP 位址] 是商業網路的網際網路外部 IP 位址，用來判斷使用者的端點是否在商業網路內。 如需如何設定信任的 IP 位址的步驟，請移至  [管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。

如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中的 IP 位址相符，請 Location-Based 路由檢查，以判斷使用者端點所在的內部子網。 如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中定義的任何 IP 位址都不相符，則會將端點分類為 [未知位置]，而對已啟用 Location-Based 路由的使用者進行任何 PSTN 呼叫，都會遭到封鎖。

## <a name="next-steps"></a>後續步驟

移至 [啟用直接路由 Location-Based 路由](location-based-routing-enable.md)。

## <a name="related-topics"></a>相關主題

- [小組中雲端語音功能的網路設定](cloud-voice-network-settings.md)
