---
title: Lync Server 2013： Location-Based 路由的用戶端和伺服器支援
description: Lync Server 2013：用戶端和伺服器支援 Location-Based 路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549629"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0de6b-103">Lync Server 2013 中的 Location-Based 路由的用戶端和伺服器支援</span><span class="sxs-lookup"><span data-stu-id="0de6b-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0de6b-104">_**主題上次修改日期：** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="0de6b-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="0de6b-105">Location-Based 路由是由 Lync Server 強制執行。</span><span class="sxs-lookup"><span data-stu-id="0de6b-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="0de6b-106">Lync Server 可以識別使用者從公司網路內部連線的網路網站。</span><span class="sxs-lookup"><span data-stu-id="0de6b-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="0de6b-107">因為遠端使用者位於公司網路外部，所以其位置被視為未知。</span><span class="sxs-lookup"><span data-stu-id="0de6b-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="0de6b-108">Lync Server 支援</span><span class="sxs-lookup"><span data-stu-id="0de6b-108">Lync Server Support</span></span>

<span data-ttu-id="0de6b-109">Location-Based 路由需要在指定的拓撲中的所有前端集區和 Standard Edition server 上部署 Lync Server 2013 CU1。</span><span class="sxs-lookup"><span data-stu-id="0de6b-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="0de6b-110">如果 Lync Server 2013 CU1 未安裝在拓撲中的某些 Lync 元件上，則無法完全強制執行 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="0de6b-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="0de6b-111">下表列出 Location-Based 路由支援的伺服器角色與版本組合。</span><span class="sxs-lookup"><span data-stu-id="0de6b-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0de6b-112">集區版本</span><span class="sxs-lookup"><span data-stu-id="0de6b-112">Pool version</span></span></th>
<th><span data-ttu-id="0de6b-113">轉送伺服器版本</span><span class="sxs-lookup"><span data-stu-id="0de6b-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="0de6b-114">支援</span><span class="sxs-lookup"><span data-stu-id="0de6b-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-115">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="0de6b-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0de6b-116">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="0de6b-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0de6b-117">是</span><span class="sxs-lookup"><span data-stu-id="0de6b-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de6b-118">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="0de6b-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0de6b-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0de6b-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="0de6b-120">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-121">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="0de6b-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0de6b-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0de6b-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="0de6b-123">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de6b-124">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="0de6b-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0de6b-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0de6b-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="0de6b-126">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0de6b-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="0de6b-128">任何</span><span class="sxs-lookup"><span data-stu-id="0de6b-128">any</span></span></p></td>
<td><p><span data-ttu-id="0de6b-129">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de6b-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0de6b-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="0de6b-131">任何</span><span class="sxs-lookup"><span data-stu-id="0de6b-131">any</span></span></p></td>
<td><p><span data-ttu-id="0de6b-132">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0de6b-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="0de6b-134">任何</span><span class="sxs-lookup"><span data-stu-id="0de6b-134">any</span></span></p></td>
<td><p><span data-ttu-id="0de6b-135">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="0de6b-136">Lync 用戶端支援</span><span class="sxs-lookup"><span data-stu-id="0de6b-136">Lync Client Support</span></span>

<span data-ttu-id="0de6b-137">下表識別 Location-Based 路由支援的用戶端。</span><span class="sxs-lookup"><span data-stu-id="0de6b-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0de6b-138">用戶端類型</span><span class="sxs-lookup"><span data-stu-id="0de6b-138">Client type</span></span></th>
<th><span data-ttu-id="0de6b-139">支援</span><span class="sxs-lookup"><span data-stu-id="0de6b-139">Supported</span></span></th>
<th><span data-ttu-id="0de6b-140">詳細資料</span><span class="sxs-lookup"><span data-stu-id="0de6b-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0de6b-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="0de6b-142">是</span><span class="sxs-lookup"><span data-stu-id="0de6b-142">yes</span></span></p></td>
<td><p><span data-ttu-id="0de6b-143">包括 Lync 2013 月2013累計更新</span><span class="sxs-lookup"><span data-stu-id="0de6b-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de6b-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0de6b-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="0de6b-145">是</span><span class="sxs-lookup"><span data-stu-id="0de6b-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0de6b-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="0de6b-147">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de6b-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0de6b-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="0de6b-149">是</span><span class="sxs-lookup"><span data-stu-id="0de6b-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-150">Lync 語音應答</span><span class="sxs-lookup"><span data-stu-id="0de6b-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="0de6b-151">是</span><span class="sxs-lookup"><span data-stu-id="0de6b-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de6b-152">Lync for Windows 8</span><span class="sxs-lookup"><span data-stu-id="0de6b-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="0de6b-153">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0de6b-154">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="0de6b-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="0de6b-155">否</span><span class="sxs-lookup"><span data-stu-id="0de6b-155">no</span></span></p></td>
<td><p><span data-ttu-id="0de6b-156">如果已啟用 Location-Based 路由的使用者使用，則必須停用 Lync Mobile 2013 用戶端的 VoIP。</span><span class="sxs-lookup"><span data-stu-id="0de6b-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0de6b-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="0de6b-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="0de6b-158">是</span><span class="sxs-lookup"><span data-stu-id="0de6b-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="0de6b-159">若要停用 Lync Mobile 2013 用戶端的 VoIP，請將行動原則指派給所有啟用位置路由之使用者的設定、IP Audio/Video、停用。</span><span class="sxs-lookup"><span data-stu-id="0de6b-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="0de6b-160">如需行動原則的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="0de6b-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0de6b-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0de6b-161">See Also</span></span>


[<span data-ttu-id="0de6b-162">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="0de6b-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

