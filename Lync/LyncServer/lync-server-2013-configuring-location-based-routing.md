---
title: Lync Server 2013：設定 Location-Based 路由
description: Lync Server 2013：設定 Location-Based 路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570879"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="b7ec8-103">在 Lync Server 2013 中設定 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="b7ec8-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7ec8-104">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="b7ec8-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="b7ec8-105">Lync Server 2013 CU1，Location-Based 路由是 Enterprise Voice 的功能。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="b7ec8-106">Location-Based 路由是通話管理功能，可控制 Lync Server 2013 CU1 路由傳送通話的方式。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="b7ec8-107">它會根據 Lync 來電者的位置，強制限制通話是否可路由傳送至 PBX 或 PSTN 目的地。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="b7ec8-108">Location-Based 路由根據來電者的網路位置，對 PSTN 通話套用呼叫授權規則。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="b7ec8-109">來電者的位置取決於與來電者相連之網路子網相關聯的網路網站。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="b7ec8-110">設定 Location-Based 路由需要先部署企業語音，然後設定網路地區、網站和子網。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="b7ec8-111">這會設定啟用 Location-Based 路由的基礎。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="b7ec8-112">在部署 Location-Based 路由之前，您必須先部署 Enterprise Voice，並設定網路地區、網站，並將網路子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="b7ec8-113">完成後，您可以設定 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="b7ec8-114">如需如何設定網路地區、網站及子網的步驟，請參閱 [在 Lync Server 2013 中部署高級 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="b7ec8-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="b7ec8-115">本節會逐步引導您使用下列範例做為 Location-Based 路由的設定，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="b7ec8-116">![Enterprise Voice 位置-基礎路由範例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 位置-基礎路由範例")</span><span class="sxs-lookup"><span data-stu-id="b7ec8-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="b7ec8-117">下表代表本範例中定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7ec8-118">端點類型</span><span class="sxs-lookup"><span data-stu-id="b7ec8-118">Endpoint type</span></span></th>
<th><span data-ttu-id="b7ec8-119">位置</span><span class="sxs-lookup"><span data-stu-id="b7ec8-119">Location</span></span></th>
<th><span data-ttu-id="b7ec8-120">使用者</span><span class="sxs-lookup"><span data-stu-id="b7ec8-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7ec8-121">Lync</span><span class="sxs-lookup"><span data-stu-id="b7ec8-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-122">新德里公司辦公室</span><span class="sxs-lookup"><span data-stu-id="b7ec8-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-123">DEL-LYNC-1、DEL-LYNC-2、DEL-3</span><span class="sxs-lookup"><span data-stu-id="b7ec8-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7ec8-124">Lync</span><span class="sxs-lookup"><span data-stu-id="b7ec8-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-125">Hyderabad 公司辦公室</span><span class="sxs-lookup"><span data-stu-id="b7ec8-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-126">HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="b7ec8-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7ec8-127">Lync</span><span class="sxs-lookup"><span data-stu-id="b7ec8-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-128">未知的 (，例如旅館) </span><span class="sxs-lookup"><span data-stu-id="b7ec8-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-129">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="b7ec8-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7ec8-130">Pbx</span><span class="sxs-lookup"><span data-stu-id="b7ec8-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-131">新德里公司辦公室</span><span class="sxs-lookup"><span data-stu-id="b7ec8-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-132">DEL-PBX-1、DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="b7ec8-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7ec8-133">Pbx</span><span class="sxs-lookup"><span data-stu-id="b7ec8-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-134">Hyderabad 公司辦公室</span><span class="sxs-lookup"><span data-stu-id="b7ec8-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-135">HYD-PBX-1、HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="b7ec8-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7ec8-136">Pstn</span><span class="sxs-lookup"><span data-stu-id="b7ec8-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-137">Unknown</span><span class="sxs-lookup"><span data-stu-id="b7ec8-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-138">PSTN-1、PSTN-2、PSTN-3</span><span class="sxs-lookup"><span data-stu-id="b7ec8-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="b7ec8-139">下表代表此範例環境中所述的系統。</span><span class="sxs-lookup"><span data-stu-id="b7ec8-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7ec8-140">系統</span><span class="sxs-lookup"><span data-stu-id="b7ec8-140">System</span></span></th>
<th><span data-ttu-id="b7ec8-141">位置</span><span class="sxs-lookup"><span data-stu-id="b7ec8-141">Location</span></span></th>
<th><span data-ttu-id="b7ec8-142">姓名</span><span class="sxs-lookup"><span data-stu-id="b7ec8-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7ec8-143">Lync Server 2013 CU1 集區</span><span class="sxs-lookup"><span data-stu-id="b7ec8-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-144">任何</span><span class="sxs-lookup"><span data-stu-id="b7ec8-144">any</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-145">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="b7ec8-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7ec8-146">Lync Server 2013 CU1，轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="b7ec8-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-147">任何</span><span class="sxs-lookup"><span data-stu-id="b7ec8-147">any</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-148">毫秒-PL1</span><span class="sxs-lookup"><span data-stu-id="b7ec8-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7ec8-149">PSTN 閘道1</span><span class="sxs-lookup"><span data-stu-id="b7ec8-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-150">德里</span><span class="sxs-lookup"><span data-stu-id="b7ec8-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-151">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="b7ec8-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7ec8-152">PSTN 閘道2</span><span class="sxs-lookup"><span data-stu-id="b7ec8-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-153">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="b7ec8-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-154">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="b7ec8-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7ec8-155">PBX 1</span><span class="sxs-lookup"><span data-stu-id="b7ec8-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-156">德里</span><span class="sxs-lookup"><span data-stu-id="b7ec8-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-157">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="b7ec8-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7ec8-158">PBX 2</span><span class="sxs-lookup"><span data-stu-id="b7ec8-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-159">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="b7ec8-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="b7ec8-160">RED PBX</span><span class="sxs-lookup"><span data-stu-id="b7ec8-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="b7ec8-161">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b7ec8-161">In This Section</span></span>

  - [<span data-ttu-id="b7ec8-162">在 Lync Server 2013 中設定企業語音</span><span class="sxs-lookup"><span data-stu-id="b7ec8-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="b7ec8-163">在 Lync Server 2013 中部署網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="b7ec8-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="b7ec8-164">在 Lync Server 2013 中啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="b7ec8-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7ec8-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b7ec8-165">See Also</span></span>


[<span data-ttu-id="b7ec8-166">在 Lync Server 2013 中部署高級 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="b7ec8-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

