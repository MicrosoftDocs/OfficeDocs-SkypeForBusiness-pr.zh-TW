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
ms.openlocfilehash: 338e2387b08898694bd621e220d7f889a8d25e0a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505540"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的網路基礎結構需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

Lync Server 2013 拓撲中每一部伺服器的網路介面卡都必須至少支援1十億位元/秒 (Gbps) 。 一般而言，您應該使用低延遲和高頻寬的局域網 (LAN) ，在 Lync Server 拓撲中連線所有伺服器角色。 LAN 的大小視拓撲的大小而定：

  - 在 Standard Edition 拓撲中，伺服器應位於支援 1 Gbps 乙太網或對等的網路上。

  - 在前端集區拓撲中，大部分的伺服器應位於支援 1 Gbps 以上的網路中，尤其是在支援音訊/視頻 (A/V) 會議和應用程式共用時。

針對公用交換電話網路 (PSTN) 整合，您可以使用 T1/E1 線路或 SIP 主幹來整合。

<div>

## <a name="audiovideo-network-requirements"></a>視訊/音訊網路需求

在 Lync Server 部署中 (A/V) 音訊/視頻的網路需求如下：

  - 若要使用 DNS 負載平衡部署單一 Edge Server 或 Edge 集區，您可以將外部防火牆設定為 NAT。 內部防火牆不可設定為 NAT。 如需這些需求的詳細資訊，請參閱規劃檔中的 [決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您有 Edge 集區，而且正在使用硬體負載平衡器，則必須在每一部 Edge Server 上使用公用 IP 位址，而且您無法在 NAT 裝置上使用 NAT 來進行伺服器或集區 (例如，防火牆或其他會 NAT 輸入或輸出流量) 的基礎結構裝置。 如需詳細資訊，請參閱規劃外部使用者存取檔中的 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">埠摘要-調整式合併 edge （Lync Server 2013 中的硬體負載平衡</A> 器）。

    
    </div>

  - 如果您的組織使用的是服務品質 (QoS) 基礎結構，則媒體子系統將會設計成配合此現有基礎結構運作。

  - 如果您使用網際網路通訊協定安全性 (IPsec)，建議您針對 A/V 流量所使用的連接埠範圍停用 IPsec。 如需詳細資訊，請參閱規劃檔中的 [IPsec 的 Lync Server 2013](lync-server-2013-ipsec-exceptions.md) 中的例外狀況。

為了確保最佳的媒體品質，請執行下列作業：

  - 佈建您的網路連結，以支援每個音訊資料流具備 65 Kbps 的傳輸量與每個視訊資料流具備 500 Kbps 的傳輸量 (啟用時在尖峰時段的速率)。雙向音訊或視訊工作階段包含兩種資料流。

  - 為了處理此層級以上流量中的意外峰值，並隨著時間增加使用量，Lync Server 媒體端點可以調整不同的網路狀況，並支援負載三倍的流量 (請查看先前段落) 的音訊和影片，但仍然保留可接受的品質。 但是，請勿認為這項調整功能可以支援未佈建齊全的網路。 在未布建的網路中，Lync Server 媒體端點可以動態處理不同網路狀況的功能 (例如，暫時的封包遺失) 會變少。

  - 對於佈建成本與困難度非常高的網路連結來說，您可能不得不考慮以較低的流量為主進行佈建。 在此案例中，請讓 Lync Server 媒體端點的彈性吸收流量流量與流量峰值流量層級之間的差異，以降低語音品質的成本。 同時，也會減少用來吸收突發性流量暴增的空間。

  - 對於無法在短時間內正確佈建的連結來說 (例如 WAN 連結品質非常差的網站)，請考慮針對某些使用者停用視訊功能。

  - 佈建網路時，請確保在尖峰用量時段保持最高 150 ms 的端對端延遲水準。 延遲是 Lync Server 媒體元件無法降低的網路障礙，所以尋找並消除薄弱點很重要。

  - 若為執行防毒軟體的伺服器，請在例外狀況清單中，加入所有執行 Lync Server 的伺服器，以提供最佳效能及音訊品質。

</div>

<div>

## <a name="conferencing-network-requirements"></a>會議網路需求

從網際網路資訊服務 (IIS) 伺服器下載會議內容所用的頻寬，取決於所上傳內容的大小。

</div>

</div>

<span> </span>

</div>

</div>

</div>

