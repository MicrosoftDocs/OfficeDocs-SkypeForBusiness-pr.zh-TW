---
title: Lync Server 2013：會議視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="05bcf-102">Lync Server 2013 中的會議視圖</span><span class="sxs-lookup"><span data-stu-id="05bcf-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05bcf-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="05bcf-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="05bcf-104">[會議] 視圖會儲存會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="05bcf-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="05bcf-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="05bcf-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05bcf-106">左欄</span><span class="sxs-lookup"><span data-stu-id="05bcf-106">Column</span></span></th>
<th><span data-ttu-id="05bcf-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="05bcf-107">Data Type</span></span></th>
<th><span data-ttu-id="05bcf-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="05bcf-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05bcf-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-110">datetime</span><span class="sxs-lookup"><span data-stu-id="05bcf-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="05bcf-111">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="05bcf-111">Time of session request.</span></span> <span data-ttu-id="05bcf-112">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="05bcf-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="05bcf-113">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="05bcf-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05bcf-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-115">int</span><span class="sxs-lookup"><span data-stu-id="05bcf-115">int</span></span></p></td>
<td><p><span data-ttu-id="05bcf-116">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="05bcf-116">ID number to identify the session.</span></span> <span data-ttu-id="05bcf-117">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="05bcf-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="05bcf-118">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="05bcf-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05bcf-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-120">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="05bcf-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="05bcf-121">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="05bcf-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05bcf-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-123">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05bcf-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05bcf-124">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="05bcf-124">Type of the conference URI.</span></span> <span data-ttu-id="05bcf-125">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="05bcf-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05bcf-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="05bcf-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="05bcf-128">用於週期性會議。</span><span class="sxs-lookup"><span data-stu-id="05bcf-128">Used for recurring conferences.</span></span> <span data-ttu-id="05bcf-129">每個週期性會議實例都有相同的 ConferenceUri，但 ConfInstance 不同。</span><span class="sxs-lookup"><span data-stu-id="05bcf-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05bcf-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-131">datetime</span><span class="sxs-lookup"><span data-stu-id="05bcf-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="05bcf-132">會議的開始時間。</span><span class="sxs-lookup"><span data-stu-id="05bcf-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05bcf-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-134">datetime</span><span class="sxs-lookup"><span data-stu-id="05bcf-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="05bcf-135">會議的結束時間。</span><span class="sxs-lookup"><span data-stu-id="05bcf-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05bcf-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-137">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="05bcf-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="05bcf-138">組織會議的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="05bcf-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05bcf-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-140">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05bcf-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05bcf-141">組織會議的使用者 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="05bcf-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="05bcf-142">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="05bcf-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05bcf-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-144">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05bcf-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05bcf-145">組織會議的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="05bcf-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="05bcf-146">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="05bcf-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05bcf-147"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-148">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05bcf-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05bcf-149">主持會議之池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="05bcf-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05bcf-150"><strong>標識</strong></span><span class="sxs-lookup"><span data-stu-id="05bcf-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="05bcf-151">Smallint</span><span class="sxs-lookup"><span data-stu-id="05bcf-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="05bcf-152">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="05bcf-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="05bcf-153">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="05bcf-153">Possible values are:</span></span></p>
<p><span data-ttu-id="05bcf-154">0X01-綜合交易</span><span class="sxs-lookup"><span data-stu-id="05bcf-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

