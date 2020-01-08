---
title: Lync Server 2013：設定容錯移轉路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="ac133-102">在 Lync Server 2013 中設定容錯移轉路由</span><span class="sxs-lookup"><span data-stu-id="ac133-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac133-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ac133-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ac133-104">下列範例顯示管理員如何定義容錯移轉路線，以便在達拉斯 GW1 關閉或無法使用的情況下使用。</span><span class="sxs-lookup"><span data-stu-id="ac133-104">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable.</span></span> <span data-ttu-id="ac133-105">下表說明所需的配置變更。</span><span class="sxs-lookup"><span data-stu-id="ac133-105">The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="ac133-106">資料表1。</span><span class="sxs-lookup"><span data-stu-id="ac133-106">Table 1.</span></span> <span data-ttu-id="ac133-107">使用者原則</span><span class="sxs-lookup"><span data-stu-id="ac133-107">User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac133-108">使用者原則</span><span class="sxs-lookup"><span data-stu-id="ac133-108">User policy</span></span></th>
<th><span data-ttu-id="ac133-109">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="ac133-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac133-110">預設通話原則</span><span class="sxs-lookup"><span data-stu-id="ac133-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="ac133-111">局部</span><span class="sxs-lookup"><span data-stu-id="ac133-111">Local</span></span></p>
<p><span data-ttu-id="ac133-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="ac133-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac133-113">雷德蒙當地原則</span><span class="sxs-lookup"><span data-stu-id="ac133-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="ac133-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="ac133-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac133-115">達拉斯通話原則</span><span class="sxs-lookup"><span data-stu-id="ac133-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="ac133-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="ac133-116">DallasUsers</span></span></p>
<p><span data-ttu-id="ac133-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="ac133-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="ac133-118">表格2。</span><span class="sxs-lookup"><span data-stu-id="ac133-118">Table 2.</span></span> <span data-ttu-id="ac133-119">到達</span><span class="sxs-lookup"><span data-stu-id="ac133-119">Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac133-120">路線名稱</span><span class="sxs-lookup"><span data-stu-id="ac133-120">Route name</span></span></th>
<th><span data-ttu-id="ac133-121">數位模式</span><span class="sxs-lookup"><span data-stu-id="ac133-121">Number pattern</span></span></th>
<th><span data-ttu-id="ac133-122">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="ac133-122">Phone usage</span></span></th>
<th><span data-ttu-id="ac133-123">去</span><span class="sxs-lookup"><span data-stu-id="ac133-123">Trunk</span></span></th>
<th><span data-ttu-id="ac133-124">關</span><span class="sxs-lookup"><span data-stu-id="ac133-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac133-125">雷德蒙的本機路線</span><span class="sxs-lookup"><span data-stu-id="ac133-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="ac133-126">^\+1（425 | 206 | 253）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="ac133-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ac133-127">局部</span><span class="sxs-lookup"><span data-stu-id="ac133-127">Local</span></span></p>
<p><span data-ttu-id="ac133-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="ac133-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="ac133-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="ac133-129">Trunk1</span></span></p>
<p><span data-ttu-id="ac133-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="ac133-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="ac133-131">紅-GW1</span><span class="sxs-lookup"><span data-stu-id="ac133-131">Red-GW1</span></span></p>
<p><span data-ttu-id="ac133-132">紅-GW2</span><span class="sxs-lookup"><span data-stu-id="ac133-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac133-133">達拉斯本機路線</span><span class="sxs-lookup"><span data-stu-id="ac133-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="ac133-134">^\+1（972 | 214 | 469）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="ac133-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ac133-135">局部</span><span class="sxs-lookup"><span data-stu-id="ac133-135">Local</span></span></p></td>
<td><p><span data-ttu-id="ac133-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ac133-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ac133-137">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="ac133-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac133-138">通用路線</span><span class="sxs-lookup"><span data-stu-id="ac133-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="ac133-139">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="ac133-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ac133-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="ac133-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="ac133-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="ac133-141">Trunk1</span></span></p>
<p><span data-ttu-id="ac133-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="ac133-142">Trunk2</span></span></p>
<p><span data-ttu-id="ac133-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ac133-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ac133-144">紅-GW1</span><span class="sxs-lookup"><span data-stu-id="ac133-144">Red-GW1</span></span></p>
<p><span data-ttu-id="ac133-145">紅-GW2</span><span class="sxs-lookup"><span data-stu-id="ac133-145">Red-GW2</span></span></p>
<p><span data-ttu-id="ac133-146">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="ac133-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac133-147">達拉斯使用者路由</span><span class="sxs-lookup"><span data-stu-id="ac133-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="ac133-148">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="ac133-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ac133-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="ac133-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="ac133-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ac133-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ac133-151">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="ac133-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ac133-152">在表格1中，在達拉斯通話原則中，在 DallasUsers 電話使用量之後，就會新增 GlobalPSTNHopoff 的電話使用方式。</span><span class="sxs-lookup"><span data-stu-id="ac133-152">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy.</span></span> <span data-ttu-id="ac133-153">這可讓使用達拉斯通話原則進行呼叫，以使用針對 GlobalPSTNHopoff 電話使用設定的路線（如果無法使用 DallasUsers 電話使用方式的路線）。</span><span class="sxs-lookup"><span data-stu-id="ac133-153">This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

