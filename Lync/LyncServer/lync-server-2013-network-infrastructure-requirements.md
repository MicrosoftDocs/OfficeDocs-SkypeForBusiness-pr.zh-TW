---
title: Lync Server 2013 網路基礎結構需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcded907075b6587eb62ea8b6b76566c4f29ac87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的網路基礎結構需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

Lync Server 2013 拓撲中每個伺服器的網路介面卡，必須至少支援1十億位元/秒（Gbps）。 一般來說，您應該使用低延遲和高頻寬的局域網（LAN），連線 Lync Server 拓撲中的所有伺服器角色。 局域網的大小取決於拓撲大小：

  - 在標準版拓撲結構中，伺服器應該位於支援 1 Gbps 乙太網或對等的網路中。

  - 在前端池拓撲中，大部分的伺服器都應該位於支援超過 1 Gbps 的網路中，特別是支援音訊/視頻（A/V）會議與應用程式共用時。

針對公用交換電話網絡（PSTN）整合，您可以使用 T1/E1 線路或 SIP 中繼整合。

<div>

## <a name="audiovideo-network-requirements"></a>音訊/視頻網路需求

Lync Server 部署中音訊/視頻（A/V）的網路需求包括下列各項：

  - 如果您是使用 DNS 負載平衡部署單一邊緣伺服器或邊緣池，您可以將外部防火牆設定為 NAT。 您無法將內部防火牆設定為 NAT。 如需這些需求的詳細資訊，請參閱在規劃檔中針對[Lync Server 2013 判斷外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您有邊緣池，且正在使用硬體負載平衡器，則您必須在每一台邊緣伺服器上使用公用 IP 位址，而且您無法在您的 NAT 裝置上使用 NAT （例如，防火牆或其他可能是 NAT inbou 的基礎結構裝置）nd 或呼出流量）。 如需詳細資訊，請參閱在規劃外部使用者存取檔中的<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的 [埠摘要] 與硬體負載平衡</A>器。

    
    </div>

  - 如果您的組織使用的是服務品質（QoS）基礎結構，媒體子系統就是設計來在這個現有的基礎結構中運作。

  - 如果您使用的是網際網路通訊協定安全性（IPsec），建議您在用於 A/V 流量的埠範圍上停用 IPsec。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)狀況。

若要確保最佳的媒體質量，請執行下列動作：

  - 您可以在高峰使用量期間啟用，將您的網路連結設定為支援每秒 65 kbps 的輸送量，以及每個視頻資料流程的 500 Kbps。 雙向音訊或視頻會話是由兩個數據流所組成。

  - 為了應對此等級以上流量中的意外峰值並隨著時間增加使用量，Lync Server 媒體端點可以適應不同的網路狀況，並支援載入三倍于音訊和視頻的輸送量（請參閱前一段），同時仍保留可接受的品質。 不過，請勿假設這種適應性支援的是預配網路。 在預配的網路中，Lync Server 媒體端點能動態處理不同網路狀況（例如，暫時大資料包遺失）的能力會減少。

  - 針對配備極其昂貴且困難的網路連結，您可能需要考慮針對較低的流量進行置備。 在這種情況下，請讓 Lync Server 媒體端點的 elasticity 佔用流量與峰值流量層級之間的差異，同時降低語音品質。 此外，預留空間也會減少，但仍可吸收通信量突然高峰的情況。

  - 針對短期內無法正確提供的連結（例如，WAN 連結較差的網站），請考慮針對特定使用者停用影片。

  - 您可以在 [峰值負載] 底下，將您的網路設定為確保最大150的端對端延遲（毫秒）。 延遲是 Lync Server 媒體元件無法減少的一個網路障礙，請務必找出並消除薄弱點。

  - 針對執行防毒軟體的伺服器，請在例外清單中包含所有執行 Lync Server 的伺服器，以提供最佳效能和音訊品質。

</div>

<div>

## <a name="conferencing-network-requirements"></a>會議網路需求

從網際網路資訊服務（IIS）伺服器下載會議內容所用的頻寬，取決於上傳的內容大小。

</div>

</div>

<span> </span>

</div>

</div>

</div>

