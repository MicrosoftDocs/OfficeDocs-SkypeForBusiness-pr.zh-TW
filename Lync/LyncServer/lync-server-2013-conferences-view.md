---
title: Lync Server 2013：會議視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="03f3d-102">Lync Server 2013 中的會議視圖</span><span class="sxs-lookup"><span data-stu-id="03f3d-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f3d-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="03f3d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="03f3d-104">[會議] 視圖會儲存會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="03f3d-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="03f3d-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="03f3d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f3d-106">左欄</span><span class="sxs-lookup"><span data-stu-id="03f3d-106">Column</span></span></th>
<th><span data-ttu-id="03f3d-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="03f3d-107">Data Type</span></span></th>
<th><span data-ttu-id="03f3d-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="03f3d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="03f3d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="03f3d-111">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="03f3d-111">Time of session request.</span></span> <span data-ttu-id="03f3d-112">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="03f3d-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="03f3d-113">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="03f3d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-115">int</span><span class="sxs-lookup"><span data-stu-id="03f3d-115">int</span></span></p></td>
<td><p><span data-ttu-id="03f3d-116">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="03f3d-116">ID number to identify the session.</span></span> <span data-ttu-id="03f3d-117">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="03f3d-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="03f3d-118">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="03f3d-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-120">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="03f3d-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="03f3d-121">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="03f3d-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-123">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="03f3d-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f3d-124">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="03f3d-124">Type of the conference URI.</span></span> <span data-ttu-id="03f3d-125">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="03f3d-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="03f3d-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="03f3d-128">用於週期性會議。</span><span class="sxs-lookup"><span data-stu-id="03f3d-128">Used for recurring conferences.</span></span> <span data-ttu-id="03f3d-129">每個週期性會議實例都有相同的 ConferenceUri，但 ConfInstance 不同。</span><span class="sxs-lookup"><span data-stu-id="03f3d-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-131">datetime</span><span class="sxs-lookup"><span data-stu-id="03f3d-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="03f3d-132">會議的開始時間。</span><span class="sxs-lookup"><span data-stu-id="03f3d-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-134">datetime</span><span class="sxs-lookup"><span data-stu-id="03f3d-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="03f3d-135">會議的結束時間。</span><span class="sxs-lookup"><span data-stu-id="03f3d-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-137">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="03f3d-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="03f3d-138">組織會議的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="03f3d-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-140">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="03f3d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f3d-141">組織會議的使用者 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="03f3d-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="03f3d-142">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="03f3d-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-144">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="03f3d-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f3d-145">組織會議的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="03f3d-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="03f3d-146">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="03f3d-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-147"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-148">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="03f3d-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f3d-149">主持會議之池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="03f3d-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-150"><strong>標識</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-151">Smallint</span><span class="sxs-lookup"><span data-stu-id="03f3d-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="03f3d-152">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="03f3d-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="03f3d-153">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="03f3d-153">Possible values are:</span></span></p>
<p><span data-ttu-id="03f3d-154">0X01-綜合交易</span><span class="sxs-lookup"><span data-stu-id="03f3d-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

