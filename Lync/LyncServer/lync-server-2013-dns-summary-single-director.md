---
title: Lync Server 2013：DNS 摘要 - 單一 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca7fea825267dcdc5aa03a2e6c3c9fb3fc26a84b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="73d54-102">Lync Server 2013 中的 DNS 摘要 - 單一 Director</span><span class="sxs-lookup"><span data-stu-id="73d54-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73d54-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="73d54-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="73d54-104">下表列出支援單一控制器所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="73d54-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="73d54-105">Director 的角色需要類似的 DNS 記錄做為前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="73d54-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="73d54-106">所需的記錄數會反映在主管憑證上所需的使用中的替代名稱。</span><span class="sxs-lookup"><span data-stu-id="73d54-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="73d54-107">與前端伺服器不同的是，控制器不會主持使用者帳戶或主持行動服務。</span><span class="sxs-lookup"><span data-stu-id="73d54-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="73d54-108">主管所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="73d54-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73d54-109">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="73d54-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="73d54-110">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="73d54-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="73d54-111">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="73d54-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="73d54-112">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="73d54-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73d54-113">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="73d54-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73d54-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="73d54-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="73d54-115">Director</span><span class="sxs-lookup"><span data-stu-id="73d54-115">Director</span></span></p></td>
<td><p><span data-ttu-id="73d54-116">用於複製和伺服器到伺服器的控制器主機記錄</span><span class="sxs-lookup"><span data-stu-id="73d54-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d54-117">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="73d54-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73d54-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73d54-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73d54-119">Director</span><span class="sxs-lookup"><span data-stu-id="73d54-119">Director</span></span></p></td>
<td><p><span data-ttu-id="73d54-120">邊緣伺服器內部邊緣介面的入站會話初始通訊協定（SIP）</span><span class="sxs-lookup"><span data-stu-id="73d54-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d54-121">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="73d54-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73d54-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73d54-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73d54-123">Director</span><span class="sxs-lookup"><span data-stu-id="73d54-123">Director</span></span></p></td>
<td><p><span data-ttu-id="73d54-124">已從反向 proxy 發佈的撥入 web 服務</span><span class="sxs-lookup"><span data-stu-id="73d54-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73d54-125">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="73d54-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73d54-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73d54-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73d54-127">Director</span><span class="sxs-lookup"><span data-stu-id="73d54-127">Director</span></span></p></td>
<td><p><span data-ttu-id="73d54-128">已發佈從反向 proxy 的 web 服務發佈</span><span class="sxs-lookup"><span data-stu-id="73d54-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73d54-129">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="73d54-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73d54-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73d54-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73d54-131">Director</span><span class="sxs-lookup"><span data-stu-id="73d54-131">Director</span></span></p></td>
<td><p><span data-ttu-id="73d54-132">由主管的反向 proxy Web Ticket 外部 Web 服務發佈並定義</span><span class="sxs-lookup"><span data-stu-id="73d54-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

