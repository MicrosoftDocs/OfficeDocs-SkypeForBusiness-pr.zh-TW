---
title: Lync Server 2013： DNS 摘要-單一 Director
description: Lync Server 2013： DNS 摘要-單一 Director。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553229"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="bf00c-103">Lync Server 2013 中的 DNS 摘要-單一 Director</span><span class="sxs-lookup"><span data-stu-id="bf00c-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf00c-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bf00c-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bf00c-105">下表包含支援單一 Director 所需之 DNS 記錄的摘要。</span><span class="sxs-lookup"><span data-stu-id="bf00c-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="bf00c-106">Director 的角色需要與前端伺服器類似的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="bf00c-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="bf00c-107">所需的記錄數目會反映在 Director 憑證所需的主體替代名稱中。</span><span class="sxs-lookup"><span data-stu-id="bf00c-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="bf00c-108">與前端伺服器不同的是，Director 不會主控使用者帳戶或主控行動性服務。</span><span class="sxs-lookup"><span data-stu-id="bf00c-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="bf00c-109">Director 所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="bf00c-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf00c-110">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="bf00c-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="bf00c-111">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="bf00c-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="bf00c-112">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="bf00c-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="bf00c-113">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="bf00c-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf00c-114">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="bf00c-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bf00c-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bf00c-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bf00c-116">Director</span><span class="sxs-lookup"><span data-stu-id="bf00c-116">Director</span></span></p></td>
<td><p><span data-ttu-id="bf00c-117">用於複寫和伺服器對伺服器的 Director 主機記錄</span><span class="sxs-lookup"><span data-stu-id="bf00c-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf00c-118">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="bf00c-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bf00c-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf00c-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bf00c-120">Director</span><span class="sxs-lookup"><span data-stu-id="bf00c-120">Director</span></span></p></td>
<td><p><span data-ttu-id="bf00c-121">從 Edge Server 的內部 Edge 介面 (SIP) 的輸入會話初始通訊協定</span><span class="sxs-lookup"><span data-stu-id="bf00c-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf00c-122">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="bf00c-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bf00c-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf00c-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bf00c-124">Director</span><span class="sxs-lookup"><span data-stu-id="bf00c-124">Director</span></span></p></td>
<td><p><span data-ttu-id="bf00c-125">從反向 Proxy 發行的 Dialin Web 服務</span><span class="sxs-lookup"><span data-stu-id="bf00c-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf00c-126">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="bf00c-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bf00c-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf00c-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bf00c-128">Director</span><span class="sxs-lookup"><span data-stu-id="bf00c-128">Director</span></span></p></td>
<td><p><span data-ttu-id="bf00c-129">從反向 Proxy 發行的會議 Web 服務</span><span class="sxs-lookup"><span data-stu-id="bf00c-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf00c-130">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="bf00c-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="bf00c-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf00c-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bf00c-132">Director</span><span class="sxs-lookup"><span data-stu-id="bf00c-132">Director</span></span></p></td>
<td><p><span data-ttu-id="bf00c-133">由 Director 的反向 proxy Web 票證外部 Web 服務所發行及定義</span><span class="sxs-lookup"><span data-stu-id="bf00c-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

