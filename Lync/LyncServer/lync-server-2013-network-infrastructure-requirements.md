---
title: Lync Server 2013 網路基礎結構需求
description: Lync Server 2013 網路基礎結構需求。
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
ms.openlocfilehash: 6f7ff21c2f936ef8e048f6831d55408994055400
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561499"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="3be52-103">Lync Server 2013 的網路基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="3be52-103">Network infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3be52-104">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3be52-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3be52-105">Lync Server 2013 拓撲中每一部伺服器的網路介面卡都必須至少支援1十億位元/秒 (Gbps) 。</span><span class="sxs-lookup"><span data-stu-id="3be52-105">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="3be52-106">一般而言，您應該使用低延遲和高頻寬的局域網 (LAN) ，在 Lync Server 拓撲中連線所有伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="3be52-106">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="3be52-107">LAN 的大小視拓撲的大小而定：</span><span class="sxs-lookup"><span data-stu-id="3be52-107">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="3be52-108">在 Standard Edition 拓撲中，伺服器應位於支援 1 Gbps 乙太網或對等的網路上。</span><span class="sxs-lookup"><span data-stu-id="3be52-108">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="3be52-109">在前端集區拓撲中，大部分的伺服器應位於支援 1 Gbps 以上的網路中，尤其是在支援音訊/視頻 (A/V) 會議和應用程式共用時。</span><span class="sxs-lookup"><span data-stu-id="3be52-109">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="3be52-110">針對公用交換電話網路 (PSTN) 整合，您可以使用 T1/E1 線路或 SIP 主幹來整合。</span><span class="sxs-lookup"><span data-stu-id="3be52-110">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="3be52-111">視訊/音訊網路需求</span><span class="sxs-lookup"><span data-stu-id="3be52-111">Audio/Video Network Requirements</span></span>

<span data-ttu-id="3be52-112">在 Lync Server 部署中 (A/V) 音訊/視頻的網路需求如下：</span><span class="sxs-lookup"><span data-stu-id="3be52-112">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="3be52-113">若要使用 DNS 負載平衡部署單一 Edge Server 或 Edge 集區，您可以將外部防火牆設定為 NAT。</span><span class="sxs-lookup"><span data-stu-id="3be52-113">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="3be52-114">內部防火牆不可設定為 NAT。</span><span class="sxs-lookup"><span data-stu-id="3be52-114">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="3be52-115">如需這些需求的詳細資訊，請參閱規劃檔中的 [決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="3be52-115">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3be52-116">如果您有 Edge 集區，而且正在使用硬體負載平衡器，則必須在每一部 Edge Server 上使用公用 IP 位址，而且您無法在 NAT 裝置上使用 NAT 來進行伺服器或集區 (例如，防火牆或其他會 NAT 輸入或輸出流量) 的基礎結構裝置。</span><span class="sxs-lookup"><span data-stu-id="3be52-116">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="3be52-117">如需詳細資訊，請參閱規劃外部使用者存取檔中的 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">埠摘要-調整式合併 edge （Lync Server 2013 中的硬體負載平衡</A> 器）。</span><span class="sxs-lookup"><span data-stu-id="3be52-117">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="3be52-118">如果您的組織使用的是服務品質 (QoS) 基礎結構，則媒體子系統將會設計成配合此現有基礎結構運作。</span><span class="sxs-lookup"><span data-stu-id="3be52-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="3be52-119">如果您使用網際網路通訊協定安全性 (IPsec)，建議您針對 A/V 流量所使用的連接埠範圍停用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="3be52-119">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="3be52-120">如需詳細資訊，請參閱規劃檔中的 [IPsec 的 Lync Server 2013](lync-server-2013-ipsec-exceptions.md) 中的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="3be52-120">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="3be52-121">為了確保最佳的媒體品質，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3be52-121">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="3be52-p105">佈建您的網路連結，以支援每個音訊資料流具備 65 Kbps 的傳輸量與每個視訊資料流具備 500 Kbps 的傳輸量 (啟用時在尖峰時段的速率)。雙向音訊或視訊工作階段包含兩種資料流。</span><span class="sxs-lookup"><span data-stu-id="3be52-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="3be52-124">為了處理此層級以上流量中的意外峰值，並隨著時間增加使用量，Lync Server 媒體端點可以調整不同的網路狀況，並支援負載三倍的流量 (請查看先前段落) 的音訊和影片，但仍然保留可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="3be52-124">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="3be52-125">但是，請勿認為這項調整功能可以支援未佈建齊全的網路。</span><span class="sxs-lookup"><span data-stu-id="3be52-125">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="3be52-126">在未布建的網路中，Lync Server 媒體端點可以動態處理不同網路狀況的功能 (例如，暫時的封包遺失) 會變少。</span><span class="sxs-lookup"><span data-stu-id="3be52-126">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="3be52-127">對於佈建成本與困難度非常高的網路連結來說，您可能不得不考慮以較低的流量為主進行佈建。</span><span class="sxs-lookup"><span data-stu-id="3be52-127">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="3be52-128">在此案例中，請讓 Lync Server 媒體端點的彈性吸收流量流量與流量峰值流量層級之間的差異，以降低語音品質的成本。</span><span class="sxs-lookup"><span data-stu-id="3be52-128">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="3be52-129">同時，也會減少用來吸收突發性流量暴增的空間。</span><span class="sxs-lookup"><span data-stu-id="3be52-129">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="3be52-130">對於無法在短時間內正確佈建的連結來說 (例如 WAN 連結品質非常差的網站)，請考慮針對某些使用者停用視訊功能。</span><span class="sxs-lookup"><span data-stu-id="3be52-130">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="3be52-131">佈建網路時，請確保在尖峰用量時段保持最高 150 ms 的端對端延遲水準。</span><span class="sxs-lookup"><span data-stu-id="3be52-131">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="3be52-132">延遲是 Lync Server 媒體元件無法降低的網路障礙，所以尋找並消除薄弱點很重要。</span><span class="sxs-lookup"><span data-stu-id="3be52-132">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="3be52-133">若為執行防毒軟體的伺服器，請在例外狀況清單中，加入所有執行 Lync Server 的伺服器，以提供最佳效能及音訊品質。</span><span class="sxs-lookup"><span data-stu-id="3be52-133">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="3be52-134">會議網路需求</span><span class="sxs-lookup"><span data-stu-id="3be52-134">Conferencing Network Requirements</span></span>

<span data-ttu-id="3be52-135">從網際網路資訊服務 (IIS) 伺服器下載會議內容所用的頻寬，取決於所上傳內容的大小。</span><span class="sxs-lookup"><span data-stu-id="3be52-135">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

