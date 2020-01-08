---
title: Lync Server 2013： DNS 摘要-自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e303ebecc42f03197f6502296c8a2708e97ebf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="0e8a6-102">DNS 摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="0e8a6-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e8a6-103">_**主題上次修改日期：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="0e8a6-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="0e8a6-104">自動探索是一種靈活的服務，因為它會接受經由 HTTP 或 HTTPS 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="0e8a6-105">若要完成這項作業，必須正確設定作為自動探索服務之宿主伺服器所使用的網域名稱系統（DNS）與證書。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="0e8a6-106">證書需求已在[Lync Server 2013 的 [認證摘要] 自動](lync-server-2013-certificate-summary-autodiscover.md)探索中講述。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e8a6-107">Lync Server 用戶端的 DNS 查閱邏輯使用特定的解析度順序。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="0e8a6-108">您永遠都必須包含 lyncdiscoverinternal。&lt;[&gt;網域] 和 [lyncdiscover]。&lt;您&gt;的 DNS 中的網域。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="0e8a6-109">不包括 lyncdiscoverinternal。&lt;網域&gt;記錄會導致內部用戶端無法連線至預期的服務，或接收不正確的自動探索回應。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="0e8a6-110">內部 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0e8a6-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e8a6-111">記錄類型</span><span class="sxs-lookup"><span data-stu-id="0e8a6-111">Record type</span></span></th>
<th><span data-ttu-id="0e8a6-112">主機名稱</span><span class="sxs-lookup"><span data-stu-id="0e8a6-112">Host name</span></span></th>
<th><span data-ttu-id="0e8a6-113">解析為</span><span class="sxs-lookup"><span data-stu-id="0e8a6-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e8a6-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="0e8a6-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-115">Lyncdiscoverinternal.&lt;內部網功能變數名稱稱&gt;</span><span class="sxs-lookup"><span data-stu-id="0e8a6-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-116">如果您有控制器池的內部 Web 服務 FQDN （如果有的話），或是您的 [前端] 池（如果您沒有主管）。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e8a6-117">A （如果是 IPv6、AAAA，則是主機）</span><span class="sxs-lookup"><span data-stu-id="0e8a6-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-118">lyncdiscoverinternal.&lt;內部網功能變數名稱稱&gt;</span><span class="sxs-lookup"><span data-stu-id="0e8a6-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-119">如果您沒有主管，則內部 Web 服務 IP 位址（虛擬 IP （VIP）位址是使用負載平衡器）（如果您有一個或多個 [前端] 池）。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0e8a6-120">您需要建立下列其中一個外部 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="0e8a6-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="0e8a6-121">外部 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0e8a6-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e8a6-122">記錄類型</span><span class="sxs-lookup"><span data-stu-id="0e8a6-122">Record type</span></span></th>
<th><span data-ttu-id="0e8a6-123">主機名稱</span><span class="sxs-lookup"><span data-stu-id="0e8a6-123">Host name</span></span></th>
<th><span data-ttu-id="0e8a6-124">解析為</span><span class="sxs-lookup"><span data-stu-id="0e8a6-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e8a6-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="0e8a6-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-126">lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="0e8a6-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-127">如果您有控制器池的外部 Web 服務 FQDN （如果有的話），或是您的 [前端] 池（如果您沒有主管）。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e8a6-128">A （如果是 IPv6、AAAA，則是主機）</span><span class="sxs-lookup"><span data-stu-id="0e8a6-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-129">lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="0e8a6-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="0e8a6-130">反向 proxy 的外部或公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="0e8a6-131">外部流量透過反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0e8a6-132">行動裝置用戶端不支援來自不同網域的多個安全通訊端層（SSL）憑證。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="0e8a6-133">因此，不支援在 HTTPS 上對不同網域進行 CNAME 重新導向。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="0e8a6-134">例如，在 HTTPS 中不支援重新導向 director.contoso.net 位址的 lyncdiscover.contoso.com 的 DNS CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="0e8a6-135">在這種拓撲中，行動裝置用戶端必須針對第一個要求使用 HTTP，才能透過 HTTP 解析 CNAME 重新導向。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="0e8a6-136">後續要求接著使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="0e8a6-137">若要支援這種情況，您必須使用埠80（HTTP）的 web 發佈規則來設定您的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="0e8a6-138">如需詳細資訊，請參閱在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定反向 proxy 以進行行動</A>中的 [針對埠80建立 web 發佈規則]。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="0e8a6-139">在 HTTPS 上支援 CNAME 重新導向至同一個網域。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="0e8a6-140">在這種情況下，目的地網域的憑證會涵蓋來源網域。</span><span class="sxs-lookup"><span data-stu-id="0e8a6-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e8a6-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="0e8a6-141">See Also</span></span>


[<span data-ttu-id="0e8a6-142">在 Lync Server 2013 中設定行動的反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="0e8a6-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="0e8a6-143">憑證摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="0e8a6-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

