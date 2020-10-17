---
title: Lync Server 2013：會議表格
description: Lync Server 2013：會議表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561599"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="1f80b-103">Lync Server 2013 中的會議表格</span><span class="sxs-lookup"><span data-stu-id="1f80b-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f80b-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1f80b-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1f80b-105">此表格中的每一筆記錄都包含有關一部會議的呼叫詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1f80b-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f80b-106">欄</span><span class="sxs-lookup"><span data-stu-id="1f80b-106">Column</span></span></th>
<th><span data-ttu-id="1f80b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="1f80b-107">Data Type</span></span></th>
<th><span data-ttu-id="1f80b-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="1f80b-108">Key/Index</span></span></th>
<th><span data-ttu-id="1f80b-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1f80b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f80b-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1f80b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f80b-112">主要</span><span class="sxs-lookup"><span data-stu-id="1f80b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f80b-113">CDR 代理程式捕獲會議要求的時間。</span><span class="sxs-lookup"><span data-stu-id="1f80b-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="1f80b-114">僅用作主鍵，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="1f80b-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f80b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-116">int</span><span class="sxs-lookup"><span data-stu-id="1f80b-116">int</span></span></p></td>
<td><p><span data-ttu-id="1f80b-117">主要</span><span class="sxs-lookup"><span data-stu-id="1f80b-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f80b-118">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="1f80b-118">ID number to identify the session.</span></span> <span data-ttu-id="1f80b-119">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="1f80b-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f80b-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-121">int</span><span class="sxs-lookup"><span data-stu-id="1f80b-121">int</span></span></p></td>
<td><p><span data-ttu-id="1f80b-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="1f80b-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f80b-123">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="1f80b-123">Conference URI.</span></span> <span data-ttu-id="1f80b-124">如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="1f80b-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f80b-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-126">唯一</span><span class="sxs-lookup"><span data-stu-id="1f80b-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1f80b-127">適用于週期性會議;每個週期性會議實例都具有相同的 <strong>ConferenceUri</strong>，但會有不同的 <strong>ConfInstance</strong>。</span><span class="sxs-lookup"><span data-stu-id="1f80b-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f80b-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-129">datetime</span><span class="sxs-lookup"><span data-stu-id="1f80b-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1f80b-130">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="1f80b-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f80b-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-132">datetime</span><span class="sxs-lookup"><span data-stu-id="1f80b-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1f80b-133">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="1f80b-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f80b-134"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-135">int</span><span class="sxs-lookup"><span data-stu-id="1f80b-135">int</span></span></p></td>
<td><p><span data-ttu-id="1f80b-136">Foreign</span><span class="sxs-lookup"><span data-stu-id="1f80b-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f80b-137">識別碼，用來識別捕獲會議的集區。</span><span class="sxs-lookup"><span data-stu-id="1f80b-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="1f80b-138">如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="1f80b-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f80b-139"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-140">臨界值</span><span class="sxs-lookup"><span data-stu-id="1f80b-140">Int</span></span></p></td>
<td><p><span data-ttu-id="1f80b-141">Foreign</span><span class="sxs-lookup"><span data-stu-id="1f80b-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f80b-142">識別此會議之召集人 URI 的識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="1f80b-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="1f80b-143">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="1f80b-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f80b-144"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-145">Smallint</span><span class="sxs-lookup"><span data-stu-id="1f80b-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f80b-146">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="1f80b-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="1f80b-147">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="1f80b-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f80b-148">0X01</span><span class="sxs-lookup"><span data-stu-id="1f80b-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="1f80b-149">合成</span><span class="sxs-lookup"><span data-stu-id="1f80b-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="1f80b-150">交易</span><span class="sxs-lookup"><span data-stu-id="1f80b-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f80b-151"><strong>處理</strong></span><span class="sxs-lookup"><span data-stu-id="1f80b-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="1f80b-152">位</span><span class="sxs-lookup"><span data-stu-id="1f80b-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f80b-153">監控服務所使用的內部欄位。</span><span class="sxs-lookup"><span data-stu-id="1f80b-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="1f80b-154">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1f80b-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1f80b-155">\* 對於大部分的會話，SessionIdSeq 的值會是1。</span><span class="sxs-lookup"><span data-stu-id="1f80b-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="1f80b-156">如果兩個會話的開始時間完全相同，則 SessionIdSeq 為1，而另一個會是2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="1f80b-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

