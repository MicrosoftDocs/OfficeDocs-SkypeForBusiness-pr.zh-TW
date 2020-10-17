---
title: Lync Server 2013：單一合併 edge （利用公用 IP 位址）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5d8af424aa334c19847c993ef338d4ba81d5b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519760"
---
# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="b08ce-102">Lync Server 2013 中的單一合併 edge （使用公用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="b08ce-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b08ce-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b08ce-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b08ce-104">如果您的組織需要支援低於15000的 Access Edge service 用戶端連線、1000作用中的 Lync Server Web 會議服務用戶端連線，以及500並行 A/V 邊際會話，而且 Edge Server 的高可用性並不重要，此拓撲提供低硬體成本和簡化部署的優點。</span><span class="sxs-lookup"><span data-stu-id="b08ce-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="b08ce-105">如果您需要較大的容量，或需要高可用性，您應該部署調整式合併 Edge Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="b08ce-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="b08ce-106">Lync Server 2013 中的調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="b08ce-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="b08ce-107">Lync Server 2013 中的調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="b08ce-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="b08ce-108">Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="b08ce-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b08ce-109">在 Edge Server 上使用公用 IP 位址時，Edge Server 上的預設閘道不再是您的防火牆或路由器，但您的公用周邊 Edge 中的路由器或防火牆會是公用位址。</span><span class="sxs-lookup"><span data-stu-id="b08ce-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="b08ce-110">反向 proxy 會繼續使用與最外面周邊網路相關聯的路由器或防火牆。</span><span class="sxs-lookup"><span data-stu-id="b08ce-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="b08ce-111">反向 proxy 與具有公用 IP 位址之 Edge Server 之間的差異是反向 proxy 仍在使用 NAT，而且 Edge Server 使用路由關聯。</span><span class="sxs-lookup"><span data-stu-id="b08ce-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="b08ce-112">此圖不會顯示 Director，也就是在 Edge server 與前端集區或伺服器之間的內部網路中部署的選用伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="b08ce-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="b08ce-113">如需 Director 拓撲的詳細資訊，請參閱 [Lync Server 2013 中 Director 所需的元件](lync-server-2013-components-required-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="b08ce-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="b08ce-114">此圖表表示單一反向 Proxy。</span><span class="sxs-lookup"><span data-stu-id="b08ce-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b08ce-115">此圖表顯示了方向及範例 IP 位址指定，但不代表具有正確傳入及傳出流量的實際通訊流程。</span><span class="sxs-lookup"><span data-stu-id="b08ce-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="b08ce-116">此圖表示的是可能流量的高階檢視。</span><span class="sxs-lookup"><span data-stu-id="b08ce-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="b08ce-117">屬於傳入 (至聆聽連接埠) 及傳出 (至目地伺服器或用戶端) 時的流量流程詳細資料皆呈現在每個案例中的連接埠摘要圖表中。</span><span class="sxs-lookup"><span data-stu-id="b08ce-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="b08ce-118">例如，TCP 443 其實僅有輸入 (至 Edge 或反向 Proxy)，且僅是一個來自通訊協定 (TCP) 方面的雙向流程。</span><span class="sxs-lookup"><span data-stu-id="b08ce-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="b08ce-119">另外，當進行 NAT (網路位址轉譯) 時 (目的地位址在輸入上變更，來源位址在輸出上變更)，此圖表還顯示了流量變更時的性質。</span><span class="sxs-lookup"><span data-stu-id="b08ce-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="b08ce-120">外部及內部防火牆和伺服器介面範例僅顯示作為參考之用。</span><span class="sxs-lookup"><span data-stu-id="b08ce-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="b08ce-121">最後，預設閘道和路由關係會視需要顯示。</span><span class="sxs-lookup"><span data-stu-id="b08ce-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="b08ce-122">另請注意，圖表會使用 <EM>.Com</EM> dns 區域來代表反向 Proxy 和 Edge server 的外部 DNS 區域，而 <EM>.net</EM> DNS 區域則是指內部 DNS 區域。</span><span class="sxs-lookup"><span data-stu-id="b08ce-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="b08ce-123">Microsoft Lync Server 2013 的新功能支援 IPv6 定址。</span><span class="sxs-lookup"><span data-stu-id="b08ce-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="b08ce-124">和 IPv4 位址指定相近的是，必須以屬於指派之 IPv6 位址空間的位址來指派 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="b08ce-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="b08ce-125">本主題中的位址僅為範例。</span><span class="sxs-lookup"><span data-stu-id="b08ce-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="b08ce-126">您必須取得可在您部署中運作的 IPv6 位址，以提供正確的範圍，並和內部及外部位址指定相互溝通。</span><span class="sxs-lookup"><span data-stu-id="b08ce-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="b08ce-127">Windows Server 提供一項功能，對過渡 IPv6 作業和 IPv4 IPv6 稱為 *雙重堆疊*的通訊很重要。</span><span class="sxs-lookup"><span data-stu-id="b08ce-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="b08ce-128">雙重堆疊是針對 IPv4 及 IPv6 獨立且獨特的網路堆疊。</span><span class="sxs-lookup"><span data-stu-id="b08ce-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="b08ce-129">雙重堆疊可允許您同時指派 IPv4 及 IPv6 的位址指定，也允許伺服器與其他主機和用戶端，根據其需求為何來進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b08ce-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="b08ce-130">用於 IPv6 定址的一般網址類別型將會是 IPv6 的全域位址 (類似于公用 IPv4 位址) 、IPv6 唯一本機位址 (類似于私人 IPv4 位址範圍) 和 IPv6 連結本機位址 (類似于 Windows Server 中 IPv4 的自動私人 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="b08ce-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="b08ce-131">IPv6 適用的網路位址轉譯技術 (NAT) 可用於 IPv6 對 IPv4 的 NAT (一般稱為 NAT64) 和 IPv6 對 IPv6 的 NAT (通常稱為 NAT66)。</span><span class="sxs-lookup"><span data-stu-id="b08ce-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="b08ce-132">NAT 技術的存在，表示 Lync Server Edge server 所呈現的五種案例仍有效。</span><span class="sxs-lookup"><span data-stu-id="b08ce-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b08ce-133">IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 供應商，以確保您在 Windows server 層級和 Lync Server 2013 層級所指派的位址如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="b08ce-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="b08ce-134">請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。</span><span class="sxs-lookup"><span data-stu-id="b08ce-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="b08ce-135">**單一合併 Edge （透過公用 IP 位址拓撲）**</span><span class="sxs-lookup"><span data-stu-id="b08ce-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="b08ce-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="b08ce-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b08ce-137">如果您使用「通話許可控制」 (CAC) ，您仍然必須將 IPv4 位址指派給 Edge Server 內部介面。</span><span class="sxs-lookup"><span data-stu-id="b08ce-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="b08ce-138">CAC 會使用 IPv4 位址，且須讓其得以運作。</span><span class="sxs-lookup"><span data-stu-id="b08ce-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b08ce-139">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b08ce-139">In This Section</span></span>

  - [<span data-ttu-id="b08ce-140">Lync Server 2013 中的憑證摘要-單一合併 edge （利用公用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="b08ce-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="b08ce-141">Lync Server 2013 中的埠摘要-含公用 IP 位址的單一合併 edge</span><span class="sxs-lookup"><span data-stu-id="b08ce-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="b08ce-142">Lync Server 2013 中的 DNS 摘要-單一合併 edge （利用公用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="b08ce-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b08ce-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b08ce-143">See Also</span></span>


[<span data-ttu-id="b08ce-144">IP 版本6定址架構</span><span class="sxs-lookup"><span data-stu-id="b08ce-144">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="b08ce-145">IPv6 全域單路廣播位址格式</span><span class="sxs-lookup"><span data-stu-id="b08ce-145">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="b08ce-146">唯一的本地 IPv6 單播位址</span><span class="sxs-lookup"><span data-stu-id="b08ce-146">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

