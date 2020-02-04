---
title: Lync Server 2013： DNS 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="1f3b9-102">Lync Server 2013 中的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1f3b9-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f3b9-103">_**主題上次修改日期：** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="1f3b9-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="1f3b9-104">Lync Server 可啟用 DNS 負載平衡，這是可大大減少網路上負載平衡之管理負荷的軟體解決方案。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="1f3b9-105">[DNS 負載平衡] 會平衡 Lync Server 特有的網路流量，例如 SIP 流量及媒體流量。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="1f3b9-106">如果您部署 DNS 負載平衡，貴組織的硬體負載平衡器的系統管理開銷將會最小化。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="1f3b9-107">此外，對於與 SIP 流量的負載平衡程式配置錯誤相關的問題，複雜的疑難排解將會消失。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="1f3b9-108">您也可以避免伺服器連線，以便讓伺服器離線。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="1f3b9-109">DNS 負載平衡也可確保硬體負載平衡器問題不會影響 SIP 流量的元素，例如基本呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="1f3b9-110">如果您使用 DNS 負載平衡，您可能也可以購買成本較低的硬體負載平衡器，而不是在所有類型的流量中使用硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="1f3b9-111">您應該使用與 Lync Server 經過互通性驗證測試的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="1f3b9-112">如需有關負載平衡程式互通性測試的詳細資料，請參閱「Lync [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)Server 2010 負載平衡器合作夥伴」。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="1f3b9-113">前端池、邊緣伺服器池、控制器池和獨立的中繼伺服器池都支援 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="1f3b9-114">前端池與控制器池上的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1f3b9-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="1f3b9-115">您可以針對前端池和控制器池上的 SIP 流量使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-115">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="1f3b9-116">在部署 DNS 負載平衡的情況下，您仍然需要同時針對這些池使用硬體負載平衡器，但僅適用于用戶端到伺服器的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-116">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="1f3b9-117">硬體負載平衡器用於來自埠443和80的用戶端的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-117">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="1f3b9-118">雖然您仍需要這些池的硬體負載平衡器，但它們的設定和管理主要是針對 HTTPS 流量（硬體負載平衡器的系統管理員習慣）。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="1f3b9-119">DNS 負載平衡及支援舊版用戶端和伺服器</span><span class="sxs-lookup"><span data-stu-id="1f3b9-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="1f3b9-120">DNS 負載平衡只支援執行 Lync Server 2013 或 Lync Server 2010 的伺服器以及 Lync 2013 和 Lync 2010 用戶端的自動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="1f3b9-121">較舊版本的用戶端和 Office 通訊伺服器仍可連線到執行 DNS 負載平衡的池，但如果它們無法連線到 DNS 負載平衡所參照的第一個伺服器，則它們無法容錯移轉至池中的另一台伺服器.</span><span class="sxs-lookup"><span data-stu-id="1f3b9-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="1f3b9-122">此外，如果您使用的是 Exchange UM，您必須至少使用 Exchange 2010 SP1，才能取得 Lync Server DNS 負載平衡的支援。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="1f3b9-123">如果您使用的是舊版 Exchange，您的使用者將沒有這些 Exchange UM 案例的容錯移轉功能：</span><span class="sxs-lookup"><span data-stu-id="1f3b9-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="1f3b9-124">在電話上播放企業語音信箱</span><span class="sxs-lookup"><span data-stu-id="1f3b9-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="1f3b9-125">轉移來自 Exchange UM 自動語音應答的呼叫</span><span class="sxs-lookup"><span data-stu-id="1f3b9-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="1f3b9-126">所有其他 Exchange UM 案例都會正常運作。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="1f3b9-127">在前端池和控制器池上部署 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1f3b9-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="1f3b9-128">在前端池和控制器池上部署 DNS 負載平衡，您需要執行幾個額外步驟，使用 Fqdn 和 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="1f3b9-129">使用 DNS 負載平衡的池必須有兩個 Fqdn：由 DNS 負載平衡所使用的一般池 FQDN （例如 pool01.contoso.com），並解析成池中伺服器的實際 Ip，以及該池 Web 服務的另一個 FQDN （例如web01.contoso.com），可解析為池的虛擬 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="1f3b9-130">在拓撲建立器中，如果您想要為池的 Web 服務部署 DNS 負載平衡，您必須選取 [覆**寫內部 Web 服務池 FQDN** ] 核取方塊，然後在 [**指定適用于此池的 Web 服務 url** ] 頁面上輸入 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="1f3b9-131">若要支援 DNS 負載平衡所使用的 FQDN，您必須提供 DNS，以將池 FQDN （例如 pool01.contoso.com）解析為池中所有伺服器的 IP 位址（例如，192.168.1.1、192.168.1.2 等等）。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-131">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="1f3b9-132">您應該只包含目前已部署之伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-132">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1f3b9-133">如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="1f3b9-134">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="1f3b9-135">如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="1f3b9-136">如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須與任何其他的前端池、控制器或主管池是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="1f3b9-137">Edge 伺服器池中的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1f3b9-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="1f3b9-138">您可以在 Edge 伺服器池中部署 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-138">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="1f3b9-139">如果您這樣做，您必須知道一些考慮。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-139">If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="1f3b9-140">在邊緣伺服器上使用 DNS 負載平衡，會造成下列案例中的容錯移轉能力損失：</span><span class="sxs-lookup"><span data-stu-id="1f3b9-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="1f3b9-141">與執行 Lync Server 2010 之前發行之 Office 通訊伺服器版本之組織的同盟。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="1f3b9-142">與公用立即訊息（IM）服務 AOLand Yahoo\!的使用者，以及 Google 交談等 XMPP 提供者和伺服器以外的立即訊息交換。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="1f3b9-143">Google 交談目前是唯一支援的 XMPP 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1f3b9-144">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1f3b9-145">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="1f3b9-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1f3b9-146">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="1f3b9-147">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="1f3b9-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1f3b9-148">已公佈。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-148">has been announced.</span></span> <span data-ttu-id="1f3b9-149">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="1f3b9-150">只要池中的所有邊緣伺服器都已啟動並執行，這些案例就能正常運作，但如果沒有一個 Edge 伺服器無法使用，傳送給它的這些案例的任何要求都會失敗，而不是路由到另一個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="1f3b9-151">如果您使用的是 Exchange UM，您必須使用 Exchange 2013 的最低限度，才能在 Edge 上取得 Lync Server DNS 負載平衡的支援。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="1f3b9-152">如果您使用的是舊版 Exchange，您的遠端使用者將沒有這些 Exchange UM 案例的容錯移轉功能：</span><span class="sxs-lookup"><span data-stu-id="1f3b9-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="1f3b9-153">在電話上播放企業語音信箱</span><span class="sxs-lookup"><span data-stu-id="1f3b9-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="1f3b9-154">轉移來自 Exchange UM 自動語音應答的呼叫</span><span class="sxs-lookup"><span data-stu-id="1f3b9-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="1f3b9-155">所有其他 Exchange UM 案例都會正常運作。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="1f3b9-156">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-156">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="1f3b9-157">您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-157">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="1f3b9-158">在 Edge 伺服器池中部署 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1f3b9-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="1f3b9-159">若要在 Edge 伺服器池的外部介面上部署 DNS 負載平衡，您需要下列 DNS 專案：</span><span class="sxs-lookup"><span data-stu-id="1f3b9-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="1f3b9-160">針對存取邊緣服務，您需要為池中的每個伺服器加入一個專案。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1f3b9-161">每個專案都必須將存取邊緣服務（例如，sip.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的存取邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="1f3b9-162">針對網路會議 Edge 服務，池中的每個伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1f3b9-163">每個專案都必須將網路會議 Edge 服務（例如，webconf.contoso.com）的 FQDN 解析成池中某個邊緣伺服器的網路會議 Edge 服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="1f3b9-164">針對音訊/視頻邊緣服務，池中的每個伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1f3b9-165">每個專案都必須將音訊/視頻邊緣服務（例如，av.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="1f3b9-166">若要在 Edge 伺服器池的內部介面上部署 DNS 負載平衡，您必須加入一個 DNS A 記錄，該記錄會將 Edge 伺服器池的內部 FQDN 解析成池中每個伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="1f3b9-167">在中繼伺服器池中使用 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1f3b9-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="1f3b9-168">您可以在獨立的中繼伺服器池上使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-168">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="1f3b9-169">所有 SIP 和媒體流量都是透過 DNS 負載平衡來平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-169">All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="1f3b9-170">若要在轉送伺服器池中部署 DNS 負載平衡，您必須建立 DNS，以將池 FQDN （例如，mediationpool1.contoso.com）解析成池中所有伺服器的 IP 位址（例如，192.168.1.1、192.168.1.2 等）。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="1f3b9-171">使用 DNS 負載平衡封鎖伺服器的流量</span><span class="sxs-lookup"><span data-stu-id="1f3b9-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="1f3b9-172">如果您使用 DNS 負載平衡，而且您需要封鎖流量至特定電腦，則只需從池 FQDN 中移除 IP 位址專案是不夠的。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-172">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="1f3b9-173">您也必須移除電腦的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-173">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="1f3b9-174">請注意，對於伺服器到伺服器的流量，Lync Server 2013 使用拓撲感知負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="1f3b9-175">伺服器會在中央管理儲存體中讀取已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器之間自動散佈流量。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="1f3b9-176">若要封鎖伺服器接收伺服器對伺服器流量，您必須從拓撲中移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f3b9-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

