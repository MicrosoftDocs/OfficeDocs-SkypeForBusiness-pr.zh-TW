---
title: Lync Server 2013： Grant-CsSetupPermission 所做的變更
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
ms.openlocfilehash: 8ec13a23daf0f3dae47ae0ce0dc630e64c596e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529410"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="996ba-102">Lync Server 2013 中 Grant-CsSetupPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="996ba-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="996ba-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="996ba-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="996ba-104">若要委派設定，您可以將許可權授與特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 通用群組，啟用該 OU 中 RTCUniversalServerAdmins 群組的成員，以在指定的網域中安裝 Lync Server 2013，而不是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="996ba-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="996ba-105">**Grant-CsSetupPermission** Cmdlet 會授與組織單位上的 RTCUniversalServerAdmins 群組許可權，如下表所指定：</span><span class="sxs-lookup"><span data-stu-id="996ba-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="996ba-106">授與 OU 中物件的許可權</span><span class="sxs-lookup"><span data-stu-id="996ba-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="996ba-107">許可權適用于：</span><span class="sxs-lookup"><span data-stu-id="996ba-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="996ba-108">授與的許可權：</span><span class="sxs-lookup"><span data-stu-id="996ba-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="996ba-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="996ba-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="996ba-110">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-111">讀取 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="996ba-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="996ba-112">寫入 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="996ba-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="996ba-113">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="996ba-114">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="996ba-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="996ba-115">子代 serviceConnectionPoint 物件</span><span class="sxs-lookup"><span data-stu-id="996ba-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-116">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-117">讀取權限</span><span class="sxs-lookup"><span data-stu-id="996ba-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="996ba-118">寫入權限</span><span class="sxs-lookup"><span data-stu-id="996ba-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="996ba-119">建立子項</span><span class="sxs-lookup"><span data-stu-id="996ba-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="996ba-120">刪除子項</span><span class="sxs-lookup"><span data-stu-id="996ba-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="996ba-121">清單內容</span><span class="sxs-lookup"><span data-stu-id="996ba-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="996ba-122">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="996ba-123">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="996ba-124">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="996ba-125">子代 msRTCSIP-Server 物件</span><span class="sxs-lookup"><span data-stu-id="996ba-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-126">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-127">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="996ba-128">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="996ba-129">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="996ba-130">子代 msRTCSIP-WebComponents 物件</span><span class="sxs-lookup"><span data-stu-id="996ba-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-131">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-132">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="996ba-133">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="996ba-134">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="996ba-135">子代 msRTCSIP-MCU 物件</span><span class="sxs-lookup"><span data-stu-id="996ba-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-136">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-137">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="996ba-138">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="996ba-139">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="996ba-140">子代 msRTCSIP-MediationServer 物件</span><span class="sxs-lookup"><span data-stu-id="996ba-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-141">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-142">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="996ba-143">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="996ba-144">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="996ba-145">子代 msRTCSIP-ApplicationServer 物件</span><span class="sxs-lookup"><span data-stu-id="996ba-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-146">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-147">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="996ba-148">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="996ba-149">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="996ba-150">子代 msRTCSIP-ConnectionPoint 物件</span><span class="sxs-lookup"><span data-stu-id="996ba-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-151">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-152">Write 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="996ba-153">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="996ba-154">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="996ba-155">子代電腦物件</span><span class="sxs-lookup"><span data-stu-id="996ba-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="996ba-156">ServiceConnectionPoint 的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-157">建立子物件</span><span class="sxs-lookup"><span data-stu-id="996ba-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="996ba-158">刪除子物件</span><span class="sxs-lookup"><span data-stu-id="996ba-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="996ba-159">刪除樹</span><span class="sxs-lookup"><span data-stu-id="996ba-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="996ba-160">公用資訊的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-161">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="996ba-162">DNS 主機名稱的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="996ba-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="996ba-163">Read 屬性</span><span class="sxs-lookup"><span data-stu-id="996ba-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

