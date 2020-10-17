---
title: Lync Server 2013： DNS 摘要-調整式 Director 集區（硬體負載平衡器）
description: Lync Server 2013： DNS 摘要-調整式 Director 集區（硬體負載平衡器）。
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
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555879"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="240a1-103">Lync Server 2013 中的 DNS 摘要-調整式 Director 集區（硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="240a1-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="240a1-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="240a1-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="240a1-105">下表包含支援硬體負載平衡 Director 所需之 DNS 記錄的摘要。</span><span class="sxs-lookup"><span data-stu-id="240a1-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="240a1-106">Director 的角色需要與前端伺服器類似的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="240a1-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="240a1-107">所需的記錄數目會反映在 Director 憑證所需的主體替代名稱中。</span><span class="sxs-lookup"><span data-stu-id="240a1-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="240a1-108">與前端伺服器不同的是，Director 集區不會主控使用者帳戶或主控行動性服務。</span><span class="sxs-lookup"><span data-stu-id="240a1-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="240a1-109">使用硬體負載平衡器和 DNS 負載平衡之 Director 集區所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="240a1-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="240a1-110">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="240a1-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="240a1-111">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="240a1-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="240a1-112">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="240a1-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="240a1-113">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="240a1-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="240a1-114">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="240a1-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="240a1-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="240a1-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="240a1-116">Director</span><span class="sxs-lookup"><span data-stu-id="240a1-116">Director</span></span></p></td>
<td><p><span data-ttu-id="240a1-117">用於複寫和伺服器對伺服器通訊的 Director 主機記錄</span><span class="sxs-lookup"><span data-stu-id="240a1-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240a1-118">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="240a1-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="240a1-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="240a1-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="240a1-120">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="240a1-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="240a1-121">DNS 負載平衡 Director 集區的主機記錄</span><span class="sxs-lookup"><span data-stu-id="240a1-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240a1-122">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="240a1-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="240a1-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="240a1-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="240a1-124">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="240a1-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="240a1-125">來自 Edge Server 內部介面的輸入會話初始通訊協定 (SIP) </span><span class="sxs-lookup"><span data-stu-id="240a1-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240a1-126">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="240a1-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="240a1-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="240a1-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="240a1-128">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="240a1-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="240a1-129">來自反向 Proxy 的硬體負載平衡發行撥入式 Web 服務</span><span class="sxs-lookup"><span data-stu-id="240a1-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240a1-130">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="240a1-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="240a1-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="240a1-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="240a1-132">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="240a1-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="240a1-133">來自反向 Proxy 的硬體負載平衡發行會議 Web 服務</span><span class="sxs-lookup"><span data-stu-id="240a1-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240a1-134">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="240a1-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="240a1-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="240a1-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="240a1-136">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="240a1-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="240a1-137">針對 Director 集區的反向 proxy Web 票證外部 Web 服務發行及定義的硬體負載平衡</span><span class="sxs-lookup"><span data-stu-id="240a1-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

