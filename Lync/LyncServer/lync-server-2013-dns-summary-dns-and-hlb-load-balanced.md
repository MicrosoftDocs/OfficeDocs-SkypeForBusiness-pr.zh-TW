---
title: Lync Server 2013： DNS 摘要-DNS 與 HLB 負載平衡
description: Lync Server 2013： DNS 摘要-DNS 與 HLB 負載平衡。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c191d653ce4025618e135b4c69bc673f79a6d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574259"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="12dd3-103">Lync Server 2013 中的 DNS 摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="12dd3-103">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12dd3-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="12dd3-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="12dd3-105">下表包含支援 DNS 負載平衡與硬體負載平衡 Director 所需之 DNS 記錄的摘要。</span><span class="sxs-lookup"><span data-stu-id="12dd3-105">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="12dd3-106">Director 的角色需要與前端伺服器類似的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="12dd3-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="12dd3-107">所需的記錄數目會反映在 Director 憑證所需的主體替代名稱中。</span><span class="sxs-lookup"><span data-stu-id="12dd3-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="12dd3-108">與前端伺服器不同的是，Director 集區不會主控使用者帳戶或主控行動性服務。</span><span class="sxs-lookup"><span data-stu-id="12dd3-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="12dd3-109">使用 DNS 負載平衡與硬體負載平衡器之 Director 集區所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="12dd3-109">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12dd3-110">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="12dd3-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="12dd3-111">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="12dd3-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="12dd3-112">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="12dd3-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="12dd3-113">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="12dd3-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12dd3-114">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="12dd3-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="12dd3-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="12dd3-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="12dd3-116">Director</span><span class="sxs-lookup"><span data-stu-id="12dd3-116">Director</span></span></p></td>
<td><p><span data-ttu-id="12dd3-117">用於複寫和伺服器對伺服器的 Director 主機記錄</span><span class="sxs-lookup"><span data-stu-id="12dd3-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12dd3-118">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="12dd3-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="12dd3-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="12dd3-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="12dd3-120">Director pool</span><span class="sxs-lookup"><span data-stu-id="12dd3-120">Director pool</span></span></p></td>
<td><p><span data-ttu-id="12dd3-121">伺服器至伺服器之 DNS 負載平衡 Director 集區的主機記錄</span><span class="sxs-lookup"><span data-stu-id="12dd3-121">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12dd3-122">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="12dd3-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="12dd3-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dd3-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12dd3-124">Director pool</span><span class="sxs-lookup"><span data-stu-id="12dd3-124">Director pool</span></span></p></td>
<td><p><span data-ttu-id="12dd3-125">來自 Edge Server 內部介面的輸入會話初始通訊協定 (SIP) </span><span class="sxs-lookup"><span data-stu-id="12dd3-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12dd3-126">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="12dd3-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="12dd3-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dd3-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12dd3-128">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="12dd3-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="12dd3-129">來自反向 Proxy 的硬體負載平衡發行撥入式 Web 服務</span><span class="sxs-lookup"><span data-stu-id="12dd3-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12dd3-130">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="12dd3-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="12dd3-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dd3-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12dd3-132">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="12dd3-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="12dd3-133">來自反向 Proxy 的硬體負載平衡發行會議 Web 服務</span><span class="sxs-lookup"><span data-stu-id="12dd3-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12dd3-134">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="12dd3-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="12dd3-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12dd3-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12dd3-136">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="12dd3-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="12dd3-137">針對 Director 集區的反向 proxy Web 票證外部 Web 服務發行及定義的硬體負載平衡</span><span class="sxs-lookup"><span data-stu-id="12dd3-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

