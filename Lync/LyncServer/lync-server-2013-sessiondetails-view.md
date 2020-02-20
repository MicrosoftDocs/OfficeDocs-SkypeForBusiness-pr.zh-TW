---
title: 'Lync Server 2013: SessionDetails 檢視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="87690-102">Lync Server 2013 中 < SessionDetails view ></span><span class="sxs-lookup"><span data-stu-id="87690-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87690-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="87690-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="87690-104">SessionDetails 檢視儲存端對端工作階段，這可能是 VoIP 對 VoIP 電話、 雙方 IM 工作階段或其他類型的工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="87690-105">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="87690-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87690-106">欄</span><span class="sxs-lookup"><span data-stu-id="87690-106">Column</span></span></th>
<th><span data-ttu-id="87690-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="87690-107">Data Type</span></span></th>
<th><span data-ttu-id="87690-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="87690-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87690-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="87690-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-110">datetime</span><span class="sxs-lookup"><span data-stu-id="87690-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="87690-111">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="87690-111">Time of session request.</span></span> <span data-ttu-id="87690-112">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="87690-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="87690-113">請參閱<a href="lync-server-2013-dialogs-table.md">Dialogs Lync Server 2013 中的表格</a>表如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="87690-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-115">int</span><span class="sxs-lookup"><span data-stu-id="87690-115">int</span></span></p></td>
<td><p><span data-ttu-id="87690-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="87690-116">ID number to identify the session.</span></span> <span data-ttu-id="87690-117">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="87690-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="87690-118"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="87690-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="87690-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-120">datetime</span><span class="sxs-lookup"><span data-stu-id="87690-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="87690-121">第一次的 INVITE 要求的時間。</span><span class="sxs-lookup"><span data-stu-id="87690-121">Time of the first INVITE request.</span></span> <span data-ttu-id="87690-122">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="87690-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="87690-123">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="87690-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="87690-124">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="87690-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="87690-125">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="87690-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="87690-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-127">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="87690-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87690-128">啟動工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="87690-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="87690-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-130">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="87690-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87690-131">參加工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="87690-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-134">啟動工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="87690-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="87690-135">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-138">參加工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="87690-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="87690-139">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="87690-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-141">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="87690-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87690-142">使用者的承租人啟動工作階段。</span><span class="sxs-lookup"><span data-stu-id="87690-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="87690-143">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="87690-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-146">租用戶的使用者參加工作階段。</span><span class="sxs-lookup"><span data-stu-id="87690-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="87690-147">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="87690-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-149">唯一</span><span class="sxs-lookup"><span data-stu-id="87690-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="87690-150">啟動工作階段之使用者的端點唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="87690-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="87690-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-152">唯一</span><span class="sxs-lookup"><span data-stu-id="87690-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="87690-153">加入工作階段之使用者的端點唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="87690-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="87690-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-155">datetime</span><span class="sxs-lookup"><span data-stu-id="87690-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="87690-156">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="87690-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="87690-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-158">int</span><span class="sxs-lookup"><span data-stu-id="87690-158">int</span></span></p></td>
<td><p><span data-ttu-id="87690-159">啟動工作階段之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="87690-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="87690-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-161">int</span><span class="sxs-lookup"><span data-stu-id="87690-161">int</span></span></p></td>
<td><p><span data-ttu-id="87690-162">加入工作階段之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="87690-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="87690-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-165">啟動工作階段之使用者所用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="87690-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-167">int</span><span class="sxs-lookup"><span data-stu-id="87690-167">int</span></span></p></td>
<td><p><span data-ttu-id="87690-168">使用用戶端由使用者啟動工作階段。</span><span class="sxs-lookup"><span data-stu-id="87690-168">Client used by the user who started the session.</span></span> <span data-ttu-id="87690-169">請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="87690-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-171">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="87690-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="87690-172">使用的用戶端由使用者啟動工作階段類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="87690-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="87690-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-175">參加工作階段之使用者所用戶端的版本</span><span class="sxs-lookup"><span data-stu-id="87690-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-177">int</span><span class="sxs-lookup"><span data-stu-id="87690-177">int</span></span></p></td>
<td><p><span data-ttu-id="87690-178">使用用戶端使用者參加工作階段。</span><span class="sxs-lookup"><span data-stu-id="87690-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="87690-179">請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="87690-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-181">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="87690-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="87690-182">使用的用戶端使用者參加工作階段類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="87690-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="87690-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-184">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="87690-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87690-185">工作階段的目標使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="87690-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-187">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="87690-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87690-188">工作階段之目標使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="87690-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="87690-189">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="87690-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-191">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="87690-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87690-192">代表啟動工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="87690-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-195">代表啟動工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="87690-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="87690-196">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="87690-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-199">代表啟動工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="87690-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="87690-200">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="87690-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-202">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="87690-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="87690-203">引用工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="87690-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-206">引用工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="87690-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="87690-207">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="87690-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-210">引用工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="87690-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="87690-211">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87690-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="87690-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-213">varchar(775)</span><span class="sxs-lookup"><span data-stu-id="87690-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="87690-214">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="87690-214">SIP dialog ID.</span></span> <span data-ttu-id="87690-215">格式為：</span><span class="sxs-lookup"><span data-stu-id="87690-215">The format is:</span></span></p>
<p><span data-ttu-id="87690-216">對話方塊; 從標籤; 來標記</span><span class="sxs-lookup"><span data-stu-id="87690-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-217"><strong>相互關聯識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="87690-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-218">唯一</span><span class="sxs-lookup"><span data-stu-id="87690-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="87690-219">用來建立多個工作階段相互關聯的 GUID。</span><span class="sxs-lookup"><span data-stu-id="87690-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="87690-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-221">datetime</span><span class="sxs-lookup"><span data-stu-id="87690-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="87690-222">[] 對話方塊中的工作階段所取代的時間。</span><span class="sxs-lookup"><span data-stu-id="87690-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="87690-223">搭配 ReplaceDialogIdSeq 用來唯一地識別工作階段所取代] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="87690-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="87690-224"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="87690-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="87690-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-226">int</span><span class="sxs-lookup"><span data-stu-id="87690-226">int</span></span></p></td>
<td><p><span data-ttu-id="87690-227">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="87690-227">ID number to identify the session.</span></span> <span data-ttu-id="87690-228">搭配 ReplaceDialogIdTime 用來唯一地識別工作階段所取代] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="87690-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="87690-229"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="87690-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="87690-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-231">varchar(775)</span><span class="sxs-lookup"><span data-stu-id="87690-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="87690-232">工作階段取代的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="87690-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="87690-233">格式為：</span><span class="sxs-lookup"><span data-stu-id="87690-233">The format is:</span></span></p>
<p><span data-ttu-id="87690-234">對話方塊; 從標籤; 來標記</span><span class="sxs-lookup"><span data-stu-id="87690-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="87690-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-236">datetime</span><span class="sxs-lookup"><span data-stu-id="87690-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="87690-p120">回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="87690-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="87690-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-241">int</span><span class="sxs-lookup"><span data-stu-id="87690-241">int</span></span></p></td>
<td><p><span data-ttu-id="87690-p121">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="87690-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="87690-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-246">int</span><span class="sxs-lookup"><span data-stu-id="87690-246">int</span></span></p></td>
<td><p><span data-ttu-id="87690-247">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="87690-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="87690-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-250">工作階段的內容類型。</span><span class="sxs-lookup"><span data-stu-id="87690-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-251"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="87690-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-253">擷取工作階段適用之資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="87690-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="87690-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-256">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="87690-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="87690-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-259">啟動工作階段之使用者所使用的 Edge server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="87690-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="87690-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-262">啟動工作階段之使用者所使用的 Edge 伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="87690-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="87690-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-264">位元</span><span class="sxs-lookup"><span data-stu-id="87690-264">bit</span></span></p></td>
<td><p><span data-ttu-id="87690-265">會指出是否已啟動工作階段之使用者從登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="87690-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="87690-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-267">位元</span><span class="sxs-lookup"><span data-stu-id="87690-267">bit</span></span></p></td>
<td><p><span data-ttu-id="87690-268">會指出從內部部署網路是否參加工作階段之使用者登入。</span><span class="sxs-lookup"><span data-stu-id="87690-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="87690-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="87690-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87690-271">通話優先順序的工作階段。</span><span class="sxs-lookup"><span data-stu-id="87690-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="87690-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-273">smallint</span><span class="sxs-lookup"><span data-stu-id="87690-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="87690-274">指出起始工作階段之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="87690-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="87690-275">以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="87690-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="87690-276">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="87690-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="87690-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-278">smallint</span><span class="sxs-lookup"><span data-stu-id="87690-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="87690-279">指出起始工作階段之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="87690-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="87690-280">以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="87690-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="87690-281">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="87690-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87690-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="87690-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-283">smallint</span><span class="sxs-lookup"><span data-stu-id="87690-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="87690-p124">指出通話屬性。以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="87690-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="87690-286">0x01 - 重試工作階段 1</span><span class="sxs-lookup"><span data-stu-id="87690-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="87690-287">0x02-代理程式所代表的回應群組通話</span><span class="sxs-lookup"><span data-stu-id="87690-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87690-288"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="87690-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="87690-289">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="87690-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="87690-290">緊急電話的位置。</span><span class="sxs-lookup"><span data-stu-id="87690-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

