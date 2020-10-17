---
title: Lync Server 2013： ConferenceSessionDetails 表格
description: Lync Server 2013： ConferenceSessionDetails 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566779"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="d3e43-103">Lync Server 2013 中的 ConferenceSessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="d3e43-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3e43-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d3e43-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d3e43-105">每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。</span><span class="sxs-lookup"><span data-stu-id="d3e43-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3e43-106">欄</span><span class="sxs-lookup"><span data-stu-id="d3e43-106">Column</span></span></th>
<th><span data-ttu-id="d3e43-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="d3e43-107">Data Type</span></span></th>
<th><span data-ttu-id="d3e43-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="d3e43-108">Key/Index</span></span></th>
<th><span data-ttu-id="d3e43-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d3e43-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-111">Datetime</span><span class="sxs-lookup"><span data-stu-id="d3e43-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="d3e43-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="d3e43-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-113">會話要求的時間;與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議會話。</span><span class="sxs-lookup"><span data-stu-id="d3e43-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="d3e43-114">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-116">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-116">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="d3e43-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-118">ID number to identify the session.</span></span> <span data-ttu-id="d3e43-119">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議會話。</span><span class="sxs-lookup"><span data-stu-id="d3e43-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="d3e43-120">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-122">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-122">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-124">與此會話相關的聚焦會議 URI。</span><span class="sxs-lookup"><span data-stu-id="d3e43-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="d3e43-125">如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="d3e43-126">此 URI 是以焦點為基礎的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="d3e43-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-128">唯一</span><span class="sxs-lookup"><span data-stu-id="d3e43-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-129">可區分週期性會議的執行個體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="d3e43-130">每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="d3e43-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="d3e43-131">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d3e43-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-133">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-133">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-134">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-135">與此會話相關的會議服務器會議 URI。</span><span class="sxs-lookup"><span data-stu-id="d3e43-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="d3e43-136">如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="d3e43-137">此 URI 是以會議服務器為基礎的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="d3e43-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="d3e43-138">若為 Focus 會議會話，此欄將會是 null。</span><span class="sxs-lookup"><span data-stu-id="d3e43-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-140">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-140">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-141">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-142">會議會話中某位使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-142">ID of one user in the conference session.</span></span> <span data-ttu-id="d3e43-143">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-145">唯一</span><span class="sxs-lookup"><span data-stu-id="d3e43-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-146">識別端點實例的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d3e43-146">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="d3e43-147">例如，如果一個使用者使用相同的帳戶登入不同的機器，則每一部機器都會有不同的端點識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-147">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-149">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-149">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-150">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-151">指出來電者所代表之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="d3e43-152">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-154">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-154">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-155">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-156">轉接此通話之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="d3e43-157">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-159">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-159">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-160">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-161">會議使用者使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="d3e43-161">Client version used by the conference user.</span></span> <span data-ttu-id="d3e43-162">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-164">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-164">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-165">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-166">會議服務器所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="d3e43-166">Client version used by the conference server.</span></span> <span data-ttu-id="d3e43-167">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-169">datetime</span><span class="sxs-lookup"><span data-stu-id="d3e43-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3e43-170">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-171">用來識別目前工作階段所取代之對話的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="d3e43-172">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-174">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-174">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-175">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-176">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-176">ID number to identify the session.</span></span> <span data-ttu-id="d3e43-177">其會與 <strong>ReplacesDialogIdTime</strong> 搭配使用，專門用於識別此工作階段所取代的工作階段。</span><span class="sxs-lookup"><span data-stu-id="d3e43-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="d3e43-178">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-180">位</span><span class="sxs-lookup"><span data-stu-id="d3e43-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-181">會指出會議服務器是否已啟動會話。</span><span class="sxs-lookup"><span data-stu-id="d3e43-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-183">位</span><span class="sxs-lookup"><span data-stu-id="d3e43-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-184">表示會話是否由會議服務器結束。</span><span class="sxs-lookup"><span data-stu-id="d3e43-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-186">位</span><span class="sxs-lookup"><span data-stu-id="d3e43-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-187">使用者是否從內部登入。</span><span class="sxs-lookup"><span data-stu-id="d3e43-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-189">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-190">會話初始通訊協定 (SIP) 回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="d3e43-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="d3e43-191">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="d3e43-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d3e43-192">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="d3e43-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-193"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-194">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-195">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-197">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-197">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-198">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-199">用於此工作階段之前端伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="d3e43-200">如需詳細資訊，請參閱 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-201"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-202">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-202">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-203">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-204">擷取工作階段所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d3e43-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="d3e43-205">如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-207">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-207">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-208">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-209">通話所使用的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="d3e43-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="d3e43-210">如需詳細資訊，請參閱 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-211"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-212">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-212">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-213">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-214">通話所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="d3e43-214">The gateway the call is using.</span></span> <span data-ttu-id="d3e43-215">如需詳細資訊，請參閱 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-217">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-217">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-218">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-219">通話所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="d3e43-219">The Edge Server the call is using.</span></span> <span data-ttu-id="d3e43-220">如需詳細資訊，請參閱 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-222">int</span><span class="sxs-lookup"><span data-stu-id="d3e43-222">int</span></span></p></td>
<td><p><span data-ttu-id="d3e43-223">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-224">工作階段中所使用的內容類型。</span><span class="sxs-lookup"><span data-stu-id="d3e43-224">Content type used in the session.</span></span> <span data-ttu-id="d3e43-225">如需詳細資訊，請參閱 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d3e43-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-226"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-227">datetime</span><span class="sxs-lookup"><span data-stu-id="d3e43-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-228">第一個 INVITE 要求的時間。</span><span class="sxs-lookup"><span data-stu-id="d3e43-228">The time of the first INVITE request.</span></span> <span data-ttu-id="d3e43-229">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="d3e43-229">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d3e43-230">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="d3e43-230">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-232">datetime</span><span class="sxs-lookup"><span data-stu-id="d3e43-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-233">第一次 SIP 回應的時間。</span><span class="sxs-lookup"><span data-stu-id="d3e43-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="d3e43-234">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="d3e43-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d3e43-235">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="d3e43-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-237">datetime</span><span class="sxs-lookup"><span data-stu-id="d3e43-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-238">會話結束的時間。</span><span class="sxs-lookup"><span data-stu-id="d3e43-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-240">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d3e43-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d3e43-241">Foreign</span><span class="sxs-lookup"><span data-stu-id="d3e43-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e43-242"><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 的 UriTypes 表格中</a>包含 MCU URI 類型值。</span><span class="sxs-lookup"><span data-stu-id="d3e43-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="d3e43-243">此欄位是用來改善查詢效能。</span><span class="sxs-lookup"><span data-stu-id="d3e43-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="d3e43-244">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d3e43-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e43-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-246">Smallint</span><span class="sxs-lookup"><span data-stu-id="d3e43-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-247">會指出使用者屬性的位組。</span><span class="sxs-lookup"><span data-stu-id="d3e43-247">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="d3e43-248">下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="d3e43-248">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="d3e43-249">與桌面電話-1 整合</span><span class="sxs-lookup"><span data-stu-id="d3e43-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e43-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d3e43-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e43-251">Smallint</span><span class="sxs-lookup"><span data-stu-id="d3e43-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e43-p125">指出通話屬性的位元設定。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="d3e43-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="d3e43-254">重新嘗試的會話-1</span><span class="sxs-lookup"><span data-stu-id="d3e43-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d3e43-255">\* 對於大部分的會話，SessionIdSeq 的值會是1。</span><span class="sxs-lookup"><span data-stu-id="d3e43-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="d3e43-256">如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="d3e43-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

