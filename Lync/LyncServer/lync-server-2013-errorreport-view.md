---
title: Lync Server 2013： ErrorReport view
description: Lync Server 2013： ErrorReport view。
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
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572039"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="f941d-103">Lync Server 2013 中的 ErrorReport 視圖</span><span class="sxs-lookup"><span data-stu-id="f941d-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f941d-104">_**主題上次修改日期：** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="f941d-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="f941d-105">ErrorReport view 會儲存所報告錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f941d-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="f941d-106">每個記錄是一個錯誤發生。</span><span class="sxs-lookup"><span data-stu-id="f941d-106">Each record is one error occurrence.</span></span> <span data-ttu-id="f941d-107">這兩個錯誤是由前端伺服器上執行的 CDR 代理程式所捕獲，或是從用戶端傳送。</span><span class="sxs-lookup"><span data-stu-id="f941d-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="f941d-108">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f941d-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f941d-109">欄</span><span class="sxs-lookup"><span data-stu-id="f941d-109">Column</span></span></th>
<th><span data-ttu-id="f941d-110">資料類型</span><span class="sxs-lookup"><span data-stu-id="f941d-110">Data Type</span></span></th>
<th><span data-ttu-id="f941d-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f941d-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f941d-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f941d-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="f941d-114">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="f941d-114">Time of error occurred.</span></span> <span data-ttu-id="f941d-115">與 ErrorReportSeq 搭配使用，以唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="f941d-115">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-117">int</span><span class="sxs-lookup"><span data-stu-id="f941d-117">int</span></span></p></td>
<td><p><span data-ttu-id="f941d-118">用以識別錯誤的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="f941d-118">ID number to identify the error.</span></span> <span data-ttu-id="f941d-119">與 ErrorTime 搭配使用，以唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="f941d-119">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-121">int</span><span class="sxs-lookup"><span data-stu-id="f941d-121">int</span></span></p></td>
<td><p><span data-ttu-id="f941d-122">錯誤報表的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="f941d-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-124">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="f941d-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f941d-125">產生錯誤之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="f941d-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-127">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-128">產生錯誤之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="f941d-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="f941d-129">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-131">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-132">產生錯誤之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="f941d-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="f941d-133">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-134"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-135">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="f941d-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f941d-136">錯誤報表之目標之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="f941d-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-138">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-139">錯誤報表目標使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="f941d-139">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="f941d-140">如需詳細資訊，請參閱＜UriTypes Table＞。</span><span class="sxs-lookup"><span data-stu-id="f941d-140">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-141"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-142">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-143">目標為錯誤報表之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="f941d-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="f941d-144">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-145"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-146">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="f941d-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f941d-147">錯誤報表目標的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="f941d-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-149">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-150">錯誤報表目標的會議 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="f941d-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="f941d-151">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-152"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-153">datetime</span><span class="sxs-lookup"><span data-stu-id="f941d-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="f941d-154">發出錯誤報表之會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="f941d-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="f941d-155">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="f941d-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f941d-156">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-158">int</span><span class="sxs-lookup"><span data-stu-id="f941d-158">int</span></span></p></td>
<td><p><span data-ttu-id="f941d-159">識別產生錯誤報表之會話要求的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="f941d-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="f941d-160">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="f941d-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f941d-161">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-163">varstring (775) </span><span class="sxs-lookup"><span data-stu-id="f941d-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="f941d-164">發出錯誤之會話的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="f941d-164">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="f941d-165">格式為：</span><span class="sxs-lookup"><span data-stu-id="f941d-165">The format is:</span></span></p>
<p><span data-ttu-id="f941d-166">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="f941d-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="f941d-167">您可以使用下列語法將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="f941d-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="f941d-168">cast (cast (ExternalId 為 Varbinary (max) # A4 做為 Varchar (最大) # A7</span><span class="sxs-lookup"><span data-stu-id="f941d-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-169"><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.rule</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-170">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-171">產生錯誤之使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="f941d-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-173">int</span><span class="sxs-lookup"><span data-stu-id="f941d-173">int</span></span></p></td>
<td><p><span data-ttu-id="f941d-174">產生錯誤之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="f941d-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="f941d-175">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-177">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="f941d-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f941d-178">產生錯誤之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="f941d-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-180">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-181">起源錯誤的伺服器名稱 (如果報告是從伺服器元件傳送) 中。</span><span class="sxs-lookup"><span data-stu-id="f941d-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-182"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-183">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-184">起源錯誤的應用程式名稱 (如果報告是從伺服器元件傳送) 。</span><span class="sxs-lookup"><span data-stu-id="f941d-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-186">int</span><span class="sxs-lookup"><span data-stu-id="f941d-186">int</span></span></p></td>
<td><p><span data-ttu-id="f941d-187">包含錯誤報表之 SIP 郵件會話的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="f941d-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-189">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="f941d-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f941d-190">失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="f941d-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-192">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="f941d-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f941d-193">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="f941d-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-195">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f941d-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f941d-196">會話類型。</span><span class="sxs-lookup"><span data-stu-id="f941d-196">Type of session.</span></span> <span data-ttu-id="f941d-197">如需詳細資訊，請參閱 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f941d-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-198"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-199">唯一</span><span class="sxs-lookup"><span data-stu-id="f941d-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f941d-200">與會議相關聯之不同元件的加入時間資訊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f941d-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-201"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-202">int</span><span class="sxs-lookup"><span data-stu-id="f941d-202">int</span></span></p></td>
<td><p><span data-ttu-id="f941d-203">特定元件加入會議所需的時間 (（毫秒）) 。</span><span class="sxs-lookup"><span data-stu-id="f941d-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-205">位</span><span class="sxs-lookup"><span data-stu-id="f941d-205">bit</span></span></p></td>
<td><p><span data-ttu-id="f941d-206">會指出是否是由前端伺服器上執行的 CDR 代理程式所捕獲，或是由用戶端所傳送的錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="f941d-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-207"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-208">Smallint</span><span class="sxs-lookup"><span data-stu-id="f941d-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="f941d-209">保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="f941d-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-211">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="f941d-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f941d-212">有關錯誤的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="f941d-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f941d-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-214">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="f941d-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="f941d-215">提交報告之前端伺服器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f941d-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f941d-216"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="f941d-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f941d-217">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="f941d-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="f941d-218">包含提交報告之前端伺服器集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f941d-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

