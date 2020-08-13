---
title: Lync Server 2013： Edge Server 嚴重損壞修復
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff0c4b685c607850921be6b15b2611e427e5e226
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="3441a-102">Lync Server 2013 中的 Edge Server 災難性修復</span><span class="sxs-lookup"><span data-stu-id="3441a-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3441a-103">_**主題上次修改日期：** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="3441a-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="3441a-p101">如同其他伺服器角色，為 Edge Server 提供高可用性的最佳作法，是在每個網站的集區中部署多部 Edge Server。如果其中一部 Edge Server 中斷連線，集區中的其他伺服器將會繼續提供 Edge Service。</span><span class="sxs-lookup"><span data-stu-id="3441a-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="3441a-p102">若要啟用嚴重損壞修復程序，您必須將在不同的網站上部署個別 Edge Server 集區。您不需要像是對前端集區一樣，明確將 Edge 集區配對在一起，但是具有多個 Edge 集區仍可在一整個 Edge 集區中斷連線時，提供可用的集區繼續執行作業。下列各節提供各種 Edge Server 功能之嚴重損壞修復的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3441a-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="3441a-109">遠端存取</span><span class="sxs-lookup"><span data-stu-id="3441a-109">Remote Access</span></span>

<span data-ttu-id="3441a-110">如果您有多個網站，每個網站都有一部 Edge server 集區，而一個整個 Edge 集區失敗，遠端存取服務將繼續運作，而不需要系統管理員的動作。</span><span class="sxs-lookup"><span data-stu-id="3441a-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="3441a-111">在不同的網站建立 Edge 集區時，您不能使用相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3441a-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="3441a-112">每個 Edge 集區的 Fqdn 都必須是唯一的 Fqdn (internal 和 external) 。</span><span class="sxs-lookup"><span data-stu-id="3441a-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="3441a-113">Edge 集區不使用反向 proxy 發行規則來與前端伺服器交談。</span><span class="sxs-lookup"><span data-stu-id="3441a-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="3441a-114">當用戶端重新查詢遠端存取 DNS 服務記錄，且遠端使用者路由傳送至其他網站中的 Edge server 時，就會發生自動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="3441a-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="3441a-115">用戶端會根據 DNS SRV 記錄的優先順序，嘗試每個外部 Edge FQDN。</span><span class="sxs-lookup"><span data-stu-id="3441a-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3441a-116">若要讓容錯移轉順利運作，請確定防火牆允許從每個集區的前端伺服器與所有 Edge server 通訊。</span><span class="sxs-lookup"><span data-stu-id="3441a-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="3441a-117">同盟</span><span class="sxs-lookup"><span data-stu-id="3441a-117">Federation</span></span>

<span data-ttu-id="3441a-118">與其他執行 Lync Server 之組織的同盟關係，輸入的同盟要求會持續運作，只要您有像是異地 DNS 伺服器的解決方案。</span><span class="sxs-lookup"><span data-stu-id="3441a-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="3441a-119">務必要瞭解，同盟容錯移轉不會在 SRV 記錄中提供優先順序的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="3441a-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="3441a-120">先前提供的解決方案可協助您提供輸入同盟的嚴重損壞修復功能。</span><span class="sxs-lookup"><span data-stu-id="3441a-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="3441a-121">輸出同盟一律透過組織中一部已發行的 Edge 集區或 Edge Server 來設定。</span><span class="sxs-lookup"><span data-stu-id="3441a-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="3441a-122">如果此 Edge 集區中斷連線，則必須使用拓撲產生器，變更輸出同盟路由以使用仍在執行的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="3441a-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="3441a-123">如需詳細資訊，請參閱[在 lync server 2013 中容錯移轉用於 Lync server 同盟的 Edge 集](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)區</span><span class="sxs-lookup"><span data-stu-id="3441a-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="3441a-124">XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="3441a-124">XMPP Federation</span></span>

<span data-ttu-id="3441a-125">以 XMPP 同盟來說，當指定為 XMPP 同盟閘道的 Edge 集區中斷連線時，輸出及輸入流量都會失敗。</span><span class="sxs-lookup"><span data-stu-id="3441a-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="3441a-126">若要讓 XMPP 同盟恢復運作，您必須變更 XMPP 同盟以使用其他 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="3441a-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="3441a-127">如需詳細資訊，請參閱[容錯移轉在 Lync Server 2013 中用於 XMPP 同盟的 Edge 集](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)區。</span><span class="sxs-lookup"><span data-stu-id="3441a-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="3441a-128">Edge 集區失敗但前端集區仍在執行中</span><span class="sxs-lookup"><span data-stu-id="3441a-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="3441a-129">如果某個網站上的 Edge 集區失敗，但是該網站上的前端集區仍在執行中，您必須在第一個 Edge 集區中斷連線時，變更前端集區使用其他網站上不同的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="3441a-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="3441a-130">如需詳細資訊，請參閱[變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="3441a-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

