---
title: 'Lync Server 2013: ErrorReport 檢視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1fe360726c94062391a4559f73a375d68b5f384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="51e2c-102">Lync Server 2013 中的 ErrorReport 檢視</span><span class="sxs-lookup"><span data-stu-id="51e2c-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51e2c-103">_**上次修改主題：** 2013年-01-22_</span><span class="sxs-lookup"><span data-stu-id="51e2c-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="51e2c-104">ErrorReport 檢視儲存錯誤報告的資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="51e2c-105">每一筆記錄就是一個錯誤發生。</span><span class="sxs-lookup"><span data-stu-id="51e2c-105">Each record is one error occurrence.</span></span> <span data-ttu-id="51e2c-106">錯誤捕捉; 或是在前端伺服器上執行的 CDR 代理程式或寄件者用戶端。</span><span class="sxs-lookup"><span data-stu-id="51e2c-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="51e2c-107">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="51e2c-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51e2c-108">欄</span><span class="sxs-lookup"><span data-stu-id="51e2c-108">Column</span></span></th>
<th><span data-ttu-id="51e2c-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="51e2c-109">Data Type</span></span></th>
<th><span data-ttu-id="51e2c-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="51e2c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="51e2c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="51e2c-113">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="51e2c-113">Time of error occurred.</span></span> <span data-ttu-id="51e2c-114">搭配 ErrorReportSeq 用來唯一地識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="51e2c-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-116">int</span><span class="sxs-lookup"><span data-stu-id="51e2c-116">int</span></span></p></td>
<td><p><span data-ttu-id="51e2c-117">若要識別錯誤的識別碼。</span><span class="sxs-lookup"><span data-stu-id="51e2c-117">ID number to identify the error.</span></span> <span data-ttu-id="51e2c-118">ErrorTime 搭配使用來唯一地識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="51e2c-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-120">int</span><span class="sxs-lookup"><span data-stu-id="51e2c-120">int</span></span></p></td>
<td><p><span data-ttu-id="51e2c-121">錯誤報告的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="51e2c-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-123">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="51e2c-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-124">錯誤源自的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="51e2c-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-127">錯誤源自使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="51e2c-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="51e2c-128">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-131">租用戶的使用者錯誤源自。</span><span class="sxs-lookup"><span data-stu-id="51e2c-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="51e2c-132">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-134">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="51e2c-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-135">錯誤報告的目標使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="51e2c-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-138">目標使用者的 URI 類型的錯誤報告。</span><span class="sxs-lookup"><span data-stu-id="51e2c-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="51e2c-139">如需詳細資訊，請參閱＜UriTypes Table＞。</span><span class="sxs-lookup"><span data-stu-id="51e2c-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-142">目標使用者的租用戶的錯誤報告。</span><span class="sxs-lookup"><span data-stu-id="51e2c-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="51e2c-143">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-145">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="51e2c-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-146">錯誤報告的目標會議 URI。</span><span class="sxs-lookup"><span data-stu-id="51e2c-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-149">錯誤報告的目標會議 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="51e2c-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="51e2c-150">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-152">datetime</span><span class="sxs-lookup"><span data-stu-id="51e2c-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="51e2c-153">來自錯誤報告的工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="51e2c-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="51e2c-154">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="51e2c-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="51e2c-155"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-157">int</span><span class="sxs-lookup"><span data-stu-id="51e2c-157">int</span></span></p></td>
<td><p><span data-ttu-id="51e2c-158">若要識別來自錯誤報告的工作階段要求的識別碼。</span><span class="sxs-lookup"><span data-stu-id="51e2c-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="51e2c-159">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="51e2c-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="51e2c-160"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-162">varstring(775)</span><span class="sxs-lookup"><span data-stu-id="51e2c-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-163">錯誤源自的工作階段 SIP 對話方塊 ID。</span><span class="sxs-lookup"><span data-stu-id="51e2c-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="51e2c-164">格式為：</span><span class="sxs-lookup"><span data-stu-id="51e2c-164">The format is:</span></span></p>
<p><span data-ttu-id="51e2c-165">對話方塊; 從標籤; 來標記</span><span class="sxs-lookup"><span data-stu-id="51e2c-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="51e2c-166">可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="51e2c-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="51e2c-167">轉換 （轉換 (ExternalId 做為 varchar(max)) varbinary(max))</span><span class="sxs-lookup"><span data-stu-id="51e2c-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-170">錯誤源自之使用者所用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="51e2c-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-172">int</span><span class="sxs-lookup"><span data-stu-id="51e2c-172">int</span></span></p></td>
<td><p><span data-ttu-id="51e2c-173">用戶端之使用者所使用源自錯誤。</span><span class="sxs-lookup"><span data-stu-id="51e2c-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="51e2c-174">請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-176">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="51e2c-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-177">錯誤源自用戶端之使用者所使用的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-180">錯誤源自 （如果報告從伺服器元件傳送） 的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-183">錯誤源自 （如果報告從伺服器元件傳送） 的應用程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-185">int</span><span class="sxs-lookup"><span data-stu-id="51e2c-185">int</span></span></p></td>
<td><p><span data-ttu-id="51e2c-186">SIP 回應碼的 SIP 訊息包含錯誤報告的工作階段。</span><span class="sxs-lookup"><span data-stu-id="51e2c-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-188">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="51e2c-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-189">失敗之要求的類型。</span><span class="sxs-lookup"><span data-stu-id="51e2c-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-191">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="51e2c-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-192">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="51e2c-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51e2c-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-195">工作階段的類型。</span><span class="sxs-lookup"><span data-stu-id="51e2c-195">Type of session.</span></span> <span data-ttu-id="51e2c-196">請參閱<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-198">唯一</span><span class="sxs-lookup"><span data-stu-id="51e2c-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="51e2c-199">相互關聯參與會議之不同元件的加入時間資訊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="51e2c-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-201">int</span><span class="sxs-lookup"><span data-stu-id="51e2c-201">int</span></span></p></td>
<td><p><span data-ttu-id="51e2c-202">時間 （以毫秒為單位） 所需的特定元件加入會議。</span><span class="sxs-lookup"><span data-stu-id="51e2c-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-204">位元</span><span class="sxs-lookup"><span data-stu-id="51e2c-204">bit</span></span></p></td>
<td><p><span data-ttu-id="51e2c-205">會指出錯誤報告是否已在前端伺服器上，執行的 CDR 代理程式所擷取，或用戶端所傳送。</span><span class="sxs-lookup"><span data-stu-id="51e2c-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-206"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-207">smallint</span><span class="sxs-lookup"><span data-stu-id="51e2c-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="51e2c-208">保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="51e2c-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-210">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="51e2c-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="51e2c-211">錯誤的相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="51e2c-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e2c-212"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="51e2c-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="51e2c-214">送出報表的前端伺服器的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e2c-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="51e2c-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="51e2c-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="51e2c-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="51e2c-217">完整網域名稱包含送出報表的前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="51e2c-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

