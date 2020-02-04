---
title: Lync Server 2013：由授與授權所做的變更 CsSetupPermission
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="41800-102">在 Lync Server 2013 中由 Grant CsSetupPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="41800-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41800-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="41800-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="41800-104">若要委派設定，您可以為特定 Active Directory 組織單位（OU）授予 RTCUniversalServerAdmins 通用群組的許可權，讓該 OU 中的 RTCUniversalServerAdmins 群組成員在指定的中安裝 Lync Server 2013。網域，而不是 [網域管理員] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="41800-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="41800-105">CsSetupPermission Cmdlet 會**授**與組織單位上的 RTCUniversalServerAdmins 群組許可權，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="41800-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="41800-106">在 OU 中授與物件的許可權</span><span class="sxs-lookup"><span data-stu-id="41800-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41800-107">許可權適用于：</span><span class="sxs-lookup"><span data-stu-id="41800-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="41800-108">已授與許可權：</span><span class="sxs-lookup"><span data-stu-id="41800-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41800-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="41800-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="41800-110">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-111">Read servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="41800-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="41800-112">撰寫 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="41800-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="41800-113">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="41800-114">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="41800-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41800-115">後代 serviceConnectionPoint 物件</span><span class="sxs-lookup"><span data-stu-id="41800-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="41800-116">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-117">讀取權限</span><span class="sxs-lookup"><span data-stu-id="41800-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="41800-118">寫入權限</span><span class="sxs-lookup"><span data-stu-id="41800-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="41800-119">建立子系</span><span class="sxs-lookup"><span data-stu-id="41800-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="41800-120">刪除子系</span><span class="sxs-lookup"><span data-stu-id="41800-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="41800-121">清單內容</span><span class="sxs-lookup"><span data-stu-id="41800-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="41800-122">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="41800-123">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="41800-124">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41800-125">子代 msRTCSIP-伺服器物件</span><span class="sxs-lookup"><span data-stu-id="41800-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="41800-126">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-127">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="41800-128">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="41800-129">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41800-130">子代 msRTCSIP-WebComponents 物件</span><span class="sxs-lookup"><span data-stu-id="41800-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="41800-131">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-132">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="41800-133">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="41800-134">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41800-135">子代 msRTCSIP-MCU 物件</span><span class="sxs-lookup"><span data-stu-id="41800-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="41800-136">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-137">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="41800-138">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="41800-139">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41800-140">子代 msRTCSIP-MediationServer 物件</span><span class="sxs-lookup"><span data-stu-id="41800-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="41800-141">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-142">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="41800-143">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="41800-144">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41800-145">子代 msRTCSIP-ApplicationServer 物件</span><span class="sxs-lookup"><span data-stu-id="41800-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="41800-146">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-147">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="41800-148">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="41800-149">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41800-150">子代 msRTCSIP-ConnectionPoint 物件</span><span class="sxs-lookup"><span data-stu-id="41800-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="41800-151">特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-152">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="41800-153">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="41800-154">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41800-155">後代電腦物件</span><span class="sxs-lookup"><span data-stu-id="41800-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="41800-156">用於 serviceConnectionPoint 的特殊存取：</span><span class="sxs-lookup"><span data-stu-id="41800-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-157">建立子物件</span><span class="sxs-lookup"><span data-stu-id="41800-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="41800-158">刪除子物件</span><span class="sxs-lookup"><span data-stu-id="41800-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="41800-159">刪除樹</span><span class="sxs-lookup"><span data-stu-id="41800-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="41800-160">公用資訊的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="41800-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-161">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="41800-162">DNS 主機名稱的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="41800-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="41800-163">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="41800-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

