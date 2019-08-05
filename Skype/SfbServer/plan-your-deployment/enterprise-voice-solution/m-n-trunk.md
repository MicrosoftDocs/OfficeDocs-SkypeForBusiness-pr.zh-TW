---
title: 商務用 Skype Server 中的 MN 幹線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: 商務用 Skype Server Enterprise Voice 支援中繼伺服器與元件 (例如 PSTN 閘道、會話邊界控制器和 IP PBX) 之間的 M:N 中繼。
ms.openlocfilehash: 24be86c3b174eff70632ddd85a71b5ee7016b990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187639"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>商務用 Skype Server 中的 M:N 幹線
 
商務用 Skype Server Enterprise Voice 支援中繼伺服器與元件 (例如 PSTN 閘道、會話邊界控制器和 IP PBX) 之間的 M:N 中繼。
  
商務用 Skype 伺服器支援從先前版本進行呼叫路由的主幹定義, 提供更大的彈性。 主幹是在中繼伺服器與偵聽埠號碼之間的邏輯關聯, 並具有閘道和偵聽埠號碼。 這表示以下幾點: 中繼伺服器可以有多個 trunks 至同一個閘道;中繼伺服器可以有多個 trunks 至不同的閘道;相反地, 閘道可以有多個 trunks 給不同的中繼伺服器。
  
您仍必須在使用 [拓撲建立器] adde 拓撲結構時建立根主幹。 指定的中繼伺服器可以處理的閘道數目, 取決於高峰期繁忙期間內伺服器的處理能力。 如果您在硬體上部署超過商務用 Skype Server 最低硬體需求的中繼伺服器, 請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)中所述, 然後估計有多少作用中非旁路呼叫獨立的中繼伺服器可以處理大約1000通話。 當您在硬體上部署這些規範時, 轉送伺服器應該會執行轉碼, 但仍會傳送多個閘道的呼叫, 即使閘道不支援媒體旁路也一樣。
  
定義通話路線時, 您可以指定與該路線相關聯的 trunks, 但不會指定哪些中繼伺服器與該路由相關聯。 相反地, 您可以使用拓撲建立器, 將 trunks 與中繼伺服器產生關聯。 換句話說, 路由會決定要使用哪個幹線來進行通話, 然後再將與該主幹相關的中繼伺服器傳送給該通話。
  
您可以將中繼伺服器部署成一個池;此池可以與前端池 collocated, 也可以將它部署為獨立的池。 當使用前端池 collocated 轉送伺服器時, 池子大小最多可以是 12 (註冊機構池大小的限制)。 總之, 這些新功能可提高中繼伺服器的可靠性和部署靈活性, 但在下列對等實體中需要相關的功能:
  
- **PSTN 閘道。** 商務用 Skype Server 合格閘道必須實現 DNS 負載平衡, 這可讓合格的公用交換電話網絡 (PSTN) 閘道充當一個中繼伺服器池的負載平衡器, 進而在整個池中進行負載平衡呼叫.
    
- **會話邊界控制器。** 對 SIP 主幹而言, 對等實體是網際網路電話服務提供者的會話邊界控制器 (SBC)。 從中繼伺服器池到 SBC 的方向, SBC 可以從池中的任何中繼伺服器接收連線。 從 SBC 到該池的方向, 流量可以傳送到池中的任何中繼伺服器。 完成這項工作的其中一個方法是透過 DNS 負載平衡 (如果服務提供者和 SBC 支援)。 另一種方法是為服務提供者提供池中所有中繼伺服器的 IP 位址, 而服務提供者將在其 SBC 中將這些資源設定為每個中繼伺服器的個別 SIP 幹線。 然後服務提供者就會處理自己伺服器的負載平衡。 並非所有服務提供者或 SBCs 都可能支援這些功能。 此外, 服務提供者可能會針對這項功能收取額外費用。 一般來說, SBC 的每個 SIP 幹線都會產生每月費用。
    
- **IP-PBX。** 從中繼伺服器池到 IP PBX SIP 終止方向, IP PBX 可以從池中的任何中繼伺服器接收連線。 從 IP PBX 到池中的方向, 流量可以傳送到池中的任何中繼伺服器。 因為大部分的 IP Pbx 不支援 DNS 負載平衡, 所以建議您從 IP PBX 將個別的直接 SIP 連線定義到池中的每個轉送伺服器。 然後, IP PBX 會透過將流量散佈到幹線群組來處理自己的負載平衡。 假設 [幹線] 群組在 IP-PBX 中有一致的一組路由規則。 特定的 IP PBX 是否支援此幹線群組概念, 以及它與 IP PBX 本身的冗余和群集架構的交集, 必須先加以決定, 才能判斷出轉送伺服器叢集是否可以正確地與 IP PBX 進行互動。
    
中繼伺服器池必須具有與其互動之對等閘道的統一視圖。 這表示該資源的所有成員都能從 [配置] 存放區存取相同的對等閘道定義, 而且與撥出通話一樣很可能與它互動。 因此, 您無法分割池, 因此有些中繼伺服器只會與特定閘道對等的撥出電話進行通訊。 如果這類分段是必要的, 則必須使用單獨的中繼伺服器池。 例如, 如果 PSTN 閘道、SIP trunks 或 IP-Pbx 中的相關功能與某個池互動 (如本主題前面所述), 就會發生這種情況。
  
特定 PSTN 閘道、IP PBX 或 SIP 中繼對等可以傳送到多個中繼伺服器或 trunks。 特定的中繼伺服器池可以控制的閘道數目, 視使用媒體旁路的呼叫數量而定。 如果大量的呼叫使用媒體旁路, 則池中的中繼伺服器可以處理更多的呼叫, 因為只需要傳輸圖層處理。 
  

