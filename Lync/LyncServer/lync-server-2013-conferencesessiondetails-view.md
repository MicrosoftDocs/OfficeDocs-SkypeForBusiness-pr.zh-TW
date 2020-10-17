---
title: Lync Server 2013： ConferenceSessionDetails view
description: Lync Server 2013： ConferenceSessionDetails view。
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
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566769"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="e5cf7-103">Lync Server 2013 中的 ConferenceSessionDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="e5cf7-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5cf7-104">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e5cf7-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e5cf7-105">ConferenceSessionDetails 檢視會儲存多方成員工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="e5cf7-106">每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="e5cf7-107">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5cf7-108">欄</span><span class="sxs-lookup"><span data-stu-id="e5cf7-108">Column</span></span></th>
<th><span data-ttu-id="e5cf7-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="e5cf7-109">Data Type</span></span></th>
<th><span data-ttu-id="e5cf7-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e5cf7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e5cf7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-113">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-113">Time of session request.</span></span> <span data-ttu-id="e5cf7-114">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e5cf7-115">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-117">int</span><span class="sxs-lookup"><span data-stu-id="e5cf7-117">int</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-118">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-118">ID number to identify the session.</span></span> <span data-ttu-id="e5cf7-119">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e5cf7-120">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-121"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e5cf7-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p104">第一個 INVITE 要求的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-126"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-127">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-128">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-130">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-131">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-131">Type of conference URI.</span></span> <span data-ttu-id="e5cf7-132">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-134">唯一</span><span class="sxs-lookup"><span data-stu-id="e5cf7-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p106">可區分週期性會議的執行個體的識別碼。每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-138">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-139">會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-141">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-142">會議伺服器 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-142">Type of conferencing server URI.</span></span> <span data-ttu-id="e5cf7-143">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-145">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-146">工作階段中所含之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-147"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-148">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-149">屬於工作階段一部分之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="e5cf7-150">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-151"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-152">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-153">屬於工作階段一部分之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="e5cf7-154">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-156">唯一</span><span class="sxs-lookup"><span data-stu-id="e5cf7-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-157">屬於工作階段一部分之使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-159">datetime</span><span class="sxs-lookup"><span data-stu-id="e5cf7-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-160">工作階段的結束時間。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-162">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-163">會議伺服器的版本。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-165">int</span><span class="sxs-lookup"><span data-stu-id="e5cf7-165">int</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-166">會議伺服器的類型。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-166">Type of conference server.</span></span> <span data-ttu-id="e5cf7-167">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-169">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-170">會議伺服器類別。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-172">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-173">參與工作階段之使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-175">int</span><span class="sxs-lookup"><span data-stu-id="e5cf7-175">int</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-176">參與工作階段之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="e5cf7-177">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-179">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-180">屬於工作階段一部分之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-182">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-183">代表啟動工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-185">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-186">代表啟動工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="e5cf7-187">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-189">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-190">代表啟動工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="e5cf7-191">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-193">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-194">引用工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-196">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-197">引用工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="e5cf7-198">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-200">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-201">引用工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="e5cf7-202">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-204">varstring (775) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p116">SIP 對話方塊識別碼。格式為</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="e5cf7-207">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="e5cf7-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-209">datetime</span><span class="sxs-lookup"><span data-stu-id="e5cf7-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-210">用來識別目前工作階段所取代之對話的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e5cf7-211">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-213">int</span><span class="sxs-lookup"><span data-stu-id="e5cf7-213">int</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-214">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-214">ID number to identify the session.</span></span> <span data-ttu-id="e5cf7-215">可與 ReplaceDialogIdTime 搭配使用，來唯一識別此工作階段所取代的工作階段。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e5cf7-216">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-218">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p119">工作階段取代的 SIP 對話方塊識別碼。格式為：</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="e5cf7-221">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="e5cf7-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-223">位</span><span class="sxs-lookup"><span data-stu-id="e5cf7-223">bit</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-224">指出是否要透過會議伺服器來啟動工作階段。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-226">位</span><span class="sxs-lookup"><span data-stu-id="e5cf7-226">bit</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-227">指出是否要透過會議伺服器來結束工作階段。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-229">位</span><span class="sxs-lookup"><span data-stu-id="e5cf7-229">bit</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-230">指出使用者是否會從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-232">datetime</span><span class="sxs-lookup"><span data-stu-id="e5cf7-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p120">回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-237">int</span><span class="sxs-lookup"><span data-stu-id="e5cf7-237">int</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p121">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-241"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-242">int</span><span class="sxs-lookup"><span data-stu-id="e5cf7-242">int</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-243">從工作階段 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-245">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-246">工作階段的內容類型。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-248">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-249">擷取工作階段適用之資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-250"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-251">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-252">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-254">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-255">參與工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-256"><strong>閘道</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-257">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-258">參與工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-259"><strong>Edgeserver atl-edge</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-260">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5cf7-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-261">參與工作階段之使用者所使用的 Edge Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5cf7-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf7-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-263">Smallint</span><span class="sxs-lookup"><span data-stu-id="e5cf7-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p122">指出參與工作階段之使用者的屬性。以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="e5cf7-266">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="e5cf7-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf7-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e5cf7-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e5cf7-268">Smallint</span><span class="sxs-lookup"><span data-stu-id="e5cf7-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5cf7-p123">指出通話屬性。以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="e5cf7-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e5cf7-271">0x01 - 已重試工作階段0</span><span class="sxs-lookup"><span data-stu-id="e5cf7-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="e5cf7-272">x02 - 代理程式代表回應群組所撥打的通話</span><span class="sxs-lookup"><span data-stu-id="e5cf7-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

