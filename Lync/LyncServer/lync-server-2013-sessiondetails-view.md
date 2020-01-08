---
title: Lync Server 2013： SessionDetails view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="d95c3-102">Lync Server 2013 中的 [SessionDetails] 視圖</span><span class="sxs-lookup"><span data-stu-id="d95c3-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d95c3-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d95c3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d95c3-104">SessionDetails view 會儲存點對點工作階段的相關資訊，這可能是 VoIP VoIP 通話、兩方 IM 會話或其他類型的會話。</span><span class="sxs-lookup"><span data-stu-id="d95c3-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="d95c3-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d95c3-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d95c3-106">左欄</span><span class="sxs-lookup"><span data-stu-id="d95c3-106">Column</span></span></th>
<th><span data-ttu-id="d95c3-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="d95c3-107">Data Type</span></span></th>
<th><span data-ttu-id="d95c3-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d95c3-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d95c3-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d95c3-111">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="d95c3-111">Time of session request.</span></span> <span data-ttu-id="d95c3-112">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="d95c3-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="d95c3-113">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 資料表中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-115">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-115">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-116">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="d95c3-116">ID number to identify the session.</span></span> <span data-ttu-id="d95c3-117">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="d95c3-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="d95c3-118">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-120">datetime</span><span class="sxs-lookup"><span data-stu-id="d95c3-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="d95c3-121">第一次邀請要求的時間。</span><span class="sxs-lookup"><span data-stu-id="d95c3-121">Time of the first INVITE request.</span></span> <span data-ttu-id="d95c3-122">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="d95c3-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d95c3-123">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="d95c3-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="d95c3-124">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="d95c3-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d95c3-125">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="d95c3-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-127">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d95c3-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-128">啟動會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="d95c3-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-130">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d95c3-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-131">加入會話的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="d95c3-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-133">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-134">啟動會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="d95c3-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="d95c3-135">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-137">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-138">加入會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="d95c3-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="d95c3-139">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-141">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d95c3-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-142">啟動會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="d95c3-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="d95c3-143">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-145">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-146">加入會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="d95c3-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="d95c3-147">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d95c3-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d95c3-150">啟動會話之使用者之端點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d95c3-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d95c3-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d95c3-153">加入會話之使用者之端點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d95c3-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-155">datetime</span><span class="sxs-lookup"><span data-stu-id="d95c3-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="d95c3-156">會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="d95c3-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-158">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-158">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-159">啟動會話的使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="d95c3-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-161">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-161">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-162">加入會話的使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="d95c3-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-164">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-165">啟動會話的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="d95c3-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-167">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-167">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-168">啟動會話的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="d95c3-168">Client used by the user who started the session.</span></span> <span data-ttu-id="d95c3-169">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-171">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="d95c3-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-172">啟動會話之使用者所使用之用戶端類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="d95c3-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-174">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-175">加入會話的使用者所使用的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="d95c3-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-177">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-177">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-178">加入會話的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="d95c3-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="d95c3-179">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-181">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="d95c3-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-182">加入會話之使用者所使用之用戶端類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="d95c3-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-184">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d95c3-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-185">會話目標使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="d95c3-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-187">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d95c3-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-188">會話的目標使用者 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="d95c3-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="d95c3-189">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-191">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d95c3-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-192">代表其啟動會話的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="d95c3-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-194">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-195">啟動會話所代表之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="d95c3-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="d95c3-196">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-198">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-199">代表啟動會話的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="d95c3-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="d95c3-200">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-202">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d95c3-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-203">參照會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="d95c3-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-205">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-206">參照會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="d95c3-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="d95c3-207">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-209">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-210">參照會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="d95c3-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="d95c3-211">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-213">Varchar （775）</span><span class="sxs-lookup"><span data-stu-id="d95c3-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-214">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="d95c3-214">SIP dialog ID.</span></span> <span data-ttu-id="d95c3-215">格式為：</span><span class="sxs-lookup"><span data-stu-id="d95c3-215">The format is:</span></span></p>
<p><span data-ttu-id="d95c3-216">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="d95c3-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-217"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d95c3-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d95c3-219">用於關聯多個會話的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d95c3-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-221">datetime</span><span class="sxs-lookup"><span data-stu-id="d95c3-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="d95c3-222">會話所取代的對話方塊時間。</span><span class="sxs-lookup"><span data-stu-id="d95c3-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="d95c3-223">與 ReplaceDialogIdSeq 搭配使用，以唯一識別會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="d95c3-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="d95c3-224">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-226">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-226">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-227">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="d95c3-227">ID number to identify the session.</span></span> <span data-ttu-id="d95c3-228">與 ReplaceDialogIdTime 搭配使用，以唯一識別會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="d95c3-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="d95c3-229">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d95c3-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-231">Varchar （775）</span><span class="sxs-lookup"><span data-stu-id="d95c3-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-232">[SIP] 對話方塊識別碼，該會話會取代。</span><span class="sxs-lookup"><span data-stu-id="d95c3-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="d95c3-233">格式為：</span><span class="sxs-lookup"><span data-stu-id="d95c3-233">The format is:</span></span></p>
<p><span data-ttu-id="d95c3-234">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="d95c3-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-236">datetime</span><span class="sxs-lookup"><span data-stu-id="d95c3-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="d95c3-237">第一次邀請訊息的回復時間。</span><span class="sxs-lookup"><span data-stu-id="d95c3-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="d95c3-238">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="d95c3-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d95c3-239">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="d95c3-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-241">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-241">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-242">SIP 回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="d95c3-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="d95c3-243">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="d95c3-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d95c3-244">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="d95c3-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-246">int</span><span class="sxs-lookup"><span data-stu-id="d95c3-246">int</span></span></p></td>
<td><p><span data-ttu-id="d95c3-247">從 SIP 標頭捕獲的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="d95c3-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-249">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-250">會話的內容類型。</span><span class="sxs-lookup"><span data-stu-id="d95c3-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-252">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-253">捕獲會話資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d95c3-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-254"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-255">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-256">捕獲會話資料之池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d95c3-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-258">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-259">啟動會話之使用者所使用的邊緣伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d95c3-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-261">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-262">啟動會話之使用者所使用的邊緣伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="d95c3-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-264">稍微</span><span class="sxs-lookup"><span data-stu-id="d95c3-264">bit</span></span></p></td>
<td><p><span data-ttu-id="d95c3-265">指出啟動會話的使用者是否已從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="d95c3-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-267">稍微</span><span class="sxs-lookup"><span data-stu-id="d95c3-267">bit</span></span></p></td>
<td><p><span data-ttu-id="d95c3-268">指出加入會話的使用者是否已從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="d95c3-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-270">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d95c3-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-271">會話的呼叫優先順序。</span><span class="sxs-lookup"><span data-stu-id="d95c3-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-273">Smallint</span><span class="sxs-lookup"><span data-stu-id="d95c3-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="d95c3-274">指出啟動會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="d95c3-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="d95c3-275">允許下列屬性定義：</span><span class="sxs-lookup"><span data-stu-id="d95c3-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d95c3-276">0x01-與桌面電話整合</span><span class="sxs-lookup"><span data-stu-id="d95c3-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-278">Smallint</span><span class="sxs-lookup"><span data-stu-id="d95c3-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="d95c3-279">指出啟動會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="d95c3-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="d95c3-280">允許下列屬性定義：</span><span class="sxs-lookup"><span data-stu-id="d95c3-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d95c3-281">0x01-與桌面電話整合</span><span class="sxs-lookup"><span data-stu-id="d95c3-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d95c3-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-283">Smallint</span><span class="sxs-lookup"><span data-stu-id="d95c3-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="d95c3-284">指出通話屬性。</span><span class="sxs-lookup"><span data-stu-id="d95c3-284">Indicates the call attributes.</span></span> <span data-ttu-id="d95c3-285">允許下列屬性定義：</span><span class="sxs-lookup"><span data-stu-id="d95c3-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d95c3-286">0x01-重新嘗試會話</span><span class="sxs-lookup"><span data-stu-id="d95c3-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="d95c3-287">0x02-代理代表回應群組所做的通話</span><span class="sxs-lookup"><span data-stu-id="d95c3-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d95c3-288"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="d95c3-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="d95c3-289">Varchar （max）</span><span class="sxs-lookup"><span data-stu-id="d95c3-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d95c3-290">緊急通話的位置。</span><span class="sxs-lookup"><span data-stu-id="d95c3-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

