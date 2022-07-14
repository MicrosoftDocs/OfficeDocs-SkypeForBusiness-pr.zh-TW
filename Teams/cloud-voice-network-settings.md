---
title: 雲端語音功能的網路設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解您必須針對直接路由Location-Based路由和增強型緊急服務所設定的網路設定。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 49709c2c3cc8816b404c88970c6ec916470f200e
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790148"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft Teams 中雲端語音功能的網路設定

瞭解網路區域、網路網站、網路子網和信任的 IP 位址。 這些字詞和概念會在我們的雲端語音檔中使用， [用於直接路由](location-based-routing-plan.md) 和 [動態緊急通話](configure-dynamic-emergency-calling.md)的定位式路由。 如果您要在組織中部署這些雲端功能，您必須設定網路設定，才能搭配 Microsoft Teams 中的這些功能使用。

本文提供您Location-Based路由和動態緊急電話常見之網路設定的概觀。 視您要部署的雲端語音功能而定，您可以設定部分或所有這些設定。 如需如何設定這些設定的步驟，請參閱 [管理 Teams 雲端功能的網路拓撲](manage-your-network-topology.md)。

> [!NOTE]
> 網路設定的任何功能特定需求都會記錄在該功能的組態主題中。

## <a name="network-region"></a>網路區域

網路區域包含一組網路網站。 它會跨多個地理區域相互連接網路的各個部分。 例如，如果您的組織有許多位於印度的網站，您可以選擇將「印度」指定為網路區域。 每個網路網站都必須與網路區域建立關聯。

相同的網路區域是由Location-Based直接路由的路由和增強型緊急服務共用。 如果您已為其中一項功能建立網路區域，則不需要為另一項功能建立新的網路區域。

## <a name="network-site"></a>網路網站

網路網站代表貴組織有實體場地的位置，例如辦公室、一組建築物或校園。 網路網站定義為 IP 子網的集合。 每個網路網站都必須與網路區域建立關聯。

您也可以使用網路網站來啟用和設定緊急通話。

## <a name="network-subnet"></a>網路子網

每個子網都必須與特定網路網站相關聯。 用戶端的位置是根據網路子網和關聯的網路網站來判斷。 您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。

子網路資訊是用來決定啟動新會話時端點所在的網路網站。 當已知各方在會話中的位置時，雲端語音功能可以套用該資訊，以決定如何處理通話設定或路由。

針對每個網路網站，請與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。 例如，北美洲地區的紐約網站可以指派下列 IP 子網：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果經常在紐約市工作的百勝前往紐約辦公室接受訓練，請開啟他的電腦並聯機到網路，他的電腦將會在四個配置給紐約的範圍中取得一個 IP 位址，例如 172.29.80.103。

## <a name="trusted-ip-address"></a>受信任的 IP 位址

信任的 IP 位址是商業網路的網際網路外部 IP 位址。 在檢查特定網站相符專案之前，他們會先判斷使用者的端點是否在公司網路內。

如果使用者的外部 IP 位址符合信任 IP 位址清單中的 IP 位址，雲端語音功能會檢查以判斷使用者端點所在的內部子網。 可以比對 IPv4 或 IPv6 IP 位址，且取決於傳送到網路設定的 IP 封包格式。  (如果公用 IP 位址同時具備 IPv4 和 IPv6，您必須將兩者同時新增為信任的 IP 位址。) 

如果使用者的外部 IP 位址與信任 IP 位址清單中的 IP 位址不符，端點會分類為位於未知的位置。

> [!Important]
> 修改 Teams 用戶端來源 IP 位址的雲端 Proxy 服務部署不支援網路設定設定查閱。
