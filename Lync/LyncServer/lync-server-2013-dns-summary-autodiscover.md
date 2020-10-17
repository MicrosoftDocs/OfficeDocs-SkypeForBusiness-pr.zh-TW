---
title: Lync Server 2013： DNS 摘要-自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc30b787d938825f229f28b10d54907ad26a4d35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501320"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="2a52c-102">Lync Server 2013 中的 DNS 摘要-自動探索</span><span class="sxs-lookup"><span data-stu-id="2a52c-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a52c-103">_**主題上次修改日期：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="2a52c-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="2a52c-104">自動探索是一種彈性服務，它會接受透過 HTTP 或 HTTPS 的通訊。</span><span class="sxs-lookup"><span data-stu-id="2a52c-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="2a52c-105">為了達到此目的，網域名稱系統 (DNS) ，而且必須正確地設定裝載自動探索服務之伺服器所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="2a52c-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="2a52c-106">憑證需求會在 [Lync Server 2013 的憑證摘要-自動](lync-server-2013-certificate-summary-autodiscover.md)探索中講述。</span><span class="sxs-lookup"><span data-stu-id="2a52c-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2a52c-107">Lync Server 用戶端的 DNS 查閱邏輯使用特定的解決順序。</span><span class="sxs-lookup"><span data-stu-id="2a52c-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="2a52c-108">您應無條件同時包含 lyncdiscoverinternal。 &lt;網域 &gt; 和 lyncdiscover。 &lt;&gt;DNS 中的網域。</span><span class="sxs-lookup"><span data-stu-id="2a52c-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="2a52c-109">排除 lyncdiscoverinternal。 &lt;網域 &gt; 記錄會導致內部用戶端無法連線至預定服務，或接收不正確的自動探索回應。</span><span class="sxs-lookup"><span data-stu-id="2a52c-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="2a52c-110">內部 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2a52c-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a52c-111">記錄類型</span><span class="sxs-lookup"><span data-stu-id="2a52c-111">Record type</span></span></th>
<th><span data-ttu-id="2a52c-112">主機名稱</span><span class="sxs-lookup"><span data-stu-id="2a52c-112">Host name</span></span></th>
<th><span data-ttu-id="2a52c-113">解析為</span><span class="sxs-lookup"><span data-stu-id="2a52c-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a52c-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="2a52c-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="2a52c-115">Lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="2a52c-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="2a52c-116">Director 集區的內部 Web 服務 FQDN （如果有的話），或如果您沒有 Director，則為前端集區。</span><span class="sxs-lookup"><span data-stu-id="2a52c-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a52c-117"> (主機，如果是 IPv6，AAAA) </span><span class="sxs-lookup"><span data-stu-id="2a52c-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="2a52c-118">lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="2a52c-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="2a52c-119">當您使用 Director 集區的負載平衡器) 時（如果您有一個或多個前端集區，則為 [內部 Web 服務] IP 位址 (虛擬 IP (VIP) 位址）。</span><span class="sxs-lookup"><span data-stu-id="2a52c-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2a52c-120">您需要建立下列其中一項外部 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="2a52c-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="2a52c-121">外部 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2a52c-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a52c-122">記錄類型</span><span class="sxs-lookup"><span data-stu-id="2a52c-122">Record type</span></span></th>
<th><span data-ttu-id="2a52c-123">主機名稱</span><span class="sxs-lookup"><span data-stu-id="2a52c-123">Host name</span></span></th>
<th><span data-ttu-id="2a52c-124">解析為</span><span class="sxs-lookup"><span data-stu-id="2a52c-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a52c-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="2a52c-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="2a52c-126">lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2a52c-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="2a52c-127">Director 集區的外部 Web 服務 FQDN （如果有的話），或如果您沒有 Director，則為前端集區。</span><span class="sxs-lookup"><span data-stu-id="2a52c-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a52c-128"> (主機，如果是 IPv6，AAAA) </span><span class="sxs-lookup"><span data-stu-id="2a52c-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="2a52c-129">lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="2a52c-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="2a52c-130">反向 proxy 的外部或公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2a52c-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2a52c-131">外部流量會通過反向 Proxy。</span><span class="sxs-lookup"><span data-stu-id="2a52c-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2a52c-132">行動裝置用戶端不支援來自不同網域的多個 Secure Sockets Layer (SSL) 憑證。</span><span class="sxs-lookup"><span data-stu-id="2a52c-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="2a52c-133">因此，不支援透過 HTTPS 將 CNAME 重新導向至不同的網域。</span><span class="sxs-lookup"><span data-stu-id="2a52c-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="2a52c-134">例如，不支援透過 HTTPS 將 lyncdiscover.contoso.com 的 DNS CNAME 記錄重新導向至 director.contoso.net 的位址。</span><span class="sxs-lookup"><span data-stu-id="2a52c-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="2a52c-135">在這樣的拓撲中，行動裝置用戶端需要使用 HTTP 來進行第一個要求，以透過 HTTP 來解析 CNAME 重新導向。</span><span class="sxs-lookup"><span data-stu-id="2a52c-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="2a52c-136">後續的要求則會使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="2a52c-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="2a52c-137">若要支援此案例，您需要以連接埠 80 的 Web 發行規則來設定反向 Proxy (HTTP)。</span><span class="sxs-lookup"><span data-stu-id="2a52c-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="2a52c-138">如需詳細資訊，請參閱在 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定行動的反向 proxy</A>中的「為埠80建立 web 發行規則」。</span><span class="sxs-lookup"><span data-stu-id="2a52c-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="2a52c-139">支援透過 HTTPS 將 CNAME 重新導向至相同網域。</span><span class="sxs-lookup"><span data-stu-id="2a52c-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="2a52c-140">在此情況下，目的網域的憑證會涵蓋原始網域。</span><span class="sxs-lookup"><span data-stu-id="2a52c-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a52c-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2a52c-141">See Also</span></span>


[<span data-ttu-id="2a52c-142">在 Lync Server 2013 中設定行動的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="2a52c-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="2a52c-143">Lync Server 2013 中的憑證摘要-自動探索</span><span class="sxs-lookup"><span data-stu-id="2a52c-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

