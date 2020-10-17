---
title: Lync Server 2013：由網域準備所進行的變更
description: Lync Server 2013：由網域準備所進行的變更。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543689"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="34c23-103">Lync Server 2013 中的網域準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="34c23-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34c23-104">_**主題上次修改日期：** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="34c23-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="34c23-105">下表列出 (Ace) 網域準備在網域根目錄上建立的存取控制專案。</span><span class="sxs-lookup"><span data-stu-id="34c23-105">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="34c23-106">除非另有說明，否則會繼承所有的 Ace。</span><span class="sxs-lookup"><span data-stu-id="34c23-106">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="34c23-107">加入至網域根目錄的 Ace</span><span class="sxs-lookup"><span data-stu-id="34c23-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34c23-108">Ace</span><span class="sxs-lookup"><span data-stu-id="34c23-108">ACE</span></span></th>
<th><span data-ttu-id="34c23-109">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="34c23-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="34c23-110">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="34c23-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="34c23-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="34c23-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="34c23-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="34c23-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="34c23-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="34c23-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34c23-114">不繼承 (讀取容器) </span><span class="sxs-lookup"><span data-stu-id="34c23-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="34c23-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-116"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-117">否</span><span class="sxs-lookup"><span data-stu-id="34c23-117">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-118">否</span><span class="sxs-lookup"><span data-stu-id="34c23-118">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-119">否</span><span class="sxs-lookup"><span data-stu-id="34c23-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c23-120">讀取使用者 PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="34c23-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="34c23-121"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-122">否</span><span class="sxs-lookup"><span data-stu-id="34c23-122">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-123">否</span><span class="sxs-lookup"><span data-stu-id="34c23-123">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-124">否</span><span class="sxs-lookup"><span data-stu-id="34c23-124">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-125">否</span><span class="sxs-lookup"><span data-stu-id="34c23-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c23-126">讀取使用者 PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="34c23-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="34c23-127"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-128">否</span><span class="sxs-lookup"><span data-stu-id="34c23-128">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-129">否</span><span class="sxs-lookup"><span data-stu-id="34c23-129">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-130">否</span><span class="sxs-lookup"><span data-stu-id="34c23-130">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-131">否</span><span class="sxs-lookup"><span data-stu-id="34c23-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c23-132">讀取使用者 PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="34c23-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="34c23-133"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-134">否</span><span class="sxs-lookup"><span data-stu-id="34c23-134">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-135">否</span><span class="sxs-lookup"><span data-stu-id="34c23-135">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-136">否</span><span class="sxs-lookup"><span data-stu-id="34c23-136">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-137">否</span><span class="sxs-lookup"><span data-stu-id="34c23-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c23-138">讀取使用者 PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="34c23-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="34c23-139"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-140">否</span><span class="sxs-lookup"><span data-stu-id="34c23-140">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-141">否</span><span class="sxs-lookup"><span data-stu-id="34c23-141">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-142">否</span><span class="sxs-lookup"><span data-stu-id="34c23-142">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-143">否</span><span class="sxs-lookup"><span data-stu-id="34c23-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c23-144">讀取使用者 PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="34c23-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="34c23-145"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-146">否</span><span class="sxs-lookup"><span data-stu-id="34c23-146">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-147">否</span><span class="sxs-lookup"><span data-stu-id="34c23-147">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-148">否</span><span class="sxs-lookup"><span data-stu-id="34c23-148">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-149"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c23-150">讀取使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="34c23-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="34c23-151"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-152">否</span><span class="sxs-lookup"><span data-stu-id="34c23-152">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-153">否</span><span class="sxs-lookup"><span data-stu-id="34c23-153">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-154">否</span><span class="sxs-lookup"><span data-stu-id="34c23-154">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-155">否</span><span class="sxs-lookup"><span data-stu-id="34c23-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c23-156">寫入使用者屬性 Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="34c23-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="34c23-157">否</span><span class="sxs-lookup"><span data-stu-id="34c23-157">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-158">否</span><span class="sxs-lookup"><span data-stu-id="34c23-158">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-159"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-160">否</span><span class="sxs-lookup"><span data-stu-id="34c23-160">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-161">否</span><span class="sxs-lookup"><span data-stu-id="34c23-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c23-162">寫入使用者 PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="34c23-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="34c23-163">否</span><span class="sxs-lookup"><span data-stu-id="34c23-163">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-164">否</span><span class="sxs-lookup"><span data-stu-id="34c23-164">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-165"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-166">否</span><span class="sxs-lookup"><span data-stu-id="34c23-166">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-167">否</span><span class="sxs-lookup"><span data-stu-id="34c23-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c23-168">寫入使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="34c23-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="34c23-169">否</span><span class="sxs-lookup"><span data-stu-id="34c23-169">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-170">否</span><span class="sxs-lookup"><span data-stu-id="34c23-170">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-171"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-172">否</span><span class="sxs-lookup"><span data-stu-id="34c23-172">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-173">否</span><span class="sxs-lookup"><span data-stu-id="34c23-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c23-174">讀取所有 Active Directory 物件的 PropertySet DS-Replication-Get-Changes</span><span class="sxs-lookup"><span data-stu-id="34c23-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="34c23-175">否</span><span class="sxs-lookup"><span data-stu-id="34c23-175">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-176">否</span><span class="sxs-lookup"><span data-stu-id="34c23-176">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-177">否</span><span class="sxs-lookup"><span data-stu-id="34c23-177">No</span></span></p></td>
<td><p><span data-ttu-id="34c23-178"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-179">否</span><span class="sxs-lookup"><span data-stu-id="34c23-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="34c23-180">下表列出網域準備在三個內建容器中建立的 Ace：使用者、電腦和網域控制站。</span><span class="sxs-lookup"><span data-stu-id="34c23-180">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="34c23-181">除非另有說明，否則會繼承所有的 Ace。</span><span class="sxs-lookup"><span data-stu-id="34c23-181">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="34c23-182">加入至內建容器的 Ace</span><span class="sxs-lookup"><span data-stu-id="34c23-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34c23-183">Ace</span><span class="sxs-lookup"><span data-stu-id="34c23-183">ACE</span></span></th>
<th><span data-ttu-id="34c23-184">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="34c23-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="34c23-185">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="34c23-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34c23-186">不繼承 (讀取容器) </span><span class="sxs-lookup"><span data-stu-id="34c23-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="34c23-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="34c23-188"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="34c23-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

