---
title: Lync Server 2013：設定容錯移轉路由
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
ms.openlocfilehash: e0a3a0d3b2eb2d505ff345af66ae8ccbcc551ee8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520060"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="7b95b-102">在 Lync Server 2013 中設定容錯移轉路由</span><span class="sxs-lookup"><span data-stu-id="7b95b-102">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b95b-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7b95b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7b95b-p101">下列範例顯示系統管理員如何定義當 Dallas-GW1 因維修或其他緣故而無法使用時所要使用的容錯移轉路由。下表說明所需的設定變更。</span><span class="sxs-lookup"><span data-stu-id="7b95b-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="7b95b-p102">表 1. 使用者原則</span><span class="sxs-lookup"><span data-stu-id="7b95b-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b95b-108">使用者原則</span><span class="sxs-lookup"><span data-stu-id="7b95b-108">User policy</span></span></th>
<th><span data-ttu-id="7b95b-109">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="7b95b-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b95b-110">預設通話原則</span><span class="sxs-lookup"><span data-stu-id="7b95b-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="7b95b-111">本機</span><span class="sxs-lookup"><span data-stu-id="7b95b-111">Local</span></span></p>
<p><span data-ttu-id="7b95b-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7b95b-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b95b-113">Redmond 本地原則</span><span class="sxs-lookup"><span data-stu-id="7b95b-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="7b95b-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="7b95b-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b95b-115">Dallas 通話原則</span><span class="sxs-lookup"><span data-stu-id="7b95b-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="7b95b-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="7b95b-116">DallasUsers</span></span></p>
<p><span data-ttu-id="7b95b-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7b95b-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="7b95b-p103">表 2. 路由</span><span class="sxs-lookup"><span data-stu-id="7b95b-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="7b95b-120">路由名稱</span><span class="sxs-lookup"><span data-stu-id="7b95b-120">Route name</span></span></th>
<th><span data-ttu-id="7b95b-121">號碼模式</span><span class="sxs-lookup"><span data-stu-id="7b95b-121">Number pattern</span></span></th>
<th><span data-ttu-id="7b95b-122">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="7b95b-122">Phone usage</span></span></th>
<th><span data-ttu-id="7b95b-123">樹幹</span><span class="sxs-lookup"><span data-stu-id="7b95b-123">Trunk</span></span></th>
<th><span data-ttu-id="7b95b-124">閘道</span><span class="sxs-lookup"><span data-stu-id="7b95b-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b95b-125">Redmond 本地路由</span><span class="sxs-lookup"><span data-stu-id="7b95b-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="7b95b-126">^\+1 (425 | 206 | 253) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="7b95b-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="7b95b-127">本機</span><span class="sxs-lookup"><span data-stu-id="7b95b-127">Local</span></span></p>
<p><span data-ttu-id="7b95b-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="7b95b-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="7b95b-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="7b95b-129">Trunk1</span></span></p>
<p><span data-ttu-id="7b95b-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="7b95b-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="7b95b-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="7b95b-131">Red-GW1</span></span></p>
<p><span data-ttu-id="7b95b-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="7b95b-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b95b-133">Dallas 本地路由</span><span class="sxs-lookup"><span data-stu-id="7b95b-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="7b95b-134">^\+1 (972 | 214 | 469) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="7b95b-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="7b95b-135">本機</span><span class="sxs-lookup"><span data-stu-id="7b95b-135">Local</span></span></p></td>
<td><p><span data-ttu-id="7b95b-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7b95b-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7b95b-137">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="7b95b-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b95b-138">全域路由</span><span class="sxs-lookup"><span data-stu-id="7b95b-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="7b95b-139">^\+？ ( \d \* ) $</span><span class="sxs-lookup"><span data-stu-id="7b95b-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="7b95b-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7b95b-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="7b95b-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="7b95b-141">Trunk1</span></span></p>
<p><span data-ttu-id="7b95b-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="7b95b-142">Trunk2</span></span></p>
<p><span data-ttu-id="7b95b-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7b95b-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7b95b-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="7b95b-144">Red-GW1</span></span></p>
<p><span data-ttu-id="7b95b-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="7b95b-145">Red-GW2</span></span></p>
<p><span data-ttu-id="7b95b-146">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="7b95b-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b95b-147">Dallas 使用者路由</span><span class="sxs-lookup"><span data-stu-id="7b95b-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="7b95b-148">^\+？ ( \d \* ) $</span><span class="sxs-lookup"><span data-stu-id="7b95b-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="7b95b-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="7b95b-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="7b95b-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7b95b-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7b95b-151">達拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="7b95b-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b95b-p104">表 1 中，在「Dallas 通話原則」的「DallasUsers」電話使用方式後，將新增 GlobalPSTNHopoff 電話使用方式。如此可讓具有「Dallas 通話原則」的電話在無法使用 DallasUsers 電話使用方式的路由時，可以使用為 GlobalPSTNHopoff 電話使用方式所設定的路由。</span><span class="sxs-lookup"><span data-stu-id="7b95b-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

