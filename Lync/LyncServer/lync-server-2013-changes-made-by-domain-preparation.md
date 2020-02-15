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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="58f1b-102">Lync Server 2013 中的網域準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="58f1b-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58f1b-103">_**主題上次修改日期：** 2010年-10-18_</span><span class="sxs-lookup"><span data-stu-id="58f1b-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="58f1b-104">下表列出網域準備作業會建立在網域根目錄存取控制項目 (Ace)。</span><span class="sxs-lookup"><span data-stu-id="58f1b-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="58f1b-105">除非另有說明，是繼承而來的所有 Ace。</span><span class="sxs-lookup"><span data-stu-id="58f1b-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="58f1b-106">新增到網域根目錄的 Ace</span><span class="sxs-lookup"><span data-stu-id="58f1b-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="58f1b-107">ACE</span><span class="sxs-lookup"><span data-stu-id="58f1b-107">ACE</span></span></th>
<th><span data-ttu-id="58f1b-108">RTCUniversal UserReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="58f1b-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="58f1b-109">RTCUniversal ServerReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="58f1b-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="58f1b-110">RTCUniversal UserAdmins</span><span class="sxs-lookup"><span data-stu-id="58f1b-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="58f1b-111">RTCHSUniversal 服務</span><span class="sxs-lookup"><span data-stu-id="58f1b-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="58f1b-112">驗證使用者</span><span class="sxs-lookup"><span data-stu-id="58f1b-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58f1b-113">讀取容器 （非繼承的）</span><span class="sxs-lookup"><span data-stu-id="58f1b-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="58f1b-114"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-116">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-116">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-117">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-117">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-118">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f1b-119">讀取使用者 User-account-restrictions 帳戶限制</span><span class="sxs-lookup"><span data-stu-id="58f1b-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="58f1b-120"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-121">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-121">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-122">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-122">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-123">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-123">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-124">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f1b-125">讀取使用者 Personal-information</span><span class="sxs-lookup"><span data-stu-id="58f1b-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="58f1b-126"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-127">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-127">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-128">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-128">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-129">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-129">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-130">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f1b-131">讀取使用者 General-information</span><span class="sxs-lookup"><span data-stu-id="58f1b-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="58f1b-132"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-133">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-133">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-134">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-134">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-135">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-135">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-136">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f1b-137">讀取使用者 Public-information</span><span class="sxs-lookup"><span data-stu-id="58f1b-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="58f1b-138"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-139">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-139">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-140">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-140">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-141">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-141">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-142">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f1b-143">讀取使用者屬性集 Rtcusersearchproperty-set</span><span class="sxs-lookup"><span data-stu-id="58f1b-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="58f1b-144"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-145">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-145">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-146">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-146">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-147">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-147">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f1b-149">讀取使用者屬性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="58f1b-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="58f1b-150"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-151">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-151">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-152">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-152">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-153">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-153">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-154">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f1b-155">寫入使用者屬性 Proxy-addresses</span><span class="sxs-lookup"><span data-stu-id="58f1b-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="58f1b-156">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-156">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-157">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-157">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-158"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-159">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-159">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-160">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f1b-161">寫入使用者屬性集 Rtcusersearchproperty-set</span><span class="sxs-lookup"><span data-stu-id="58f1b-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="58f1b-162">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-162">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-163">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-163">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-164"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-165">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-165">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-166">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f1b-167">寫入使用者屬性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="58f1b-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="58f1b-168">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-168">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-169">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-169">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-170"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-171">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-171">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-172">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f1b-173">讀取屬性 DS-複寫的 Get-變更的所有 Active Directory 物件</span><span class="sxs-lookup"><span data-stu-id="58f1b-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="58f1b-174">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-174">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-175">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-175">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-176">否</span><span class="sxs-lookup"><span data-stu-id="58f1b-176">No</span></span></p></td>
<td><p><span data-ttu-id="58f1b-177"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-178">無</span><span class="sxs-lookup"><span data-stu-id="58f1b-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58f1b-179">下表列出網域準備會在三個內建容器中建立之 Ace： 使用者、 電腦和網域控制站。</span><span class="sxs-lookup"><span data-stu-id="58f1b-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="58f1b-180">除非另有說明，是繼承而來的所有 Ace。</span><span class="sxs-lookup"><span data-stu-id="58f1b-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="58f1b-181">新增到內建容器的 Ace</span><span class="sxs-lookup"><span data-stu-id="58f1b-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58f1b-182">ACE</span><span class="sxs-lookup"><span data-stu-id="58f1b-182">ACE</span></span></th>
<th><span data-ttu-id="58f1b-183">RTCUniversal UserReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="58f1b-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="58f1b-184">RTCUniversal ServerReadOnly 群組</span><span class="sxs-lookup"><span data-stu-id="58f1b-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58f1b-185">讀取容器 （非繼承的）</span><span class="sxs-lookup"><span data-stu-id="58f1b-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="58f1b-186"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="58f1b-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="58f1b-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

