---
title: Lync Server 2013： 會議檢視
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
ms.openlocfilehash: 56f292a35f5e4f24ba5226e06a308e780ce5c687
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="52d6d-102">Lync Server 2013 中的 conferences 檢視</span><span class="sxs-lookup"><span data-stu-id="52d6d-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52d6d-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="52d6d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="52d6d-104">Conferences 檢視儲存會議相關資訊。</span><span class="sxs-lookup"><span data-stu-id="52d6d-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="52d6d-105">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="52d6d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52d6d-106">欄</span><span class="sxs-lookup"><span data-stu-id="52d6d-106">Column</span></span></th>
<th><span data-ttu-id="52d6d-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="52d6d-107">Data Type</span></span></th>
<th><span data-ttu-id="52d6d-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="52d6d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52d6d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="52d6d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="52d6d-111">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="52d6d-111">Time of session request.</span></span> <span data-ttu-id="52d6d-112">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="52d6d-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="52d6d-113"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="52d6d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d6d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-115">int</span><span class="sxs-lookup"><span data-stu-id="52d6d-115">int</span></span></p></td>
<td><p><span data-ttu-id="52d6d-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="52d6d-116">ID number to identify the session.</span></span> <span data-ttu-id="52d6d-117">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="52d6d-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="52d6d-118"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="52d6d-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d6d-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="52d6d-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52d6d-121">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="52d6d-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d6d-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="52d6d-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52d6d-124">會議 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="52d6d-124">Type of the conference URI.</span></span> <span data-ttu-id="52d6d-125">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="52d6d-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d6d-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-127">唯一</span><span class="sxs-lookup"><span data-stu-id="52d6d-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="52d6d-128">用於週期性會議。</span><span class="sxs-lookup"><span data-stu-id="52d6d-128">Used for recurring conferences.</span></span> <span data-ttu-id="52d6d-129">每個週期性會議執行個體 ConferenceUri 皆相同但不同 ConfInstance。</span><span class="sxs-lookup"><span data-stu-id="52d6d-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d6d-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-131">datetime</span><span class="sxs-lookup"><span data-stu-id="52d6d-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="52d6d-132">起始會議的時間。</span><span class="sxs-lookup"><span data-stu-id="52d6d-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d6d-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-134">datetime</span><span class="sxs-lookup"><span data-stu-id="52d6d-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="52d6d-135">會議的結束時間。</span><span class="sxs-lookup"><span data-stu-id="52d6d-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d6d-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-137">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="52d6d-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52d6d-138">召開會議之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="52d6d-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d6d-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="52d6d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52d6d-141">召開會議之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="52d6d-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="52d6d-142">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="52d6d-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d6d-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="52d6d-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52d6d-145">使用者的承租人召開會議。</span><span class="sxs-lookup"><span data-stu-id="52d6d-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="52d6d-146">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="52d6d-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d6d-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="52d6d-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52d6d-149">裝載會議之集區的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="52d6d-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d6d-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="52d6d-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="52d6d-151">smallint</span><span class="sxs-lookup"><span data-stu-id="52d6d-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="52d6d-152">包含會議屬性的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="52d6d-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="52d6d-153">可能的值為：</span><span class="sxs-lookup"><span data-stu-id="52d6d-153">Possible values are:</span></span></p>
<p><span data-ttu-id="52d6d-154">0X01 – 綜合交易</span><span class="sxs-lookup"><span data-stu-id="52d6d-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

