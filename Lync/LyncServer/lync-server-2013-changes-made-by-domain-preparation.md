---
title: Lync Server 2013：由網域準備所進行的變更
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
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529500"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="3ce27-102">Lync Server 2013 中的網域準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="3ce27-102">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ce27-103">_**主題上次修改日期：** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="3ce27-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="3ce27-104">下表列出 (Ace) 網域準備在網域根目錄上建立的存取控制專案。</span><span class="sxs-lookup"><span data-stu-id="3ce27-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="3ce27-105">除非另有說明，否則會繼承所有的 Ace。</span><span class="sxs-lookup"><span data-stu-id="3ce27-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="3ce27-106">加入至網域根目錄的 Ace</span><span class="sxs-lookup"><span data-stu-id="3ce27-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="3ce27-107">Ace</span><span class="sxs-lookup"><span data-stu-id="3ce27-107">ACE</span></span></th>
<th><span data-ttu-id="3ce27-108">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="3ce27-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3ce27-109">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="3ce27-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="3ce27-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="3ce27-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="3ce27-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="3ce27-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="3ce27-112">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="3ce27-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ce27-113">不繼承 (讀取容器) </span><span class="sxs-lookup"><span data-stu-id="3ce27-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3ce27-114"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-116">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-116">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-117">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-117">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-118">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ce27-119">讀取使用者 PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="3ce27-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3ce27-120"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-121">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-121">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-122">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-122">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-123">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-123">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-124">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ce27-125">讀取使用者 PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="3ce27-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="3ce27-126"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-127">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-127">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-128">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-128">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-129">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-129">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-130">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ce27-131">讀取使用者 PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="3ce27-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="3ce27-132"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-133">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-133">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-134">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-134">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-135">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-135">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-136">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ce27-137">讀取使用者 PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="3ce27-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="3ce27-138"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-139">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-139">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-140">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-140">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-141">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-141">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-142">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ce27-143">讀取使用者 PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="3ce27-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3ce27-144"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-145">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-145">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-146">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-146">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-147">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-147">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ce27-149">讀取使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3ce27-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3ce27-150"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-151">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-151">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-152">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-152">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-153">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-153">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-154">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ce27-155">寫入使用者屬性 Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="3ce27-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="3ce27-156">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-156">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-157">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-157">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-158"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-159">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-159">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-160">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ce27-161">寫入使用者 PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="3ce27-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3ce27-162">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-162">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-163">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-163">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-164"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-165">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-165">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-166">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ce27-167">寫入使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3ce27-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3ce27-168">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-168">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-169">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-169">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-170"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-171">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-171">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-172">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ce27-173">讀取所有 Active Directory 物件的 PropertySet DS-Replication-Get-Changes</span><span class="sxs-lookup"><span data-stu-id="3ce27-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="3ce27-174">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-174">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-175">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-175">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-176">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-176">No</span></span></p></td>
<td><p><span data-ttu-id="3ce27-177"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-178">否</span><span class="sxs-lookup"><span data-stu-id="3ce27-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3ce27-179">下表列出網域準備在三個內建容器中建立的 Ace：使用者、電腦和網域控制站。</span><span class="sxs-lookup"><span data-stu-id="3ce27-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="3ce27-180">除非另有說明，否則會繼承所有的 Ace。</span><span class="sxs-lookup"><span data-stu-id="3ce27-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="3ce27-181">加入至內建容器的 Ace</span><span class="sxs-lookup"><span data-stu-id="3ce27-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ce27-182">Ace</span><span class="sxs-lookup"><span data-stu-id="3ce27-182">ACE</span></span></th>
<th><span data-ttu-id="3ce27-183">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="3ce27-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3ce27-184">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="3ce27-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ce27-185">不繼承 (讀取容器) </span><span class="sxs-lookup"><span data-stu-id="3ce27-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3ce27-186"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce27-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3ce27-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

