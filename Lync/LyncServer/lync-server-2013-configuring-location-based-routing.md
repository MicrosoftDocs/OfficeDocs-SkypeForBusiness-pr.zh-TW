---
title: Lync Server 2013：設定 Location-Based 路由
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
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517411"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="30119-102">在 Lync Server 2013 中設定 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="30119-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30119-103">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="30119-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="30119-104">Lync Server 2013 CU1，Location-Based 路由是 Enterprise Voice 的功能。</span><span class="sxs-lookup"><span data-stu-id="30119-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="30119-105">Location-Based 路由是通話管理功能，可控制 Lync Server 2013 CU1 路由傳送通話的方式。</span><span class="sxs-lookup"><span data-stu-id="30119-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="30119-106">它會根據 Lync 來電者的位置，強制限制通話是否可路由傳送至 PBX 或 PSTN 目的地。</span><span class="sxs-lookup"><span data-stu-id="30119-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="30119-107">Location-Based 路由根據來電者的網路位置，對 PSTN 通話套用呼叫授權規則。</span><span class="sxs-lookup"><span data-stu-id="30119-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="30119-108">來電者的位置取決於與來電者相連之網路子網相關聯的網路網站。</span><span class="sxs-lookup"><span data-stu-id="30119-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="30119-109">設定 Location-Based 路由需要先部署企業語音，然後設定網路地區、網站和子網。</span><span class="sxs-lookup"><span data-stu-id="30119-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="30119-110">這會設定啟用 Location-Based 路由的基礎。</span><span class="sxs-lookup"><span data-stu-id="30119-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="30119-111">在部署 Location-Based 路由之前，您必須先部署 Enterprise Voice，並設定網路地區、網站，並將網路子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="30119-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="30119-112">完成後，您可以設定 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="30119-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="30119-113">如需如何設定網路地區、網站及子網的步驟，請參閱 [在 Lync Server 2013 中部署高級 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="30119-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="30119-114">本節會逐步引導您使用下列範例做為 Location-Based 路由的設定，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="30119-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="30119-115">![Enterprise Voice 位置-基礎路由範例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 位置-基礎路由範例")</span><span class="sxs-lookup"><span data-stu-id="30119-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="30119-116">下表代表本範例中定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="30119-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30119-117">端點類型</span><span class="sxs-lookup"><span data-stu-id="30119-117">Endpoint type</span></span></th>
<th><span data-ttu-id="30119-118">位置</span><span class="sxs-lookup"><span data-stu-id="30119-118">Location</span></span></th>
<th><span data-ttu-id="30119-119">使用者</span><span class="sxs-lookup"><span data-stu-id="30119-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30119-120">Lync</span><span class="sxs-lookup"><span data-stu-id="30119-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="30119-121">新德里公司辦公室</span><span class="sxs-lookup"><span data-stu-id="30119-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="30119-122">DEL-LYNC-1、DEL-LYNC-2、DEL-3</span><span class="sxs-lookup"><span data-stu-id="30119-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30119-123">Lync</span><span class="sxs-lookup"><span data-stu-id="30119-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="30119-124">Hyderabad 公司辦公室</span><span class="sxs-lookup"><span data-stu-id="30119-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="30119-125">HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="30119-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30119-126">Lync</span><span class="sxs-lookup"><span data-stu-id="30119-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="30119-127">未知的 (，例如旅館) </span><span class="sxs-lookup"><span data-stu-id="30119-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="30119-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="30119-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30119-129">Pbx</span><span class="sxs-lookup"><span data-stu-id="30119-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="30119-130">新德里公司辦公室</span><span class="sxs-lookup"><span data-stu-id="30119-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="30119-131">DEL-PBX-1、DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="30119-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30119-132">Pbx</span><span class="sxs-lookup"><span data-stu-id="30119-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="30119-133">Hyderabad 公司辦公室</span><span class="sxs-lookup"><span data-stu-id="30119-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="30119-134">HYD-PBX-1、HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="30119-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30119-135">Pstn</span><span class="sxs-lookup"><span data-stu-id="30119-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="30119-136">Unknown</span><span class="sxs-lookup"><span data-stu-id="30119-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="30119-137">PSTN-1、PSTN-2、PSTN-3</span><span class="sxs-lookup"><span data-stu-id="30119-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="30119-138">下表代表此範例環境中所述的系統。</span><span class="sxs-lookup"><span data-stu-id="30119-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30119-139">系統</span><span class="sxs-lookup"><span data-stu-id="30119-139">System</span></span></th>
<th><span data-ttu-id="30119-140">位置</span><span class="sxs-lookup"><span data-stu-id="30119-140">Location</span></span></th>
<th><span data-ttu-id="30119-141">姓名</span><span class="sxs-lookup"><span data-stu-id="30119-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30119-142">Lync Server 2013 CU1 集區</span><span class="sxs-lookup"><span data-stu-id="30119-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="30119-143">任何</span><span class="sxs-lookup"><span data-stu-id="30119-143">any</span></span></p></td>
<td><p><span data-ttu-id="30119-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="30119-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30119-145">Lync Server 2013 CU1，轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="30119-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="30119-146">任何</span><span class="sxs-lookup"><span data-stu-id="30119-146">any</span></span></p></td>
<td><p><span data-ttu-id="30119-147">毫秒-PL1</span><span class="sxs-lookup"><span data-stu-id="30119-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30119-148">PSTN 閘道1</span><span class="sxs-lookup"><span data-stu-id="30119-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="30119-149">德里</span><span class="sxs-lookup"><span data-stu-id="30119-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="30119-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="30119-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30119-151">PSTN 閘道2</span><span class="sxs-lookup"><span data-stu-id="30119-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="30119-152">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="30119-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="30119-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="30119-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30119-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="30119-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="30119-155">德里</span><span class="sxs-lookup"><span data-stu-id="30119-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="30119-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="30119-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30119-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="30119-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="30119-158">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="30119-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="30119-159">RED PBX</span><span class="sxs-lookup"><span data-stu-id="30119-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="30119-160">本章節內容</span><span class="sxs-lookup"><span data-stu-id="30119-160">In This Section</span></span>

  - [<span data-ttu-id="30119-161">在 Lync Server 2013 中設定企業語音</span><span class="sxs-lookup"><span data-stu-id="30119-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="30119-162">在 Lync Server 2013 中部署網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="30119-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="30119-163">在 Lync Server 2013 中啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="30119-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30119-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="30119-164">See Also</span></span>


[<span data-ttu-id="30119-165">在 Lync Server 2013 中部署高級 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="30119-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

