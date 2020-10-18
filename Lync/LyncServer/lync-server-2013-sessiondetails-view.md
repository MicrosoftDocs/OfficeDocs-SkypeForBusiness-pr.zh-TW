---
title: Lync Server 2013： SessionDetails view
description: Lync Server 2013： SessionDetails view。
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573239"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="b945d-103">Lync Server 2013 中的 SessionDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="b945d-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b945d-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b945d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b945d-105">SessionDetails view 儲存點對點工作階段的資訊，這可能是 VoIP-VoIP 電話、兩方 IM 會話或其他類型的會話。</span><span class="sxs-lookup"><span data-stu-id="b945d-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="b945d-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b945d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b945d-107">欄</span><span class="sxs-lookup"><span data-stu-id="b945d-107">Column</span></span></th>
<th><span data-ttu-id="b945d-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="b945d-108">Data Type</span></span></th>
<th><span data-ttu-id="b945d-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b945d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b945d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b945d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b945d-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="b945d-112">Time of session request.</span></span> <span data-ttu-id="b945d-113">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="b945d-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b945d-114">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表格中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-116">int</span><span class="sxs-lookup"><span data-stu-id="b945d-116">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-117">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="b945d-117">ID number to identify the session.</span></span> <span data-ttu-id="b945d-118">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="b945d-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b945d-119">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b945d-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="b945d-122">第一個邀請要求的時間。</span><span class="sxs-lookup"><span data-stu-id="b945d-122">Time of the first INVITE request.</span></span> <span data-ttu-id="b945d-123">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="b945d-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b945d-124">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="b945d-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="b945d-125">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="b945d-125">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b945d-126">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="b945d-126">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-128">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b945d-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b945d-129">啟動會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b945d-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-130"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-131">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b945d-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b945d-132">加入會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b945d-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-134">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-135">啟動會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="b945d-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="b945d-136">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-138">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-139">加入會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="b945d-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="b945d-140">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-142">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b945d-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b945d-143">啟動會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="b945d-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="b945d-144">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-145"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-146">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-147">加入會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="b945d-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="b945d-148">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-150">唯一</span><span class="sxs-lookup"><span data-stu-id="b945d-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b945d-151">啟動會話之使用者的端點唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b945d-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-152"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-153">唯一</span><span class="sxs-lookup"><span data-stu-id="b945d-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b945d-154">加入會話之使用者的端點唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b945d-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-156">datetime</span><span class="sxs-lookup"><span data-stu-id="b945d-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="b945d-157">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="b945d-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-159">int</span><span class="sxs-lookup"><span data-stu-id="b945d-159">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-160">啟動會話之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="b945d-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-162">int</span><span class="sxs-lookup"><span data-stu-id="b945d-162">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-163">加入會話之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="b945d-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-165">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-166">啟動會話之使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="b945d-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-168">int</span><span class="sxs-lookup"><span data-stu-id="b945d-168">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-169">啟動會話之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b945d-169">Client used by the user who started the session.</span></span> <span data-ttu-id="b945d-170">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-172">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="b945d-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b945d-173">啟動會話之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="b945d-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-175">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-176">加入會話之使用者所使用的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="b945d-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-177"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-178">int</span><span class="sxs-lookup"><span data-stu-id="b945d-178">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-179">加入會話之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b945d-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="b945d-180">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-182">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="b945d-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b945d-183">加入會話之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="b945d-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-185">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b945d-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b945d-186">會話目標使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b945d-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-188">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b945d-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b945d-189">會話之目標使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="b945d-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="b945d-190">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-192">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b945d-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b945d-193">代表啟動工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b945d-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-195">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-196">代表啟動工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="b945d-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="b945d-197">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-199">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-200">代表啟動工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="b945d-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="b945d-201">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-203">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b945d-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b945d-204">引用工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b945d-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-206">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-207">引用工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="b945d-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="b945d-208">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-210">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-211">引用工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="b945d-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="b945d-212">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-214">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="b945d-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b945d-215">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="b945d-215">SIP dialog ID.</span></span> <span data-ttu-id="b945d-216">格式為：</span><span class="sxs-lookup"><span data-stu-id="b945d-216">The format is:</span></span></p>
<p><span data-ttu-id="b945d-217">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="b945d-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-218"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-219">唯一</span><span class="sxs-lookup"><span data-stu-id="b945d-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b945d-220">用於關聯多個會話的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b945d-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-222">datetime</span><span class="sxs-lookup"><span data-stu-id="b945d-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="b945d-223">會話所取代之對話方塊的時間。</span><span class="sxs-lookup"><span data-stu-id="b945d-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="b945d-224">與 ReplaceDialogIdSeq 搭配使用，以唯一識別會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b945d-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="b945d-225">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-227">int</span><span class="sxs-lookup"><span data-stu-id="b945d-227">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-228">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="b945d-228">ID number to identify the session.</span></span> <span data-ttu-id="b945d-229">與 ReplaceDialogIdTime 搭配使用，以唯一識別會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b945d-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="b945d-230">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b945d-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-232">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="b945d-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b945d-233">工作階段取代的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="b945d-233">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="b945d-234">格式為：</span><span class="sxs-lookup"><span data-stu-id="b945d-234">The format is:</span></span></p>
<p><span data-ttu-id="b945d-235">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="b945d-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-237">datetime</span><span class="sxs-lookup"><span data-stu-id="b945d-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="b945d-p120">回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="b945d-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-242">int</span><span class="sxs-lookup"><span data-stu-id="b945d-242">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-p121">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="b945d-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-246"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-247">int</span><span class="sxs-lookup"><span data-stu-id="b945d-247">int</span></span></p></td>
<td><p><span data-ttu-id="b945d-248">從 SIP 標頭捕獲的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="b945d-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-250">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-251">會話的內容類型。</span><span class="sxs-lookup"><span data-stu-id="b945d-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-253">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-254">擷取工作階段適用之資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b945d-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-255"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-256">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-257">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b945d-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-259">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-260">啟動會話之使用者所使用的 Edge server FQDN。</span><span class="sxs-lookup"><span data-stu-id="b945d-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-262">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-263">啟動會話之使用者所使用的 Edge server FQDN</span><span class="sxs-lookup"><span data-stu-id="b945d-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-265">位</span><span class="sxs-lookup"><span data-stu-id="b945d-265">bit</span></span></p></td>
<td><p><span data-ttu-id="b945d-266">會指出啟動會話的使用者是否從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="b945d-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-268">位</span><span class="sxs-lookup"><span data-stu-id="b945d-268">bit</span></span></p></td>
<td><p><span data-ttu-id="b945d-269">會指出加入會話的使用者是否從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="b945d-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-271">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b945d-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b945d-272">會話的呼叫優先順序。</span><span class="sxs-lookup"><span data-stu-id="b945d-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-274">Smallint</span><span class="sxs-lookup"><span data-stu-id="b945d-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="b945d-275">會指出啟動會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="b945d-275">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="b945d-276">以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="b945d-276">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b945d-277">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="b945d-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-279">Smallint</span><span class="sxs-lookup"><span data-stu-id="b945d-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="b945d-280">會指出啟動會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="b945d-280">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="b945d-281">以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="b945d-281">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b945d-282">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="b945d-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b945d-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-284">Smallint</span><span class="sxs-lookup"><span data-stu-id="b945d-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="b945d-p124">指出通話屬性。以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="b945d-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b945d-287">0x01 - 重試工作階段 1</span><span class="sxs-lookup"><span data-stu-id="b945d-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="b945d-288">0x02-代理程式代表回應群組所撥打的通話</span><span class="sxs-lookup"><span data-stu-id="b945d-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b945d-289"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="b945d-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="b945d-290">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="b945d-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b945d-291">緊急電話的位置。</span><span class="sxs-lookup"><span data-stu-id="b945d-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

