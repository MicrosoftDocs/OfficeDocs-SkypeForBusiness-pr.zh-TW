---
title: 雲端語音功能的網路設定
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解您必須針對直接路由及增強緊急服務的位置路由設定的網路設定。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bc2694760e93579a78cb849cc054d70a65431724
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139062"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft 團隊中雲端語音功能的網路設定

瞭解網路區域、網路網站、網路子網和信任的 IP 位址。 這些條款與概念在整個雲端語音檔中都是用來進行[直接路由](location-based-routing-plan.md)和[動態緊急通話](configure-dynamic-emergency-calling.md)的以位置為基礎的路由。 如果您要在組織中部署這些雲端功能，您必須設定網路設定，以便與 Microsoft 團隊中的這些功能搭配使用。

本文將為您概述位置式路由和動態緊急通話中常見的網路設定。 視您部署的雲端語音功能和功能而定，您可以設定部分或所有的設定。 如需如何設定這些設定的步驟，請參閱在[團隊中管理雲端功能的網路拓撲](manage-your-network-topology.md)。

> [!NOTE]
> 此功能的設定主題中記錄了網路設定的任何特定功能需求。

## <a name="network-region"></a>網路區域

網路區域包含一個網路網站集合。 它跨多個地理區域相互互連網路的各個部分。 例如，如果您的組織有許多位於印度的網站，您可以選擇將 "印度" 指定為網路區域。 每個網路網站都必須與一個網路區域建立關聯。

相同的網路區域是由直接路由及增強的緊急服務的位置路由所共用。 如果您已經為一個功能建立了網路區域，您就不需要為其他功能建立新的網路區域。

## <a name="network-site"></a>網路網站

網路網站代表貴組織有實體場所（例如辦公室、一組建築物或校園）的位置。 網路網站定義為 IP 子網的集合。 每個網路網站都必須與一個網路區域建立關聯。

您也可以使用網路網站來啟用和設定緊急通話。

## <a name="network-subnet"></a>網路子網上

每個子網都必須與特定的網路網站相關聯。 用戶端的位置是根據網路子網和相關的網路網站來決定。 您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。

子網資訊可用來決定啟動新的會話時，端點所在的網路網站。 當會話中每一方的位置已知時，雲端語音功能可以套用該資訊來決定如何處理撥號設定或路由。

針對每個網路網站，請與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。 例如，您可以將下列 IP 子網指派給北美地區的紐約網站： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果王俊元是在底特律中使用，請前往紐約 office 進行訓練，然後開啟他的電腦並聯機到網路上，他的電腦將會取得 IP 位址，在為紐約所指派的四個範圍其中之一，例如172.29.80.103。

## <a name="trusted-ip-address"></a>信任的 IP 位址

[信任的 IP 位址] 是商業網路的網際網路外部 IP 位址。 在檢查特定網站相符前，他們會判斷使用者的端點是否在公司網路內。

如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中的 IP 位址相符，雲端語音功能會進行檢查，以判斷使用者端點所在的內部子網。 您可以針對 IPv4 或 IPv6 IP 位址進行相符，並視傳送至網路設定的 IP 資料包格式而定。 （如果公用 IP 位址同時具有 IPv4 和 IPv6，您必須將兩者都新增為信任的 IP 位址。）

如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中的 IP 位址不相符，該端點會分類為未知位置。
