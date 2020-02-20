---
title: 'Lync Server 2013: Grant-cssetuppermission 所做的變更'
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="4f799-102">Grant-cssetuppermission Lync Server 2013 中所做的變更</span><span class="sxs-lookup"><span data-stu-id="4f799-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f799-103">_**主題上次修改日期：** 2012年-06-20 個_</span><span class="sxs-lookup"><span data-stu-id="4f799-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="4f799-104">若要委派設定，您可以授與權限的 RTCUniversalServerAdmins 萬用群組特定 Active Directory 組織單位 (OU)，讓該 OU 中指定之安裝 Lync Server 2013 中的 RTCUniversalServerAdmins 群組成員不需要以 Domain Admins 群組成員的網域。</span><span class="sxs-lookup"><span data-stu-id="4f799-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="4f799-105">**Grant-cssetuppermission** cmdlet 授與下表中所指定 OU 上的 RTCUniversalServerAdmins 群組權限：</span><span class="sxs-lookup"><span data-stu-id="4f799-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="4f799-106">OU 中的物件授與權限</span><span class="sxs-lookup"><span data-stu-id="4f799-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f799-107">若要套用權限：</span><span class="sxs-lookup"><span data-stu-id="4f799-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="4f799-108">授與的權限為：</span><span class="sxs-lookup"><span data-stu-id="4f799-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f799-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4f799-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="4f799-110">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-111">讀取 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="4f799-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="4f799-112">寫入 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="4f799-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="4f799-113">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="4f799-114">「 複寫目錄變更</span><span class="sxs-lookup"><span data-stu-id="4f799-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f799-115">子系 serviceConnectionPoint 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-116">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-117">讀取權限</span><span class="sxs-lookup"><span data-stu-id="4f799-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="4f799-118">寫入權限</span><span class="sxs-lookup"><span data-stu-id="4f799-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="4f799-119">建立子項</span><span class="sxs-lookup"><span data-stu-id="4f799-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="4f799-120">刪除子項</span><span class="sxs-lookup"><span data-stu-id="4f799-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="4f799-121">列出內容</span><span class="sxs-lookup"><span data-stu-id="4f799-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="4f799-122">寫入屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="4f799-123">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="4f799-124">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f799-125">子系 Msrtcsip-server 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-126">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-127">寫入屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="4f799-128">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="4f799-129">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f799-130">子系 Msrtcsip-webcomponents 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-131">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-132">寫入屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="4f799-133">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="4f799-134">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f799-135">子系 MSRTCSIP-MCU 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-136">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-137">寫入屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="4f799-138">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="4f799-139">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f799-140">子系 Msrtcsip-mediationserver 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-141">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-142">寫入屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="4f799-143">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="4f799-144">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f799-145">子系 Msrtcsip-applicationserver 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-146">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-147">寫入屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="4f799-148">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="4f799-149">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f799-150">子系 Msrtcsip-connectionpoint 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-151">特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-152">寫入屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="4f799-153">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="4f799-154">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f799-155">子系 Computer 物件</span><span class="sxs-lookup"><span data-stu-id="4f799-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="4f799-156">ServiceConnectionPoint 的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-157">建立子物件</span><span class="sxs-lookup"><span data-stu-id="4f799-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="4f799-158">刪除子物件</span><span class="sxs-lookup"><span data-stu-id="4f799-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="4f799-159">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="4f799-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="4f799-160">公用資訊的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-161">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="4f799-162">DNS 主機名稱的特殊存取權：</span><span class="sxs-lookup"><span data-stu-id="4f799-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f799-163">讀取屬性</span><span class="sxs-lookup"><span data-stu-id="4f799-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

