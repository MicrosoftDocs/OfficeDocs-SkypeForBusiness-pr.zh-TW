---
title: Lync Server 2013：會議視圖
description: Lync Server 2013：會議視圖。
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
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561579"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="adddf-103">Lync Server 2013 中的會議視圖</span><span class="sxs-lookup"><span data-stu-id="adddf-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adddf-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="adddf-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="adddf-105">會議視圖會儲存會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="adddf-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="adddf-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="adddf-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adddf-107">欄</span><span class="sxs-lookup"><span data-stu-id="adddf-107">Column</span></span></th>
<th><span data-ttu-id="adddf-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="adddf-108">Data Type</span></span></th>
<th><span data-ttu-id="adddf-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="adddf-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adddf-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-111">datetime</span><span class="sxs-lookup"><span data-stu-id="adddf-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="adddf-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="adddf-112">Time of session request.</span></span> <span data-ttu-id="adddf-113">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="adddf-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="adddf-114">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="adddf-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adddf-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-116">int</span><span class="sxs-lookup"><span data-stu-id="adddf-116">int</span></span></p></td>
<td><p><span data-ttu-id="adddf-117">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="adddf-117">ID number to identify the session.</span></span> <span data-ttu-id="adddf-118">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="adddf-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="adddf-119">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="adddf-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adddf-120"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-121">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="adddf-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="adddf-122">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="adddf-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adddf-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-124">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="adddf-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="adddf-125">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="adddf-125">Type of the conference URI.</span></span> <span data-ttu-id="adddf-126">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="adddf-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adddf-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-128">唯一</span><span class="sxs-lookup"><span data-stu-id="adddf-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="adddf-129">用於週期性會議。</span><span class="sxs-lookup"><span data-stu-id="adddf-129">Used for recurring conferences.</span></span> <span data-ttu-id="adddf-130">每個週期性會議實例都具有相同的 ConferenceUri，但不同 ConfInstance。</span><span class="sxs-lookup"><span data-stu-id="adddf-130">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adddf-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-132">datetime</span><span class="sxs-lookup"><span data-stu-id="adddf-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="adddf-133">會議的開始時間。</span><span class="sxs-lookup"><span data-stu-id="adddf-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adddf-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-135">datetime</span><span class="sxs-lookup"><span data-stu-id="adddf-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="adddf-136">會議的結束時間。</span><span class="sxs-lookup"><span data-stu-id="adddf-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adddf-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-138">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="adddf-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="adddf-139">組織會議之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="adddf-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adddf-140"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-141">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="adddf-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="adddf-142">組織會議之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="adddf-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="adddf-143">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="adddf-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adddf-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-145">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="adddf-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="adddf-146">組織會議之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="adddf-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="adddf-147">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="adddf-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adddf-148"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-149">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="adddf-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="adddf-150">主控會議之集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="adddf-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adddf-151"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="adddf-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="adddf-152">Smallint</span><span class="sxs-lookup"><span data-stu-id="adddf-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="adddf-153">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="adddf-153">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="adddf-154">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="adddf-154">Possible values are:</span></span></p>
<p><span data-ttu-id="adddf-155">0X01 –綜合交易</span><span class="sxs-lookup"><span data-stu-id="adddf-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

