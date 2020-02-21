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
ms.openlocfilehash: 3571dba317998af4fe19f7d2dfd1677d3691f278
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="439f4-102">Lync Server 2013 的網路基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="439f4-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="439f4-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="439f4-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="439f4-104">Lync Server 2013 拓撲中的每部伺服器的網路介面卡必須支援每秒 (Gbps)，至少有 1 gb。</span><span class="sxs-lookup"><span data-stu-id="439f4-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="439f4-105">一般而言，您應該連接 Lync Server 拓撲中使用低延遲以及高頻寬本機區域網路 (LAN) 內的所有伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="439f4-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="439f4-106">LAN 的大小視拓撲的大小而定：</span><span class="sxs-lookup"><span data-stu-id="439f4-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="439f4-107">在 Standard Edition 拓撲中，伺服器應位於支援 1 Gbps 乙太網路或相等的網路中。</span><span class="sxs-lookup"><span data-stu-id="439f4-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="439f4-108">在前端集區拓撲中，大部分的伺服器應位於支援 1 Gbps 以上，特別是在支援音訊/視訊網路中 (A / V) 會議和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="439f4-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="439f4-109">針對公用交換電話網路 (PSTN) 整合，您可以使用 T1/E1 線路或 SIP 主幹來整合。</span><span class="sxs-lookup"><span data-stu-id="439f4-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="439f4-110">視訊/音訊網路需求</span><span class="sxs-lookup"><span data-stu-id="439f4-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="439f4-111">網路需求音訊/視訊 (A / V) 中的 Lync Server 部署包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="439f4-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="439f4-112">如果您要部署單一 Edge Server 或使用 DNS 負載平衡 Edge 集區，您可以將外部防火牆設定為 nat。</span><span class="sxs-lookup"><span data-stu-id="439f4-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="439f4-113">內部防火牆不可設定為 NAT。</span><span class="sxs-lookup"><span data-stu-id="439f4-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="439f4-114">如需這些需求的詳細資訊，請參閱[決定外部 A / V 防火牆和連接埠需求 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="439f4-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="439f4-115">如果您有 Edge 集區，而且所使用的硬體負載平衡器，您必須在每個 Edge Server 上使用公用 IP 位址，而且無法在您的 NAT 裝置 （例如防火牆或會 NAT inbou 其他基礎結構裝置的伺服器或集區使用 NATnd 或輸出流量）。</span><span class="sxs-lookup"><span data-stu-id="439f4-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="439f4-116">如需詳細資訊，請參閱<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">連接埠摘要-調整式合併邊緣搭配硬體負載平衡器 Lync Server 2013 中</A>中的 Planning for External User Access > 文件。</span><span class="sxs-lookup"><span data-stu-id="439f4-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="439f4-117">如果您的組織使用的是服務品質 (QoS) 基礎結構，則媒體子系統將會設計成配合此現有基礎結構運作。</span><span class="sxs-lookup"><span data-stu-id="439f4-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="439f4-118">如果您使用網際網路通訊協定安全性 (IPsec)，建議您針對 A/V 流量所使用的連接埠範圍停用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="439f4-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="439f4-119">如需詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的 IPsec 例外狀況](lync-server-2013-ipsec-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="439f4-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="439f4-120">為了確保最佳的媒體品質，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="439f4-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="439f4-p105">佈建您的網路連結，以支援每個音訊資料流具備 65 Kbps 的傳輸量與每個視訊資料流具備 500 Kbps 的傳輸量 (啟用時在尖峰時段的速率)。雙向音訊或視訊工作階段包含兩種資料流。</span><span class="sxs-lookup"><span data-stu-id="439f4-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="439f4-123">若要應付經過一段時間未預期尖峰流量上方此層級和增加的流量，Lync Server 媒體端點可以適用於不同的條件和網路支援負載的三倍輸送量 （請參閱前一段） 的音訊和視訊，當您仍保留可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="439f4-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="439f4-124">但是，請勿認為這項調整功能可以支援未佈建齊全的網路。</span><span class="sxs-lookup"><span data-stu-id="439f4-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="439f4-125">在 [佈建網路，就會減少 Lync Server 的媒體端點以動態方式處理不同網路狀況 （例如，暫存高封包遺失） 的能力。</span><span class="sxs-lookup"><span data-stu-id="439f4-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="439f4-126">對於佈建成本與困難度非常高的網路連結來說，您可能不得不考慮以較低的流量為主進行佈建。</span><span class="sxs-lookup"><span data-stu-id="439f4-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="439f4-127">在此案例中，可讓 Lync Server 的媒體端點的彈性吸收流量磁碟區，並犧牲某些減少的聲音品質的尖峰流量層級之間的差異。</span><span class="sxs-lookup"><span data-stu-id="439f4-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="439f4-128">同時，也會減少用來吸收突發性流量暴增的空間。</span><span class="sxs-lookup"><span data-stu-id="439f4-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="439f4-129">對於無法在短時間內正確佈建的連結來說 (例如 WAN 連結品質非常差的網站)，請考慮針對某些使用者停用視訊功能。</span><span class="sxs-lookup"><span data-stu-id="439f4-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="439f4-130">佈建網路時，請確保在尖峰用量時段保持最高 150 ms 的端對端延遲水準。</span><span class="sxs-lookup"><span data-stu-id="439f4-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="439f4-131">延遲是減少 Lync Server 媒體元件，不能有一個網路減損小，很重要來找出並消除弱式的點。</span><span class="sxs-lookup"><span data-stu-id="439f4-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="439f4-132">對於執行防毒軟體的伺服器，包括所有伺服器執行 Lync Server 例外狀況清單中，以達到最佳效能和音訊品質。</span><span class="sxs-lookup"><span data-stu-id="439f4-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="439f4-133">會議網路需求</span><span class="sxs-lookup"><span data-stu-id="439f4-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="439f4-134">用來從網際網路資訊服務 (IIS) 伺服器下載會議內容的頻寬需視上傳的內容大小而定。</span><span class="sxs-lookup"><span data-stu-id="439f4-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

