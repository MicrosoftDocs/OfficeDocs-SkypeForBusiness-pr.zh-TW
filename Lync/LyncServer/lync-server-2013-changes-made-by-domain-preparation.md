---
title: Lync Server 2013：由網域準備所做的變更
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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="9d8b9-102">在 Lync Server 2013 中由網域準備所做的變更</span><span class="sxs-lookup"><span data-stu-id="9d8b9-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d8b9-103">_**主題上次修改日期：** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="9d8b9-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="9d8b9-104">下表列出網域準備在網域根目錄上建立的存取控制專案（Ace）。</span><span class="sxs-lookup"><span data-stu-id="9d8b9-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="9d8b9-105">除非另有說明，否則所有 Ace 都是繼承的。</span><span class="sxs-lookup"><span data-stu-id="9d8b9-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="9d8b9-106">加入到網域根目錄的 Ace</span><span class="sxs-lookup"><span data-stu-id="9d8b9-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="9d8b9-107">A</span><span class="sxs-lookup"><span data-stu-id="9d8b9-107">ACE</span></span></th>
<th><span data-ttu-id="9d8b9-108">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="9d8b9-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="9d8b9-109">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="9d8b9-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="9d8b9-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="9d8b9-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="9d8b9-111">RTCHSUniversal-服務</span><span class="sxs-lookup"><span data-stu-id="9d8b9-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="9d8b9-112">已驗證-使用者</span><span class="sxs-lookup"><span data-stu-id="9d8b9-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d8b9-113">讀取容器（不是繼承的）</span><span class="sxs-lookup"><span data-stu-id="9d8b9-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-114"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-115"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-116">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-116">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-117">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-117">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-118">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d8b9-119">讀取使用者 PropertySet 使用者帳戶-限制</span><span class="sxs-lookup"><span data-stu-id="9d8b9-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-120"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-121">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-121">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-122">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-122">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-123">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-123">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-124">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d8b9-125">閱讀使用者 PropertySet 個人資訊</span><span class="sxs-lookup"><span data-stu-id="9d8b9-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-126"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-127">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-127">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-128">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-128">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-129">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-129">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-130">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d8b9-131">閱讀使用者 PropertySet 一般資訊</span><span class="sxs-lookup"><span data-stu-id="9d8b9-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-132"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-133">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-133">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-134">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-134">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-135">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-135">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-136">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d8b9-137">讀取使用者 PropertySet 公用資訊</span><span class="sxs-lookup"><span data-stu-id="9d8b9-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-138"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-139">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-139">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-140">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-140">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-141">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-141">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-142">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d8b9-143">讀取使用者 PropertySet RTCUserSearchProperty-設定</span><span class="sxs-lookup"><span data-stu-id="9d8b9-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-144"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-145">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-145">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-146">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-146">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-147">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-147">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d8b9-149">讀取使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9d8b9-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-150"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-151">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-151">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-152">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-152">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-153">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-153">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-154">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d8b9-155">撰寫使用者屬性 Proxy-位址</span><span class="sxs-lookup"><span data-stu-id="9d8b9-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-156">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-156">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-157">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-157">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-158"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-159">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-159">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-160">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d8b9-161">撰寫使用者 PropertySet RTCUserSearchProperty-設定</span><span class="sxs-lookup"><span data-stu-id="9d8b9-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-162">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-162">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-163">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-163">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-164"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-165">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-165">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-166">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d8b9-167">撰寫使用者 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9d8b9-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-168">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-168">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-169">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-169">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-170"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-171">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-171">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-172">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d8b9-173">讀取 PropertySet DS-複製-變更所有 Active Directory 物件</span><span class="sxs-lookup"><span data-stu-id="9d8b9-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-174">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-174">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-175">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-175">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-176">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-176">No</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-177"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-178">否</span><span class="sxs-lookup"><span data-stu-id="9d8b9-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9d8b9-179">下表列出了網域準備在三個內建容器中建立的 Ace：使用者、電腦及網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="9d8b9-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="9d8b9-180">除非另有說明，否則所有 Ace 都是繼承的。</span><span class="sxs-lookup"><span data-stu-id="9d8b9-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="9d8b9-181">加入到內建容器中的 Ace</span><span class="sxs-lookup"><span data-stu-id="9d8b9-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d8b9-182">A</span><span class="sxs-lookup"><span data-stu-id="9d8b9-182">ACE</span></span></th>
<th><span data-ttu-id="9d8b9-183">RTCUniversal-UserReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="9d8b9-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="9d8b9-184">RTCUniversal-ServerReadOnly-群組</span><span class="sxs-lookup"><span data-stu-id="9d8b9-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d8b9-185">讀取容器（不是繼承的）</span><span class="sxs-lookup"><span data-stu-id="9d8b9-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="9d8b9-186"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9d8b9-187"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="9d8b9-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

