---
title: Lync Server 2013： 設定邊際伺服器的網路介面
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
ms.openlocfilehash: 267db7062c19a0b1344d11f27205a51bf1e750ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="b915d-102">設定 Lync Server 2013 中的 Edge server 的網路介面</span><span class="sxs-lookup"><span data-stu-id="b915d-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b915d-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="b915d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b915d-104">在每部 Edge Server 是多重主機電腦與外部及內部對外的介面。</span><span class="sxs-lookup"><span data-stu-id="b915d-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="b915d-105">介面卡的網域名稱系統 (DNS) 設定值取決於是否在周邊網路中有 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b915d-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="b915d-106">如果周邊網路中 DNS 伺服器，則必須區域，其中包含一或多個 DNS A 記錄下, 一個躍點伺服器或集區 （也就是 Director 或指定的前端集區），且外部查詢其參照至其他公用 DNS 伺服器的名稱查閱。</span><span class="sxs-lookup"><span data-stu-id="b915d-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="b915d-107">如果沒有 DNS 伺服器周邊網路中，Edge server 使用的外部 DNS 伺服器來解析網際網路名稱查閱，並在每部 Edge Server 使用主機來解析成 IP 位址的下一個躍點伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="b915d-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="b915d-109">安全性附註：</span><span class="sxs-lookup"><span data-stu-id="b915d-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b915d-110">基於安全性考量，建議您不需要 Edge Server 存取位於內部網路的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b915d-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="b915d-111">若要設定的介面與周邊網路中的 DNS 伺服器</span><span class="sxs-lookup"><span data-stu-id="b915d-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="b915d-112">每個 Edge Server，一個用於向內介面，另一個用於向外介面安裝兩個網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="b915d-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b915d-113">內部和外部子網路必須不是路由傳送給對方。</span><span class="sxs-lookup"><span data-stu-id="b915d-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="b915d-114">在外部介面，設定 [外部周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路） 上的三個靜態 IP 位址子網路及外部防火牆的點至內部介面的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="b915d-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="b915d-115">設定介面卡的 DNS 設定以指向周邊 DNS 伺服器的一組。</span><span class="sxs-lookup"><span data-stu-id="b915d-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b915d-116">就此介面中，使用最少一個 IP 位址，不過，若要這麼做您需要變更連接埠指派為非標準的值。</span><span class="sxs-lookup"><span data-stu-id="b915d-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="b915d-117">在拓撲產生器建立拓撲時，判斷這。</span><span class="sxs-lookup"><span data-stu-id="b915d-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="b915d-118">在內部介面，設定一個靜態 IP 位址內部周邊網路子網路上並沒有設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="b915d-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="b915d-119">設定介面卡的 DNS 設定以指向至少一部 DNS 伺服器，最好是一組的周邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b915d-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="b915d-120">在用戶端、 Lync Server 2013 和 Exchange 整合通訊 (UM) 伺服器所在的內部介面所有內部網路上建立持續性靜態路由。</span><span class="sxs-lookup"><span data-stu-id="b915d-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="b915d-121">若要設定周邊網路中沒有 DNS 伺服器的介面</span><span class="sxs-lookup"><span data-stu-id="b915d-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="b915d-122">每個 Edge Server，一個用於向內介面，另一個用於向外介面安裝兩個網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="b915d-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b915d-123">內部和外部子網路必須不是路由傳送給對方。</span><span class="sxs-lookup"><span data-stu-id="b915d-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="b915d-124">在外部介面，設定外部周邊網路子網路上的三個靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b915d-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="b915d-125">您也可以設定預設閘道上的外部介面。</span><span class="sxs-lookup"><span data-stu-id="b915d-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="b915d-126">例如，定義為網際網路對向路由器或外部防火牆作為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="b915d-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="b915d-127">設定 DNS 以指向 DNS 伺服器上，preferably to 一組的外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b915d-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b915d-128">它是可行的但不是建議使用，以使用最少一個 IP 位址的外部介面。</span><span class="sxs-lookup"><span data-stu-id="b915d-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="b915d-129">若要允許此功能才能運作，您需要變更連接埠指派，為非標準的值，及開通常是 「 易記 」 的防火牆用戶端通訊的預設連接埠 443。</span><span class="sxs-lookup"><span data-stu-id="b915d-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="b915d-130">當您在拓撲產生器建立拓撲時決定的 IP 位址設定及連接埠設定。</span><span class="sxs-lookup"><span data-stu-id="b915d-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="b915d-131">在內部介面，設定一個靜態 IP 位址內部周邊網路子網路上並沒有設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="b915d-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="b915d-132">配接器 DNS 設定保留空白。</span><span class="sxs-lookup"><span data-stu-id="b915d-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="b915d-133">在 Lync 用戶端或執行 Lync Server 2013 的伺服器所在的內部介面到所有的內部網路上建立持續性靜態路由。</span><span class="sxs-lookup"><span data-stu-id="b915d-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="b915d-134">編輯主機上的檔案包含的下一個躍點伺服器的記錄每部 Edge Server 或虛擬 IP (VIP) （Director、 Standard Edition server 或前端集區已設定為在拓撲產生器中的 Edge Server 下一個躍點地址，可能會記錄）。</span><span class="sxs-lookup"><span data-stu-id="b915d-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="b915d-135">如果您使用 DNS 負載平衡，包括行的下一個躍點集區的每個成員。</span><span class="sxs-lookup"><span data-stu-id="b915d-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

