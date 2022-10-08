---
title: 設定網路設定 - 以位置為基礎的路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何建立及設定適用于直接路由的Location-Based路由的網路區域、網站和子網。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9a7c02a7299029ec267011f962880884d1d9f4d7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999328"
---
# <a name="configure-network-settings-for-location-based-routing"></a>設定依位置路由的網路設定

本文說明如何設定Location-Based路由的網路設定。 如果您尚未這麼做，請閱讀 [規劃Location-Based直接路由的路由](location-based-routing-plan.md) ，以在設定網路設定之前檢閱您需要採取的其他步驟。

在組織中部署直接路由之後，接下來的步驟是建立及設定網路區域、網路網站和網路子網。

## <a name="define-network-regions"></a>定義網路區域

網路區域包含一組網路網站，並且跨多個地理區域互連網路的各個部分。 如需如何設定網路區域的步驟，請移至 [管理 Teams 雲端功能的網路拓撲](manage-your-network-topology.md)。

## <a name="define-network-sites"></a>定義網路網站

網路網站代表貴組織有實體場地的位置，例如辦公室、一組建築物或校園。 您必須將拓撲中的每個網路網站與網路區域建立關聯。 如需如何設定網路網站的步驟，請參閱 [管理 Teams 雲端功能的網路拓撲](manage-your-network-topology.md)。

Location-Based路由的最佳做法是為每個具有唯一公用交換電話網 (PSTN) 連線的位置建立個別的網站。 您可以建立啟用Location-Based路由的網站，或是未啟用Location-Based路由的網站。 例如，您可能會想要建立一個未啟用Location-Based路由的網站，允許啟用Location-Based路由的使用者在漫遊至該網站時撥打 PSTN 電話。

## <a name="define-network-subnets"></a>定義網路子網

每個子網都必須與特定網路網站相關聯。 您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。 如需如何設定網路子網的步驟，請參閱  [管理 Teams 中雲端功能的網路拓撲](manage-your-network-topology.md)。

對於Location-Based路由，必須定義 Teams 端點可連線到網路之位置的 IP 子網，並與定義的網路建立關聯，以強制執行付費略過。 此子閘道聯可讓Location-Based路由在地理位置找出端點，以判斷是否應該允許指定的 PSTN 通話。 支援 IPv6 和 IPv4 子網。 判斷 Teams 端點是否位於網站時，Location-Based路由會先檢查符合的 IPv6 位址。 如果 IPv6 位址不存在，Location-Based路由檢查 IPv4 位址。

## <a name="define-trusted-ip-addresses-external-subnets"></a>定義外部子網 (受信任的 IP 位址) 

信任的 IP 位址是商業網路的網際網路外部 IP 位址，用來判斷使用者的端點是否在公司網路內。 如需如何設定受信任 IP 位址的步驟，請參閱 [管理 Teams 雲端功能的網路拓撲](manage-your-network-topology.md)。

如果使用者的外部 IP 位址符合信任 IP 位址清單中的 IP 位址，Location-Based路由檢查以判斷使用者端點所在的內部子網。 如果使用者的外部 IP 位址與信任 IP 位址清單中所定義的任何 IP 位址不符，端點會分類為位於未知的位置，且任何 PSTN 來電來自啟用Location-Based路由的使用者，都會遭到封鎖。

## <a name="next-steps"></a>後續步驟

移至 [啟用直接路由Location-Based路由](location-based-routing-enable.md)。

## <a name="related-topics"></a>相關主題

- [Teams 中雲端語音功能的網路設定](cloud-voice-network-settings.md)
