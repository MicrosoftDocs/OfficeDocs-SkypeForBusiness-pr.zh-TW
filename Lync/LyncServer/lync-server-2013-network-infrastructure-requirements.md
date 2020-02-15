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
ms.openlocfilehash: 93e68a7aecd8c1390993d25d23668813cad0abbf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的網路基礎結構需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-18_

Lync Server 2013 拓撲中的每部伺服器的網路介面卡必須支援每秒 (Gbps)，至少有 1 gb。 一般而言，您應該連接 Lync Server 拓撲中使用低延遲以及高頻寬本機區域網路 (LAN) 內的所有伺服器角色。 LAN 的大小視拓撲的大小而定：

  - 在 Standard Edition 拓撲中，伺服器應位於支援 1 Gbps 乙太網路或相等的網路中。

  - 在前端集區拓撲中，大部分的伺服器應位於支援 1 Gbps 以上，特別是在支援音訊/視訊網路中 (A / V) 會議和應用程式共用。

針對公用交換電話網路 (PSTN) 整合，您可以使用 T1/E1 線路或 SIP 主幹來整合。

<div>

## <a name="audiovideo-network-requirements"></a>視訊/音訊網路需求

網路需求音訊/視訊 (A / V) 中的 Lync Server 部署包括下列項目：

  - 如果您要部署單一 Edge Server 或使用 DNS 負載平衡 Edge 集區，您可以將外部防火牆設定為 nat。 內部防火牆不可設定為 NAT。 如需這些需求的詳細資訊，請參閱[決定外部 A / V 防火牆和連接埠需求 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)中規劃文件。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您有 Edge 集區，而且所使用的硬體負載平衡器，您必須在每個 Edge Server 上使用公用 IP 位址，而且無法在您的 NAT 裝置 （例如防火牆或會 NAT inbou 其他基礎結構裝置的伺服器或集區使用 NATnd 或輸出流量）。 如需詳細資訊，請參閱<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">連接埠摘要-調整式合併邊緣搭配硬體負載平衡器 Lync Server 2013 中</A>中的 Planning for External User Access > 文件。

    
    </div>

  - 如果您的組織使用的是服務品質 (QoS) 基礎結構，則媒體子系統將會設計成配合此現有基礎結構運作。

  - 如果您使用網際網路通訊協定安全性 (IPsec)，建議您針對 A/V 流量所使用的連接埠範圍停用 IPsec。 如需詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的 IPsec 例外狀況](lync-server-2013-ipsec-exceptions.md)。

為了確保最佳的媒體品質，請執行下列作業：

  - 佈建您的網路連結，以支援每個音訊資料流具備 65 Kbps 的傳輸量與每個視訊資料流具備 500 Kbps 的傳輸量 (啟用時在尖峰時段的速率)。雙向音訊或視訊工作階段包含兩種資料流。

  - 若要應付經過一段時間未預期尖峰流量上方此層級和增加的流量，Lync Server 媒體端點可以適用於不同的條件和網路支援負載的三倍輸送量 （請參閱前一段） 的音訊和視訊，當您仍保留可接受的品質。 但是，請勿認為這項調整功能可以支援未佈建齊全的網路。 在 [佈建網路，就會減少 Lync Server 的媒體端點以動態方式處理不同網路狀況 （例如，暫存高封包遺失） 的能力。

  - 對於佈建成本與困難度非常高的網路連結來說，您可能不得不考慮以較低的流量為主進行佈建。 在此案例中，可讓 Lync Server 的媒體端點的彈性吸收流量磁碟區，並犧牲某些減少的聲音品質的尖峰流量層級之間的差異。 同時，也會減少用來吸收突發性流量暴增的空間。

  - 對於無法在短時間內正確佈建的連結來說 (例如 WAN 連結品質非常差的網站)，請考慮針對某些使用者停用視訊功能。

  - 佈建網路時，請確保在尖峰用量時段保持最高 150 ms 的端對端延遲水準。 延遲是減少 Lync Server 媒體元件，不能有一個網路減損小，很重要來找出並消除弱式的點。

  - 對於執行防毒軟體的伺服器，包括所有伺服器執行 Lync Server 例外狀況清單中，以達到最佳效能和音訊品質。

</div>

<div>

## <a name="conferencing-network-requirements"></a>會議網路需求

用來從網際網路資訊服務 (IIS) 伺服器下載會議內容的頻寬需視上傳的內容大小而定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

