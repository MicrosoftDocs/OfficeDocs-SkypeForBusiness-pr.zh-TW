---
title: Lync Server 2013：設定 Edge Server 的網路介面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="1fca7-102">在 Lync Server 2013 中設定 Edge Server 的網路介面</span><span class="sxs-lookup"><span data-stu-id="1fca7-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fca7-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1fca7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1fca7-104">每個 Edge 伺服器都是具有外部與內部介面的多重主目錄電腦。</span><span class="sxs-lookup"><span data-stu-id="1fca7-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="1fca7-105">配接器的網域名稱系統（DNS）設定，取決於周邊網路中是否有 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1fca7-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="1fca7-106">如果 DNS 伺服器存在於周邊中，他們必須有一個區域包含一或多個適用于下一個躍點伺服器或池的 DNS A 記錄（也就是 Director 或指定的前端池），而且外部查詢會將名稱查閱參照至其他公用 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1fca7-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="1fca7-107">如果周長中不存在 DNS 伺服器，Edge 伺服器會使用外部 DNS 伺服器來解析網際網路名稱查閱，而每個 Edge 伺服器則會使用主機將下一個躍點伺服器名稱解析為 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1fca7-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="1fca7-109">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="1fca7-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1fca7-110">基於安全性的考慮，我們建議您不要讓邊緣伺服器存取位於內部網路的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1fca7-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="1fca7-111">在周邊網路中將介面與 DNS 伺服器進行設定</span><span class="sxs-lookup"><span data-stu-id="1fca7-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="1fca7-112">針對每個邊緣伺服器安裝兩個網路介面卡，一個用於內部方介面，另一個用於面向外部介面。</span><span class="sxs-lookup"><span data-stu-id="1fca7-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1fca7-113">內部和外部子網必須彼此無法路由。</span><span class="sxs-lookup"><span data-stu-id="1fca7-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="1fca7-114">在外部介面上，設定外部周邊網路（也稱為 DMZ、網路隔離區域及遮罩式子網）子網上的三個靜態 IP 位址，並將預設閘道指向外部防火牆的內部介面。</span><span class="sxs-lookup"><span data-stu-id="1fca7-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="1fca7-115">將 [配接器 DNS 設定] 設定為指向一對週邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1fca7-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1fca7-116">您可以為這個介面使用的位址只是一個 IP 位址，但若要這麼做，您需要將埠指派變更為非標準值。</span><span class="sxs-lookup"><span data-stu-id="1fca7-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="1fca7-117">當您在拓撲建立器中建立拓撲時，就會決定這麼做。</span><span class="sxs-lookup"><span data-stu-id="1fca7-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="1fca7-118">在內部介面上，在內部周邊網路子網上設定一個靜態 IP 位址，而不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="1fca7-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="1fca7-119">將 [配接器 DNS 設定] 設定為指向至少一個 DNS 伺服器，最好是一對週邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1fca7-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="1fca7-120">在內部介面上為用戶端、Lync Server 2013 和 Exchange 整合通訊（UM）伺服器所駐留的所有內部網路建立永久靜態路由。</span><span class="sxs-lookup"><span data-stu-id="1fca7-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="1fca7-121">在周邊網路中設定不含 DNS 伺服器的介面</span><span class="sxs-lookup"><span data-stu-id="1fca7-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="1fca7-122">針對每個邊緣伺服器安裝兩個網路介面卡，一個用於內部方介面，另一個用於面向外部介面。</span><span class="sxs-lookup"><span data-stu-id="1fca7-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1fca7-123">內部和外部子網必須彼此無法路由。</span><span class="sxs-lookup"><span data-stu-id="1fca7-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="1fca7-124">在外部介面上，設定外部周邊網路子網上的三個靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1fca7-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="1fca7-125">您也可以在外部介面上設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="1fca7-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="1fca7-126">例如，將網際網路式路由器或外部防火牆定義為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="1fca7-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="1fca7-127">將 DNS 設定設定為指向 DNS 伺服器（最好是一對外部 DNS 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="1fca7-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1fca7-128">您可以（但不建議這樣做）只使用外部介面的一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1fca7-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="1fca7-129">若要允許這樣做，您必須將埠指派變更為非標準值，並移出預設埠443（通常是「防火牆易記」）以進行用戶端通訊。</span><span class="sxs-lookup"><span data-stu-id="1fca7-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="1fca7-130">您會在拓撲建立器中建立拓撲時，決定 IP 位址設定和埠設定。</span><span class="sxs-lookup"><span data-stu-id="1fca7-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="1fca7-131">在內部介面上，在內部周邊網路子網上設定一個靜態 IP 位址，而不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="1fca7-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="1fca7-132">將配接器 DNS 設定保留為空白。</span><span class="sxs-lookup"><span data-stu-id="1fca7-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="1fca7-133">在內部介面上建立永久靜態路由至 Lync 用戶端或執行 Lync Server 2013 的伺服器所在的所有內部網路。</span><span class="sxs-lookup"><span data-stu-id="1fca7-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="1fca7-134">在每個邊緣伺服器上編輯主機檔案，以包含下一個躍點伺服器或虛擬 IP （VIP）的記錄（記錄將是 Director、標準版伺服器，或在拓撲結構建立器中設定為 Edge 伺服器下一個躍點位址的前端池）。</span><span class="sxs-lookup"><span data-stu-id="1fca7-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="1fca7-135">如果您使用的是 DNS 負載平衡，請為下一個躍點池的每個成員包含一條線。</span><span class="sxs-lookup"><span data-stu-id="1fca7-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

