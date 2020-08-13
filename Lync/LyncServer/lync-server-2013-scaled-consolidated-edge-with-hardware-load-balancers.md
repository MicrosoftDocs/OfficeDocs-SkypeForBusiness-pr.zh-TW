---
title: Lync Server 2013：調整式合併 edge （使用硬體負載平衡器）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a961b6eabb85e135b1cfb36cf5738cbf757b547
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="55128-102">Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="55128-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55128-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="55128-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="55128-104">在 Edge 集區拓撲中，會在資料中心的周邊網路中，將兩個或多個 Edge Server 部署為負載平衡集區。</span><span class="sxs-lookup"><span data-stu-id="55128-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="55128-105">硬體負載平衡用於外部和內部 Edge Server 介面的流量。</span><span class="sxs-lookup"><span data-stu-id="55128-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="55128-106">如果您的組織需要支援15000以上的 Access Edge service 用戶端連線、1000作用中 Web 會議 Edge service 用戶端連線，或500並行 A/V Edge service 會話，而且 Edge Server 的高可用性非常重要，此拓撲提供擴充性和容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="55128-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="55128-107">此圖不會顯示 Director，也就是在 Edge server 與前端集區或伺服器之間的內部網路中部署的選用伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="55128-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="55128-108">.</span><span class="sxs-lookup"><span data-stu-id="55128-108">.</span></span> <span data-ttu-id="55128-109">如需 Director 拓撲的詳細資訊，請參閱[Lync Server 2013 中 Director 所需的元件](lync-server-2013-components-required-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="55128-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55128-110">此圖說明 IP 位址定址的方向和範例，但並未嘗試使用正確的傳出和傳入流量來表示實際的通訊流量。</span><span class="sxs-lookup"><span data-stu-id="55128-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="55128-111">此圖表示的是可能流量的高階檢視。</span><span class="sxs-lookup"><span data-stu-id="55128-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="55128-112">有關傳入 (至聆聽連接埠) 和傳出 (至目的地伺服器或用戶端) 流量的詳細資訊，會在每個案例中表示於連接埠摘要圖中。</span><span class="sxs-lookup"><span data-stu-id="55128-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="55128-113">例如，TCP 443 實際上只會輸入 (至 Edge Server 或反向 proxy) ，而且只是從通訊協定 (TCP) 觀點的雙向流程。</span><span class="sxs-lookup"><span data-stu-id="55128-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="55128-114">另外，此圖也顯示在 NAT (網路位址轉譯) 發生之時 (目的地位址在傳入時變更，來源位址在傳出時變更) 流量在變化時的特性。</span><span class="sxs-lookup"><span data-stu-id="55128-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="55128-115">外部及內部防火牆和伺服器介面範例僅顯示作為參考之用。</span><span class="sxs-lookup"><span data-stu-id="55128-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="55128-116">最後，預設閘道和路由關係會視需要顯示。</span><span class="sxs-lookup"><span data-stu-id="55128-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="55128-117">另請注意，圖表會使用<EM>.Com</EM> dns 區域來代表反向 Proxy 和 Edge server 的外部 DNS 區域，而<EM>.net</EM> DNS 區域則是指內部 DNS 區域。</span><span class="sxs-lookup"><span data-stu-id="55128-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="55128-118">Microsoft Lync Server 2013 的新功能支援 IPv6 定址。</span><span class="sxs-lookup"><span data-stu-id="55128-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="55128-119">和 IPv4 位址指定相近的是，必須以屬於指派之 IPv6 位址空間的位址來指派 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="55128-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="55128-120">本主題中的位址僅為範例。</span><span class="sxs-lookup"><span data-stu-id="55128-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="55128-121">您必須取得可在您部署中運作的 IPv6 位址，以提供正確的範圍，並和內部及外部位址指定相互溝通。</span><span class="sxs-lookup"><span data-stu-id="55128-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="55128-122">Windows Server 提供一項功能，對過渡 IPv6 作業和 IPv4 IPv6 稱為*雙重堆疊*的通訊很重要。</span><span class="sxs-lookup"><span data-stu-id="55128-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="55128-123">雙重堆疊是針對 IPv4 及 IPv6 獨立且獨特的網路堆疊。</span><span class="sxs-lookup"><span data-stu-id="55128-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="55128-124">雙重堆疊可允許您同時指派 IPv4 及 IPv6 的位址指定，也允許伺服器與其他主機和用戶端，根據其需求為何來進行通訊。</span><span class="sxs-lookup"><span data-stu-id="55128-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="55128-125">用於 IPv6 定址的一般網址類別型將會是 IPv6 的全域位址 (類似于公用 IPv4 位址) 、IPv6 唯一本機位址 (類似于私人 IPv4 位址範圍) 和 IPv6 連結本機位址 (類似于 Windows Server 中 IPv4 的自動私人 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="55128-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="55128-126">IPv6 適用的網路位址轉譯技術 (NAT) 可用於 IPv6 對 IPv4 的 NAT (一般稱為 NAT64) 和 IPv6 對 IPv6 的 NAT (通常稱為 NAT66)。</span><span class="sxs-lookup"><span data-stu-id="55128-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="55128-127">NAT 技術的存在，表示 Lync Server Edge server 所呈現的五種案例仍有效。</span><span class="sxs-lookup"><span data-stu-id="55128-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="55128-128">IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 供應商，以確保您在 Windows server 層級和 Lync Server 2013 層級所指派的位址如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="55128-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="55128-129">請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。</span><span class="sxs-lookup"><span data-stu-id="55128-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="55128-130">**硬體負載平衡器設定**</span><span class="sxs-lookup"><span data-stu-id="55128-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="55128-131">如需詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取所需的元件](lync-server-2013-components-required-for-external-user-access.md)中的「A/V Edge 的硬體負載平衡器需求」一節。</span><span class="sxs-lookup"><span data-stu-id="55128-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="55128-132">**調整式合併 Edge 拓撲 (硬體負載平衡)**</span><span class="sxs-lookup"><span data-stu-id="55128-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="55128-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="55128-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55128-134">如果您使用「通話許可控制」 (CAC) ，您仍然必須將 IPv4 位址指派給 Edge Server 內部介面。</span><span class="sxs-lookup"><span data-stu-id="55128-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="55128-135">CAC 會使用 IPv4 位址，且須讓其得以運作。</span><span class="sxs-lookup"><span data-stu-id="55128-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="55128-136">本章節內容</span><span class="sxs-lookup"><span data-stu-id="55128-136">In This Section</span></span>

  - [<span data-ttu-id="55128-137">Lync Server 2013 的憑證摘要-調整式合併 edge （含硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="55128-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="55128-138">Lync Server 2013 中的埠摘要-調整式合併 edge （使用硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="55128-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="55128-139">Lync Server 2013 中的 DNS 摘要-調整式合併 edge （使用硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="55128-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55128-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55128-140">See Also</span></span>


[<span data-ttu-id="55128-141">IP 版本6定址架構</span><span class="sxs-lookup"><span data-stu-id="55128-141">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="55128-142">IPv6 全域單路廣播位址格式</span><span class="sxs-lookup"><span data-stu-id="55128-142">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="55128-143">唯一的本地 IPv6 單播位址</span><span class="sxs-lookup"><span data-stu-id="55128-143">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

