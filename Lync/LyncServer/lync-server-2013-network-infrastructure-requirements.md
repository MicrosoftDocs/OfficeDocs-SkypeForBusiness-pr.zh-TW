---
title: Lync Server 2013 網路基礎結構需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="5134d-102">Lync Server 2013 的網路基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="5134d-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5134d-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5134d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5134d-104">Lync Server 2013 拓撲中每個伺服器的網路介面卡，必須至少支援1十億位元/秒（Gbps）。</span><span class="sxs-lookup"><span data-stu-id="5134d-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="5134d-105">一般來說，您應該使用低延遲和高頻寬的局域網（LAN），連線 Lync Server 拓撲中的所有伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="5134d-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="5134d-106">局域網的大小取決於拓撲大小：</span><span class="sxs-lookup"><span data-stu-id="5134d-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="5134d-107">在標準版拓撲結構中，伺服器應該位於支援 1 Gbps 乙太網或對等的網路中。</span><span class="sxs-lookup"><span data-stu-id="5134d-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="5134d-108">在前端池拓撲中，大部分的伺服器都應該位於支援超過 1 Gbps 的網路中，特別是支援音訊/視頻（A/V）會議與應用程式共用時。</span><span class="sxs-lookup"><span data-stu-id="5134d-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="5134d-109">針對公用交換電話網絡（PSTN）整合，您可以使用 T1/E1 線路或 SIP 中繼整合。</span><span class="sxs-lookup"><span data-stu-id="5134d-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="5134d-110">音訊/視頻網路需求</span><span class="sxs-lookup"><span data-stu-id="5134d-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="5134d-111">Lync Server 部署中音訊/視頻（A/V）的網路需求包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5134d-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="5134d-112">如果您是使用 DNS 負載平衡部署單一邊緣伺服器或邊緣池，您可以將外部防火牆設定為 NAT。</span><span class="sxs-lookup"><span data-stu-id="5134d-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="5134d-113">您無法將內部防火牆設定為 NAT。</span><span class="sxs-lookup"><span data-stu-id="5134d-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="5134d-114">如需這些需求的詳細資訊，請參閱在規劃檔中針對[Lync Server 2013 判斷外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5134d-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5134d-115">如果您有邊緣池，且正在使用硬體負載平衡器，則您必須在每一台邊緣伺服器上使用公用 IP 位址，而且您無法在您的 NAT 裝置上使用 NAT （例如，防火牆或其他可能是 NAT inbou 的基礎結構裝置）nd 或呼出流量）。</span><span class="sxs-lookup"><span data-stu-id="5134d-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="5134d-116">如需詳細資訊，請參閱在規劃外部使用者存取檔中的<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的 [埠摘要] 與硬體負載平衡</A>器。</span><span class="sxs-lookup"><span data-stu-id="5134d-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="5134d-117">如果您的組織使用的是服務品質（QoS）基礎結構，媒體子系統就是設計來在這個現有的基礎結構中運作。</span><span class="sxs-lookup"><span data-stu-id="5134d-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="5134d-118">如果您使用的是網際網路通訊協定安全性（IPsec），建議您在用於 A/V 流量的埠範圍上停用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="5134d-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="5134d-119">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)狀況。</span><span class="sxs-lookup"><span data-stu-id="5134d-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="5134d-120">若要確保最佳的媒體質量，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5134d-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="5134d-121">您可以在高峰使用量期間啟用，將您的網路連結設定為支援每秒 65 kbps 的輸送量，以及每個視頻資料流程的 500 Kbps。</span><span class="sxs-lookup"><span data-stu-id="5134d-121">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods.</span></span> <span data-ttu-id="5134d-122">雙向音訊或視頻會話是由兩個數據流所組成。</span><span class="sxs-lookup"><span data-stu-id="5134d-122">A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="5134d-123">為了應對此等級以上流量中的意外峰值並隨著時間增加使用量，Lync Server 媒體端點可以適應不同的網路狀況，並支援載入三倍于音訊和視頻的輸送量（請參閱前一段），同時仍保留可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="5134d-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="5134d-124">不過，請勿假設這種適應性支援的是預配網路。</span><span class="sxs-lookup"><span data-stu-id="5134d-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="5134d-125">在預配的網路中，Lync Server 媒體端點能動態處理不同網路狀況（例如，暫時大資料包遺失）的能力會減少。</span><span class="sxs-lookup"><span data-stu-id="5134d-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="5134d-126">針對配備極其昂貴且困難的網路連結，您可能需要考慮針對較低的流量進行置備。</span><span class="sxs-lookup"><span data-stu-id="5134d-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="5134d-127">在這種情況下，請讓 Lync Server 媒體端點的 elasticity 佔用流量與峰值流量層級之間的差異，同時降低語音品質。</span><span class="sxs-lookup"><span data-stu-id="5134d-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="5134d-128">此外，預留空間也會減少，但仍可吸收通信量突然高峰的情況。</span><span class="sxs-lookup"><span data-stu-id="5134d-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="5134d-129">針對短期內無法正確提供的連結（例如，WAN 連結較差的網站），請考慮針對特定使用者停用影片。</span><span class="sxs-lookup"><span data-stu-id="5134d-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="5134d-130">您可以在 [峰值負載] 底下，將您的網路設定為確保最大150的端對端延遲（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="5134d-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="5134d-131">延遲是 Lync Server 媒體元件無法減少的一個網路障礙，請務必找出並消除薄弱點。</span><span class="sxs-lookup"><span data-stu-id="5134d-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="5134d-132">針對執行防毒軟體的伺服器，請在例外清單中包含所有執行 Lync Server 的伺服器，以提供最佳效能和音訊品質。</span><span class="sxs-lookup"><span data-stu-id="5134d-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="5134d-133">會議網路需求</span><span class="sxs-lookup"><span data-stu-id="5134d-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="5134d-134">從網際網路資訊服務（IIS）伺服器下載會議內容所用的頻寬，取決於上傳的內容大小。</span><span class="sxs-lookup"><span data-stu-id="5134d-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

