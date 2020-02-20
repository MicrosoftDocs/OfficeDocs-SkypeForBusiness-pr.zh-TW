---
title: Lync Server 2013： 設定容錯移轉路由
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
ms.openlocfilehash: b012b1bbab693e9a95a64d1fb3150723523cb53d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="569dc-102">在 Lync Server 2013 中設定容錯移轉路由</span><span class="sxs-lookup"><span data-stu-id="569dc-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="569dc-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="569dc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="569dc-p101">下列範例顯示系統管理員如何定義當 Dallas-GW1 因維修或其他緣故而無法使用時所要使用的容錯移轉路由。下表說明所需的設定變更。</span><span class="sxs-lookup"><span data-stu-id="569dc-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="569dc-p102">表 1. 使用者原則</span><span class="sxs-lookup"><span data-stu-id="569dc-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="569dc-108">使用者原則</span><span class="sxs-lookup"><span data-stu-id="569dc-108">User policy</span></span></th>
<th><span data-ttu-id="569dc-109">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="569dc-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="569dc-110">預設通話原則</span><span class="sxs-lookup"><span data-stu-id="569dc-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="569dc-111">Local</span><span class="sxs-lookup"><span data-stu-id="569dc-111">Local</span></span></p>
<p><span data-ttu-id="569dc-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="569dc-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="569dc-113">Redmond 本地原則</span><span class="sxs-lookup"><span data-stu-id="569dc-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="569dc-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="569dc-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="569dc-115">Dallas 通話原則</span><span class="sxs-lookup"><span data-stu-id="569dc-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="569dc-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="569dc-116">DallasUsers</span></span></p>
<p><span data-ttu-id="569dc-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="569dc-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="569dc-p103">表 2. 路由</span><span class="sxs-lookup"><span data-stu-id="569dc-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="569dc-120">路由名稱</span><span class="sxs-lookup"><span data-stu-id="569dc-120">Route name</span></span></th>
<th><span data-ttu-id="569dc-121">號碼模式</span><span class="sxs-lookup"><span data-stu-id="569dc-121">Number pattern</span></span></th>
<th><span data-ttu-id="569dc-122">電話使用方式</span><span class="sxs-lookup"><span data-stu-id="569dc-122">Phone usage</span></span></th>
<th><span data-ttu-id="569dc-123">主幹</span><span class="sxs-lookup"><span data-stu-id="569dc-123">Trunk</span></span></th>
<th><span data-ttu-id="569dc-124">閘道</span><span class="sxs-lookup"><span data-stu-id="569dc-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="569dc-125">Redmond 本地路由</span><span class="sxs-lookup"><span data-stu-id="569dc-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="569dc-126">^\+1(425|206|253)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="569dc-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="569dc-127">Local</span><span class="sxs-lookup"><span data-stu-id="569dc-127">Local</span></span></p>
<p><span data-ttu-id="569dc-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="569dc-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="569dc-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="569dc-129">Trunk1</span></span></p>
<p><span data-ttu-id="569dc-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="569dc-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="569dc-131">紅色 GW1</span><span class="sxs-lookup"><span data-stu-id="569dc-131">Red-GW1</span></span></p>
<p><span data-ttu-id="569dc-132">紅色 GW2</span><span class="sxs-lookup"><span data-stu-id="569dc-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="569dc-133">Dallas 本地路由</span><span class="sxs-lookup"><span data-stu-id="569dc-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="569dc-134">^\+1(972|214|469)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="569dc-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="569dc-135">Local</span><span class="sxs-lookup"><span data-stu-id="569dc-135">Local</span></span></p></td>
<td><p><span data-ttu-id="569dc-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="569dc-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="569dc-137">Dallas GW1</span><span class="sxs-lookup"><span data-stu-id="569dc-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="569dc-138">全域路由</span><span class="sxs-lookup"><span data-stu-id="569dc-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="569dc-139">^\+?(\d\*)$</span><span class="sxs-lookup"><span data-stu-id="569dc-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="569dc-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="569dc-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="569dc-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="569dc-141">Trunk1</span></span></p>
<p><span data-ttu-id="569dc-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="569dc-142">Trunk2</span></span></p>
<p><span data-ttu-id="569dc-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="569dc-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="569dc-144">紅色 GW1</span><span class="sxs-lookup"><span data-stu-id="569dc-144">Red-GW1</span></span></p>
<p><span data-ttu-id="569dc-145">紅色 GW2</span><span class="sxs-lookup"><span data-stu-id="569dc-145">Red-GW2</span></span></p>
<p><span data-ttu-id="569dc-146">Dallas GW1</span><span class="sxs-lookup"><span data-stu-id="569dc-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="569dc-147">Dallas 使用者路由</span><span class="sxs-lookup"><span data-stu-id="569dc-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="569dc-148">^\+?(\d\*)$</span><span class="sxs-lookup"><span data-stu-id="569dc-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="569dc-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="569dc-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="569dc-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="569dc-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="569dc-151">Dallas GW1</span><span class="sxs-lookup"><span data-stu-id="569dc-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="569dc-p104">表 1 中，在「Dallas 通話原則」的「DallasUsers」電話使用方式後，將新增 GlobalPSTNHopoff 電話使用方式。如此可讓具有「Dallas 通話原則」的電話在無法使用 DallasUsers 電話使用方式的路由時，可以使用為 GlobalPSTNHopoff 電話使用方式所設定的路由。</span><span class="sxs-lookup"><span data-stu-id="569dc-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

