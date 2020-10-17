---
title: Lync Server 2013：設定 Edge server 的網路介面
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
ms.openlocfilehash: 5b7eee448ffd5176797ebfbb0fb43afc4c9e41a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509820"
---
# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="a252d-102">在 Lync Server 2013 中設定 Edge server 的網路介面</span><span class="sxs-lookup"><span data-stu-id="a252d-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a252d-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a252d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a252d-104">每一部 Edge Server 都是具有外部及內部介面的多主機電腦。</span><span class="sxs-lookup"><span data-stu-id="a252d-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="a252d-105">DNS) 設定 (的「配接器網域名稱系統」，取決於周邊網路中是否有 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a252d-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="a252d-106">如果周邊中已存在 DNS 伺服器，則他們必須具有一個區域，其中包含下一個躍點伺服器或集區 (的一個或多個 DNS A 記錄，也就是 Director 或指定的前端集區) ，以及它們參照其他公用 DNS 伺服器名稱查閱的外部查詢。</span><span class="sxs-lookup"><span data-stu-id="a252d-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="a252d-107">若周邊中沒有 DNS 伺服器，Edge Server (s) 使用外部 DNS 伺服器來解析網際網路名稱查閱，而每個 Edge Server 會使用主機將下一個躍點伺服器名稱解析為 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a252d-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="a252d-109">安全性附注：</span><span class="sxs-lookup"><span data-stu-id="a252d-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a252d-110">基於安全性考慮，建議您不要讓 Edge Server 存取位於內部網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a252d-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="a252d-111">在周邊網路中使用 DNS 伺服器設定介面</span><span class="sxs-lookup"><span data-stu-id="a252d-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="a252d-112">為每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對向介面，另一個用於外部介面。</span><span class="sxs-lookup"><span data-stu-id="a252d-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a252d-113">內部和外部子網不得彼此路由傳送。</span><span class="sxs-lookup"><span data-stu-id="a252d-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="a252d-114">在外部介面上，設定外部周邊網路上的三個靜態 IP 位址 (也稱為 DMZ、隔離區域和遮罩式子網) 子網，然後將預設閘道指向外部防火牆的內部介面。</span><span class="sxs-lookup"><span data-stu-id="a252d-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="a252d-115">設定介面卡 DNS 設定，以指向一對周邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a252d-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a252d-116">您可以只使用此介面的一個 IP 位址，但若要這麼做，您必須將埠指派變更為非標準值。</span><span class="sxs-lookup"><span data-stu-id="a252d-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="a252d-117">您可以在拓撲產生器中建立拓撲時加以判斷。</span><span class="sxs-lookup"><span data-stu-id="a252d-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="a252d-118">在 internal 介面上，在內部周邊網路子網上設定一個靜態 IP 位址，而不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="a252d-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="a252d-119">設定介面卡 DNS 設定，使其指向至少一部 DNS 伺服器，最好是一對周邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a252d-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="a252d-120">在內部介面上建立持續性靜態路由，以傳送用戶端、Lync Server 2013 和 Exchange 整合通訊 (UM) 伺服器所在的所有內部網路。</span><span class="sxs-lookup"><span data-stu-id="a252d-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="a252d-121">在周邊網路中設定沒有 DNS 伺服器的介面</span><span class="sxs-lookup"><span data-stu-id="a252d-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="a252d-122">為每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對向介面，另一個用於外部介面。</span><span class="sxs-lookup"><span data-stu-id="a252d-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a252d-123">內部和外部子網不得彼此路由傳送。</span><span class="sxs-lookup"><span data-stu-id="a252d-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="a252d-124">在外部介面上，設定外部周邊網路子網上的三個靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a252d-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="a252d-125">您也可以在外部介面上設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="a252d-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="a252d-126">例如，將網際網路對向路由器或外部防火牆定義為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="a252d-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="a252d-127">設定 DNS 設定以指向 DNS 伺服器，最好是一對外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a252d-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a252d-128">您可以使用但不建議使用，只使用外部介面的一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a252d-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="a252d-129">若要讓這種方式可以運作，您必須將埠指派變更為非標準值，並從預設埠443（通常為「防火牆友好」）變更為用戶端通訊。</span><span class="sxs-lookup"><span data-stu-id="a252d-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="a252d-130">您可以在拓撲產生器中建立拓撲時決定 IP 位址設定及埠設定。</span><span class="sxs-lookup"><span data-stu-id="a252d-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="a252d-131">在 internal 介面上，在內部周邊網路子網上設定一個靜態 IP 位址，而不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="a252d-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="a252d-132">將配接器 DNS 設定保留空白。</span><span class="sxs-lookup"><span data-stu-id="a252d-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="a252d-133">在內部介面上建立持續性靜態路由，以傳送 Lync 用戶端或執行 Lync Server 2013 之伺服器所在的所有內部網路。</span><span class="sxs-lookup"><span data-stu-id="a252d-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="a252d-134">編輯每一部 Edge Server 上的主機檔案，以包含下一個躍點伺服器或虛擬 IP (VIP) 的記錄， (該記錄將是 Director、Standard Edition Server 或前端集區，其設定為拓撲產生器) 中已設定為 Edge Server 下一個躍點位址的前端集區。</span><span class="sxs-lookup"><span data-stu-id="a252d-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="a252d-135">如果您使用 DNS 負載平衡，請在下一個躍點集區的每個成員中包含一行。</span><span class="sxs-lookup"><span data-stu-id="a252d-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

