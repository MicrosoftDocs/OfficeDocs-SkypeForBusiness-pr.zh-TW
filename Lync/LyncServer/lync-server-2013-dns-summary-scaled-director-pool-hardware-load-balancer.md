---
title: 'Lync Server 2013: DNS 摘要-調整式 Director 集區、 硬體負載平衡器'
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
ms.openlocfilehash: 790b740e9f22c52a166759799fcb085dce453a25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="eafb0-102">DNS 摘要-調整式 Director 集區、 硬體負載平衡器在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eafb0-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eafb0-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="eafb0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="eafb0-104">下表包含摘要的 DNS 記錄所需支援的硬體負載平衡 Director。</span><span class="sxs-lookup"><span data-stu-id="eafb0-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="eafb0-105">Director 角色為前端伺服器需要類似的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="eafb0-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="eafb0-106">Director 憑證上所需的主體替代名稱會反映所需的記錄筆數。</span><span class="sxs-lookup"><span data-stu-id="eafb0-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="eafb0-107">不同於前端伺服器，Director 集區不會主控使用者帳戶或裝載行動服務。</span><span class="sxs-lookup"><span data-stu-id="eafb0-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="eafb0-108">使用硬體負載平衡器和 DNS 負載平衡的 Director 集區所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="eafb0-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eafb0-109">位置/類型/連接埠</span><span class="sxs-lookup"><span data-stu-id="eafb0-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="eafb0-110">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="eafb0-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="eafb0-111">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="eafb0-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="eafb0-112">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="eafb0-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eafb0-113">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="eafb0-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="eafb0-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="eafb0-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="eafb0-115">Director</span><span class="sxs-lookup"><span data-stu-id="eafb0-115">Director</span></span></p></td>
<td><p><span data-ttu-id="eafb0-116">用於複寫及伺服器對伺服器通訊的 director 主機記錄</span><span class="sxs-lookup"><span data-stu-id="eafb0-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eafb0-117">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="eafb0-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="eafb0-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="eafb0-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="eafb0-119">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="eafb0-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="eafb0-120">主機記錄，DNS 負載平衡 Director 集區</span><span class="sxs-lookup"><span data-stu-id="eafb0-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eafb0-121">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="eafb0-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="eafb0-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafb0-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eafb0-123">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="eafb0-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="eafb0-124">輸入工作階段初始通訊協定 (SIP) 從 Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="eafb0-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eafb0-125">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="eafb0-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="eafb0-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafb0-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eafb0-127">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="eafb0-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="eafb0-128">來自反向 Proxy 的硬體負載平衡發行撥入式 Web 服務</span><span class="sxs-lookup"><span data-stu-id="eafb0-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eafb0-129">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="eafb0-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="eafb0-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafb0-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eafb0-131">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="eafb0-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="eafb0-132">來自反向 Proxy 的硬體負載平衡發行會議 Web 服務</span><span class="sxs-lookup"><span data-stu-id="eafb0-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eafb0-133">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="eafb0-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="eafb0-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eafb0-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eafb0-135">Director 集區 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="eafb0-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="eafb0-136">硬體負載平衡、 發行和定義反向 proxy Web 票證外部 web 服務的 Director 集區</span><span class="sxs-lookup"><span data-stu-id="eafb0-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

