---
title: Lync Server 2013：Conferences 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="19afa-102">Lync Server 2013 中的 Conferences 表格</span><span class="sxs-lookup"><span data-stu-id="19afa-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19afa-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="19afa-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="19afa-104">此表格中的每筆記錄都包含一個會議的通話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="19afa-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19afa-105">左欄</span><span class="sxs-lookup"><span data-stu-id="19afa-105">Column</span></span></th>
<th><span data-ttu-id="19afa-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="19afa-106">Data Type</span></span></th>
<th><span data-ttu-id="19afa-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="19afa-107">Key/Index</span></span></th>
<th><span data-ttu-id="19afa-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="19afa-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19afa-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-110">datetime</span><span class="sxs-lookup"><span data-stu-id="19afa-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="19afa-111">首選</span><span class="sxs-lookup"><span data-stu-id="19afa-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="19afa-112">由 CDR 代理程式捕獲會議要求的時間。</span><span class="sxs-lookup"><span data-stu-id="19afa-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="19afa-113">僅用作主鍵來唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="19afa-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19afa-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-115">int</span><span class="sxs-lookup"><span data-stu-id="19afa-115">int</span></span></p></td>
<td><p><span data-ttu-id="19afa-116">首選</span><span class="sxs-lookup"><span data-stu-id="19afa-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="19afa-117">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="19afa-117">ID number to identify the session.</span></span> <span data-ttu-id="19afa-118">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="19afa-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19afa-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-120">int</span><span class="sxs-lookup"><span data-stu-id="19afa-120">int</span></span></p></td>
<td><p><span data-ttu-id="19afa-121">外</span><span class="sxs-lookup"><span data-stu-id="19afa-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="19afa-122">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="19afa-122">Conference URI.</span></span> <span data-ttu-id="19afa-123">如需詳細資訊，請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中</a>的 [ConferenceUris] 資料表。</span><span class="sxs-lookup"><span data-stu-id="19afa-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19afa-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="19afa-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19afa-126">適用于週期性會議;每個週期性會議實例都有相同的<strong>ConferenceUri</strong>，但會有不同的<strong>ConfInstance</strong>。</span><span class="sxs-lookup"><span data-stu-id="19afa-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19afa-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-128">datetime</span><span class="sxs-lookup"><span data-stu-id="19afa-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19afa-129">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="19afa-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19afa-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-131">datetime</span><span class="sxs-lookup"><span data-stu-id="19afa-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19afa-132">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="19afa-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19afa-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-134">int</span><span class="sxs-lookup"><span data-stu-id="19afa-134">int</span></span></p></td>
<td><p><span data-ttu-id="19afa-135">外</span><span class="sxs-lookup"><span data-stu-id="19afa-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="19afa-136">[識別碼] 編號，可識別捕獲會議的池。</span><span class="sxs-lookup"><span data-stu-id="19afa-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="19afa-137">如需詳細資訊，請參閱<a href="lync-server-2013-pools-table.md">Lync Server 2013 中</a>的 [pool] 資料表。</span><span class="sxs-lookup"><span data-stu-id="19afa-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19afa-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-139">Int</span><span class="sxs-lookup"><span data-stu-id="19afa-139">Int</span></span></p></td>
<td><p><span data-ttu-id="19afa-140">外</span><span class="sxs-lookup"><span data-stu-id="19afa-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="19afa-141">識別此會議之召集人 URI 的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="19afa-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="19afa-142">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="19afa-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19afa-143"><strong>標識</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-144">Smallint</span><span class="sxs-lookup"><span data-stu-id="19afa-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="19afa-145">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="19afa-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="19afa-146">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="19afa-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="19afa-147">0X01</span><span class="sxs-lookup"><span data-stu-id="19afa-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="19afa-148">合成</span><span class="sxs-lookup"><span data-stu-id="19afa-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="19afa-149">事物</span><span class="sxs-lookup"><span data-stu-id="19afa-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19afa-150"><strong>預處理</strong></span><span class="sxs-lookup"><span data-stu-id="19afa-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="19afa-151">稍微</span><span class="sxs-lookup"><span data-stu-id="19afa-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="19afa-152">[監視服務] 使用的內部欄位。</span><span class="sxs-lookup"><span data-stu-id="19afa-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="19afa-153">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="19afa-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="19afa-154">\*在大部分的會話中，SessionIdSeq 將會有1的值。</span><span class="sxs-lookup"><span data-stu-id="19afa-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="19afa-155">如果兩個會話是完全相同的時間，則其中一個會話的 SessionIdSeq 會是1，而另一個則是2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="19afa-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

