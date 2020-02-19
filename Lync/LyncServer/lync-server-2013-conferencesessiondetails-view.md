---
title: 'Lync Server 2013: ConferenceSessionDetails 檢視'
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
ms.openlocfilehash: ef6d8baf95cc99c342e18200f9a17e5ab03a7f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="fa0a7-102">Lync Server 2013 中的 ConferenceSessionDetails 檢視</span><span class="sxs-lookup"><span data-stu-id="fa0a7-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa0a7-103">_**主題上次修改日期：** 2012年-11-12_</span><span class="sxs-lookup"><span data-stu-id="fa0a7-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="fa0a7-104">ConferenceSessionDetails 檢視會儲存多方成員工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="fa0a7-105">每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="fa0a7-106">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa0a7-107">欄</span><span class="sxs-lookup"><span data-stu-id="fa0a7-107">Column</span></span></th>
<th><span data-ttu-id="fa0a7-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="fa0a7-108">Data Type</span></span></th>
<th><span data-ttu-id="fa0a7-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="fa0a7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fa0a7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-112">Time of session request.</span></span> <span data-ttu-id="fa0a7-113">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fa0a7-114"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-116">int</span><span class="sxs-lookup"><span data-stu-id="fa0a7-116">int</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-117">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-117">ID number to identify the session.</span></span> <span data-ttu-id="fa0a7-118">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="fa0a7-119"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-121">datetime</span><span class="sxs-lookup"><span data-stu-id="fa0a7-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p104">第一個 INVITE 要求的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-126">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-127">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-130">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-130">Type of conference URI.</span></span> <span data-ttu-id="fa0a7-131">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-133">唯一</span><span class="sxs-lookup"><span data-stu-id="fa0a7-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p106">可區分週期性會議的執行個體的識別碼。每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-137">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-138">會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-141">會議伺服器 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-141">Type of conferencing server URI.</span></span> <span data-ttu-id="fa0a7-142">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-144">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-145">工作階段中所含之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-148">屬於工作階段一部分之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="fa0a7-149">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-152">屬於工作階段一部分之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="fa0a7-153">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-155">唯一</span><span class="sxs-lookup"><span data-stu-id="fa0a7-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-156">屬於工作階段一部分之使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-158">datetime</span><span class="sxs-lookup"><span data-stu-id="fa0a7-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-159">工作階段的結束時間。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-162">會議伺服器的版本。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-164">int</span><span class="sxs-lookup"><span data-stu-id="fa0a7-164">int</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-165">會議伺服器的類型。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-165">Type of conference server.</span></span> <span data-ttu-id="fa0a7-166">請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-168">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-169">會議伺服器類別。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-172">參與工作階段之使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-174">int</span><span class="sxs-lookup"><span data-stu-id="fa0a7-174">int</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-175">參與工作階段之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="fa0a7-176">請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-178">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-179">屬於工作階段一部分之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-181">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-182">代表啟動工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-185">代表啟動工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="fa0a7-186">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-189">代表啟動工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="fa0a7-190">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-192">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-193">引用工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-196">引用工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="fa0a7-197">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-200">引用工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="fa0a7-201">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-203">varstring(775)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p116">SIP 對話方塊識別碼。格式為</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="fa0a7-206">： 對話方塊; 從標籤; 來標記</span><span class="sxs-lookup"><span data-stu-id="fa0a7-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-208">datetime</span><span class="sxs-lookup"><span data-stu-id="fa0a7-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-209">用來識別目前工作階段所取代之對話的識別碼。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="fa0a7-210"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-212">int</span><span class="sxs-lookup"><span data-stu-id="fa0a7-212">int</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-213">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-213">ID number to identify the session.</span></span> <span data-ttu-id="fa0a7-214">可與 ReplaceDialogIdTime 搭配使用，來唯一識別此工作階段所取代的工作階段。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="fa0a7-215"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-217">varchar(775)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p119">工作階段取代的 SIP 對話方塊識別碼。格式為：</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="fa0a7-220">對話方塊; 從標籤; 來標記</span><span class="sxs-lookup"><span data-stu-id="fa0a7-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-222">位元</span><span class="sxs-lookup"><span data-stu-id="fa0a7-222">bit</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-223">指出是否要透過會議伺服器來啟動工作階段。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-225">位元</span><span class="sxs-lookup"><span data-stu-id="fa0a7-225">bit</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-226">指出是否要透過會議伺服器來結束工作階段。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-228">位元</span><span class="sxs-lookup"><span data-stu-id="fa0a7-228">bit</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-229">指出使用者是否會從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-231">datetime</span><span class="sxs-lookup"><span data-stu-id="fa0a7-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p120">回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-236">int</span><span class="sxs-lookup"><span data-stu-id="fa0a7-236">int</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p121">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-241">int</span><span class="sxs-lookup"><span data-stu-id="fa0a7-241">int</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-242">從工作階段 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-245">工作階段的內容類型。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-246"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-248">擷取工作階段適用之資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-251">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-254">參與工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-255"><strong>閘道</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-257">參與工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa0a7-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-260">參與工作階段之使用者所使用的 Edge Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="fa0a7-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0a7-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-262">smallint</span><span class="sxs-lookup"><span data-stu-id="fa0a7-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p122">指出參與工作階段之使用者的屬性。以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="fa0a7-265">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="fa0a7-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0a7-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="fa0a7-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="fa0a7-267">smallint</span><span class="sxs-lookup"><span data-stu-id="fa0a7-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="fa0a7-p123">指出通話屬性。以下為允許的屬性定義：</span><span class="sxs-lookup"><span data-stu-id="fa0a7-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="fa0a7-270">0x01 - 已重試工作階段0</span><span class="sxs-lookup"><span data-stu-id="fa0a7-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="fa0a7-271">x02 - 代理程式代表回應群組所撥打的通話</span><span class="sxs-lookup"><span data-stu-id="fa0a7-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

