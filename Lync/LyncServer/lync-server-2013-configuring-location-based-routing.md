---
title: Lync Server 2013： 設定位置型的路由
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
ms.openlocfilehash: 64e7df946d5e120352c2f0253a87197cb22b7276
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="e1917-102">設定 Lync Server 2013 中的位置型路由</span><span class="sxs-lookup"><span data-stu-id="e1917-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1917-103">_**上次修改主題：** 2013年-03-12_</span><span class="sxs-lookup"><span data-stu-id="e1917-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e1917-104">Lync Server 2013 CU1、 位置型的路由是企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="e1917-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="e1917-105">位置型路由會控制如何來電會路由傳送的 Lync Server 2013 CU1 通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="e1917-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="e1917-106">它會強制執行是否來電可被路由傳送至 PBX 或 PSTN 目的地取決於 Lync 發話者的位置的限制。</span><span class="sxs-lookup"><span data-stu-id="e1917-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="e1917-107">位置型路由將通話授權規則套用至發話者的網路位置為基礎的 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="e1917-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="e1917-108">發話者的位置取決於來電者連接的網路網站的網路子網路相關聯。</span><span class="sxs-lookup"><span data-stu-id="e1917-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="e1917-109">若要設定位置型的路由需要先部署 Enterprise Voice，然後再設定網路地區、 網站及子網路。</span><span class="sxs-lookup"><span data-stu-id="e1917-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="e1917-110">這會啟用位置型路由 foundation 設定。</span><span class="sxs-lookup"><span data-stu-id="e1917-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="e1917-111">之前部署位置型的路由，您必須先部署 Enterprise Voice、 網路地區、 網站，並設定網路子網路關聯至您的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e1917-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="e1917-112">完成之後，您可以設定位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="e1917-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="e1917-113">如需如何設定網路地區、 網站及子步驟，請參閱[部署進階 Enterprise Voice 功能在 Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="e1917-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="e1917-114">本節會引導您完成位置型的路由，請使用下列範例為圖例的組態。</span><span class="sxs-lookup"><span data-stu-id="e1917-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="e1917-115">![Enterprise Voice 位置型的路由範例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 位置型的路由範例")</span><span class="sxs-lookup"><span data-stu-id="e1917-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="e1917-116">下表代表此範例中所定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="e1917-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1917-117">端點類型</span><span class="sxs-lookup"><span data-stu-id="e1917-117">Endpoint type</span></span></th>
<th><span data-ttu-id="e1917-118">位置</span><span class="sxs-lookup"><span data-stu-id="e1917-118">Location</span></span></th>
<th><span data-ttu-id="e1917-119">使用者</span><span class="sxs-lookup"><span data-stu-id="e1917-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1917-120">Lync</span><span class="sxs-lookup"><span data-stu-id="e1917-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="e1917-121">德里的公司辦公室</span><span class="sxs-lookup"><span data-stu-id="e1917-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="e1917-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="e1917-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1917-123">Lync</span><span class="sxs-lookup"><span data-stu-id="e1917-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="e1917-124">Hyderabad 公司辦公室</span><span class="sxs-lookup"><span data-stu-id="e1917-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="e1917-125">HYD-LYNC-1、 HYD-LYNC-2、 HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="e1917-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1917-126">Lync</span><span class="sxs-lookup"><span data-stu-id="e1917-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="e1917-127">未知 （亦即旅館）</span><span class="sxs-lookup"><span data-stu-id="e1917-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="e1917-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="e1917-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1917-129">PBX</span><span class="sxs-lookup"><span data-stu-id="e1917-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="e1917-130">德里的公司辦公室</span><span class="sxs-lookup"><span data-stu-id="e1917-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="e1917-131">DEL-PBX-1、 DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="e1917-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1917-132">PBX</span><span class="sxs-lookup"><span data-stu-id="e1917-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="e1917-133">Hyderabad 公司辦公室</span><span class="sxs-lookup"><span data-stu-id="e1917-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="e1917-134">HYD-PBX-1、 HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="e1917-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1917-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="e1917-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="e1917-136">Unknown</span><span class="sxs-lookup"><span data-stu-id="e1917-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="e1917-137">PSTN-1、 PSTN-2、 PSTN-3</span><span class="sxs-lookup"><span data-stu-id="e1917-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="e1917-138">下表代表此範例環境中所示的系統。</span><span class="sxs-lookup"><span data-stu-id="e1917-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1917-139">系統</span><span class="sxs-lookup"><span data-stu-id="e1917-139">System</span></span></th>
<th><span data-ttu-id="e1917-140">位置</span><span class="sxs-lookup"><span data-stu-id="e1917-140">Location</span></span></th>
<th><span data-ttu-id="e1917-141">名稱</span><span class="sxs-lookup"><span data-stu-id="e1917-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1917-142">Lync Server 2013 CU1 集區</span><span class="sxs-lookup"><span data-stu-id="e1917-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="e1917-143">任何</span><span class="sxs-lookup"><span data-stu-id="e1917-143">any</span></span></p></td>
<td><p><span data-ttu-id="e1917-144">LS PL1</span><span class="sxs-lookup"><span data-stu-id="e1917-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1917-145">Lync Server 2013 CU1，中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="e1917-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e1917-146">任何</span><span class="sxs-lookup"><span data-stu-id="e1917-146">any</span></span></p></td>
<td><p><span data-ttu-id="e1917-147">MS PL1</span><span class="sxs-lookup"><span data-stu-id="e1917-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1917-148">PSTN 閘道 1</span><span class="sxs-lookup"><span data-stu-id="e1917-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="e1917-149">德里</span><span class="sxs-lookup"><span data-stu-id="e1917-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="e1917-150">DEL GW</span><span class="sxs-lookup"><span data-stu-id="e1917-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1917-151">PSTN 閘道 2</span><span class="sxs-lookup"><span data-stu-id="e1917-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="e1917-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e1917-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="e1917-153">HYD GW</span><span class="sxs-lookup"><span data-stu-id="e1917-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1917-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="e1917-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="e1917-155">德里</span><span class="sxs-lookup"><span data-stu-id="e1917-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="e1917-156">DEL PBX</span><span class="sxs-lookup"><span data-stu-id="e1917-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1917-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="e1917-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="e1917-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e1917-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="e1917-159">紅色 PBX</span><span class="sxs-lookup"><span data-stu-id="e1917-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="e1917-160">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e1917-160">In This Section</span></span>

  - [<span data-ttu-id="e1917-161">在 Lync Server 2013 中設定企業語音</span><span class="sxs-lookup"><span data-stu-id="e1917-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="e1917-162">部署網路地區、 網站及 Lync Server 2013 中的子網路</span><span class="sxs-lookup"><span data-stu-id="e1917-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="e1917-163">啟用 Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="e1917-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e1917-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1917-164">See Also</span></span>


[<span data-ttu-id="e1917-165">部署 Lync Server 2013 中的進階的 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="e1917-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

