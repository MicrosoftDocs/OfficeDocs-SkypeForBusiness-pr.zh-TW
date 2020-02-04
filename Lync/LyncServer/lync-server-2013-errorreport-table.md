---
title: Lync Server 2013：ErrorReport 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="f621f-102">Lync Server 2013 中的 ErrorReport 表格</span><span class="sxs-lookup"><span data-stu-id="f621f-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f621f-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f621f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f621f-104">ErrorReport 資料表儲存所發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f621f-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="f621f-105">每一筆記錄都是一個錯誤發生。</span><span class="sxs-lookup"><span data-stu-id="f621f-105">Each record is one error occurrence.</span></span> <span data-ttu-id="f621f-106">錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。</span><span class="sxs-lookup"><span data-stu-id="f621f-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f621f-107">左欄</span><span class="sxs-lookup"><span data-stu-id="f621f-107">Column</span></span></th>
<th><span data-ttu-id="f621f-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="f621f-108">Data Type</span></span></th>
<th><span data-ttu-id="f621f-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="f621f-109">Key/Index</span></span></th>
<th><span data-ttu-id="f621f-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f621f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f621f-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f621f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f621f-113">首選</span><span class="sxs-lookup"><span data-stu-id="f621f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f621f-114">發生錯誤的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="f621f-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-116">int</span><span class="sxs-lookup"><span data-stu-id="f621f-116">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-117">首選</span><span class="sxs-lookup"><span data-stu-id="f621f-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f621f-118">識別錯誤報表的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="f621f-118">ID number to identify the error report.</span></span> <span data-ttu-id="f621f-119">與<strong>ErrorTime</strong>搭配使用，可唯一識別錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="f621f-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-121">int</span><span class="sxs-lookup"><span data-stu-id="f621f-121">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-122">外</span><span class="sxs-lookup"><span data-stu-id="f621f-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-123">錯誤類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f621f-123">Unique ID of the error type.</span></span> <span data-ttu-id="f621f-124">如需詳細資訊，請參閱<a href="lync-server-2013-errordef-table.md">Lync Server 2013 中</a>的 [ErrorDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-126">int</span><span class="sxs-lookup"><span data-stu-id="f621f-126">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-127">外</span><span class="sxs-lookup"><span data-stu-id="f621f-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-128">產生導致錯誤之要求的使用者。</span><span class="sxs-lookup"><span data-stu-id="f621f-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="f621f-129">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-131">int</span><span class="sxs-lookup"><span data-stu-id="f621f-131">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-132">外</span><span class="sxs-lookup"><span data-stu-id="f621f-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-133">導致錯誤之要求的目的地使用者。</span><span class="sxs-lookup"><span data-stu-id="f621f-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="f621f-134">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-136">int</span><span class="sxs-lookup"><span data-stu-id="f621f-136">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-137">外</span><span class="sxs-lookup"><span data-stu-id="f621f-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-138">與錯誤相關的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="f621f-138">Conference URI related to the error.</span></span> <span data-ttu-id="f621f-139">如需詳細資訊，請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中</a>的 [ConferenceUris] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f621f-140">通常，如果 ConferenceUriId 不是 null，則 FromUserId 或 ToUserId 將會是 null。</span><span class="sxs-lookup"><span data-stu-id="f621f-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-142">datetime</span><span class="sxs-lookup"><span data-stu-id="f621f-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="f621f-143">外</span><span class="sxs-lookup"><span data-stu-id="f621f-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-144">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="f621f-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f621f-145">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-147">int</span><span class="sxs-lookup"><span data-stu-id="f621f-147">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-148">外</span><span class="sxs-lookup"><span data-stu-id="f621f-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-149">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="f621f-149">ID number to identify the session.</span></span> <span data-ttu-id="f621f-150">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="f621f-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f621f-151">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-152"><strong>源</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-153">int</span><span class="sxs-lookup"><span data-stu-id="f621f-153">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-154">外</span><span class="sxs-lookup"><span data-stu-id="f621f-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-155">傳送錯誤報表的伺服器（如果報告是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="f621f-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="f621f-156">如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f621f-157">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="f621f-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-159">int</span><span class="sxs-lookup"><span data-stu-id="f621f-159">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-160">外</span><span class="sxs-lookup"><span data-stu-id="f621f-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-161">傳送錯誤報表的伺服器（如果報告是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="f621f-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="f621f-162">如需詳細資訊，請參閱<a href="lync-server-2013-application-table.md">Lync Server 2013 中的 [應用程式] 資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="f621f-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f621f-163">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="f621f-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-165">影像</span><span class="sxs-lookup"><span data-stu-id="f621f-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f621f-166">有關錯誤的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f621f-166">More information about the error.</span></span></p>
<p><span data-ttu-id="f621f-167">您可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="f621f-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-169">int</span><span class="sxs-lookup"><span data-stu-id="f621f-169">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-170">外</span><span class="sxs-lookup"><span data-stu-id="f621f-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-171">傳送錯誤報表的用戶端版本端點。</span><span class="sxs-lookup"><span data-stu-id="f621f-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="f621f-172">如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f621f-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-174">稍微</span><span class="sxs-lookup"><span data-stu-id="f621f-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f621f-175">是由在前端伺服器上執行的 CDR 代理程式所捕獲，或由用戶端傳送的錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="f621f-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-176"><strong>標識</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-177">Smallint</span><span class="sxs-lookup"><span data-stu-id="f621f-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f621f-178">保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="f621f-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-180">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="f621f-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f621f-181">與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f621f-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="f621f-182">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="f621f-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-184">int</span><span class="sxs-lookup"><span data-stu-id="f621f-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f621f-185">特定元件加入會議所需的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="f621f-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="f621f-186">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="f621f-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f621f-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-188">int</span><span class="sxs-lookup"><span data-stu-id="f621f-188">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-189">外</span><span class="sxs-lookup"><span data-stu-id="f621f-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-190">代表產生錯誤報表之伺服器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f621f-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f621f-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="f621f-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="f621f-192">int</span><span class="sxs-lookup"><span data-stu-id="f621f-192">int</span></span></p></td>
<td><p><span data-ttu-id="f621f-193">外</span><span class="sxs-lookup"><span data-stu-id="f621f-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f621f-194">代表產生錯誤報表之池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f621f-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

