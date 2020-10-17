---
title: Lync Server 2013： Grant-CsSetupPermission 所做的變更
description: Lync Server 2013： Grant-CsSetupPermission 所做的變更。
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
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543599"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="f0d2b-103">Lync Server 2013 中 Grant-CsSetupPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="f0d2b-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0d2b-104">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f0d2b-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f0d2b-105">若要委派設定，您可以將許可權授與特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 通用群組，啟用該 OU 中 RTCUniversalServerAdmins 群組的成員，以在指定的網域中安裝 Lync Server 2013，而不是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="f0d2b-106">**Grant-CsSetupPermission** Cmdlet 會授與組織單位上的 RTCUniversalServerAdmins 群組許可權，如下表所指定：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="f0d2b-107">授與 OU 中物件的許可權</span><span class="sxs-lookup"><span data-stu-id="f0d2b-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0d2b-108">許可權適用于：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="f0d2b-109">授與的許可權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0d2b-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f0d2b-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-111">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-112">讀取 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="f0d2b-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-113">寫入 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="f0d2b-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-114">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-115">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="f0d2b-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d2b-116">子代 serviceConnectionPoint 物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-117">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-118">讀取權限</span><span class="sxs-lookup"><span data-stu-id="f0d2b-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-119">寫入權限</span><span class="sxs-lookup"><span data-stu-id="f0d2b-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-120">建立子項</span><span class="sxs-lookup"><span data-stu-id="f0d2b-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-121">刪除子項</span><span class="sxs-lookup"><span data-stu-id="f0d2b-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-122">清單內容</span><span class="sxs-lookup"><span data-stu-id="f0d2b-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-123">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-124">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-125">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d2b-126">子代 msRTCSIP-Server 物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-127">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-128">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-129">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-130">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d2b-131">子代 msRTCSIP-WebComponents 物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-132">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-133">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-134">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-135">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d2b-136">子代 msRTCSIP-MCU 物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-137">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-138">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-139">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-140">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d2b-141">子代 msRTCSIP-MediationServer 物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-142">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-143">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-144">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-145">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d2b-146">子代 msRTCSIP-ApplicationServer 物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-147">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-148">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-149">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-150">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0d2b-151">子代 msRTCSIP-ConnectionPoint 物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-152">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-153">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-154">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-155">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0d2b-156">子代電腦物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="f0d2b-157">ServiceConnectionPoint 的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-158">建立子物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-159">刪除子物件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="f0d2b-160">刪除樹</span><span class="sxs-lookup"><span data-stu-id="f0d2b-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="f0d2b-161">公用資訊的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-162">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="f0d2b-163">DNS 主機名稱的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0d2b-164">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="f0d2b-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

