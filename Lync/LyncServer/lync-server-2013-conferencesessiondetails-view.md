---
title: Lync Server 2013： ConferenceSessionDetails view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="e39ea-102">Lync Server 2013 中的 [ConferenceSessionDetails] 視圖</span><span class="sxs-lookup"><span data-stu-id="e39ea-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e39ea-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e39ea-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e39ea-104">[ConferenceSessionDetails] 視圖儲存有關多方會話的資訊。</span><span class="sxs-lookup"><span data-stu-id="e39ea-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="e39ea-105">每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。</span><span class="sxs-lookup"><span data-stu-id="e39ea-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="e39ea-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="e39ea-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e39ea-107">左欄</span><span class="sxs-lookup"><span data-stu-id="e39ea-107">Column</span></span></th>
<th><span data-ttu-id="e39ea-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="e39ea-108">Data Type</span></span></th>
<th><span data-ttu-id="e39ea-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e39ea-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e39ea-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e39ea-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="e39ea-112">Time of session request.</span></span> <span data-ttu-id="e39ea-113">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="e39ea-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e39ea-114">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-116">int</span><span class="sxs-lookup"><span data-stu-id="e39ea-116">int</span></span></p></td>
<td><p><span data-ttu-id="e39ea-117">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="e39ea-117">ID number to identify the session.</span></span> <span data-ttu-id="e39ea-118">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="e39ea-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e39ea-119">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e39ea-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="e39ea-122">第一次邀請要求的時間。</span><span class="sxs-lookup"><span data-stu-id="e39ea-122">Time of the first INVITE request.</span></span> <span data-ttu-id="e39ea-123">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="e39ea-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e39ea-124">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="e39ea-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-126">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e39ea-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-127">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="e39ea-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-129">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-130">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="e39ea-130">Type of conference URI.</span></span> <span data-ttu-id="e39ea-131">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e39ea-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e39ea-134">區分週期性會議實例的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e39ea-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="e39ea-135">每個週期性會議實例都有相同的 ConferenceURI，但有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="e39ea-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-137">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e39ea-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-138">會議服務器的 URI。</span><span class="sxs-lookup"><span data-stu-id="e39ea-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-140">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-141">會議服務器 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="e39ea-141">Type of conferencing server URI.</span></span> <span data-ttu-id="e39ea-142">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-144">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e39ea-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-145">會話中所涉及之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e39ea-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-147">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-148">屬於會話一部分之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e39ea-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="e39ea-149">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-151">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-152">屬於會話一部分之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="e39ea-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="e39ea-153">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e39ea-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e39ea-156">會話中的使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e39ea-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-158">datetime</span><span class="sxs-lookup"><span data-stu-id="e39ea-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="e39ea-159">會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="e39ea-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-161">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-162">[會議服務器] 版本。</span><span class="sxs-lookup"><span data-stu-id="e39ea-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-164">int</span><span class="sxs-lookup"><span data-stu-id="e39ea-164">int</span></span></p></td>
<td><p><span data-ttu-id="e39ea-165">會議服務器的類型。</span><span class="sxs-lookup"><span data-stu-id="e39ea-165">Type of conference server.</span></span> <span data-ttu-id="e39ea-166">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-168">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e39ea-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-169">[會議服務器] 類別。</span><span class="sxs-lookup"><span data-stu-id="e39ea-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-171">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-172">參與會話之使用者使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="e39ea-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-174">int</span><span class="sxs-lookup"><span data-stu-id="e39ea-174">int</span></span></p></td>
<td><p><span data-ttu-id="e39ea-175">參與會話的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e39ea-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="e39ea-176">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-178">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e39ea-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-179">參與會話之使用者所使用之用戶端類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="e39ea-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-181">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e39ea-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-182">代表其啟動會話的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="e39ea-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-184">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-185">啟動會話所代表之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e39ea-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="e39ea-186">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-188">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-189">代表啟動會話的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="e39ea-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="e39ea-190">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-192">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e39ea-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-193">參照會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e39ea-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-195">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-196">參照會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e39ea-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="e39ea-197">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-199">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-200">參照會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="e39ea-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="e39ea-201">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-203">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="e39ea-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-204">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="e39ea-204">SIP dialog ID.</span></span> <span data-ttu-id="e39ea-205">格式為</span><span class="sxs-lookup"><span data-stu-id="e39ea-205">The format is</span></span></p>
<p><span data-ttu-id="e39ea-206">:d ialog; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="e39ea-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-208">datetime</span><span class="sxs-lookup"><span data-stu-id="e39ea-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="e39ea-209">[識別碼] 編號，找出目前會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e39ea-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e39ea-210">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-212">int</span><span class="sxs-lookup"><span data-stu-id="e39ea-212">int</span></span></p></td>
<td><p><span data-ttu-id="e39ea-213">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="e39ea-213">ID number to identify the session.</span></span> <span data-ttu-id="e39ea-214">與 ReplaceDialogIdTime 搭配使用，可唯一識別此會話所取代的會話。</span><span class="sxs-lookup"><span data-stu-id="e39ea-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e39ea-215">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="e39ea-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-217">Varchar （775）</span><span class="sxs-lookup"><span data-stu-id="e39ea-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-218">[SIP] 對話方塊識別碼，該會話會取代。</span><span class="sxs-lookup"><span data-stu-id="e39ea-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="e39ea-219">的格式為：</span><span class="sxs-lookup"><span data-stu-id="e39ea-219">The format of the is:</span></span></p>
<p><span data-ttu-id="e39ea-220">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="e39ea-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-222">稍微</span><span class="sxs-lookup"><span data-stu-id="e39ea-222">bit</span></span></p></td>
<td><p><span data-ttu-id="e39ea-223">指出會話是否由會議服務器啟動。</span><span class="sxs-lookup"><span data-stu-id="e39ea-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-225">稍微</span><span class="sxs-lookup"><span data-stu-id="e39ea-225">bit</span></span></p></td>
<td><p><span data-ttu-id="e39ea-226">指出會議服務器是否已結束會話。</span><span class="sxs-lookup"><span data-stu-id="e39ea-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-228">稍微</span><span class="sxs-lookup"><span data-stu-id="e39ea-228">bit</span></span></p></td>
<td><p><span data-ttu-id="e39ea-229">指示使用者是否從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="e39ea-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-231">datetime</span><span class="sxs-lookup"><span data-stu-id="e39ea-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="e39ea-232">第一次邀請訊息的回復時間。</span><span class="sxs-lookup"><span data-stu-id="e39ea-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="e39ea-233">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="e39ea-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e39ea-234">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="e39ea-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-236">int</span><span class="sxs-lookup"><span data-stu-id="e39ea-236">int</span></span></p></td>
<td><p><span data-ttu-id="e39ea-237">SIP 回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="e39ea-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="e39ea-238">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="e39ea-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e39ea-239">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="e39ea-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-241">int</span><span class="sxs-lookup"><span data-stu-id="e39ea-241">int</span></span></p></td>
<td><p><span data-ttu-id="e39ea-242">從會話 SIP 標頭捕獲的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="e39ea-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-244">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-245">會話的內容類型。</span><span class="sxs-lookup"><span data-stu-id="e39ea-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-247">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-248">捕獲會話資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e39ea-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-249"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-250">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-251">捕獲會話資料之池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e39ea-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-253">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-254">參與會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="e39ea-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-255"><strong>關</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-256">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-257">參與會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="e39ea-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-259">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e39ea-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e39ea-260">參與會話之使用者所使用的邊緣伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e39ea-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39ea-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-262">Smallint</span><span class="sxs-lookup"><span data-stu-id="e39ea-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="e39ea-263">指出參與會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="e39ea-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="e39ea-264">允許下列屬性定義：</span><span class="sxs-lookup"><span data-stu-id="e39ea-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="e39ea-265">0x01-與桌面電話整合</span><span class="sxs-lookup"><span data-stu-id="e39ea-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39ea-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e39ea-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e39ea-267">Smallint</span><span class="sxs-lookup"><span data-stu-id="e39ea-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="e39ea-268">指出通話屬性。</span><span class="sxs-lookup"><span data-stu-id="e39ea-268">Indicates the call attributes.</span></span> <span data-ttu-id="e39ea-269">允許下列屬性定義：</span><span class="sxs-lookup"><span data-stu-id="e39ea-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e39ea-270">0x01-重試 Session0</span><span class="sxs-lookup"><span data-stu-id="e39ea-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="e39ea-271">x02-代表回應群組發出的代理通話</span><span class="sxs-lookup"><span data-stu-id="e39ea-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

