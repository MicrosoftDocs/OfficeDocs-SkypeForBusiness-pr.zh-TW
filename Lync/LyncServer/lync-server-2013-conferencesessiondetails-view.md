---
title: Lync Server 2013： ConferenceSessionDetails view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="95549-102">Lync Server 2013 中的 [ConferenceSessionDetails] 視圖</span><span class="sxs-lookup"><span data-stu-id="95549-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95549-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="95549-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="95549-104">[ConferenceSessionDetails] 視圖儲存有關多方會話的資訊。</span><span class="sxs-lookup"><span data-stu-id="95549-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="95549-105">每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。</span><span class="sxs-lookup"><span data-stu-id="95549-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="95549-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="95549-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95549-107">左欄</span><span class="sxs-lookup"><span data-stu-id="95549-107">Column</span></span></th>
<th><span data-ttu-id="95549-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="95549-108">Data Type</span></span></th>
<th><span data-ttu-id="95549-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="95549-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95549-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="95549-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-111">datetime</span><span class="sxs-lookup"><span data-stu-id="95549-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="95549-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="95549-112">Time of session request.</span></span> <span data-ttu-id="95549-113">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="95549-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="95549-114">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="95549-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-116">int</span><span class="sxs-lookup"><span data-stu-id="95549-116">int</span></span></p></td>
<td><p><span data-ttu-id="95549-117">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="95549-117">ID number to identify the session.</span></span> <span data-ttu-id="95549-118">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="95549-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="95549-119">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="95549-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-121">datetime</span><span class="sxs-lookup"><span data-stu-id="95549-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="95549-122">第一次邀請要求的時間。</span><span class="sxs-lookup"><span data-stu-id="95549-122">Time of the first INVITE request.</span></span> <span data-ttu-id="95549-123">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="95549-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="95549-124">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="95549-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="95549-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-126">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="95549-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95549-127">會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="95549-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-129">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-130">會議 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="95549-130">Type of conference URI.</span></span> <span data-ttu-id="95549-131">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="95549-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="95549-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="95549-134">區分週期性會議實例的識別碼。</span><span class="sxs-lookup"><span data-stu-id="95549-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="95549-135">每個週期性會議實例都有相同的 ConferenceURI，但有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="95549-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="95549-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-137">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="95549-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95549-138">會議服務器的 URI。</span><span class="sxs-lookup"><span data-stu-id="95549-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-140">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-141">會議服務器 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="95549-141">Type of conferencing server URI.</span></span> <span data-ttu-id="95549-142">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="95549-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-144">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="95549-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95549-145">會話中所涉及之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="95549-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-147">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-148">屬於會話一部分之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="95549-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="95549-149">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="95549-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-151">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-152">屬於會話一部分之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="95549-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="95549-153">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="95549-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="95549-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="95549-156">會話中的使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="95549-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="95549-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-158">datetime</span><span class="sxs-lookup"><span data-stu-id="95549-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="95549-159">會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="95549-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="95549-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-161">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-162">[會議服務器] 版本。</span><span class="sxs-lookup"><span data-stu-id="95549-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-164">int</span><span class="sxs-lookup"><span data-stu-id="95549-164">int</span></span></p></td>
<td><p><span data-ttu-id="95549-165">會議服務器的類型。</span><span class="sxs-lookup"><span data-stu-id="95549-165">Type of conference server.</span></span> <span data-ttu-id="95549-166">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="95549-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-168">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="95549-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="95549-169">[會議服務器] 類別。</span><span class="sxs-lookup"><span data-stu-id="95549-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="95549-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-171">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-172">參與會話之使用者使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="95549-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-174">int</span><span class="sxs-lookup"><span data-stu-id="95549-174">int</span></span></p></td>
<td><p><span data-ttu-id="95549-175">參與會話的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="95549-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="95549-176">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="95549-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-178">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="95549-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="95549-179">參與會話之使用者所使用之用戶端類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="95549-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="95549-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-181">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="95549-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95549-182">代表其啟動會話的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="95549-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-184">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-185">啟動會話所代表之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="95549-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="95549-186">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="95549-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-188">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-189">代表啟動會話的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="95549-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="95549-190">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="95549-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-192">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="95549-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95549-193">參照會話之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="95549-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-195">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-196">參照會話之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="95549-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="95549-197">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="95549-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-199">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-200">參照會話之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="95549-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="95549-201">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="95549-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-203">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="95549-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="95549-204">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="95549-204">SIP dialog ID.</span></span> <span data-ttu-id="95549-205">格式為</span><span class="sxs-lookup"><span data-stu-id="95549-205">The format is</span></span></p>
<p><span data-ttu-id="95549-206">:d ialog; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="95549-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="95549-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-208">datetime</span><span class="sxs-lookup"><span data-stu-id="95549-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="95549-209">[識別碼] 編號，找出目前會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="95549-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="95549-210">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="95549-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-212">int</span><span class="sxs-lookup"><span data-stu-id="95549-212">int</span></span></p></td>
<td><p><span data-ttu-id="95549-213">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="95549-213">ID number to identify the session.</span></span> <span data-ttu-id="95549-214">與 ReplaceDialogIdTime 搭配使用，可唯一識別此會話所取代的會話。</span><span class="sxs-lookup"><span data-stu-id="95549-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="95549-215">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="95549-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="95549-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-217">Varchar （775）</span><span class="sxs-lookup"><span data-stu-id="95549-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="95549-218">[SIP] 對話方塊識別碼，該會話會取代。</span><span class="sxs-lookup"><span data-stu-id="95549-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="95549-219">的格式為：</span><span class="sxs-lookup"><span data-stu-id="95549-219">The format of the is:</span></span></p>
<p><span data-ttu-id="95549-220">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="95549-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="95549-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-222">稍微</span><span class="sxs-lookup"><span data-stu-id="95549-222">bit</span></span></p></td>
<td><p><span data-ttu-id="95549-223">指出會話是否由會議服務器啟動。</span><span class="sxs-lookup"><span data-stu-id="95549-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="95549-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-225">稍微</span><span class="sxs-lookup"><span data-stu-id="95549-225">bit</span></span></p></td>
<td><p><span data-ttu-id="95549-226">指出會議服務器是否已結束會話。</span><span class="sxs-lookup"><span data-stu-id="95549-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="95549-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-228">稍微</span><span class="sxs-lookup"><span data-stu-id="95549-228">bit</span></span></p></td>
<td><p><span data-ttu-id="95549-229">指示使用者是否從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="95549-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="95549-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-231">datetime</span><span class="sxs-lookup"><span data-stu-id="95549-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="95549-232">第一次邀請訊息的回復時間。</span><span class="sxs-lookup"><span data-stu-id="95549-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="95549-233">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="95549-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="95549-234">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="95549-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="95549-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-236">int</span><span class="sxs-lookup"><span data-stu-id="95549-236">int</span></span></p></td>
<td><p><span data-ttu-id="95549-237">SIP 回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="95549-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="95549-238">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="95549-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="95549-239">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="95549-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="95549-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-241">int</span><span class="sxs-lookup"><span data-stu-id="95549-241">int</span></span></p></td>
<td><p><span data-ttu-id="95549-242">從會話 SIP 標頭捕獲的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="95549-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="95549-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-244">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-245">會話的內容類型。</span><span class="sxs-lookup"><span data-stu-id="95549-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="95549-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-247">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-248">捕獲會話資料的前端伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="95549-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-249"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="95549-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-250">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-251">捕獲會話資料之池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="95549-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="95549-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-253">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-254">參與會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="95549-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-255"><strong>關</strong></span><span class="sxs-lookup"><span data-stu-id="95549-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-256">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-257">參與會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="95549-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="95549-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-259">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="95549-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95549-260">參與會話之使用者所使用的邊緣伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="95549-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95549-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="95549-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-262">Smallint</span><span class="sxs-lookup"><span data-stu-id="95549-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="95549-263">指出參與會話之使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="95549-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="95549-264">允許下列屬性定義：</span><span class="sxs-lookup"><span data-stu-id="95549-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="95549-265">0x01-與桌面電話整合</span><span class="sxs-lookup"><span data-stu-id="95549-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95549-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="95549-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="95549-267">Smallint</span><span class="sxs-lookup"><span data-stu-id="95549-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="95549-268">指出通話屬性。</span><span class="sxs-lookup"><span data-stu-id="95549-268">Indicates the call attributes.</span></span> <span data-ttu-id="95549-269">允許下列屬性定義：</span><span class="sxs-lookup"><span data-stu-id="95549-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="95549-270">0x01-重試 Session0</span><span class="sxs-lookup"><span data-stu-id="95549-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="95549-271">x02-代表回應群組發出的代理通話</span><span class="sxs-lookup"><span data-stu-id="95549-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

