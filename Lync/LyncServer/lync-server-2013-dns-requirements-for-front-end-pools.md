---
title: Lync Server 2013：前端池的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="be864-102">Lync Server 2013 中前端池的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="be864-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be864-103">_**主題上次修改日期：** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="be864-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="be864-104">本節說明部署前端池所需的網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="be864-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="be864-105">前端池的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="be864-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="be864-106">下表指定 Lync Server 2013 前端池部署的 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="be864-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="be864-107">前端池的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="be864-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be864-108">部署案例</span><span class="sxs-lookup"><span data-stu-id="be864-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="be864-109">DNS 需求</span><span class="sxs-lookup"><span data-stu-id="be864-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be864-110">具有多個前端伺服器和硬體負載平衡器的前端池（無論是否也在該池中部署 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="be864-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="be864-111">同時使用 DNS 負載平衡與硬體負載平衡器時，您必須裝載（A）記錄。</span><span class="sxs-lookup"><span data-stu-id="be864-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="be864-112">建立可解析 DNS 負載平衡之前端池的完整功能變數名稱（FQDN）的內部 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="be864-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="be864-113">在負載平衡器的虛擬 IP （VIP）位址建立內部 Web 服務的內部主機（A）記錄。</span><span class="sxs-lookup"><span data-stu-id="be864-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="be864-114">您必須使用 [拓撲建立器] 中定義的內部 Web 服務名稱。</span><span class="sxs-lookup"><span data-stu-id="be864-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="be864-115">例如，如果您同時使用 [DNS 負載平衡] 和 [硬體負載平衡]，您將會在 DNS 負載平衡的池中有一份記錄，並將內部 Web 服務的記錄指向硬體負載平衡器的虛擬 IP:</span><span class="sxs-lookup"><span data-stu-id="be864-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="be864-116">DNS 負載平衡： Pool01.contoso.net pool 10.10.10.5 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="be864-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="be864-117">每個前端伺服器也會有不同的 A 記錄：</span><span class="sxs-lookup"><span data-stu-id="be864-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="be864-118">FE01.contoso.net 10.10.10。1</span><span class="sxs-lookup"><span data-stu-id="be864-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="be864-119">FE02.contoso.net 10.10.10。2</span><span class="sxs-lookup"><span data-stu-id="be864-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="be864-120">FE03.contoso.net 10.10.10。3</span><span class="sxs-lookup"><span data-stu-id="be864-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="be864-121">FE04.contoso.net 10.10.10。4</span><span class="sxs-lookup"><span data-stu-id="be864-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="be864-122">硬體負載平衡： WebInternal.contoso.net HLB VIP 192.168.10.5 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="be864-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="be864-123">除 HTTP/HTTPS 流量以外的所有流量，都將使用 Pool01.contoso.net 記錄。</span><span class="sxs-lookup"><span data-stu-id="be864-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="be864-124">HTTP/HTTPS 流量將使用已定義的內部 Web 服務位址192.168.10。5</span><span class="sxs-lookup"><span data-stu-id="be864-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be864-125">已部署 DNS 負載平衡的前端池</span><span class="sxs-lookup"><span data-stu-id="be864-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="be864-126">一組內部 A 記錄，可將池的 FQDN 解析為池中每個伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="be864-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="be864-127">池中的每個伺服器都必須有一個記錄。</span><span class="sxs-lookup"><span data-stu-id="be864-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be864-128">已部署 DNS 負載平衡的前端池</span><span class="sxs-lookup"><span data-stu-id="be864-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="be864-129">一組內部 A 記錄，可將池中每個伺服器的 FQDN 解析為該伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="be864-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="be864-130">如需詳細資訊，請參閱規劃檔中的<a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 中的 DNS 負載平衡</a>。</span><span class="sxs-lookup"><span data-stu-id="be864-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be864-131">具有單一前端伺服器與專用後端資料庫但沒有負載平衡器的前端池</span><span class="sxs-lookup"><span data-stu-id="be864-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="be864-132">內部 A 記錄，可將前端池的 FQDN 解析為單一企業版前端伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="be864-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be864-133">自動用戶端登入</span><span class="sxs-lookup"><span data-stu-id="be864-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="be864-134">針對每個支援的 SIP 網域，_sipinternaltls _tcp 的 SRV 記錄。&lt;埠&gt; 5061 上的網域會對應到前端池的 FQDN，以驗證並重新導向用戶端的登入要求。</span><span class="sxs-lookup"><span data-stu-id="be864-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="be864-135">如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自動用戶端登入 DNS 需求</a>。</span><span class="sxs-lookup"><span data-stu-id="be864-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be864-136">透過整合通訊（UC）裝置進行的裝置更新 Web 服務探索</span><span class="sxs-lookup"><span data-stu-id="be864-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="be864-137">含 name ucupdates-r2 的內部 A 記錄。&lt;可解析&gt;為主機裝置更新 Web 服務之前端池之 IP 位址的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="be864-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="be864-138">在已開啟 UC 裝置但使用者從未登入裝置的情況下，A 記錄可讓裝置探索前端池託管裝置更新 Web 服務並取得更新。</span><span class="sxs-lookup"><span data-stu-id="be864-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="be864-139">否則，裝置會在使用者第一次登入時，透過頻帶內配來取得此資訊。</span><span class="sxs-lookup"><span data-stu-id="be864-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="be864-140">如果您已在 Lync Server 2010 中部署裝置更新 Web 服務，就表示您已使用名稱 ucupdates 建立了一個內部 A 記錄。&lt;SIP 網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="be864-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="be864-141">若是 Microsoft Office 通訊伺服器 2007 R2，您必須使用 name ucupdates-R2 建立額外的 DNS A 記錄。&lt;SIP 網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="be864-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be864-142">支援 HTTP 流量的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="be864-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="be864-143">外部 A 記錄，可將外部 web farm FQDN 解析成反向 proxy 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="be864-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="be864-144">用戶端和 UC 裝置使用此記錄連線到反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="be864-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="be864-145">如需詳細資訊，請參閱在規劃檔中<a href="lync-server-2013-determine-dns-requirements.md">判斷 Lync Server 2013 的 DNS 需求</a>。</span><span class="sxs-lookup"><span data-stu-id="be864-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be864-146">下表顯示內部網站集群 FQDN 所需的 DNS 記錄範例。</span><span class="sxs-lookup"><span data-stu-id="be864-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="be864-147">內部網路場 FQDN 的 DNS 記錄範例</span><span class="sxs-lookup"><span data-stu-id="be864-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be864-148">內部網站伺服器陣列 FQDN</span><span class="sxs-lookup"><span data-stu-id="be864-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="be864-149">池 FQDN</span><span class="sxs-lookup"><span data-stu-id="be864-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="be864-150">DNS A 記錄（s）</span><span class="sxs-lookup"><span data-stu-id="be864-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be864-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be864-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="be864-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be864-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="be864-153">Ee-pool.contoso.com 的 DNS A 記錄，可解析為前端伺服器所使用之負載平衡器的 VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="be864-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="be864-154">DNS A webcon.contoso.com 的記錄，可解析為前端伺服器所使用之負載平衡器的 VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="be864-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be864-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be864-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="be864-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be864-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="be864-157">DNS A ee-pool.contoso.com 的記錄，可解析為 [前端] 池中的企業版前端伺服器所使用之負載平衡器的虛擬 IP （VIP）位址。</span><span class="sxs-lookup"><span data-stu-id="be864-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="be864-158">請注意，如果您使用的是此 pool 的 DNS 負載平衡，您的前臺池和內部網路群不能有相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="be864-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

