---
title: Lync Server 2013：由網域準備所做的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="be090-102">在 Lync Server 2013 中由網域準備所做的變更</span><span class="sxs-lookup"><span data-stu-id="be090-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be090-103">_**主題上次修改日期：** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="be090-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="be090-104">下表列出網域準備在網域根目錄上建立的存取控制專案（Ace）。</span><span class="sxs-lookup"><span data-stu-id="be090-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="be090-105">除非另有說明，否則所有 Ace 都是繼承的。</span><span class="sxs-lookup"><span data-stu-id="be090-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="be090-106">加入到網域根目錄的 Ace</span><span class="sxs-lookup"><span data-stu-id="be090-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="be090-107">A</span><span class="sxs-lookup"><span data-stu-id="be090-107">ACE</span></span></th>
<th><span data-ttu-id="be090-108">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="be090-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="be090-109">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="be090-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="be090-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="be090-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="be090-111">RTCHSUniversal-服務</span><span class="sxs-lookup"><span data-stu-id="be090-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="be090-112">已驗證-使用者</span><span class="sxs-lookup"><span data-stu-id="be090-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be090-113">讀取容器（不是繼承的）</span><span class="sxs-lookup"><span data-stu-id="be090-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="be090-114"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-116">否</span><span class="sxs-lookup"><span data-stu-id="be090-116">No</span></span></p></td>
<td><p><span data-ttu-id="be090-117">否</span><span class="sxs-lookup"><span data-stu-id="be090-117">No</span></span></p></td>
<td><p><span data-ttu-id="be090-118">否</span><span class="sxs-lookup"><span data-stu-id="be090-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be090-119">讀取使用者 PropertySet 使用者帳戶-限制</span><span class="sxs-lookup"><span data-stu-id="be090-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="be090-120"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-121">否</span><span class="sxs-lookup"><span data-stu-id="be090-121">No</span></span></p></td>
<td><p><span data-ttu-id="be090-122">否</span><span class="sxs-lookup"><span data-stu-id="be090-122">No</span></span></p></td>
<td><p><span data-ttu-id="be090-123">否</span><span class="sxs-lookup"><span data-stu-id="be090-123">No</span></span></p></td>
<td><p><span data-ttu-id="be090-124">否</span><span class="sxs-lookup"><span data-stu-id="be090-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be090-125">閱讀使用者 PropertySet 個人資訊</span><span class="sxs-lookup"><span data-stu-id="be090-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="be090-126"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-127">否</span><span class="sxs-lookup"><span data-stu-id="be090-127">No</span></span></p></td>
<td><p><span data-ttu-id="be090-128">否</span><span class="sxs-lookup"><span data-stu-id="be090-128">No</span></span></p></td>
<td><p><span data-ttu-id="be090-129">否</span><span class="sxs-lookup"><span data-stu-id="be090-129">No</span></span></p></td>
<td><p><span data-ttu-id="be090-130">否</span><span class="sxs-lookup"><span data-stu-id="be090-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be090-131">閱讀使用者 PropertySet 一般資訊</span><span class="sxs-lookup"><span data-stu-id="be090-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="be090-132"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-133">否</span><span class="sxs-lookup"><span data-stu-id="be090-133">No</span></span></p></td>
<td><p><span data-ttu-id="be090-134">否</span><span class="sxs-lookup"><span data-stu-id="be090-134">No</span></span></p></td>
<td><p><span data-ttu-id="be090-135">否</span><span class="sxs-lookup"><span data-stu-id="be090-135">No</span></span></p></td>
<td><p><span data-ttu-id="be090-136">否</span><span class="sxs-lookup"><span data-stu-id="be090-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be090-137">讀取使用者 PropertySet 公用資訊</span><span class="sxs-lookup"><span data-stu-id="be090-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="be090-138"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-139">否</span><span class="sxs-lookup"><span data-stu-id="be090-139">No</span></span></p></td>
<td><p><span data-ttu-id="be090-140">否</span><span class="sxs-lookup"><span data-stu-id="be090-140">No</span></span></p></td>
<td><p><span data-ttu-id="be090-141">否</span><span class="sxs-lookup"><span data-stu-id="be090-141">No</span></span></p></td>
<td><p><span data-ttu-id="be090-142">否</span><span class="sxs-lookup"><span data-stu-id="be090-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be090-143">讀取使用者 PropertySet RTCUserSearchProperty-設定</span><span class="sxs-lookup"><span data-stu-id="be090-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="be090-144"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-145">否</span><span class="sxs-lookup"><span data-stu-id="be090-145">No</span></span></p></td>
<td><p><span data-ttu-id="be090-146">否</span><span class="sxs-lookup"><span data-stu-id="be090-146">No</span></span></p></td>
<td><p><span data-ttu-id="be090-147">否</span><span class="sxs-lookup"><span data-stu-id="be090-147">No</span></span></p></td>
<td><p><span data-ttu-id="be090-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be090-149">讀取使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="be090-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="be090-150"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-151">否</span><span class="sxs-lookup"><span data-stu-id="be090-151">No</span></span></p></td>
<td><p><span data-ttu-id="be090-152">否</span><span class="sxs-lookup"><span data-stu-id="be090-152">No</span></span></p></td>
<td><p><span data-ttu-id="be090-153">否</span><span class="sxs-lookup"><span data-stu-id="be090-153">No</span></span></p></td>
<td><p><span data-ttu-id="be090-154">否</span><span class="sxs-lookup"><span data-stu-id="be090-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be090-155">撰寫使用者屬性 Proxy-位址</span><span class="sxs-lookup"><span data-stu-id="be090-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="be090-156">否</span><span class="sxs-lookup"><span data-stu-id="be090-156">No</span></span></p></td>
<td><p><span data-ttu-id="be090-157">否</span><span class="sxs-lookup"><span data-stu-id="be090-157">No</span></span></p></td>
<td><p><span data-ttu-id="be090-158"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-159">否</span><span class="sxs-lookup"><span data-stu-id="be090-159">No</span></span></p></td>
<td><p><span data-ttu-id="be090-160">否</span><span class="sxs-lookup"><span data-stu-id="be090-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be090-161">撰寫使用者 PropertySet RTCUserSearchProperty-設定</span><span class="sxs-lookup"><span data-stu-id="be090-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="be090-162">否</span><span class="sxs-lookup"><span data-stu-id="be090-162">No</span></span></p></td>
<td><p><span data-ttu-id="be090-163">否</span><span class="sxs-lookup"><span data-stu-id="be090-163">No</span></span></p></td>
<td><p><span data-ttu-id="be090-164"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-165">否</span><span class="sxs-lookup"><span data-stu-id="be090-165">No</span></span></p></td>
<td><p><span data-ttu-id="be090-166">否</span><span class="sxs-lookup"><span data-stu-id="be090-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be090-167">撰寫使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="be090-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="be090-168">否</span><span class="sxs-lookup"><span data-stu-id="be090-168">No</span></span></p></td>
<td><p><span data-ttu-id="be090-169">否</span><span class="sxs-lookup"><span data-stu-id="be090-169">No</span></span></p></td>
<td><p><span data-ttu-id="be090-170"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-171">否</span><span class="sxs-lookup"><span data-stu-id="be090-171">No</span></span></p></td>
<td><p><span data-ttu-id="be090-172">否</span><span class="sxs-lookup"><span data-stu-id="be090-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be090-173">讀取 PropertySet DS-複製-變更所有 Active Directory 物件</span><span class="sxs-lookup"><span data-stu-id="be090-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="be090-174">否</span><span class="sxs-lookup"><span data-stu-id="be090-174">No</span></span></p></td>
<td><p><span data-ttu-id="be090-175">否</span><span class="sxs-lookup"><span data-stu-id="be090-175">No</span></span></p></td>
<td><p><span data-ttu-id="be090-176">否</span><span class="sxs-lookup"><span data-stu-id="be090-176">No</span></span></p></td>
<td><p><span data-ttu-id="be090-177"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-178">否</span><span class="sxs-lookup"><span data-stu-id="be090-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be090-179">下表列出了網域準備在三個內建容器中建立的 Ace：使用者、電腦及網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="be090-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="be090-180">除非另有說明，否則所有 Ace 都是繼承的。</span><span class="sxs-lookup"><span data-stu-id="be090-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="be090-181">加入到內建容器中的 Ace</span><span class="sxs-lookup"><span data-stu-id="be090-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be090-182">A</span><span class="sxs-lookup"><span data-stu-id="be090-182">ACE</span></span></th>
<th><span data-ttu-id="be090-183">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="be090-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="be090-184">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="be090-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be090-185">讀取容器（不是繼承的）</span><span class="sxs-lookup"><span data-stu-id="be090-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="be090-186"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="be090-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="be090-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

