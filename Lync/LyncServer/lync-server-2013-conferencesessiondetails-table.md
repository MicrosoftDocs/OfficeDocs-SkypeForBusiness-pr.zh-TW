---
title: Lync Server 2013：ConferenceSessionDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="10353-102">Lync Server 2013 中的 ConferenceSessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="10353-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10353-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="10353-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="10353-104">每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。</span><span class="sxs-lookup"><span data-stu-id="10353-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10353-105">左欄</span><span class="sxs-lookup"><span data-stu-id="10353-105">Column</span></span></th>
<th><span data-ttu-id="10353-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="10353-106">Data Type</span></span></th>
<th><span data-ttu-id="10353-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="10353-107">Key/Index</span></span></th>
<th><span data-ttu-id="10353-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="10353-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10353-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="10353-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="10353-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="10353-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="10353-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-112">會話要求的時間;與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會議會話。</span><span class="sxs-lookup"><span data-stu-id="10353-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="10353-113">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="10353-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-115">int</span><span class="sxs-lookup"><span data-stu-id="10353-115">int</span></span></p></td>
<td><p><span data-ttu-id="10353-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="10353-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-117">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="10353-117">ID number to identify the session.</span></span> <span data-ttu-id="10353-118">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會議會話。</span><span class="sxs-lookup"><span data-stu-id="10353-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="10353-119">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-121">int</span><span class="sxs-lookup"><span data-stu-id="10353-121">int</span></span></p></td>
<td><p><span data-ttu-id="10353-122">外</span><span class="sxs-lookup"><span data-stu-id="10353-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-123">與此會話相關的焦點會議 URI。</span><span class="sxs-lookup"><span data-stu-id="10353-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="10353-124">如需詳細資訊，請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中</a>的 [ConferenceUris] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="10353-125">此 URI 是以焦點為基礎的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="10353-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="10353-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="10353-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-128">區分週期性會議實例的識別碼。</span><span class="sxs-lookup"><span data-stu-id="10353-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="10353-129">每個週期性會議實例都有相同的 ConferenceURI，但有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="10353-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="10353-130">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="10353-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-132">int</span><span class="sxs-lookup"><span data-stu-id="10353-132">int</span></span></p></td>
<td><p><span data-ttu-id="10353-133">外</span><span class="sxs-lookup"><span data-stu-id="10353-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-134">與此會話相關的會議服務器會議 URI。</span><span class="sxs-lookup"><span data-stu-id="10353-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="10353-135">如需詳細資訊，請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中</a>的 [ConferenceUris] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="10353-136">此 URI 是會議服務器的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="10353-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="10353-137">針對焦點會議會話，此欄會是 null。</span><span class="sxs-lookup"><span data-stu-id="10353-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-139">int</span><span class="sxs-lookup"><span data-stu-id="10353-139">int</span></span></p></td>
<td><p><span data-ttu-id="10353-140">外</span><span class="sxs-lookup"><span data-stu-id="10353-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-141">在會議會話中，有一個使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="10353-141">ID of one user in the conference session.</span></span> <span data-ttu-id="10353-142">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="10353-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-145">識別端點實例的 GUID。</span><span class="sxs-lookup"><span data-stu-id="10353-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="10353-146">例如，如果某個使用者使用相同的帳戶登入不同的電腦，則每個電腦將會有不同的端點 ID。</span><span class="sxs-lookup"><span data-stu-id="10353-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-148">int</span><span class="sxs-lookup"><span data-stu-id="10353-148">int</span></span></p></td>
<td><p><span data-ttu-id="10353-149">外</span><span class="sxs-lookup"><span data-stu-id="10353-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-150">表示呼叫者代表者的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="10353-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="10353-151">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="10353-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-153">int</span><span class="sxs-lookup"><span data-stu-id="10353-153">int</span></span></p></td>
<td><p><span data-ttu-id="10353-154">外</span><span class="sxs-lookup"><span data-stu-id="10353-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-155">呼叫者的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="10353-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="10353-156">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-158">int</span><span class="sxs-lookup"><span data-stu-id="10353-158">int</span></span></p></td>
<td><p><span data-ttu-id="10353-159">外</span><span class="sxs-lookup"><span data-stu-id="10353-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-160">會議使用者使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="10353-160">Client version used by the conference user.</span></span> <span data-ttu-id="10353-161">如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-163">int</span><span class="sxs-lookup"><span data-stu-id="10353-163">int</span></span></p></td>
<td><p><span data-ttu-id="10353-164">外</span><span class="sxs-lookup"><span data-stu-id="10353-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-165">會議服務器所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="10353-165">Client version used by the conference server.</span></span> <span data-ttu-id="10353-166">如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="10353-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-168">datetime</span><span class="sxs-lookup"><span data-stu-id="10353-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="10353-169">外</span><span class="sxs-lookup"><span data-stu-id="10353-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-170">[識別碼] 編號，找出目前會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="10353-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="10353-171">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="10353-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-173">int</span><span class="sxs-lookup"><span data-stu-id="10353-173">int</span></span></p></td>
<td><p><span data-ttu-id="10353-174">外</span><span class="sxs-lookup"><span data-stu-id="10353-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-175">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="10353-175">ID number to identify the session.</span></span> <span data-ttu-id="10353-176">與<strong>ReplacesDialogIdTime</strong>搭配使用，可唯一識別此會話所取代的會話。</span><span class="sxs-lookup"><span data-stu-id="10353-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="10353-177">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="10353-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-179">稍微</span><span class="sxs-lookup"><span data-stu-id="10353-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-180">指示會議服務器是否已啟動會話。</span><span class="sxs-lookup"><span data-stu-id="10353-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="10353-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-182">稍微</span><span class="sxs-lookup"><span data-stu-id="10353-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-183">表示會議服務器是否已結束會話。</span><span class="sxs-lookup"><span data-stu-id="10353-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="10353-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-185">稍微</span><span class="sxs-lookup"><span data-stu-id="10353-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-186">使用者是否已從內部登入。</span><span class="sxs-lookup"><span data-stu-id="10353-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="10353-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-188">int</span><span class="sxs-lookup"><span data-stu-id="10353-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-189">會話初始通訊協定（SIP）回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="10353-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="10353-190">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="10353-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="10353-191">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="10353-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-193">int</span><span class="sxs-lookup"><span data-stu-id="10353-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-194">從 SIP 標頭捕獲的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="10353-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-196">int</span><span class="sxs-lookup"><span data-stu-id="10353-196">int</span></span></p></td>
<td><p><span data-ttu-id="10353-197">外</span><span class="sxs-lookup"><span data-stu-id="10353-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-198">此會話所用的前端伺服器 ID。</span><span class="sxs-lookup"><span data-stu-id="10353-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="10353-199">如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-201">int</span><span class="sxs-lookup"><span data-stu-id="10353-201">int</span></span></p></td>
<td><p><span data-ttu-id="10353-202">外</span><span class="sxs-lookup"><span data-stu-id="10353-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-203">捕獲會話的池 ID。</span><span class="sxs-lookup"><span data-stu-id="10353-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="10353-204">如需詳細資訊，請參閱<a href="lync-server-2013-pools-table.md">Lync Server 2013 中</a>的 [pool] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-206">int</span><span class="sxs-lookup"><span data-stu-id="10353-206">int</span></span></p></td>
<td><p><span data-ttu-id="10353-207">外</span><span class="sxs-lookup"><span data-stu-id="10353-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-208">通話使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="10353-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="10353-209">如需詳細資訊，請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中</a>的 [MediationServers] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-211">int</span><span class="sxs-lookup"><span data-stu-id="10353-211">int</span></span></p></td>
<td><p><span data-ttu-id="10353-212">外</span><span class="sxs-lookup"><span data-stu-id="10353-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-213">通話使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="10353-213">The gateway the call is using.</span></span> <span data-ttu-id="10353-214">如需詳細資訊，請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 [閘道] 資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="10353-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-216">int</span><span class="sxs-lookup"><span data-stu-id="10353-216">int</span></span></p></td>
<td><p><span data-ttu-id="10353-217">外</span><span class="sxs-lookup"><span data-stu-id="10353-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-218">通話使用的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="10353-218">The Edge Server the call is using.</span></span> <span data-ttu-id="10353-219">如需詳細資訊，請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中</a>的 [EdgeServers] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-221">int</span><span class="sxs-lookup"><span data-stu-id="10353-221">int</span></span></p></td>
<td><p><span data-ttu-id="10353-222">外</span><span class="sxs-lookup"><span data-stu-id="10353-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-223">會話中使用的內容類型。</span><span class="sxs-lookup"><span data-stu-id="10353-223">Content type used in the session.</span></span> <span data-ttu-id="10353-224">如需詳細資訊，請參閱<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中</a>的 [主控] 資料表。</span><span class="sxs-lookup"><span data-stu-id="10353-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="10353-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-226">datetime</span><span class="sxs-lookup"><span data-stu-id="10353-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-227">第一次邀請要求的時間。</span><span class="sxs-lookup"><span data-stu-id="10353-227">The time of the first INVITE request.</span></span> <span data-ttu-id="10353-228">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="10353-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="10353-229">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="10353-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="10353-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-231">datetime</span><span class="sxs-lookup"><span data-stu-id="10353-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-232">第一次 SIP 回應的時間。</span><span class="sxs-lookup"><span data-stu-id="10353-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="10353-233">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="10353-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="10353-234">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="10353-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="10353-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-236">datetime</span><span class="sxs-lookup"><span data-stu-id="10353-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-237">會話結束的時間。</span><span class="sxs-lookup"><span data-stu-id="10353-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="10353-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-239">Tinyint</span><span class="sxs-lookup"><span data-stu-id="10353-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="10353-240">外</span><span class="sxs-lookup"><span data-stu-id="10353-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="10353-241"><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 的 UriTypes 資料表中</a>包含 MCU URI 類型值。</span><span class="sxs-lookup"><span data-stu-id="10353-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="10353-242">此欄位可用來改善查詢效能。</span><span class="sxs-lookup"><span data-stu-id="10353-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="10353-243">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="10353-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10353-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="10353-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-245">Smallint</span><span class="sxs-lookup"><span data-stu-id="10353-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-246">指示使用者屬性的位組。</span><span class="sxs-lookup"><span data-stu-id="10353-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="10353-247">下列屬性定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="10353-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="10353-248">與桌面手機整合-1</span><span class="sxs-lookup"><span data-stu-id="10353-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10353-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="10353-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="10353-250">Smallint</span><span class="sxs-lookup"><span data-stu-id="10353-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10353-251">指明通話屬性的位組。</span><span class="sxs-lookup"><span data-stu-id="10353-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="10353-252">下列屬性定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="10353-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="10353-253">重試會話-1</span><span class="sxs-lookup"><span data-stu-id="10353-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="10353-254">\*在大部分的會話中，SessionIdSeq 將會有1的值。</span><span class="sxs-lookup"><span data-stu-id="10353-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="10353-255">如果多個會話的開始時間完全相同，則 SessionIdSeq 會是1，另一個會是2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="10353-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

