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
ms.openlocfilehash: c5412f57c2dc355b7063faaf6c50eda31b9240bc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529220"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="67027-102">Lync Server 2013 中的會議視圖</span><span class="sxs-lookup"><span data-stu-id="67027-102">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67027-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="67027-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="67027-104">會議視圖會儲存會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="67027-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="67027-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="67027-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67027-106">欄</span><span class="sxs-lookup"><span data-stu-id="67027-106">Column</span></span></th>
<th><span data-ttu-id="67027-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="67027-107">Data Type</span></span></th>
<th><span data-ttu-id="67027-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="67027-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67027-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="67027-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-110">datetime</span><span class="sxs-lookup"><span data-stu-id="67027-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="67027-111">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="67027-111">Time of session request.</span></span> <span data-ttu-id="67027-112">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="67027-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="67027-113">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="67027-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67027-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="67027-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-115">int</span><span class="sxs-lookup"><span data-stu-id="67027-115">int</span></span></p></td>
<td><p><span data-ttu-id="67027-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="67027-116">ID number to identify the session.</span></span> <span data-ttu-id="67027-117">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="67027-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="67027-118">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="67027-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67027-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="67027-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-120">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="67027-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="67027-121">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="67027-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67027-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="67027-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-123">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="67027-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="67027-124">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="67027-124">Type of the conference URI.</span></span> <span data-ttu-id="67027-125">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="67027-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67027-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="67027-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-127">唯一</span><span class="sxs-lookup"><span data-stu-id="67027-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="67027-128">用於週期性會議。</span><span class="sxs-lookup"><span data-stu-id="67027-128">Used for recurring conferences.</span></span> <span data-ttu-id="67027-129">每個週期性會議實例都具有相同的 ConferenceUri，但不同 ConfInstance。</span><span class="sxs-lookup"><span data-stu-id="67027-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67027-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="67027-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-131">datetime</span><span class="sxs-lookup"><span data-stu-id="67027-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="67027-132">會議的開始時間。</span><span class="sxs-lookup"><span data-stu-id="67027-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67027-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="67027-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-134">datetime</span><span class="sxs-lookup"><span data-stu-id="67027-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="67027-135">會議的結束時間。</span><span class="sxs-lookup"><span data-stu-id="67027-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67027-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="67027-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-137">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="67027-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="67027-138">組織會議之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="67027-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67027-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="67027-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-140">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="67027-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="67027-141">組織會議之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="67027-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="67027-142">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="67027-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67027-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="67027-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-144">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="67027-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="67027-145">組織會議之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="67027-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="67027-146">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="67027-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67027-147"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="67027-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-148">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="67027-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="67027-149">主控會議之集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="67027-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67027-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="67027-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="67027-151">Smallint</span><span class="sxs-lookup"><span data-stu-id="67027-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="67027-152">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="67027-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="67027-153">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="67027-153">Possible values are:</span></span></p>
<p><span data-ttu-id="67027-154">0X01 –綜合交易</span><span class="sxs-lookup"><span data-stu-id="67027-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

