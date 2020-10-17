---
title: Lync Server 2013： DNS 摘要-調整式 Director 集區（硬體負載平衡器）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7755acc815da690312d2f60c2348076b2231cc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501260"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="f5cbc-102">Lync Server 2013 中的 DNS 摘要-調整式 Director 集區（硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="f5cbc-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5cbc-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f5cbc-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f5cbc-104">下表包含支援硬體負載平衡 Director 所需之 DNS 記錄的摘要。</span><span class="sxs-lookup"><span data-stu-id="f5cbc-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="f5cbc-105">Director 的角色需要與前端伺服器類似的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="f5cbc-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="f5cbc-106">所需的記錄數目會反映在 Director 憑證所需的主體替代名稱中。</span><span class="sxs-lookup"><span data-stu-id="f5cbc-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="f5cbc-107">與前端伺服器不同的是，Director 集區不會主控使用者帳戶或主控行動性服務。</span><span class="sxs-lookup"><span data-stu-id="f5cbc-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="f5cbc-108">使用硬體負載平衡器和 DNS 負載平衡之 Director 集區所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="f5cbc-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5cbc-109">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="f5cbc-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f5cbc-110">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="f5cbc-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f5cbc-111">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="f5cbc-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f5cbc-112">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="f5cbc-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5cbc-113">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f5cbc-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f5cbc-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-115">Director</span><span class="sxs-lookup"><span data-stu-id="f5cbc-115">Director</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-116">用於複寫和伺服器對伺服器通訊的 Director 主機記錄</span><span class="sxs-lookup"><span data-stu-id="f5cbc-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5cbc-117">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f5cbc-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f5cbc-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-119">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f5cbc-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-120">DNS 負載平衡 Director 集區的主機記錄</span><span class="sxs-lookup"><span data-stu-id="f5cbc-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5cbc-121">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f5cbc-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5cbc-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-123">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f5cbc-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-124">來自 Edge Server 內部介面的輸入會話初始通訊協定 (SIP) </span><span class="sxs-lookup"><span data-stu-id="f5cbc-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5cbc-125">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f5cbc-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5cbc-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-127">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f5cbc-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-128">來自反向 Proxy 的硬體負載平衡發行撥入式 Web 服務</span><span class="sxs-lookup"><span data-stu-id="f5cbc-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5cbc-129">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f5cbc-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5cbc-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-131">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f5cbc-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-132">來自反向 Proxy 的硬體負載平衡發行會議 Web 服務</span><span class="sxs-lookup"><span data-stu-id="f5cbc-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5cbc-133">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f5cbc-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5cbc-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-135">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="f5cbc-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f5cbc-136">針對 Director 集區的反向 proxy Web 票證外部 Web 服務發行及定義的硬體負載平衡</span><span class="sxs-lookup"><span data-stu-id="f5cbc-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

