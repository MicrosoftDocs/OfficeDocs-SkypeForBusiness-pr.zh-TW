---
title: Lync Server 2013：調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ccae081e80b61be767dfbdc82664ff90d4dfabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="f5f18-102">Lync Server 2013 中的調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="f5f18-102">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5f18-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f5f18-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f5f18-104">在 Edge 伺服器池拓撲結構中，兩個或多個 Edge 伺服器會在資料中心的周邊網路中部署為負載平衡的池。</span><span class="sxs-lookup"><span data-stu-id="f5f18-104">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="f5f18-105">[網域名稱系統（DNS）] 負載平衡用於外部與內部邊緣介面的流量。</span><span class="sxs-lookup"><span data-stu-id="f5f18-105">Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="f5f18-106">如果您的組織需要支援超過15000的 Access Edge 服務用戶端連線、1000使用中的 Lync Server Web 會議服務用戶端連線，或500併發的 A/V 邊緣會話，以及/或邊緣伺服器的高可用性，這種拓撲提供了可伸縮性與容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="f5f18-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="f5f18-107">此圖不會顯示控制器，也就是在邊緣伺服器與您的前端池或伺服器之間部署于內部網路中的選用伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="f5f18-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="f5f18-108">如需控制器拓撲結構的詳細資料，請參閱[Lync Server 2013 中主管所需的元件](lync-server-2013-components-required-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="f5f18-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="f5f18-109">此圖代表單一反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="f5f18-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5f18-110">所示的圖形是針對方向和範例 IP 定址，但不想要以正確的內送和外送流量來代表實際通訊流程。</span><span class="sxs-lookup"><span data-stu-id="f5f18-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="f5f18-111">此圖代表可能流量的高層視圖。</span><span class="sxs-lookup"><span data-stu-id="f5f18-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="f5f18-112">在每個案例的埠摘要圖表中，會顯示通信量與傳入（到偵聽埠）及傳出（目的地伺服器或用戶端）相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f5f18-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="f5f18-113">例如，TCP 443 實際上是入站（到 Edge 或反向 proxy），而且只是從通訊協定（TCP）角度來看，只是雙向流程。</span><span class="sxs-lookup"><span data-stu-id="f5f18-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="f5f18-114">此外，此圖顯示的是在發生 NAT （網路位址轉譯）時，通信量變更的性質（在輸入的目的地位址變更時，來源位址會在輸出中變更）。</span><span class="sxs-lookup"><span data-stu-id="f5f18-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="f5f18-115">範例外部與內部防火牆，且伺服器介面僅供參考之用。</span><span class="sxs-lookup"><span data-stu-id="f5f18-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="f5f18-116">最後，會顯示預設閘道與路由關聯的範例（如果適用的話）。</span><span class="sxs-lookup"><span data-stu-id="f5f18-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="f5f18-117">另請注意，圖表會使用<EM>.Com</EM> DNS 區域來代表反向 Proxy 與 Edge 伺服器的外部 DNS 區域，而<EM>.net</EM> DNS 區域則是指內部 dns 區域。</span><span class="sxs-lookup"><span data-stu-id="f5f18-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="f5f18-118">Microsoft Lync Server 2013 的新功能支援 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="f5f18-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="f5f18-119">就像 IPv4 定址一樣，IPv6 位址必須以這種方式指派，就是位址是您指派的 IPv6 位址空間的一部分。</span><span class="sxs-lookup"><span data-stu-id="f5f18-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="f5f18-120">本主題中的位址只適用于範例。</span><span class="sxs-lookup"><span data-stu-id="f5f18-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="f5f18-121">您必須取得 IPv6 位址，才能在您的部署中運作，提供正確的範圍，並將與內部和外部定址進行互動。</span><span class="sxs-lookup"><span data-stu-id="f5f18-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="f5f18-122">Windows Server 提供將 IPv6 作業和 IPv4 轉換為稱為*雙重堆疊*之 ipv6 通訊的重要功能。</span><span class="sxs-lookup"><span data-stu-id="f5f18-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="f5f18-123">雙堆疊是 IPv4 與 IPv6 的個別且不同的網路堆疊。</span><span class="sxs-lookup"><span data-stu-id="f5f18-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="f5f18-124">雙重堆疊可讓您同時指派 IPv4 與 IPv6 的定址，並允許伺服器根據其需求與其他主機與用戶端進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f5f18-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="f5f18-125">Ipv6 定址所用的一般網址類別型將是 IPv6 全域位址（類似公用 IPv4 位址）、IPv6 唯一本機位址（類似于專用 IPv4 位址範圍）以及 IPv6 連結本機位址（類似自動私人 IP）Windows Server for IPv4 中的位址</span><span class="sxs-lookup"><span data-stu-id="f5f18-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="f5f18-126">IPv6 的網路位址轉譯技術（NAT），可讓 NAT IPv6 至 IPv4 （通常稱為 NAT64），以及 NAT IPv6 至 IPv6 （通常稱為 NAT66）。</span><span class="sxs-lookup"><span data-stu-id="f5f18-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="f5f18-127">NAT 技術的存在表示，提供給 Lync Server Edge 伺服器的五種案例仍然有效。</span><span class="sxs-lookup"><span data-stu-id="f5f18-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f5f18-128">IPv6 是一個複雜的主題，需要謹慎規劃您的網路小組和 Internet 提供者，以確保您在 Windows server 層級和 Lync Server 2013 層級指派的位址會如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="f5f18-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="f5f18-129">如需有關 IPv6 定址與規劃的其他資源，請參閱本主題結尾的連結。</span><span class="sxs-lookup"><span data-stu-id="f5f18-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="f5f18-130">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span><span class="sxs-lookup"><span data-stu-id="f5f18-130">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f5f18-131">如果您使用的是 [通話許可控制] （CAC），您仍然必須將 IPv4 位址指派給 Edge 伺服器內部介面。</span><span class="sxs-lookup"><span data-stu-id="f5f18-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="f5f18-132">CAC 使用 IPv4 位址，而且必須有它們可供操作。</span><span class="sxs-lookup"><span data-stu-id="f5f18-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5f18-133">本節內容</span><span class="sxs-lookup"><span data-stu-id="f5f18-133">In This Section</span></span>

  - [<span data-ttu-id="f5f18-134">Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="f5f18-134">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="f5f18-135">Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="f5f18-135">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="f5f18-136">Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="f5f18-136">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5f18-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="f5f18-137">See Also</span></span>


[<span data-ttu-id="f5f18-138">IP 版本6定址架構</span><span class="sxs-lookup"><span data-stu-id="f5f18-138">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="f5f18-139">IPv6 全域單播位址格式</span><span class="sxs-lookup"><span data-stu-id="f5f18-139">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="f5f18-140">唯一的局部 IPv6 單播位址</span><span class="sxs-lookup"><span data-stu-id="f5f18-140">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

