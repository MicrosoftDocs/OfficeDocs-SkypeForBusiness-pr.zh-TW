---
title: Lync Server 2013：位置基礎路由的用戶端和伺服器支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d388f-102">Lync Server 2013 中的位置基礎路由的用戶端和伺服器支援</span><span class="sxs-lookup"><span data-stu-id="d388f-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d388f-103">_**主題上次修改日期：** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="d388f-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="d388f-104">Lync Server 會強制執行以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="d388f-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="d388f-105">Lync Server 可以識別使用者從公司網路中連線的網路網站。</span><span class="sxs-lookup"><span data-stu-id="d388f-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="d388f-106">由於遠端使用者位於公司網路之外，因此其位置被認為是未知的。</span><span class="sxs-lookup"><span data-stu-id="d388f-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="d388f-107">Lync Server 支援</span><span class="sxs-lookup"><span data-stu-id="d388f-107">Lync Server Support</span></span>

<span data-ttu-id="d388f-108">位置式路由要求 Lync Server 2013 CU1 是在指定拓撲中的所有前端池和標準版伺服器上部署。</span><span class="sxs-lookup"><span data-stu-id="d388f-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="d388f-109">如果未在拓撲中的特定 Lync 元件上安裝 Lync Server 2013 CU1，則無法完全強制執行以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="d388f-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="d388f-110">下表列出針對位置路由支援的伺服器角色與版本組合。</span><span class="sxs-lookup"><span data-stu-id="d388f-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d388f-111">泳池版本</span><span class="sxs-lookup"><span data-stu-id="d388f-111">Pool version</span></span></th>
<th><span data-ttu-id="d388f-112">中繼伺服器版本</span><span class="sxs-lookup"><span data-stu-id="d388f-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="d388f-113">受</span><span class="sxs-lookup"><span data-stu-id="d388f-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d388f-114">Lync Server 2013 2013 年2月累計更新</span><span class="sxs-lookup"><span data-stu-id="d388f-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="d388f-115">Lync Server 2013 2013 年2月累計更新</span><span class="sxs-lookup"><span data-stu-id="d388f-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="d388f-116">是的</span><span class="sxs-lookup"><span data-stu-id="d388f-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d388f-117">Lync Server 2013 2013 年2月累計更新</span><span class="sxs-lookup"><span data-stu-id="d388f-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="d388f-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d388f-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="d388f-119">不</span><span class="sxs-lookup"><span data-stu-id="d388f-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d388f-120">Lync Server 2013 2013 年2月累計更新</span><span class="sxs-lookup"><span data-stu-id="d388f-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="d388f-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d388f-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="d388f-122">不</span><span class="sxs-lookup"><span data-stu-id="d388f-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d388f-123">Lync Server 2013 2013 年2月累計更新</span><span class="sxs-lookup"><span data-stu-id="d388f-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="d388f-124">Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d388f-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d388f-125">不</span><span class="sxs-lookup"><span data-stu-id="d388f-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d388f-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d388f-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="d388f-127">每</span><span class="sxs-lookup"><span data-stu-id="d388f-127">any</span></span></p></td>
<td><p><span data-ttu-id="d388f-128">不</span><span class="sxs-lookup"><span data-stu-id="d388f-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d388f-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d388f-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="d388f-130">每</span><span class="sxs-lookup"><span data-stu-id="d388f-130">any</span></span></p></td>
<td><p><span data-ttu-id="d388f-131">不</span><span class="sxs-lookup"><span data-stu-id="d388f-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d388f-132">Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d388f-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d388f-133">每</span><span class="sxs-lookup"><span data-stu-id="d388f-133">any</span></span></p></td>
<td><p><span data-ttu-id="d388f-134">不</span><span class="sxs-lookup"><span data-stu-id="d388f-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="d388f-135">Lync 用戶端支援</span><span class="sxs-lookup"><span data-stu-id="d388f-135">Lync Client Support</span></span>

<span data-ttu-id="d388f-136">下表會識別以位置為基礎的路由支援的用戶端。</span><span class="sxs-lookup"><span data-stu-id="d388f-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d388f-137">用戶端類型</span><span class="sxs-lookup"><span data-stu-id="d388f-137">Client type</span></span></th>
<th><span data-ttu-id="d388f-138">受</span><span class="sxs-lookup"><span data-stu-id="d388f-138">Supported</span></span></th>
<th><span data-ttu-id="d388f-139">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d388f-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d388f-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d388f-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="d388f-141">是的</span><span class="sxs-lookup"><span data-stu-id="d388f-141">yes</span></span></p></td>
<td><p><span data-ttu-id="d388f-142">包括 Lync 2013 2013 年2月累計更新</span><span class="sxs-lookup"><span data-stu-id="d388f-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d388f-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d388f-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="d388f-144">是的</span><span class="sxs-lookup"><span data-stu-id="d388f-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d388f-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d388f-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="d388f-146">不</span><span class="sxs-lookup"><span data-stu-id="d388f-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d388f-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d388f-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="d388f-148">是的</span><span class="sxs-lookup"><span data-stu-id="d388f-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d388f-149">Lync 助理</span><span class="sxs-lookup"><span data-stu-id="d388f-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="d388f-150">是的</span><span class="sxs-lookup"><span data-stu-id="d388f-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d388f-151">Windows 8 版 Lync</span><span class="sxs-lookup"><span data-stu-id="d388f-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="d388f-152">不</span><span class="sxs-lookup"><span data-stu-id="d388f-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d388f-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="d388f-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="d388f-154">不</span><span class="sxs-lookup"><span data-stu-id="d388f-154">no</span></span></p></td>
<td><p><span data-ttu-id="d388f-155">如果使用者使用的是啟用位置路由的使用者，則必須針對 Lync Mobile 2013 用戶端停用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="d388f-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d388f-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="d388f-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="d388f-157">是的</span><span class="sxs-lookup"><span data-stu-id="d388f-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="d388f-158">若要針對 Lync Mobile 2013 用戶端停用 VoIP，請針對所有啟用位置路由的使用者，指派您已停用的設定、IP 音訊/影片的行動原則。</span><span class="sxs-lookup"><span data-stu-id="d388f-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="d388f-159">如需行動原則的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">新 CsMobilityPolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="d388f-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d388f-160">請參閱</span><span class="sxs-lookup"><span data-stu-id="d388f-160">See Also</span></span>


[<span data-ttu-id="d388f-161">在 Lync Server 2013 中規劃位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="d388f-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

