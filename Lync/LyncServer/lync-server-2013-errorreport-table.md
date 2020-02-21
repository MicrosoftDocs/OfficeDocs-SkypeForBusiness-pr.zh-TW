---
title: 'Lync Server 2013: ErrorReport 表格'
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
ms.openlocfilehash: 0fad1f4138f1fae95f4e3d2ea88c8a8c72f7198a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="0a030-102">Lync Server 2013 中的 ErrorReport 表格</span><span class="sxs-lookup"><span data-stu-id="0a030-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a030-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="0a030-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0a030-104">ErrorReport 表格會儲存已發生之錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0a030-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="0a030-105">每一筆記錄就是一個錯誤發生。</span><span class="sxs-lookup"><span data-stu-id="0a030-105">Each record is one error occurrence.</span></span> <span data-ttu-id="0a030-106">錯誤捕捉; 或是在前端伺服器上執行的 CDR 代理程式或寄件者用戶端。</span><span class="sxs-lookup"><span data-stu-id="0a030-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a030-107">欄</span><span class="sxs-lookup"><span data-stu-id="0a030-107">Column</span></span></th>
<th><span data-ttu-id="0a030-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="0a030-108">Data Type</span></span></th>
<th><span data-ttu-id="0a030-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="0a030-109">Key/Index</span></span></th>
<th><span data-ttu-id="0a030-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="0a030-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a030-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0a030-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="0a030-113">主要</span><span class="sxs-lookup"><span data-stu-id="0a030-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="0a030-114">日期和時間發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="0a030-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-116">int</span><span class="sxs-lookup"><span data-stu-id="0a030-116">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-117">主要</span><span class="sxs-lookup"><span data-stu-id="0a030-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="0a030-118">若要識別錯誤報告的識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a030-118">ID number to identify the error report.</span></span> <span data-ttu-id="0a030-119"><strong>ErrorTime</strong>搭配使用來唯一地識別 [錯誤報告。</span><span class="sxs-lookup"><span data-stu-id="0a030-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-121">int</span><span class="sxs-lookup"><span data-stu-id="0a030-121">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-123">錯誤類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a030-123">Unique ID of the error type.</span></span> <span data-ttu-id="0a030-124">請參閱<a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0a030-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-126">int</span><span class="sxs-lookup"><span data-stu-id="0a030-126">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-127">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-128">源自的要求，導致錯誤發生的使用者。</span><span class="sxs-lookup"><span data-stu-id="0a030-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="0a030-129">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="0a030-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-131">int</span><span class="sxs-lookup"><span data-stu-id="0a030-131">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-132">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-133">目的地使用者要求導致錯誤發生。</span><span class="sxs-lookup"><span data-stu-id="0a030-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="0a030-134">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="0a030-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-136">int</span><span class="sxs-lookup"><span data-stu-id="0a030-136">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-137">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-138">會議 URI 相關的錯誤。</span><span class="sxs-lookup"><span data-stu-id="0a030-138">Conference URI related to the error.</span></span> <span data-ttu-id="0a030-139">請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0a030-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="0a030-140">一般而言，如果 ConferenceUriId 不是 null，然後 FromUserId 或 ToUserId 都是 null。</span><span class="sxs-lookup"><span data-stu-id="0a030-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-142">datetime</span><span class="sxs-lookup"><span data-stu-id="0a030-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="0a030-143">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-144">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="0a030-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0a030-145"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0a030-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-147">int</span><span class="sxs-lookup"><span data-stu-id="0a030-147">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-148">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-149">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a030-149">ID number to identify the session.</span></span> <span data-ttu-id="0a030-150">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="0a030-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0a030-151"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0a030-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-153">int</span><span class="sxs-lookup"><span data-stu-id="0a030-153">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-154">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-155">（如果報告從伺服器元件傳送） 傳送錯誤報告的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a030-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="0a030-156">請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0a030-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0a030-157">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="0a030-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-159">int</span><span class="sxs-lookup"><span data-stu-id="0a030-159">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-160">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-161">（如果報告從伺服器元件傳送） 傳送錯誤報告的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a030-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="0a030-162">請參閱<a href="lync-server-2013-application-table.md">Lync Server 2013 中的應用程式表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0a030-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0a030-163">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="0a030-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-165">image</span><span class="sxs-lookup"><span data-stu-id="0a030-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0a030-166">錯誤的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0a030-166">More information about the error.</span></span></p>
<p><span data-ttu-id="0a030-167">可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="0a030-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-169">int</span><span class="sxs-lookup"><span data-stu-id="0a030-169">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-170">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-171">會傳送錯誤報告的端點的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="0a030-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="0a030-172">請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0a030-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-174">位元</span><span class="sxs-lookup"><span data-stu-id="0a030-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0a030-175">是錯誤報告由前端伺服器上執行的 CDR 代理程式擷取，或用戶端所傳送。</span><span class="sxs-lookup"><span data-stu-id="0a030-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-176"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-177">smallint</span><span class="sxs-lookup"><span data-stu-id="0a030-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0a030-178">保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="0a030-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-180">唯一</span><span class="sxs-lookup"><span data-stu-id="0a030-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0a030-181">相互關聯參與會議之不同元件的加入時間資訊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a030-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="0a030-182">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="0a030-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-184">int</span><span class="sxs-lookup"><span data-stu-id="0a030-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0a030-185">時間 （以毫秒為單位） 所需的特定元件加入會議。</span><span class="sxs-lookup"><span data-stu-id="0a030-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="0a030-186">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="0a030-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a030-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-188">int</span><span class="sxs-lookup"><span data-stu-id="0a030-188">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-189">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-190">代表產生錯誤報告之伺服器的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="0a030-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a030-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="0a030-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="0a030-192">int</span><span class="sxs-lookup"><span data-stu-id="0a030-192">int</span></span></p></td>
<td><p><span data-ttu-id="0a030-193">Foreign</span><span class="sxs-lookup"><span data-stu-id="0a030-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0a030-194">代表產生錯誤報告其中的集區的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="0a030-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

