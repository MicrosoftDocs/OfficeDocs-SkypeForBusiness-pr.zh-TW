---
title: Lync Server 2013： 前端集區的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae56cdf07ae76ca0499050574793421864de818
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="20fd2-102">Lync Server 2013 中的前端集區的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="20fd2-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20fd2-103">_**主題上次修改日期：** 2012年-11-07_</span><span class="sxs-lookup"><span data-stu-id="20fd2-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="20fd2-104">本節描述部署前端集區所需的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="20fd2-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="20fd2-105">前端集區的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="20fd2-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="20fd2-106">下表指定 Lync Server 2013 前端集區部署的 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="20fd2-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="20fd2-107">前端集區的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="20fd2-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20fd2-108">部署案例</span><span class="sxs-lookup"><span data-stu-id="20fd2-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="20fd2-109">DNS 需求</span><span class="sxs-lookup"><span data-stu-id="20fd2-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fd2-110">前端集區使用多個前端伺服器和硬體負載平衡器 （無論該集區上也部署 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="20fd2-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="20fd2-111">使用 DNS 負載平衡與硬體負載平衡器，您需要主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="20fd2-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="20fd2-112">建立內部完整的網域名稱 (FQDN) 解析一筆記錄的 DNS 負載平衡的前端集區。</span><span class="sxs-lookup"><span data-stu-id="20fd2-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="20fd2-113">建立負載平衡器的虛擬 IP (VIP) 位址的內部主機 (A) 記錄的內部 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="20fd2-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="20fd2-114">拓撲產生器中所定義，您必須使用的內部 Web 服務名稱。</span><span class="sxs-lookup"><span data-stu-id="20fd2-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="20fd2-115">例如，如果您使用 DNS 負載平衡與硬體負載平衡，您會有每個前端伺服器的 DNS 負載平衡集區中的記錄以及指向硬體負載平衡器虛擬 IP 的內部 Web 服務之 A 記錄:</span><span class="sxs-lookup"><span data-stu-id="20fd2-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="20fd2-116">DNS 負載平衡： 集區 10.10.10.5 的 Pool01.contoso.net IP 位址</span><span class="sxs-lookup"><span data-stu-id="20fd2-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="20fd2-117">每個前端伺服器也會有不同的記錄：</span><span class="sxs-lookup"><span data-stu-id="20fd2-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="20fd2-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="20fd2-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="20fd2-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="20fd2-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="20fd2-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="20fd2-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="20fd2-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="20fd2-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="20fd2-122">硬體負載平衡： WebInternal.contoso.net IP 位址 HLB VIP 192.168.10.5 的</span><span class="sxs-lookup"><span data-stu-id="20fd2-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="20fd2-123">HTTP/HTTPS 流量除外的所有流量將都使用的 Pool01.contoso.net 筆記錄。</span><span class="sxs-lookup"><span data-stu-id="20fd2-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="20fd2-124">用以定義內部 Web 服務位址 192.168.10.5 的 HTTP/HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="20fd2-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fd2-125">前端集區的 DNS 負載平衡部署</span><span class="sxs-lookup"><span data-stu-id="20fd2-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="20fd2-126">內部的一組記錄集區中的每一部伺服器的 IP 位址的集區 FQDN 必須解決。</span><span class="sxs-lookup"><span data-stu-id="20fd2-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="20fd2-127">那里必須針對每部伺服器集區中的一個 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="20fd2-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20fd2-128">前端集區的 DNS 負載平衡部署</span><span class="sxs-lookup"><span data-stu-id="20fd2-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="20fd2-129">內部的一組記錄在該伺服器的 IP 位址的集區中，該解決每部伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="20fd2-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="20fd2-130">如需詳細資訊，請參閱規劃文件中的<a href="lync-server-2013-dns-load-balancing.md">DNS 負載平衡 Lync Server 2013 中</a>。</span><span class="sxs-lookup"><span data-stu-id="20fd2-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fd2-131">前端集區具有單一前端伺服器和專用的後端資料庫但無負載平衡器</span><span class="sxs-lookup"><span data-stu-id="20fd2-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="20fd2-132">一筆內部 A 記錄，解析為前端集區的 FQDN 為單一 Enterprise Edition 前端伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="20fd2-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20fd2-133">自動用戶端登入</span><span class="sxs-lookup"><span data-stu-id="20fd2-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="20fd2-134">每個支援的 SIP 網域，_sipinternaltls._tcp 的 SRV 記錄。&lt;網域&gt;透過連接埠 5061，對應到驗證，並將登入的用戶端要求重新導向的前端集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="20fd2-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="20fd2-135">如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS 需求的用戶端自動登入 Lync Server 2013 中</a>。</span><span class="sxs-lookup"><span data-stu-id="20fd2-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fd2-136">整合通訊 (UC) 裝置的裝置更新 Web 服務探索</span><span class="sxs-lookup"><span data-stu-id="20fd2-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="20fd2-137">一筆內部 A 記錄名稱 ucupdates-r2。&lt;SIP 網域&gt;，解析為前端集區主控的裝置更新 Web 服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="20fd2-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="20fd2-138">在其中 UC 裝置已開啟，但使用者永遠不登入裝置情況下，A 記錄可讓探索主控裝置更新 Web 服務的前端集區，並取得更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="20fd2-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="20fd2-139">否則，裝置取得這項資訊，但是頻內佈建使用者登入第一次。</span><span class="sxs-lookup"><span data-stu-id="20fd2-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="20fd2-140">如果您有裝置更新 Web 服務的現有部署 Lync Server 2010 中，您已經建立一筆內部 A 記錄與名稱 ucupdates-r2。&lt;SIP 網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="20fd2-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="20fd2-141">對於 Microsoft Office Communications Server 2007 R2，您必須建立額外的 DNS A 記錄與名稱 ucupdates-r2。&lt;SIP 網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="20fd2-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20fd2-142">支援 HTTP 流量的反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="20fd2-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="20fd2-143">一筆外部 A 記錄，將外部 Web 伺服陣列 FQDN 解析為反向 Proxy 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="20fd2-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="20fd2-144">用戶端和 UC 裝置會使用這個記錄來連線至反向 Proxy。</span><span class="sxs-lookup"><span data-stu-id="20fd2-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="20fd2-145">如需詳細資訊，請參閱規劃文件中的<a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 的判斷 DNS 需求</a>。</span><span class="sxs-lookup"><span data-stu-id="20fd2-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20fd2-146">下表顯示所需的內部 web 伺服陣列 FQDN 的 DNS 記錄範例。</span><span class="sxs-lookup"><span data-stu-id="20fd2-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="20fd2-147">內部 Web 伺服陣列 FQDN 的 DNS 記錄範例</span><span class="sxs-lookup"><span data-stu-id="20fd2-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20fd2-148">內部 web 伺服陣列 FQDN</span><span class="sxs-lookup"><span data-stu-id="20fd2-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="20fd2-149">集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="20fd2-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="20fd2-150">DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="20fd2-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20fd2-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20fd2-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20fd2-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20fd2-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20fd2-153">Ee-pool.contoso.com 的解析為前端伺服器所用負載平衡器的 VIP 位址的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="20fd2-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="20fd2-154">會解析為前端伺服器所用負載平衡器的 VIP 位址的 webcon.contoso.com 的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="20fd2-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20fd2-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20fd2-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20fd2-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20fd2-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20fd2-157">Ee-pool.contoso.com 的且可使用 Enterprise Edition 前端伺服器的前端集區中的負載平衡器虛擬 IP (VIP) 位址解析的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="20fd2-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="20fd2-158">請注意，是否您使用 DNS 負載平衡此集區上，您的前端集區和內部 web 伺服陣列不能有相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="20fd2-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

