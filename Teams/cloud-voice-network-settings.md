---
title: 雲端語音功能的網路設定
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解您必須為直接路由和增強的緊急服務Location-Based路由所必須設定的網路設定。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2165ea1e4e9732f0e840b4f0949b230f5243121d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769941"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>雲端語音功能的網路設定Microsoft Teams

瞭解網路區域、網路網站、網路子網和受信任的 IP 位址。 這些條款和概念會用於我們的雲端語音檔，用於[](location-based-routing-plan.md)直接路由和動態緊急電話的定位式[路由](configure-dynamic-emergency-calling.md)。 如果您要在組織中部署這些雲端功能，您必須設定網路設定，以在 Microsoft Teams。

本文提供路由和動態緊急Location-Based常見的網路設定概觀。 根據您部署的雲端語音功能，您可以設定部分或所有設定。 若要瞭解如何設定這些設定的步驟，請參閱在 Teams 中管理雲端功能[的網路拓撲](manage-your-network-topology.md)。

> [!NOTE]
> 網路設定的任何特定功能需求會記錄在該功能的設定主題中。

## <a name="network-region"></a>網路區域

網路區域包含網路網站的集合。 它會跨多個地理區域連接網路的各個部分。 例如，如果貴組織有許多位於印度的網站，您可以選擇將「印度」指定為網路區域。 每個網路網站都必須與網路區域相關聯。

相同的網路區域會由直接路由Location-Based路由和增強的緊急服務共用。 如果您已經為一項功能建立網路區域，則不需要為另一項功能建立新網路區域。

## <a name="network-site"></a>網路網站

網路網站代表貴組織有實體場地的位置，例如辦公室、一組建築物或校園。 網路網站定義為 IP 子網的集合。 每個網路網站都必須與網路區域相關聯。

您也可以使用網路網站啟用及設定緊急通話。

## <a name="network-subnet"></a>網路子網

每個子網都必須與特定的網路網站相關聯。 用戶端的位置是根據網路子網和相關聯的網路網站所決定。 您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。

子網資訊會用來判斷啟動新會話時端點所在的網路網站。 當會話內每一方的位置為已知時，雲端語音功能可以運用該資訊來決定如何處理通話設定或路由。

針對每個網路網站，請與您的網路系統管理員合作，決定指派給每個網路網站的 IP 子網。 例如，北美地區的紐約網站可以指派下列 IP 子網：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果一般在密地安地亞工作的 Bob 前往紐約辦公室接受訓練，開啟電腦並連接到網路，他的電腦就會在四個為紐約配置的範圍之一取得 IP 位址，例如 172.29.80.103。

## <a name="trusted-ip-address"></a>信任的 IP 位址

信任的 IP 位址是商業網路的網際網路外部 IP 位址。 他們先判斷使用者的端點是否位於公司網路內，然後再檢查特定網站相符專案。

如果使用者的外部 IP 位址符合信任 IP 位址清單中的 IP 位址，雲端語音功能會檢查以判斷使用者端點所在的內部子網。 您可以根據 IPv4 或 IPv6 IP 位址進行比對，並視要送至網路設定之 IP 封包的格式而定。  (如果公用 IP 位址同時有 IPv4 和 IPv6，您必須同時將兩者新增為信任的 IP 位址。) 

如果使用者的外部 IP 位址與信任 IP 位址清單中的 IP 位址不相符，端點會分類為位於未知位置。

> [!Important]
> 修改來自用戶端之來源 IP 位址的雲端 Proxy 服務部署不支援網路設定Teams檢查。
