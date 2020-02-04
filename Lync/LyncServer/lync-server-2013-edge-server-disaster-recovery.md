---
title: Lync Server 2013：Edge Server 災害復原
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
ms.openlocfilehash: 431b4853407b65bca2b029626cc5659490a493d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0b5db-102">Lync Server 2013 中的 Edge Server 災害復原</span><span class="sxs-lookup"><span data-stu-id="0b5db-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b5db-103">_**主題上次修改日期：** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="0b5db-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="0b5db-104">與其他伺服器角色一樣，為邊緣伺服器提供高可用性的最佳方式，就是在每個網站的池中部署多個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b5db-104">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site.</span></span> <span data-ttu-id="0b5db-105">如果一個邊緣伺服器關閉，則池中的其他伺服器將繼續提供 Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="0b5db-105">If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="0b5db-106">若要啟用災害復原程式，您必須在不同的網站上部署獨立的邊緣伺服器池。</span><span class="sxs-lookup"><span data-stu-id="0b5db-106">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites.</span></span> <span data-ttu-id="0b5db-107">您不需要將邊緣池完全配對，就像使用前端池一樣，但如果有多個邊緣池出現，則有多個邊緣池仍可提供該可用性來繼續。</span><span class="sxs-lookup"><span data-stu-id="0b5db-107">You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down.</span></span> <span data-ttu-id="0b5db-108">下列各節提供有關 Edge 伺服器各種功能的災害復原的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0b5db-108">The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="0b5db-109">遠端存取</span><span class="sxs-lookup"><span data-stu-id="0b5db-109">Remote Access</span></span>

<span data-ttu-id="0b5db-110">如果您有多個網站，每個網站都有一個 Edge 伺服器池，而一個整個邊緣池則無法正常運作，遠端存取服務將繼續運作，而不需要系統管理員動作。</span><span class="sxs-lookup"><span data-stu-id="0b5db-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="0b5db-111">在不同的網站建立邊緣池時，您無法使用相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0b5db-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="0b5db-112">每個 Edge 池都必須有唯一的 Fqdn （內部和外部）。</span><span class="sxs-lookup"><span data-stu-id="0b5db-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="0b5db-113">Edge 池不使用反向 proxy 發佈規則來與前端伺服器交談。</span><span class="sxs-lookup"><span data-stu-id="0b5db-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="0b5db-114">自動容錯移轉會在用戶端重新查詢遠端存取 DNS 服務記錄，而遠端使用者路由到另一個網站中的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b5db-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="0b5db-115">用戶端會根據 DNS SRV 記錄的優先順序，嘗試每個外部邊緣 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0b5db-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b5db-116">若要讓容錯移轉順利運作，請確定防火牆允許每個池中的前端伺服器與所有邊緣伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="0b5db-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="0b5db-117">同盟</span><span class="sxs-lookup"><span data-stu-id="0b5db-117">Federation</span></span>

<span data-ttu-id="0b5db-118">對於其他執行 Lync Server 的組織而言，當您擁有諸如地域傳送的解決方案時，輸入同盟要求就會繼續運作。</span><span class="sxs-lookup"><span data-stu-id="0b5db-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="0b5db-119">請務必瞭解，同盟容錯移轉不會以 SRV 記錄中的優先順序提供容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="0b5db-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="0b5db-120">先前提供的解決方案可協助您為輸入的同盟提供災害復原功能。</span><span class="sxs-lookup"><span data-stu-id="0b5db-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="0b5db-121">輸出同盟永遠是透過組織中的一個已發佈的邊緣池或邊緣伺服器來設定。</span><span class="sxs-lookup"><span data-stu-id="0b5db-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="0b5db-122">如果此 Edge 池已關閉，您必須使用拓撲建立器，將輸出同盟路由改為使用仍在執行的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="0b5db-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="0b5db-123">如需詳細資訊，請參閱[在 Lync server 2013 中針對 Lync server federation 使用的邊緣池失敗](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="0b5db-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="0b5db-124">XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="0b5db-124">XMPP Federation</span></span>

<span data-ttu-id="0b5db-125">針對 XMPP 同盟，如果邊緣池被指定為 XMPP 同盟閘道，則輸出和輸入流量都會失敗。</span><span class="sxs-lookup"><span data-stu-id="0b5db-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="0b5db-126">若要再次進行 XMPP 同盟作業，您必須將 XMPP 同盟變更為使用不同的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="0b5db-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="0b5db-127">如需詳細資訊，請參閱[在 Lync Server 2013 中針對 XMPP 同盟使用的邊緣池失敗](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="0b5db-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="0b5db-128">Edge 池失敗，但前臺池仍在執行</span><span class="sxs-lookup"><span data-stu-id="0b5db-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="0b5db-129">如果邊緣池在網站上失敗，但該網站的前端池仍在執行，您將需要變更前端池，以便在第一個邊緣池關閉時，在不同的網站上使用不同的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="0b5db-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="0b5db-130">如需詳細資訊，請參閱[在 Lync Server 2013 中變更與前端池相關聯的邊緣池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="0b5db-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

