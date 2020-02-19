---
title: 'Lync Server 2013: Conferences 表格'
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
ms.openlocfilehash: e8cbb42d078ccba029ae0cf55c7b1ced803aa94f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="375e1-102">Lync Server 2013 中的會議表格</span><span class="sxs-lookup"><span data-stu-id="375e1-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="375e1-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="375e1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="375e1-104">此表格中的每一筆記錄包含一場電話會議的通話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="375e1-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="375e1-105">欄</span><span class="sxs-lookup"><span data-stu-id="375e1-105">Column</span></span></th>
<th><span data-ttu-id="375e1-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="375e1-106">Data Type</span></span></th>
<th><span data-ttu-id="375e1-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="375e1-107">Key/Index</span></span></th>
<th><span data-ttu-id="375e1-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="375e1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="375e1-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="375e1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="375e1-111">主要</span><span class="sxs-lookup"><span data-stu-id="375e1-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="375e1-112">會議邀請的 CDR 代理程式所擷取的時間。</span><span class="sxs-lookup"><span data-stu-id="375e1-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="375e1-113">只能作為主索引鍵用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="375e1-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375e1-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-115">int</span><span class="sxs-lookup"><span data-stu-id="375e1-115">int</span></span></p></td>
<td><p><span data-ttu-id="375e1-116">主要</span><span class="sxs-lookup"><span data-stu-id="375e1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="375e1-117">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="375e1-117">ID number to identify the session.</span></span> <span data-ttu-id="375e1-118">搭配<strong>SessionIdTime</strong>用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="375e1-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375e1-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-120">int</span><span class="sxs-lookup"><span data-stu-id="375e1-120">int</span></span></p></td>
<td><p><span data-ttu-id="375e1-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="375e1-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="375e1-122">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="375e1-122">Conference URI.</span></span> <span data-ttu-id="375e1-123">請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="375e1-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375e1-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-125">唯一</span><span class="sxs-lookup"><span data-stu-id="375e1-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="375e1-126">可用於週期性會議;每個週期性會議執行個體有相同的<strong>ConferenceUri</strong>，但會有不同的<strong>ConfInstance</strong>。</span><span class="sxs-lookup"><span data-stu-id="375e1-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375e1-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-128">datetime</span><span class="sxs-lookup"><span data-stu-id="375e1-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="375e1-129">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="375e1-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375e1-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-131">datetime</span><span class="sxs-lookup"><span data-stu-id="375e1-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="375e1-132">會議開始時間。</span><span class="sxs-lookup"><span data-stu-id="375e1-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375e1-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-134">int</span><span class="sxs-lookup"><span data-stu-id="375e1-134">int</span></span></p></td>
<td><p><span data-ttu-id="375e1-135">Foreign</span><span class="sxs-lookup"><span data-stu-id="375e1-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="375e1-136">若要識別已擷取的會議集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="375e1-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="375e1-137">請參閱如需詳細資訊，<a href="lync-server-2013-pools-table.md">在 Lync Server 2013 中的集區資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="375e1-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375e1-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-139">臨界值</span><span class="sxs-lookup"><span data-stu-id="375e1-139">Int</span></span></p></td>
<td><p><span data-ttu-id="375e1-140">Foreign</span><span class="sxs-lookup"><span data-stu-id="375e1-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="375e1-141">若要識別此會議 URI 召集人的識別碼。</span><span class="sxs-lookup"><span data-stu-id="375e1-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="375e1-142">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="375e1-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375e1-143"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-144">smallint</span><span class="sxs-lookup"><span data-stu-id="375e1-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="375e1-145">位元遮罩，包含會議屬性。</span><span class="sxs-lookup"><span data-stu-id="375e1-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="375e1-146">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="375e1-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="375e1-147">0X01</span><span class="sxs-lookup"><span data-stu-id="375e1-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="375e1-148">綜合</span><span class="sxs-lookup"><span data-stu-id="375e1-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="375e1-149">交易</span><span class="sxs-lookup"><span data-stu-id="375e1-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375e1-150"><strong>處理</strong></span><span class="sxs-lookup"><span data-stu-id="375e1-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="375e1-151">位元</span><span class="sxs-lookup"><span data-stu-id="375e1-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="375e1-152">監視服務所使用的內部欄位。</span><span class="sxs-lookup"><span data-stu-id="375e1-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="375e1-153">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="375e1-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="375e1-154">\*對於大多數的工作階段，SessionIdSeq 會有 1 的值。</span><span class="sxs-lookup"><span data-stu-id="375e1-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="375e1-155">如果兩個工作階段時間來啟動完全相同，SessionIdSeq 的其中一個會是 1，並為其他將會是 2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="375e1-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

