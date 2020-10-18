---
title: Lync Server 2013： DNS 負載平衡
description: Lync Server 2013： DNS 負載平衡。
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
ms.openlocfilehash: ba95604ca8f4007c76cedea9bf2a16dbd7db455c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574419"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="23260-103">Lync Server 2013 中的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="23260-103">DNS load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23260-104">_**主題上次修改日期：** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="23260-104">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="23260-105">Lync Server 可讓您在網路上大幅減少負載平衡之管理負荷的軟體解決方案，以進行 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="23260-105">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="23260-106">DNS 負載平衡會平衡 Lync 伺服器特有的網路流量，例如 SIP 流量和媒體流量。</span><span class="sxs-lookup"><span data-stu-id="23260-106">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="23260-107">如果您部署 DNS 負載平衡，您組織的硬體負載平衡器的管理系統開銷將會降到最低。</span><span class="sxs-lookup"><span data-stu-id="23260-107">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="23260-108">此外，負載平衡器中針對 SIP 流量的設定錯誤問題所涉及的複雜疑難排解也得以排除。</span><span class="sxs-lookup"><span data-stu-id="23260-108">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="23260-109">您也可以防止伺服器連線，以便將伺服器離線。</span><span class="sxs-lookup"><span data-stu-id="23260-109">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="23260-110">DNS 負載平衡也可以確保硬體負載平衡器問題不會影響基本通話路由等這類 SIP 流量元素。</span><span class="sxs-lookup"><span data-stu-id="23260-110">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="23260-111">相較於將硬體負載平衡器用於全部的流量類型，如果使用 DNS 負載平衡也能讓您購買成本較低的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="23260-111">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="23260-112">您應該使用已通過 Lync Server 的互通性驗證測試的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="23260-112">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="23260-113">如需負載平衡器互通性測試的詳細資訊，請參閱 at 中的「Lync Server 2010 負載平衡器合作夥伴」 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。</span><span class="sxs-lookup"><span data-stu-id="23260-113">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="23260-114">DNS 負載平衡支援前端集區、Edge Server 集區、Director 集區和獨立中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="23260-114">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="23260-115">前端集區和 Director 集區上的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="23260-115">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="23260-p104">您可以針對前端集區和 Director 集區上的 SIP 流量使用 DNS 負載平衡。部署 DNS 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限用戶端到伺服器的 HTTPS 流量。硬體負載平衡器會用於用戶端透過連接埠 443 和 80 送出的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="23260-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="23260-119">雖然這些集區仍然需要硬體負載平衡器，但是其設定和系統管理主要是針對 HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。</span><span class="sxs-lookup"><span data-stu-id="23260-119">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="23260-120">DNS 負載平衡以及支援的舊版用戶端和伺服器</span><span class="sxs-lookup"><span data-stu-id="23260-120">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="23260-121">DNS 負載平衡只支援執行 Lync Server 2013 或 Lync Server 2010 的伺服器，以及 Lync 2013 和 Lync 2010 用戶端的自動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="23260-121">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="23260-122">較舊版本的用戶端和 Office 通訊伺服器仍然可以連線到執行 DNS 負載平衡的集區，但如果這些集區無法連線至 DNS 負載平衡所參照的第一部伺服器，則他們無法容錯移轉至集區中的另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="23260-122">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="23260-123">此外，如果您使用 Exchange UM，您必須至少使用 Exchange 2010 SP1 以取得 Lync Server DNS 負載平衡的支援。</span><span class="sxs-lookup"><span data-stu-id="23260-123">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="23260-124">如果您使用舊版的 Exchange，您的使用者將不會有這些 Exchange UM 案例的容錯移轉功能：</span><span class="sxs-lookup"><span data-stu-id="23260-124">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="23260-125">在電話上播放企業語音語音信箱</span><span class="sxs-lookup"><span data-stu-id="23260-125">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="23260-126">從 Exchange UM 自動語音應答轉接通話</span><span class="sxs-lookup"><span data-stu-id="23260-126">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="23260-127">所有其他 Exchange UM 案例則會正常運作。</span><span class="sxs-lookup"><span data-stu-id="23260-127">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="23260-128">在前端集區和 Director 集區上部署 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="23260-128">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="23260-129">在前端集區和 Director 集區上部署 DNS 負載平衡，需要您對 FQDN 和 DNS 記錄執行一些額外步驟。</span><span class="sxs-lookup"><span data-stu-id="23260-129">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="23260-130">集區若要使用 DNS 負載平衡，必須要有兩個 FQDN：一個是供 DNS 負載平衡使用的一般集區 FQDN (如 pool01.contoso.com)，這會解析為集區中伺服器的實體 IP；另一個是集區的 Web 服務的 FQDN (如 web01.contoso.com)，這會解析為集區的虛擬 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23260-130">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="23260-131">在 [拓撲產生器] 中，如果您想要為集區部署 DNS 負載平衡，若要為集區的 Web 服務建立額外的 FQDN，您必須選取 [覆 **寫內部 Web 服務集區 FQDN** ] 核取方塊，然後在 [ **指定 Web 服務 URLs 中為此集** 區] 頁面中輸入 FQDN。</span><span class="sxs-lookup"><span data-stu-id="23260-131">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="23260-p107">若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23260-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="23260-134">如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="23260-134">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="23260-135">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="23260-135">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="23260-136">如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="23260-136">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="23260-137">如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="23260-137">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="23260-138">Edge Server 集區上的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="23260-138">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="23260-p109">您可以在 Edge Server 集區上部署 DNS 負載平衡。如果這麼做，則必須注意下列考量。</span><span class="sxs-lookup"><span data-stu-id="23260-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="23260-141">在 Edge Server 上使用 DNS 負載平衡，會導致下列案例喪失容錯移轉能力：</span><span class="sxs-lookup"><span data-stu-id="23260-141">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="23260-142">與執行 Lync Server 2010 之前發行之 Office 通訊伺服器版本的組織同盟。</span><span class="sxs-lookup"><span data-stu-id="23260-142">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="23260-143">與 \! XMPP 提供者和伺服器（如 Google 談話）以外的公開立即訊息使用者 (IM) Services AOLand Yahoo）的立即訊息交換。</span><span class="sxs-lookup"><span data-stu-id="23260-143">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="23260-144">Google 交談目前是唯一支援的 XMPP 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="23260-144">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="23260-145">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="23260-145">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="23260-146">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="23260-146">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="23260-147">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="23260-147">Messenger until the service shut down date.</span></span> <span data-ttu-id="23260-148">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="23260-148">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="23260-149">已宣告。</span><span class="sxs-lookup"><span data-stu-id="23260-149">has been announced.</span></span> <span data-ttu-id="23260-150">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="23260-150">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="23260-151">只要集區中的所有 Edge Server 都啟動並執行，這些案例就能運作，但是如果其中一個 Edge Server 無法使用，則在這些案例中任何傳送給該 Edge Server 的要求都會失敗，而不是路由至另一個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="23260-151">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="23260-152">如果您使用的是 Exchange UM，您必須至少使用 Exchange 2013，以取得對 Edge 的 Lync Server DNS 負載平衡的支援。</span><span class="sxs-lookup"><span data-stu-id="23260-152">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="23260-153">如果您使用舊版的 Exchange，您的遠端使用者將不會有這些 Exchange UM 案例的容錯移轉功能：</span><span class="sxs-lookup"><span data-stu-id="23260-153">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="23260-154">在電話上播放企業語音語音信箱</span><span class="sxs-lookup"><span data-stu-id="23260-154">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="23260-155">從 Exchange UM 自動語音應答轉接通話</span><span class="sxs-lookup"><span data-stu-id="23260-155">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="23260-156">所有其他 Exchange UM 案例則會正常運作。</span><span class="sxs-lookup"><span data-stu-id="23260-156">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="23260-p112">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="23260-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="23260-159">在 Edge Server 集區上部署 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="23260-159">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="23260-160">若要在 Edge Server 集區的外部介面上部署 DNS 負載平衡，您需要下列 DNS 項目：</span><span class="sxs-lookup"><span data-stu-id="23260-160">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="23260-161">對於 Access Edge service，集區中的每一部伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="23260-161">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="23260-162">每個專案都必須解析 Access Edge service (的 FQDN，例如，sip.contoso.com) 到集區中某一部 Edge Server 上的 Access Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23260-162">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="23260-163">針對 Web 會議 Edge service，集區中的每一部伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="23260-163">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="23260-164">每個專案都必須解析 Web 會議 Edge service (的 FQDN，例如，webconf.contoso.com) 至集區中某一部 Edge Server 上的 Web 會議 Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23260-164">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="23260-165">針對 Audio/Video Edge service，集區中的每一部伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="23260-165">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="23260-166">每個專案都必須解析 Audio/Video Edge service 的 FQDN (例如，av.contoso.com) 至集區中某一部 Edge Server 上的 A/V Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23260-166">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="23260-167">若要在 Edge Server 集區的內部介面上部署 DNS 負載平衡，您必須新增一筆 DNS A 記錄，並讓它將 Edge Server 集區的內部 FQDN 解析為集區中每部伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23260-167">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="23260-168">在中繼伺服器集區上使用 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="23260-168">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="23260-p116">您可以在獨立中繼伺服器集區上使用 DNS 負載平衡，所有 SIP 和媒體流量都是透過 DNS 負載平衡進行平衡處理。</span><span class="sxs-lookup"><span data-stu-id="23260-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="23260-171">若要在中繼伺服器集區上部署 DNS 負載平衡，您必須佈建 DNS，以將集區 FQDN (例如，mediationpool1.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。</span><span class="sxs-lookup"><span data-stu-id="23260-171">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="23260-172">使用 DNS 負載平衡封鎖伺服器的流量</span><span class="sxs-lookup"><span data-stu-id="23260-172">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="23260-173">如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。</span><span class="sxs-lookup"><span data-stu-id="23260-173">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="23260-174">您也必須移除電腦的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="23260-174">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="23260-175">請注意，針對伺服器對伺服器流量，Lync Server 2013 使用拓撲感知負載平衡。</span><span class="sxs-lookup"><span data-stu-id="23260-175">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="23260-176">伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。</span><span class="sxs-lookup"><span data-stu-id="23260-176">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="23260-177">若要封鎖伺服器接收伺服器對伺服器的流量，您必須從拓撲中移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="23260-177">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

