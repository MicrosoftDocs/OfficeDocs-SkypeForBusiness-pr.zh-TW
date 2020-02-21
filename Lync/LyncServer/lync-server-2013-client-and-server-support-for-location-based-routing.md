---
title: Lync Server 2013： 用戶端與伺服器支援的位置型的路由
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
ms.openlocfilehash: daf0fb3656a5a57a5e4c7a6c25b7a08d29f79e86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="17626-102">Lync Server 2013 中的位置型路由的用戶端與伺服器支援</span><span class="sxs-lookup"><span data-stu-id="17626-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17626-103">_**上次修改主題：** 2013年-06-18_</span><span class="sxs-lookup"><span data-stu-id="17626-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="17626-104">位置型路由會強制執行 Lync server。</span><span class="sxs-lookup"><span data-stu-id="17626-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="17626-105">Lync Server 可以識別使用者會將連線從公司網路內的網路網站。</span><span class="sxs-lookup"><span data-stu-id="17626-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="17626-106">遠端使用者位於公司網路之外，因為它們的位置會被視為未知。</span><span class="sxs-lookup"><span data-stu-id="17626-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="17626-107">Lync Server 支援</span><span class="sxs-lookup"><span data-stu-id="17626-107">Lync Server Support</span></span>

<span data-ttu-id="17626-108">位置型的路由需要上所有的前端集區和 Standard Edition 伺服器之給定拓撲中的已部署了 Lync Server 2013 CU1。</span><span class="sxs-lookup"><span data-stu-id="17626-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="17626-109">如果在拓撲中特定 Lync 元件上未安裝 Lync Server 2013 CU1、 位置型路由限制無法完全強制執行。</span><span class="sxs-lookup"><span data-stu-id="17626-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="17626-110">下表列出位置型路由可支援的伺服器角色和版本組合。</span><span class="sxs-lookup"><span data-stu-id="17626-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17626-111">集區版本</span><span class="sxs-lookup"><span data-stu-id="17626-111">Pool version</span></span></th>
<th><span data-ttu-id="17626-112">中繼伺服器版本</span><span class="sxs-lookup"><span data-stu-id="17626-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="17626-113">支援</span><span class="sxs-lookup"><span data-stu-id="17626-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17626-114">Lync Server 2013 年 2 月 2013年累計更新</span><span class="sxs-lookup"><span data-stu-id="17626-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="17626-115">Lync Server 2013 年 2 月 2013年累計更新</span><span class="sxs-lookup"><span data-stu-id="17626-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="17626-116">是</span><span class="sxs-lookup"><span data-stu-id="17626-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17626-117">Lync Server 2013 年 2 月 2013年累計更新</span><span class="sxs-lookup"><span data-stu-id="17626-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="17626-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17626-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="17626-119">否</span><span class="sxs-lookup"><span data-stu-id="17626-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17626-120">Lync Server 2013 年 2 月 2013年累計更新</span><span class="sxs-lookup"><span data-stu-id="17626-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="17626-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="17626-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="17626-122">否</span><span class="sxs-lookup"><span data-stu-id="17626-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17626-123">Lync Server 2013 年 2 月 2013年累計更新</span><span class="sxs-lookup"><span data-stu-id="17626-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="17626-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="17626-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="17626-125">否</span><span class="sxs-lookup"><span data-stu-id="17626-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17626-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17626-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="17626-127">任何</span><span class="sxs-lookup"><span data-stu-id="17626-127">any</span></span></p></td>
<td><p><span data-ttu-id="17626-128">否</span><span class="sxs-lookup"><span data-stu-id="17626-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17626-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="17626-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="17626-130">任何</span><span class="sxs-lookup"><span data-stu-id="17626-130">any</span></span></p></td>
<td><p><span data-ttu-id="17626-131">否</span><span class="sxs-lookup"><span data-stu-id="17626-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17626-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="17626-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="17626-133">任何</span><span class="sxs-lookup"><span data-stu-id="17626-133">any</span></span></p></td>
<td><p><span data-ttu-id="17626-134">否</span><span class="sxs-lookup"><span data-stu-id="17626-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="17626-135">Lync 用戶端支援</span><span class="sxs-lookup"><span data-stu-id="17626-135">Lync Client Support</span></span>

<span data-ttu-id="17626-136">下表列出位置型路由支援的用戶端。</span><span class="sxs-lookup"><span data-stu-id="17626-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17626-137">用戶端類型</span><span class="sxs-lookup"><span data-stu-id="17626-137">Client type</span></span></th>
<th><span data-ttu-id="17626-138">支援</span><span class="sxs-lookup"><span data-stu-id="17626-138">Supported</span></span></th>
<th><span data-ttu-id="17626-139">詳細資料</span><span class="sxs-lookup"><span data-stu-id="17626-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17626-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="17626-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="17626-141">是</span><span class="sxs-lookup"><span data-stu-id="17626-141">yes</span></span></p></td>
<td><p><span data-ttu-id="17626-142">包括 Lync 2013 年 2 月 2013年累計更新</span><span class="sxs-lookup"><span data-stu-id="17626-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17626-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="17626-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="17626-144">是</span><span class="sxs-lookup"><span data-stu-id="17626-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17626-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="17626-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="17626-146">否</span><span class="sxs-lookup"><span data-stu-id="17626-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17626-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="17626-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="17626-148">是</span><span class="sxs-lookup"><span data-stu-id="17626-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17626-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="17626-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="17626-150">是</span><span class="sxs-lookup"><span data-stu-id="17626-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17626-151">Lync for Windows 8</span><span class="sxs-lookup"><span data-stu-id="17626-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="17626-152">否</span><span class="sxs-lookup"><span data-stu-id="17626-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17626-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="17626-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="17626-154">否</span><span class="sxs-lookup"><span data-stu-id="17626-154">no</span></span></p></td>
<td><p><span data-ttu-id="17626-155">VoIP 必須停用 Lync Mobile 2013 用戶端如果啟用位置型路由與使用者使用。</span><span class="sxs-lookup"><span data-stu-id="17626-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17626-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="17626-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="17626-157">是</span><span class="sxs-lookup"><span data-stu-id="17626-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="17626-158">若要停用 VoIP Lync Mobile 2013 用戶端，請指派行動性原則的設定，IP 音訊/視訊，停用所有使用者啟用位置型路由與。</span><span class="sxs-lookup"><span data-stu-id="17626-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="17626-159">如需行動性原則的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-csmobilitypolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="17626-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17626-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17626-160">See Also</span></span>


[<span data-ttu-id="17626-161">規劃 Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="17626-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

