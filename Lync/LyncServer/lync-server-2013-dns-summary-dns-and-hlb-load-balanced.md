---
title: Lync Server 2013：DNS 摘要 - DNS 與 HLB 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="2d66a-102">Lync Server 2013 中的 DNS 摘要 - DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="2d66a-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d66a-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="2d66a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="2d66a-104">下表包含支援 DNS 負載平衡與硬體負載平衡控制器所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="2d66a-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="2d66a-105">Director 的角色需要類似的 DNS 記錄做為前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d66a-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="2d66a-106">所需的記錄數會反映在主管憑證上所需的使用中的替代名稱。</span><span class="sxs-lookup"><span data-stu-id="2d66a-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="2d66a-107">與前端伺服器不同的是，控制器池不會主持使用者帳戶或主持行動服務。</span><span class="sxs-lookup"><span data-stu-id="2d66a-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="2d66a-108">使用 DNS 負載平衡和硬體負載平衡器的控制器池所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2d66a-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d66a-109">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="2d66a-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2d66a-110">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2d66a-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="2d66a-111">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="2d66a-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="2d66a-112">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="2d66a-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d66a-113">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2d66a-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2d66a-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2d66a-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2d66a-115">Director</span><span class="sxs-lookup"><span data-stu-id="2d66a-115">Director</span></span></p></td>
<td><p><span data-ttu-id="2d66a-116">用於複製和伺服器到伺服器的控制器主機記錄</span><span class="sxs-lookup"><span data-stu-id="2d66a-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d66a-117">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2d66a-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2d66a-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2d66a-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2d66a-119">主管池</span><span class="sxs-lookup"><span data-stu-id="2d66a-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="2d66a-120">伺服器到伺服器的 DNS 負載平衡控制器池的主機記錄</span><span class="sxs-lookup"><span data-stu-id="2d66a-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d66a-121">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2d66a-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2d66a-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d66a-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2d66a-123">主管池</span><span class="sxs-lookup"><span data-stu-id="2d66a-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="2d66a-124">來自 Edge 伺服器內部介面的入站會話初始通訊協定（SIP）</span><span class="sxs-lookup"><span data-stu-id="2d66a-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d66a-125">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2d66a-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2d66a-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d66a-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2d66a-127">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="2d66a-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="2d66a-128">從反向 proxy 發佈的硬體負載平衡發佈的 web 服務</span><span class="sxs-lookup"><span data-stu-id="2d66a-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d66a-129">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2d66a-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2d66a-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d66a-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2d66a-131">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="2d66a-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="2d66a-132">已發佈的硬體負載平衡已公佈從反向 proxy 的 web 服務</span><span class="sxs-lookup"><span data-stu-id="2d66a-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d66a-133">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2d66a-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2d66a-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d66a-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2d66a-135">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="2d66a-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="2d66a-136">硬體負載平衡發佈，且由主管池的反向 proxy Web 入場券外部 Web 服務所定義</span><span class="sxs-lookup"><span data-stu-id="2d66a-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

