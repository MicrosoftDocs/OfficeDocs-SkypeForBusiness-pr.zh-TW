---
title: Lync Server 2013：設定容錯移轉路由
description: Lync Server 2013：設定容錯移轉路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560489"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="7e181-103">在 Lync Server 2013 中設定容錯移轉路由</span><span class="sxs-lookup"><span data-stu-id="7e181-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e181-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7e181-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7e181-p101">下列範例顯示系統管理員如何定義當 Dallas-GW1 因維修或其他緣故而無法使用時所要使用的容錯移轉路由。下表說明所需的設定變更。</span><span class="sxs-lookup"><span data-stu-id="7e181-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="7e181-p102">表 1. 使用者原則</span><span class="sxs-lookup"><span data-stu-id="7e181-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e181-109">使用者原則</span><span class="sxs-lookup"><span data-stu-id="7e181-109">User policy</span></span></th>
<th><span data-ttu-id="7e181-110">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="7e181-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e181-111">預設通話原則</span><span class="sxs-lookup"><span data-stu-id="7e181-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="7e181-112">本機</span><span class="sxs-lookup"><span data-stu-id="7e181-112">Local</span></span></p>
<p><span data-ttu-id="7e181-113">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7e181-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e181-114">Redmond 本地原則</span><span class="sxs-lookup"><span data-stu-id="7e181-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="7e181-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="7e181-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e181-116">Dallas 通話原則</span><span class="sxs-lookup"><span data-stu-id="7e181-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="7e181-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="7e181-117">DallasUsers</span></span></p>
<p><span data-ttu-id="7e181-118">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7e181-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="7e181-p103">表 2. 路由</span><span class="sxs-lookup"><span data-stu-id="7e181-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="7e181-121">路由名稱</span><span class="sxs-lookup"><span data-stu-id="7e181-121">Route name</span></span></th>
<th><span data-ttu-id="7e181-122">號碼模式</span><span class="sxs-lookup"><span data-stu-id="7e181-122">Number pattern</span></span></th>
<th><span data-ttu-id="7e181-123">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="7e181-123">Phone usage</span></span></th>
<th><span data-ttu-id="7e181-124">樹幹</span><span class="sxs-lookup"><span data-stu-id="7e181-124">Trunk</span></span></th>
<th><span data-ttu-id="7e181-125">閘道</span><span class="sxs-lookup"><span data-stu-id="7e181-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e181-126">Redmond 本地路由</span><span class="sxs-lookup"><span data-stu-id="7e181-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="7e181-127">^\+1 (425 | 206 | 253) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="7e181-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="7e181-128">本機</span><span class="sxs-lookup"><span data-stu-id="7e181-128">Local</span></span></p>
<p><span data-ttu-id="7e181-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="7e181-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="7e181-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="7e181-130">Trunk1</span></span></p>
<p><span data-ttu-id="7e181-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="7e181-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="7e181-132">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="7e181-132">Red-GW1</span></span></p>
<p><span data-ttu-id="7e181-133">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="7e181-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e181-134">Dallas 本地路由</span><span class="sxs-lookup"><span data-stu-id="7e181-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="7e181-135">^\+1 (972 | 214 | 469) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="7e181-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="7e181-136">本機</span><span class="sxs-lookup"><span data-stu-id="7e181-136">Local</span></span></p></td>
<td><p><span data-ttu-id="7e181-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7e181-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7e181-138">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="7e181-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e181-139">全域路由</span><span class="sxs-lookup"><span data-stu-id="7e181-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="7e181-140">^\+？ ( \d \* ) $</span><span class="sxs-lookup"><span data-stu-id="7e181-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="7e181-141">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7e181-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="7e181-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="7e181-142">Trunk1</span></span></p>
<p><span data-ttu-id="7e181-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="7e181-143">Trunk2</span></span></p>
<p><span data-ttu-id="7e181-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7e181-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7e181-145">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="7e181-145">Red-GW1</span></span></p>
<p><span data-ttu-id="7e181-146">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="7e181-146">Red-GW2</span></span></p>
<p><span data-ttu-id="7e181-147">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="7e181-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e181-148">Dallas 使用者路由</span><span class="sxs-lookup"><span data-stu-id="7e181-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="7e181-149">^\+？ ( \d \* ) $</span><span class="sxs-lookup"><span data-stu-id="7e181-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="7e181-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="7e181-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="7e181-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7e181-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7e181-152">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="7e181-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e181-p104">表 1 中，在「Dallas 通話原則」的「DallasUsers」電話使用方式後，將新增 GlobalPSTNHopoff 電話使用方式。如此可讓具有「Dallas 通話原則」的電話在無法使用 DallasUsers 電話使用方式的路由時，可以使用為 GlobalPSTNHopoff 電話使用方式所設定的路由。</span><span class="sxs-lookup"><span data-stu-id="7e181-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

