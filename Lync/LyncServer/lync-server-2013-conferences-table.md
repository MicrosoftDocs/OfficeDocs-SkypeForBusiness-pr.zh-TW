---
title: Lync Server 2013：會議表格
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
ms.openlocfilehash: ef5e8811ad4b0adaccd8964e2f0bca718ca531e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529260"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="f3194-102">Lync Server 2013 中的會議表格</span><span class="sxs-lookup"><span data-stu-id="f3194-102">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3194-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f3194-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f3194-104">此表格中的每一筆記錄都包含有關一部會議的呼叫詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f3194-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3194-105">欄</span><span class="sxs-lookup"><span data-stu-id="f3194-105">Column</span></span></th>
<th><span data-ttu-id="f3194-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="f3194-106">Data Type</span></span></th>
<th><span data-ttu-id="f3194-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="f3194-107">Key/Index</span></span></th>
<th><span data-ttu-id="f3194-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f3194-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3194-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f3194-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3194-111">主要</span><span class="sxs-lookup"><span data-stu-id="f3194-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3194-112">CDR 代理程式捕獲會議要求的時間。</span><span class="sxs-lookup"><span data-stu-id="f3194-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="f3194-113">僅用作主鍵，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="f3194-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3194-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-115">int</span><span class="sxs-lookup"><span data-stu-id="f3194-115">int</span></span></p></td>
<td><p><span data-ttu-id="f3194-116">主要</span><span class="sxs-lookup"><span data-stu-id="f3194-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3194-117">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="f3194-117">ID number to identify the session.</span></span> <span data-ttu-id="f3194-118">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="f3194-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3194-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-120">int</span><span class="sxs-lookup"><span data-stu-id="f3194-120">int</span></span></p></td>
<td><p><span data-ttu-id="f3194-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="f3194-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f3194-122">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="f3194-122">Conference URI.</span></span> <span data-ttu-id="f3194-123">如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f3194-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3194-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-125">唯一</span><span class="sxs-lookup"><span data-stu-id="f3194-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f3194-126">適用于週期性會議;每個週期性會議實例都具有相同的 <strong>ConferenceUri</strong>，但會有不同的 <strong>ConfInstance</strong>。</span><span class="sxs-lookup"><span data-stu-id="f3194-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3194-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-128">datetime</span><span class="sxs-lookup"><span data-stu-id="f3194-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f3194-129">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="f3194-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3194-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-131">datetime</span><span class="sxs-lookup"><span data-stu-id="f3194-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f3194-132">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="f3194-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3194-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-134">int</span><span class="sxs-lookup"><span data-stu-id="f3194-134">int</span></span></p></td>
<td><p><span data-ttu-id="f3194-135">Foreign</span><span class="sxs-lookup"><span data-stu-id="f3194-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f3194-136">識別碼，用來識別捕獲會議的集區。</span><span class="sxs-lookup"><span data-stu-id="f3194-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="f3194-137">如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f3194-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3194-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-139">臨界值</span><span class="sxs-lookup"><span data-stu-id="f3194-139">Int</span></span></p></td>
<td><p><span data-ttu-id="f3194-140">Foreign</span><span class="sxs-lookup"><span data-stu-id="f3194-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f3194-141">識別此會議之召集人 URI 的識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="f3194-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="f3194-142">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f3194-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3194-143"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-144">Smallint</span><span class="sxs-lookup"><span data-stu-id="f3194-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f3194-145">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="f3194-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="f3194-146">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="f3194-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f3194-147">0X01</span><span class="sxs-lookup"><span data-stu-id="f3194-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="f3194-148">合成</span><span class="sxs-lookup"><span data-stu-id="f3194-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="f3194-149">交易</span><span class="sxs-lookup"><span data-stu-id="f3194-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3194-150"><strong>處理</strong></span><span class="sxs-lookup"><span data-stu-id="f3194-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="f3194-151">位</span><span class="sxs-lookup"><span data-stu-id="f3194-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f3194-152">監控服務所使用的內部欄位。</span><span class="sxs-lookup"><span data-stu-id="f3194-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="f3194-153">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f3194-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f3194-154">\* 對於大部分的會話，SessionIdSeq 的值會是1。</span><span class="sxs-lookup"><span data-stu-id="f3194-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="f3194-155">如果兩個會話的開始時間完全相同，則 SessionIdSeq 為1，而另一個會是2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="f3194-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

