---
title: Lync Server 2013： ErrorReport view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="e876b-102">Lync Server 2013 中的 [ErrorReport] 視圖</span><span class="sxs-lookup"><span data-stu-id="e876b-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e876b-103">_**主題上次修改日期：** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="e876b-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="e876b-104">[ErrorReport] 視圖儲存所報告錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e876b-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="e876b-105">每一筆記錄都是一個錯誤發生。</span><span class="sxs-lookup"><span data-stu-id="e876b-105">Each record is one error occurrence.</span></span> <span data-ttu-id="e876b-106">錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。</span><span class="sxs-lookup"><span data-stu-id="e876b-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="e876b-107">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="e876b-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e876b-108">左欄</span><span class="sxs-lookup"><span data-stu-id="e876b-108">Column</span></span></th>
<th><span data-ttu-id="e876b-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="e876b-109">Data Type</span></span></th>
<th><span data-ttu-id="e876b-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e876b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e876b-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e876b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e876b-113">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="e876b-113">Time of error occurred.</span></span> <span data-ttu-id="e876b-114">與 ErrorReportSeq 搭配使用，可唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="e876b-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-116">int</span><span class="sxs-lookup"><span data-stu-id="e876b-116">int</span></span></p></td>
<td><p><span data-ttu-id="e876b-117">識別錯誤的識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="e876b-117">ID number to identify the error.</span></span> <span data-ttu-id="e876b-118">與 ErrorTime 搭配使用，可唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="e876b-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-120">int</span><span class="sxs-lookup"><span data-stu-id="e876b-120">int</span></span></p></td>
<td><p><span data-ttu-id="e876b-121">錯誤報表的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="e876b-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-123">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e876b-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e876b-124">產生錯誤之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e876b-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-126">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-127">產生錯誤之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e876b-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="e876b-128">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-130">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-131">產生錯誤之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="e876b-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="e876b-132">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-134">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e876b-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e876b-135">錯誤報表目標使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e876b-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-137">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-138">錯誤報表目標使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e876b-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="e876b-139">如需詳細資訊，請參閱 UriTypes 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-141">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-142">針對錯誤報表的目標使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="e876b-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="e876b-143">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-145">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e876b-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e876b-146">錯誤報表目標的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="e876b-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-148">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-149">錯誤報表目標會議的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e876b-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="e876b-150">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-152">datetime</span><span class="sxs-lookup"><span data-stu-id="e876b-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="e876b-153">產生錯誤報表之會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="e876b-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="e876b-154">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="e876b-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e876b-155">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-157">int</span><span class="sxs-lookup"><span data-stu-id="e876b-157">int</span></span></p></td>
<td><p><span data-ttu-id="e876b-158">識別產生錯誤報表之會話要求的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="e876b-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="e876b-159">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="e876b-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e876b-160">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-162">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="e876b-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e876b-163">產生錯誤之會話的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="e876b-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="e876b-164">格式為：</span><span class="sxs-lookup"><span data-stu-id="e876b-164">The format is:</span></span></p>
<p><span data-ttu-id="e876b-165">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="e876b-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="e876b-166">您可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="e876b-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="e876b-167">cast （轉換（ExternalId 為 Varbinary （max））做為 Varchar （max））</span><span class="sxs-lookup"><span data-stu-id="e876b-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-169">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-170">產生錯誤的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="e876b-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-172">int</span><span class="sxs-lookup"><span data-stu-id="e876b-172">int</span></span></p></td>
<td><p><span data-ttu-id="e876b-173">產生錯誤的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e876b-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="e876b-174">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-176">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e876b-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e876b-177">產生錯誤之使用者所使用之用戶端類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="e876b-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-178"><strong>從源</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-179">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-180">產生錯誤的伺服器名稱（如果報表是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="e876b-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-181"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-182">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-183">產生錯誤的應用程式名稱（如果報表是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="e876b-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-185">int</span><span class="sxs-lookup"><span data-stu-id="e876b-185">int</span></span></p></td>
<td><p><span data-ttu-id="e876b-186">SIP 回應程式碼加入包含錯誤報表之 SIP 訊息的會話中。</span><span class="sxs-lookup"><span data-stu-id="e876b-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-188">Varchar （max）</span><span class="sxs-lookup"><span data-stu-id="e876b-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e876b-189">失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="e876b-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-191">Varchar （max）</span><span class="sxs-lookup"><span data-stu-id="e876b-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e876b-192">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="e876b-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-194">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e876b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e876b-195">會話類型。</span><span class="sxs-lookup"><span data-stu-id="e876b-195">Type of session.</span></span> <span data-ttu-id="e876b-196">如需詳細資訊，請參閱<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中</a>的 [CallType] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e876b-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-198">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e876b-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e876b-199">與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e876b-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-201">int</span><span class="sxs-lookup"><span data-stu-id="e876b-201">int</span></span></p></td>
<td><p><span data-ttu-id="e876b-202">特定元件加入會議所需的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="e876b-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-204">稍微</span><span class="sxs-lookup"><span data-stu-id="e876b-204">bit</span></span></p></td>
<td><p><span data-ttu-id="e876b-205">指示錯誤報表是由在前端伺服器上執行的 CDR 代理程式捕獲，還是由用戶端傳送。</span><span class="sxs-lookup"><span data-stu-id="e876b-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-206"><strong>標識</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-207">Smallint</span><span class="sxs-lookup"><span data-stu-id="e876b-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="e876b-208">保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="e876b-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-210">Varchar （max）</span><span class="sxs-lookup"><span data-stu-id="e876b-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e876b-211">錯誤的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e876b-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e876b-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-213">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="e876b-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="e876b-214">提交報表之前端伺服器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e876b-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e876b-215"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="e876b-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e876b-216">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="e876b-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="e876b-217">包含提交報表之前端伺服器之池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e876b-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

