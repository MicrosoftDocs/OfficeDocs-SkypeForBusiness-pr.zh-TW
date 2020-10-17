---
title: Lync Server 2013： Location-Based 路由的用戶端和伺服器支援
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
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529340"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="e25dd-102">Lync Server 2013 中的 Location-Based 路由的用戶端和伺服器支援</span><span class="sxs-lookup"><span data-stu-id="e25dd-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e25dd-103">_**主題上次修改日期：** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="e25dd-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="e25dd-104">Location-Based 路由是由 Lync Server 強制執行。</span><span class="sxs-lookup"><span data-stu-id="e25dd-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="e25dd-105">Lync Server 可以識別使用者從公司網路內部連線的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e25dd-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="e25dd-106">因為遠端使用者位於公司網路外部，所以其位置被視為未知。</span><span class="sxs-lookup"><span data-stu-id="e25dd-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="e25dd-107">Lync Server 支援</span><span class="sxs-lookup"><span data-stu-id="e25dd-107">Lync Server Support</span></span>

<span data-ttu-id="e25dd-108">Location-Based 路由需要在指定的拓撲中的所有前端集區和 Standard Edition server 上部署 Lync Server 2013 CU1。</span><span class="sxs-lookup"><span data-stu-id="e25dd-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="e25dd-109">如果 Lync Server 2013 CU1 未安裝在拓撲中的某些 Lync 元件上，則無法完全強制執行 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="e25dd-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="e25dd-110">下表列出 Location-Based 路由支援的伺服器角色與版本組合。</span><span class="sxs-lookup"><span data-stu-id="e25dd-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25dd-111">集區版本</span><span class="sxs-lookup"><span data-stu-id="e25dd-111">Pool version</span></span></th>
<th><span data-ttu-id="e25dd-112">轉送伺服器版本</span><span class="sxs-lookup"><span data-stu-id="e25dd-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="e25dd-113">支援</span><span class="sxs-lookup"><span data-stu-id="e25dd-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-114">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="e25dd-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e25dd-115">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="e25dd-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e25dd-116">是</span><span class="sxs-lookup"><span data-stu-id="e25dd-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25dd-117">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="e25dd-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e25dd-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e25dd-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="e25dd-119">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-120">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="e25dd-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e25dd-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e25dd-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="e25dd-122">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25dd-123">Lync Server 2013 2013 月累計更新</span><span class="sxs-lookup"><span data-stu-id="e25dd-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e25dd-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e25dd-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e25dd-125">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e25dd-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="e25dd-127">任何</span><span class="sxs-lookup"><span data-stu-id="e25dd-127">any</span></span></p></td>
<td><p><span data-ttu-id="e25dd-128">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25dd-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e25dd-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="e25dd-130">任何</span><span class="sxs-lookup"><span data-stu-id="e25dd-130">any</span></span></p></td>
<td><p><span data-ttu-id="e25dd-131">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e25dd-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e25dd-133">任何</span><span class="sxs-lookup"><span data-stu-id="e25dd-133">any</span></span></p></td>
<td><p><span data-ttu-id="e25dd-134">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="e25dd-135">Lync 用戶端支援</span><span class="sxs-lookup"><span data-stu-id="e25dd-135">Lync Client Support</span></span>

<span data-ttu-id="e25dd-136">下表識別 Location-Based 路由支援的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e25dd-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25dd-137">用戶端類型</span><span class="sxs-lookup"><span data-stu-id="e25dd-137">Client type</span></span></th>
<th><span data-ttu-id="e25dd-138">支援</span><span class="sxs-lookup"><span data-stu-id="e25dd-138">Supported</span></span></th>
<th><span data-ttu-id="e25dd-139">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e25dd-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e25dd-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="e25dd-141">是</span><span class="sxs-lookup"><span data-stu-id="e25dd-141">yes</span></span></p></td>
<td><p><span data-ttu-id="e25dd-142">包括 Lync 2013 月2013累計更新</span><span class="sxs-lookup"><span data-stu-id="e25dd-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25dd-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e25dd-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="e25dd-144">是</span><span class="sxs-lookup"><span data-stu-id="e25dd-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e25dd-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e25dd-146">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25dd-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="e25dd-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="e25dd-148">是</span><span class="sxs-lookup"><span data-stu-id="e25dd-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-149">Lync 語音應答</span><span class="sxs-lookup"><span data-stu-id="e25dd-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="e25dd-150">是</span><span class="sxs-lookup"><span data-stu-id="e25dd-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25dd-151">Lync for Windows 8</span><span class="sxs-lookup"><span data-stu-id="e25dd-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="e25dd-152">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25dd-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="e25dd-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="e25dd-154">否</span><span class="sxs-lookup"><span data-stu-id="e25dd-154">no</span></span></p></td>
<td><p><span data-ttu-id="e25dd-155">如果已啟用 Location-Based 路由的使用者使用，則必須停用 Lync Mobile 2013 用戶端的 VoIP。</span><span class="sxs-lookup"><span data-stu-id="e25dd-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25dd-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="e25dd-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="e25dd-157">是</span><span class="sxs-lookup"><span data-stu-id="e25dd-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="e25dd-158">若要停用 Lync Mobile 2013 用戶端的 VoIP，請將行動原則指派給所有啟用位置路由之使用者的設定、IP Audio/Video、停用。</span><span class="sxs-lookup"><span data-stu-id="e25dd-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="e25dd-159">如需行動原則的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="e25dd-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e25dd-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e25dd-160">See Also</span></span>


[<span data-ttu-id="e25dd-161">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="e25dd-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

