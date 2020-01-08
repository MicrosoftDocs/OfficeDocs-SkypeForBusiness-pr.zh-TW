---
title: Lync Server 2013：設定位置基礎路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="4c834-102">在 Lync Server 2013 中設定位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="4c834-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c834-103">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="4c834-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="4c834-104">Lync Server 2013 CU1，以位置為基礎的路由是企業語音的功能。</span><span class="sxs-lookup"><span data-stu-id="4c834-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="4c834-105">位置式路由是呼叫管理的功能，可控制 Lync Server 2013 CU1 路由呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="4c834-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="4c834-106">它會強制限制通話是否可以根據 Lync 來電者的位置路由到 PBX 或 PSTN 目的地。</span><span class="sxs-lookup"><span data-stu-id="4c834-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="4c834-107">以位置為基礎的路由根據呼叫者的網路位置，將呼叫授權規則套用至 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="4c834-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="4c834-108">來電者的位置是根據與呼叫者連線之網路子網相關的網路網站來決定。</span><span class="sxs-lookup"><span data-stu-id="4c834-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="4c834-109">設定以位置為基礎的路由需要先部署企業語音，然後再設定網路區域、網站和子網。</span><span class="sxs-lookup"><span data-stu-id="4c834-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="4c834-110">這會為啟用以位置為基礎的路由設定奠定基礎。</span><span class="sxs-lookup"><span data-stu-id="4c834-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="4c834-111">在部署以位置為基礎的路由前，您必須先部署企業語音，並設定網路區域、網站，以及將網路子網與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="4c834-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="4c834-112">完成之後，您就可以設定以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="4c834-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="4c834-113">如需如何設定網路區域、網站和子網的步驟，請參閱[在 Lync Server 2013 中部署高級企業語音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="4c834-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="4c834-114">本節將引導您逐步完成以位置為基礎的路由設定，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="4c834-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="4c834-115">![企業語音位置-基礎路由範例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "企業語音位置-基礎路由範例")</span><span class="sxs-lookup"><span data-stu-id="4c834-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="4c834-116">下表代表在這個範例中定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="4c834-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c834-117">端點類型</span><span class="sxs-lookup"><span data-stu-id="4c834-117">Endpoint type</span></span></th>
<th><span data-ttu-id="4c834-118">位置</span><span class="sxs-lookup"><span data-stu-id="4c834-118">Location</span></span></th>
<th><span data-ttu-id="4c834-119">使用者</span><span class="sxs-lookup"><span data-stu-id="4c834-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c834-120">Lync</span><span class="sxs-lookup"><span data-stu-id="4c834-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="4c834-121">新德里公司 office</span><span class="sxs-lookup"><span data-stu-id="4c834-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="4c834-122">DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="4c834-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c834-123">Lync</span><span class="sxs-lookup"><span data-stu-id="4c834-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="4c834-124">Hyderabad 公司 office</span><span class="sxs-lookup"><span data-stu-id="4c834-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="4c834-125">HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="4c834-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c834-126">Lync</span><span class="sxs-lookup"><span data-stu-id="4c834-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="4c834-127">未知（亦即賓館）</span><span class="sxs-lookup"><span data-stu-id="4c834-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="4c834-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="4c834-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c834-129">PBX</span><span class="sxs-lookup"><span data-stu-id="4c834-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="4c834-130">新德里公司 office</span><span class="sxs-lookup"><span data-stu-id="4c834-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="4c834-131">DEL-PBX-1，DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="4c834-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c834-132">PBX</span><span class="sxs-lookup"><span data-stu-id="4c834-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="4c834-133">Hyderabad 公司 office</span><span class="sxs-lookup"><span data-stu-id="4c834-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="4c834-134">HYD-1，HYD，2</span><span class="sxs-lookup"><span data-stu-id="4c834-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c834-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="4c834-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="4c834-136">清楚</span><span class="sxs-lookup"><span data-stu-id="4c834-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="4c834-137">PSTN-1、PSTN-2、PSTN-3</span><span class="sxs-lookup"><span data-stu-id="4c834-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="4c834-138">下表代表此範例環境中闡釋的系統。</span><span class="sxs-lookup"><span data-stu-id="4c834-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c834-139">作業系統</span><span class="sxs-lookup"><span data-stu-id="4c834-139">System</span></span></th>
<th><span data-ttu-id="4c834-140">位置</span><span class="sxs-lookup"><span data-stu-id="4c834-140">Location</span></span></th>
<th><span data-ttu-id="4c834-141">名稱</span><span class="sxs-lookup"><span data-stu-id="4c834-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c834-142">Lync Server 2013 CU1 池</span><span class="sxs-lookup"><span data-stu-id="4c834-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="4c834-143">每</span><span class="sxs-lookup"><span data-stu-id="4c834-143">any</span></span></p></td>
<td><p><span data-ttu-id="4c834-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="4c834-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c834-145">Lync Server 2013 CU1，中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="4c834-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="4c834-146">每</span><span class="sxs-lookup"><span data-stu-id="4c834-146">any</span></span></p></td>
<td><p><span data-ttu-id="4c834-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="4c834-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c834-148">PSTN 閘道1</span><span class="sxs-lookup"><span data-stu-id="4c834-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="4c834-149">新德里</span><span class="sxs-lookup"><span data-stu-id="4c834-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="4c834-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="4c834-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c834-151">PSTN 閘道2</span><span class="sxs-lookup"><span data-stu-id="4c834-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="4c834-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c834-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="4c834-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="4c834-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c834-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="4c834-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="4c834-155">新德里</span><span class="sxs-lookup"><span data-stu-id="4c834-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="4c834-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="4c834-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c834-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="4c834-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="4c834-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c834-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="4c834-159">紅-PBX</span><span class="sxs-lookup"><span data-stu-id="4c834-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="4c834-160">本節內容</span><span class="sxs-lookup"><span data-stu-id="4c834-160">In This Section</span></span>

  - [<span data-ttu-id="4c834-161">在 Lync Server 2013 中設定企業語音</span><span class="sxs-lookup"><span data-stu-id="4c834-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="4c834-162">在 Lync Server 2013 中部署網路區域、網站和子網</span><span class="sxs-lookup"><span data-stu-id="4c834-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="4c834-163">在 Lync Server 2013 啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="4c834-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c834-164">請參閱</span><span class="sxs-lookup"><span data-stu-id="4c834-164">See Also</span></span>


[<span data-ttu-id="4c834-165">在 Lync Server 2013 中部署高級企業語音功能</span><span class="sxs-lookup"><span data-stu-id="4c834-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

