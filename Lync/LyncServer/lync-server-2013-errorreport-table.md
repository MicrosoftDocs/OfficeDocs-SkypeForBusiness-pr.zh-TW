---
title: Lync Server 2013： ErrorReport 表格
description: Lync Server 2013： ErrorReport 表格。
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572009"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="06264-103">Lync Server 2013 中的 ErrorReport 表格</span><span class="sxs-lookup"><span data-stu-id="06264-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06264-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="06264-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="06264-105">ErrorReport 表儲存發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="06264-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="06264-106">每個記錄是一個錯誤發生。</span><span class="sxs-lookup"><span data-stu-id="06264-106">Each record is one error occurrence.</span></span> <span data-ttu-id="06264-107">這兩個錯誤是由前端伺服器上執行的 CDR 代理程式所捕獲，或是從用戶端傳送。</span><span class="sxs-lookup"><span data-stu-id="06264-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06264-108">欄</span><span class="sxs-lookup"><span data-stu-id="06264-108">Column</span></span></th>
<th><span data-ttu-id="06264-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="06264-109">Data Type</span></span></th>
<th><span data-ttu-id="06264-110">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="06264-110">Key/Index</span></span></th>
<th><span data-ttu-id="06264-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="06264-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06264-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="06264-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-113">datetime</span><span class="sxs-lookup"><span data-stu-id="06264-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="06264-114">主要</span><span class="sxs-lookup"><span data-stu-id="06264-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="06264-115">發生錯誤的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="06264-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="06264-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-117">int</span><span class="sxs-lookup"><span data-stu-id="06264-117">int</span></span></p></td>
<td><p><span data-ttu-id="06264-118">主要</span><span class="sxs-lookup"><span data-stu-id="06264-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="06264-119">用以識別錯誤報表的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="06264-119">ID number to identify the error report.</span></span> <span data-ttu-id="06264-120">與 <strong>ErrorTime</strong> 搭配使用，以唯一識別錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="06264-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-121"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-122">int</span><span class="sxs-lookup"><span data-stu-id="06264-122">int</span></span></p></td>
<td><p><span data-ttu-id="06264-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-124">錯誤類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="06264-124">Unique ID of the error type.</span></span> <span data-ttu-id="06264-125">如需詳細資訊，請參閱 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-127">int</span><span class="sxs-lookup"><span data-stu-id="06264-127">int</span></span></p></td>
<td><p><span data-ttu-id="06264-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-129">產生導致錯誤之要求的使用者。</span><span class="sxs-lookup"><span data-stu-id="06264-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="06264-130">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-131"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-132">int</span><span class="sxs-lookup"><span data-stu-id="06264-132">int</span></span></p></td>
<td><p><span data-ttu-id="06264-133">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-134">導致錯誤之要求的目的地使用者。</span><span class="sxs-lookup"><span data-stu-id="06264-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="06264-135">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-137">int</span><span class="sxs-lookup"><span data-stu-id="06264-137">int</span></span></p></td>
<td><p><span data-ttu-id="06264-138">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-139">與錯誤相關的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="06264-139">Conference URI related to the error.</span></span> <span data-ttu-id="06264-140">如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="06264-141">一般來說，如果 ConferenceUriId 不是 null，則 FromUserId 或 ToUserId 將會是 null。</span><span class="sxs-lookup"><span data-stu-id="06264-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-142"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="06264-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-143">datetime</span><span class="sxs-lookup"><span data-stu-id="06264-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="06264-144">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-145">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="06264-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="06264-146">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="06264-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-148">int</span><span class="sxs-lookup"><span data-stu-id="06264-148">int</span></span></p></td>
<td><p><span data-ttu-id="06264-149">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-150">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="06264-150">ID number to identify the session.</span></span> <span data-ttu-id="06264-151">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="06264-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="06264-152">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-154">int</span><span class="sxs-lookup"><span data-stu-id="06264-154">int</span></span></p></td>
<td><p><span data-ttu-id="06264-155">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-156">傳送錯誤報表 (的伺服器，如果報告是從伺服器元件傳送) 中傳送。</span><span class="sxs-lookup"><span data-stu-id="06264-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="06264-157">如需詳細資訊，請參閱 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="06264-158">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="06264-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-160">int</span><span class="sxs-lookup"><span data-stu-id="06264-160">int</span></span></p></td>
<td><p><span data-ttu-id="06264-161">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-162">傳送錯誤報表 (的伺服器，如果報告是從伺服器元件傳送) 中傳送。</span><span class="sxs-lookup"><span data-stu-id="06264-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="06264-163">如需詳細資訊，請參閱 <a href="lync-server-2013-application-table.md">Lync Server 2013 中的應用程式表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="06264-164">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="06264-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="06264-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-166">image</span><span class="sxs-lookup"><span data-stu-id="06264-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="06264-167">錯誤的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="06264-167">More information about the error.</span></span></p>
<p><span data-ttu-id="06264-168">您可以使用下列語法將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="06264-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-170">int</span><span class="sxs-lookup"><span data-stu-id="06264-170">int</span></span></p></td>
<td><p><span data-ttu-id="06264-171">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-172">傳送錯誤報表之端點的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="06264-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="06264-173">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="06264-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="06264-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-175">位</span><span class="sxs-lookup"><span data-stu-id="06264-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06264-176">是由前端伺服器上執行的 CDR 代理程式所捕獲的錯誤報表，或是由用戶端所傳送的錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="06264-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-177"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="06264-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-178">Smallint</span><span class="sxs-lookup"><span data-stu-id="06264-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06264-179">保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="06264-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-180"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-181">唯一</span><span class="sxs-lookup"><span data-stu-id="06264-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06264-182">與會議相關聯之不同元件的加入時間資訊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="06264-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="06264-183">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="06264-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-184"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="06264-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-185">int</span><span class="sxs-lookup"><span data-stu-id="06264-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06264-186">特定元件加入會議所需的時間 (（毫秒）) 。</span><span class="sxs-lookup"><span data-stu-id="06264-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="06264-187">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="06264-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06264-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-189">int</span><span class="sxs-lookup"><span data-stu-id="06264-189">int</span></span></p></td>
<td><p><span data-ttu-id="06264-190">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-191">代表產生錯誤報表之伺服器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="06264-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06264-192"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="06264-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="06264-193">int</span><span class="sxs-lookup"><span data-stu-id="06264-193">int</span></span></p></td>
<td><p><span data-ttu-id="06264-194">Foreign</span><span class="sxs-lookup"><span data-stu-id="06264-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="06264-195">代表產生錯誤報表之集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="06264-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

