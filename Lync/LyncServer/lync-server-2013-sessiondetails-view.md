---
title: Lync Server 2013： SessionDetails view
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
ms.openlocfilehash: 8baf67ce72103ef0dda64a9b0b43a8f6dd6402f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510060"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="240bc-102">Lync Server 2013 中的 SessionDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="240bc-102">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="240bc-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="240bc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="240bc-104">SessionDetails view 儲存點對點工作階段的資訊，這可能是 VoIP-VoIP 電話、兩方 IM 會話或其他類型的會話。</span><span class="sxs-lookup"><span data-stu-id="240bc-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="240bc-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="240bc-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="240bc-106">欄</span><span class="sxs-lookup"><span data-stu-id="240bc-106">Column</span></span></th>
<th><span data-ttu-id="240bc-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="240bc-107">Data Type</span></span></th>
<th><span data-ttu-id="240bc-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="240bc-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="240bc-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-110">datetime</span><span class="sxs-lookup"><span data-stu-id="240bc-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="240bc-111">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="240bc-111">Time of session request.</span></span> <span data-ttu-id="240bc-112">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="240bc-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="240bc-113">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表格中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-115">int</span><span class="sxs-lookup"><span data-stu-id="240bc-115">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="240bc-116">ID number to identify the session.</span></span> <span data-ttu-id="240bc-117">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="240bc-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="240bc-118">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-120">datetime</span><span class="sxs-lookup"><span data-stu-id="240bc-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="240bc-121">第一個邀請要求的時間。</span><span class="sxs-lookup"><span data-stu-id="240bc-121">Time of the first INVITE request.</span></span> <span data-ttu-id="240bc-122">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="240bc-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="240bc-123">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="240bc-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="240bc-124">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="240bc-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="240bc-125">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="240bc-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-127">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="240bc-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="240bc-128">啟動會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="240bc-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-130">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="240bc-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="240bc-131">加入會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="240bc-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-133">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-134">啟動會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="240bc-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="240bc-135">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-137">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-138">加入會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="240bc-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="240bc-139">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-141">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="240bc-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="240bc-142">啟動會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="240bc-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="240bc-143">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-145">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-146">加入會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="240bc-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="240bc-147">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-149">唯一</span><span class="sxs-lookup"><span data-stu-id="240bc-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="240bc-150">啟動會話之使用者的端點唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="240bc-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-152">唯一</span><span class="sxs-lookup"><span data-stu-id="240bc-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="240bc-153">加入會話之使用者的端點唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="240bc-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-155">datetime</span><span class="sxs-lookup"><span data-stu-id="240bc-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="240bc-156">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="240bc-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-158">int</span><span class="sxs-lookup"><span data-stu-id="240bc-158">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-159">啟動會話之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="240bc-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-161">int</span><span class="sxs-lookup"><span data-stu-id="240bc-161">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-162">加入會話之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="240bc-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-164">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-165">啟動會話之使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="240bc-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-167">int</span><span class="sxs-lookup"><span data-stu-id="240bc-167">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-168">啟動會話之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="240bc-168">Client used by the user who started the session.</span></span> <span data-ttu-id="240bc-169">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-171">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="240bc-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="240bc-172">啟動會話之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="240bc-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-174">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-175">加入會話之使用者所使用的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="240bc-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-177">int</span><span class="sxs-lookup"><span data-stu-id="240bc-177">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-178">加入會話之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="240bc-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="240bc-179">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-181">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="240bc-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="240bc-182">加入會話之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="240bc-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-184">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="240bc-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="240bc-185">會話目標使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="240bc-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-187">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="240bc-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="240bc-188">會話之目標使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="240bc-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="240bc-189">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-191">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="240bc-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="240bc-192">代表啟動工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="240bc-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-194">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-195">代表啟動工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="240bc-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="240bc-196">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-198">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-199">代表啟動工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="240bc-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="240bc-200">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-202">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="240bc-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="240bc-203">引用工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="240bc-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-205">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-206">引用工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="240bc-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="240bc-207">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-209">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-210">引用工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="240bc-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="240bc-211">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-213">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="240bc-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="240bc-214">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="240bc-214">SIP dialog ID.</span></span> <span data-ttu-id="240bc-215">格式為：</span><span class="sxs-lookup"><span data-stu-id="240bc-215">The format is:</span></span></p>
<p><span data-ttu-id="240bc-216">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="240bc-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-218">唯一</span><span class="sxs-lookup"><span data-stu-id="240bc-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="240bc-219">用於關聯多個會話的 GUID。</span><span class="sxs-lookup"><span data-stu-id="240bc-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-221">datetime</span><span class="sxs-lookup"><span data-stu-id="240bc-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="240bc-222">會話所取代之對話方塊的時間。</span><span class="sxs-lookup"><span data-stu-id="240bc-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="240bc-223">與 ReplaceDialogIdSeq 搭配使用，以唯一識別會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="240bc-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="240bc-224">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-226">int</span><span class="sxs-lookup"><span data-stu-id="240bc-226">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-227">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="240bc-227">ID number to identify the session.</span></span> <span data-ttu-id="240bc-228">與 ReplaceDialogIdTime 搭配使用，以唯一識別會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="240bc-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="240bc-229">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="240bc-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-231">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="240bc-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="240bc-232">工作階段取代的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="240bc-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="240bc-233">格式為：</span><span class="sxs-lookup"><span data-stu-id="240bc-233">The format is:</span></span></p>
<p><span data-ttu-id="240bc-234">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="240bc-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-236">datetime</span><span class="sxs-lookup"><span data-stu-id="240bc-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="240bc-p120">回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="240bc-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-241">int</span><span class="sxs-lookup"><span data-stu-id="240bc-241">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-p121">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="240bc-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-246">int</span><span class="sxs-lookup"><span data-stu-id="240bc-246">int</span></span></p></td>
<td><p><span data-ttu-id="240bc-247">從 SIP 標頭捕獲的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="240bc-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-249">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-250">會話的內容類型。</span><span class="sxs-lookup"><span data-stu-id="240bc-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-252">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-253">擷取工作階段適用之資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="240bc-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-254"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-255">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-256">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="240bc-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-258">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-259">啟動會話之使用者所使用的 Edge server FQDN。</span><span class="sxs-lookup"><span data-stu-id="240bc-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-261">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-262">啟動會話之使用者所使用的 Edge server FQDN</span><span class="sxs-lookup"><span data-stu-id="240bc-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-264">位</span><span class="sxs-lookup"><span data-stu-id="240bc-264">bit</span></span></p></td>
<td><p><span data-ttu-id="240bc-265">會指出啟動會話的使用者是否從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="240bc-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-267">位</span><span class="sxs-lookup"><span data-stu-id="240bc-267">bit</span></span></p></td>
<td><p><span data-ttu-id="240bc-268">會指出加入會話的使用者是否從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="240bc-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-270">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="240bc-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="240bc-271">會話的呼叫優先順序。</span><span class="sxs-lookup"><span data-stu-id="240bc-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-273">Smallint</span><span class="sxs-lookup"><span data-stu-id="240bc-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="240bc-274">會指出啟動會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="240bc-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="240bc-275">以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="240bc-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="240bc-276">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="240bc-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-278">Smallint</span><span class="sxs-lookup"><span data-stu-id="240bc-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="240bc-279">會指出啟動會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="240bc-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="240bc-280">以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="240bc-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="240bc-281">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="240bc-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240bc-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-283">Smallint</span><span class="sxs-lookup"><span data-stu-id="240bc-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="240bc-p124">指出通話屬性。以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="240bc-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="240bc-286">0x01 - 重試工作階段 1</span><span class="sxs-lookup"><span data-stu-id="240bc-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="240bc-287">0x02-代理程式代表回應群組所撥打的通話</span><span class="sxs-lookup"><span data-stu-id="240bc-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240bc-288"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="240bc-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="240bc-289">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="240bc-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="240bc-290">緊急電話的位置。</span><span class="sxs-lookup"><span data-stu-id="240bc-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

