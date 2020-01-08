---
title: Lync Server 2013：DNS 摘要 - 調整式 Director 集區 (硬體負載平衡器)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff76d69952d08db72e5647b58e38a43b4181c8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="ee118-102">Lync Server 2013 中的 DNS 摘要 - 調整式 Director 集區 (硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="ee118-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee118-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ee118-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ee118-104">下表包含支援硬體負載平衡控制器所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="ee118-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="ee118-105">Director 的角色需要類似的 DNS 記錄做為前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ee118-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="ee118-106">所需的記錄數會反映在主管憑證上所需的使用中的替代名稱。</span><span class="sxs-lookup"><span data-stu-id="ee118-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="ee118-107">與前端伺服器不同的是，控制器池不會主持使用者帳戶或主持行動服務。</span><span class="sxs-lookup"><span data-stu-id="ee118-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="ee118-108">使用硬體負載平衡器和 DNS 負載平衡的主管池所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ee118-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee118-109">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="ee118-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="ee118-110">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ee118-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="ee118-111">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="ee118-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="ee118-112">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="ee118-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee118-113">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="ee118-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ee118-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ee118-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ee118-115">Director</span><span class="sxs-lookup"><span data-stu-id="ee118-115">Director</span></span></p></td>
<td><p><span data-ttu-id="ee118-116">用於複製和伺服器與伺服器通訊的控制器主機記錄</span><span class="sxs-lookup"><span data-stu-id="ee118-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee118-117">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="ee118-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ee118-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ee118-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ee118-119">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="ee118-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="ee118-120">DNS 負載平衡控制器池的主機記錄</span><span class="sxs-lookup"><span data-stu-id="ee118-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee118-121">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="ee118-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ee118-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee118-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ee118-123">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="ee118-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="ee118-124">來自 Edge 伺服器內部介面的入站會話初始通訊協定（SIP）</span><span class="sxs-lookup"><span data-stu-id="ee118-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee118-125">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="ee118-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ee118-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee118-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ee118-127">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="ee118-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="ee118-128">從反向 proxy 發佈的硬體負載平衡發佈的 web 服務</span><span class="sxs-lookup"><span data-stu-id="ee118-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee118-129">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="ee118-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ee118-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee118-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ee118-131">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="ee118-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="ee118-132">已發佈的硬體負載平衡已公佈從反向 proxy 的 web 服務</span><span class="sxs-lookup"><span data-stu-id="ee118-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee118-133">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="ee118-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ee118-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee118-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ee118-135">控制器泳池 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="ee118-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="ee118-136">硬體負載平衡發佈，且由主管池的反向 proxy Web 入場券外部 Web 服務所定義</span><span class="sxs-lookup"><span data-stu-id="ee118-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

