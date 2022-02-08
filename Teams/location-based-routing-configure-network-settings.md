---
title: 設定網路設定 - 位置式路由
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何建立及設定網路區域、網站和子網，Location-Based直接路由的路由。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2c6c0c317d934439acc5413f44b508a22b5cd8d3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393495"
---
# <a name="configure-network-settings-for-location-based-routing"></a>設定依位置路由的網路設定

如果您尚未這麼做，請參閱規劃直接路由Location-Based路由[](location-based-routing-plan.md)，以在設定路由的網路設定之前，先檢查Location-Based步驟。

本文將說明如何設定路由Location-Based設定。 在組織中電話系統直接路由之後，接下來的步驟是建立和設定網路區域、網路網站和網路子網。

## <a name="define-network-regions"></a>定義網路區域

網路區域包含網路網站集合，並跨多個地理區域互連網路的各個部分。 若要瞭解如何設定網路區域的步驟，請前往管理網路拓撲以在[Teams。](manage-your-network-topology.md)

## <a name="define-network-sites"></a>定義網路網站

網路網站代表貴組織有實體場地的位置，例如辦公室、一組建築物或校園。 您必須將拓撲中的每個網路網站與網路區域建立關聯。 若要瞭解如何設定網路網站的步驟，請參閱在 Teams 中管理雲端[功能的網路拓撲](manage-your-network-topology.md)。

使用 [路由Location-Based最佳做法是為每個具有唯一 PSTN 連線性的位置建立個別的網站。 您可以建立為路由Location-Based啟用的網站，或未針對路由啟用Location-Based網站。 例如，您可能會想要建立未針對 Location-Based 路由啟用的網站，讓已啟用 Location-Based 路由的使用者在漫遊到該網站時撥打 PSTN 通話。

## <a name="define-network-subnets"></a>定義網路子網

每個子網都必須與特定的網路網站相關聯。 您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。 若要瞭解如何設定網路子網的步驟，請前往管理網路拓撲以在[Teams。](manage-your-network-topology.md)

若要Location-Based路由，必須定義可Teams端點可連至網路的 IP 子網，並與已定義的網路建立關聯，才能強制執行免付費。 此子閘道聯可讓 [Location-Based路由在地理位置上找出端點，以判斷是否應該允許特定 PSTN 通話。 支援 IPv6 和 IPv4 子網。 當判斷Teams端點是否位於網站時，Location-Based路由會先檢查符合的 IPv6 位址。 如果沒有 IPv6 位址，請Location-Based路由檢查 IPv4 位址。

## <a name="define-trusted-ip-addresses-external-subnets"></a>在外部子網中定義 (IP 位址) 

信任的 IP 位址是商業網路的網際網路外部 IP 位址，用來判斷使用者的端點是否位於公司網路內。 若要瞭解如何設定信任的 IP 位址的步驟，請前往管理網路拓撲以在[Teams。](manage-your-network-topology.md)

如果使用者的外部 IP 位址符合信任 IP 位址清單中的 IP 位址，Location-Based 路由會檢查以判斷使用者端點所在的內部子網。 如果使用者的外部 IP 位址與信任 IP 位址清單中定義的任何 IP 位址不相符，端點會分類為位於未知位置，而且會封鎖與啟用 Location-Based 路由的使用者的任何 PSTN 通話。

## <a name="next-steps"></a>後續步驟

前往啟用[直接Location-Based路由的路由。](location-based-routing-enable.md)

## <a name="related-topics"></a>相關主題

- [雲端語音功能的網路設定Teams](cloud-voice-network-settings.md)
