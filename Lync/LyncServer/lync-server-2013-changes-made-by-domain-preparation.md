---
title: Lync Server 2013： 網域準備所進行的變更
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
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="4ddad-102">Lync Server 2013 中的網域準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="4ddad-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ddad-103">_**主題上次修改日期：** 2010年-10-18_</span><span class="sxs-lookup"><span data-stu-id="4ddad-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="4ddad-104">下表列出網域準備作業會建立在網域根目錄存取控制項目 (Ace)。</span><span class="sxs-lookup"><span data-stu-id="4ddad-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="4ddad-105">除非另有說明，是繼承而來的所有 Ace。</span><span class="sxs-lookup"><span data-stu-id="4ddad-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="4ddad-106">新增到網域根目錄的 Ace</span><span class="sxs-lookup"><span data-stu-id="4ddad-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="4ddad-107">ACE</span><span class="sxs-lookup"><span data-stu-id="4ddad-107">ACE</span></span></th>
<th><span data-ttu-id="4ddad-108">RTCUniversal UserReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="4ddad-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="4ddad-109">RTCUniversal ServerReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="4ddad-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="4ddad-110">RTCUniversal UserAdmins</span><span class="sxs-lookup"><span data-stu-id="4ddad-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="4ddad-111">RTCHSUniversal 服務</span><span class="sxs-lookup"><span data-stu-id="4ddad-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="4ddad-112">驗證使用者</span><span class="sxs-lookup"><span data-stu-id="4ddad-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ddad-113">讀取容器 （非繼承的）</span><span class="sxs-lookup"><span data-stu-id="4ddad-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="4ddad-114"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-116">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-116">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-117">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-117">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-118">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ddad-119">讀取使用者 User-account-restrictions 帳戶限制</span><span class="sxs-lookup"><span data-stu-id="4ddad-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="4ddad-120"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-121">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-121">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-122">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-122">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-123">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-123">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-124">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ddad-125">讀取使用者 Personal-information</span><span class="sxs-lookup"><span data-stu-id="4ddad-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="4ddad-126"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-127">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-127">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-128">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-128">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-129">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-129">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-130">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ddad-131">讀取使用者 General-information</span><span class="sxs-lookup"><span data-stu-id="4ddad-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="4ddad-132"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-133">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-133">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-134">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-134">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-135">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-135">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-136">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ddad-137">讀取使用者 Public-information</span><span class="sxs-lookup"><span data-stu-id="4ddad-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="4ddad-138"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-139">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-139">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-140">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-140">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-141">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-141">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-142">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ddad-143">讀取使用者屬性集 Rtcusersearchproperty-set</span><span class="sxs-lookup"><span data-stu-id="4ddad-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="4ddad-144"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-145">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-145">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-146">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-146">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-147">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-147">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ddad-149">讀取使用者屬性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4ddad-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="4ddad-150"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-151">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-151">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-152">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-152">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-153">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-153">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-154">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ddad-155">寫入使用者屬性 Proxy-addresses</span><span class="sxs-lookup"><span data-stu-id="4ddad-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="4ddad-156">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-156">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-157">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-157">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-158"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-159">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-159">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-160">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ddad-161">寫入使用者屬性集 Rtcusersearchproperty-set</span><span class="sxs-lookup"><span data-stu-id="4ddad-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="4ddad-162">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-162">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-163">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-163">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-164"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-165">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-165">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-166">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ddad-167">寫入使用者屬性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4ddad-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="4ddad-168">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-168">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-169">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-169">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-170"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-171">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-171">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-172">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ddad-173">讀取屬性 DS-複寫的 Get-變更的所有 Active Directory 物件</span><span class="sxs-lookup"><span data-stu-id="4ddad-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="4ddad-174">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-174">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-175">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-175">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-176">否</span><span class="sxs-lookup"><span data-stu-id="4ddad-176">No</span></span></p></td>
<td><p><span data-ttu-id="4ddad-177"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-178">無</span><span class="sxs-lookup"><span data-stu-id="4ddad-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4ddad-179">下表列出網域準備會在三個內建容器中建立之 Ace： 使用者、 電腦和網域控制站。</span><span class="sxs-lookup"><span data-stu-id="4ddad-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="4ddad-180">除非另有說明，是繼承而來的所有 Ace。</span><span class="sxs-lookup"><span data-stu-id="4ddad-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="4ddad-181">新增到內建容器的 Ace</span><span class="sxs-lookup"><span data-stu-id="4ddad-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ddad-182">ACE</span><span class="sxs-lookup"><span data-stu-id="4ddad-182">ACE</span></span></th>
<th><span data-ttu-id="4ddad-183">RTCUniversal UserReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="4ddad-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="4ddad-184">RTCUniversal ServerReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="4ddad-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ddad-185">讀取容器 （非繼承的）</span><span class="sxs-lookup"><span data-stu-id="4ddad-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="4ddad-186"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddad-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="4ddad-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

