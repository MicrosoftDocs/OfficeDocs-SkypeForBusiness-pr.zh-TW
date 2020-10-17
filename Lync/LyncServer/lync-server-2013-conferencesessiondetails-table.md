---
title: Lync Server 2013： ConferenceSessionDetails 表格
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
ms.openlocfilehash: 57d8e3cb0a79c8ce6a6c1c51891fbad265f045de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529200"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="5b099-102">Lync Server 2013 中的 ConferenceSessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="5b099-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b099-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5b099-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5b099-104">每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。</span><span class="sxs-lookup"><span data-stu-id="5b099-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b099-105">欄</span><span class="sxs-lookup"><span data-stu-id="5b099-105">Column</span></span></th>
<th><span data-ttu-id="5b099-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="5b099-106">Data Type</span></span></th>
<th><span data-ttu-id="5b099-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="5b099-107">Key/Index</span></span></th>
<th><span data-ttu-id="5b099-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="5b099-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b099-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="5b099-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="5b099-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="5b099-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-112">會話要求的時間;與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議會話。</span><span class="sxs-lookup"><span data-stu-id="5b099-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="5b099-113">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-115">int</span><span class="sxs-lookup"><span data-stu-id="5b099-115">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-116">主要，外部</span><span class="sxs-lookup"><span data-stu-id="5b099-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-117">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-117">ID number to identify the session.</span></span> <span data-ttu-id="5b099-118">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議會話。</span><span class="sxs-lookup"><span data-stu-id="5b099-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="5b099-119">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-121">int</span><span class="sxs-lookup"><span data-stu-id="5b099-121">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-123">與此會話相關的聚焦會議 URI。</span><span class="sxs-lookup"><span data-stu-id="5b099-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="5b099-124">如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5b099-125">此 URI 是以焦點為基礎的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="5b099-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-127">唯一</span><span class="sxs-lookup"><span data-stu-id="5b099-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-128">可區分週期性會議的執行個體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="5b099-129">每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="5b099-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="5b099-130">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5b099-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-132">int</span><span class="sxs-lookup"><span data-stu-id="5b099-132">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-133">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-134">與此會話相關的會議服務器會議 URI。</span><span class="sxs-lookup"><span data-stu-id="5b099-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="5b099-135">如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5b099-136">此 URI 是以會議服務器為基礎的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="5b099-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="5b099-137">若為 Focus 會議會話，此欄將會是 null。</span><span class="sxs-lookup"><span data-stu-id="5b099-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-139">int</span><span class="sxs-lookup"><span data-stu-id="5b099-139">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-140">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-141">會議會話中某位使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-141">ID of one user in the conference session.</span></span> <span data-ttu-id="5b099-142">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-144">唯一</span><span class="sxs-lookup"><span data-stu-id="5b099-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-145">識別端點實例的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5b099-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="5b099-146">例如，如果一個使用者使用相同的帳戶登入不同的機器，則每一部機器都會有不同的端點識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-148">int</span><span class="sxs-lookup"><span data-stu-id="5b099-148">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-149">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-150">指出來電者所代表之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="5b099-151">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-153">int</span><span class="sxs-lookup"><span data-stu-id="5b099-153">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-154">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-155">轉接此通話之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="5b099-156">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-158">int</span><span class="sxs-lookup"><span data-stu-id="5b099-158">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-159">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-160">會議使用者使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="5b099-160">Client version used by the conference user.</span></span> <span data-ttu-id="5b099-161">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-163">int</span><span class="sxs-lookup"><span data-stu-id="5b099-163">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-164">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-165">會議服務器所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="5b099-165">Client version used by the conference server.</span></span> <span data-ttu-id="5b099-166">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-168">datetime</span><span class="sxs-lookup"><span data-stu-id="5b099-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b099-169">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-170">用來識別目前工作階段所取代之對話的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="5b099-171">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-173">int</span><span class="sxs-lookup"><span data-stu-id="5b099-173">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-174">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-175">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-175">ID number to identify the session.</span></span> <span data-ttu-id="5b099-176">其會與 <strong>ReplacesDialogIdTime</strong> 搭配使用，專門用於識別此工作階段所取代的工作階段。</span><span class="sxs-lookup"><span data-stu-id="5b099-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="5b099-177">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-179">位</span><span class="sxs-lookup"><span data-stu-id="5b099-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-180">會指出會議服務器是否已啟動會話。</span><span class="sxs-lookup"><span data-stu-id="5b099-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-182">位</span><span class="sxs-lookup"><span data-stu-id="5b099-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-183">表示會話是否由會議服務器結束。</span><span class="sxs-lookup"><span data-stu-id="5b099-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-185">位</span><span class="sxs-lookup"><span data-stu-id="5b099-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-186">使用者是否從內部登入。</span><span class="sxs-lookup"><span data-stu-id="5b099-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-188">int</span><span class="sxs-lookup"><span data-stu-id="5b099-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-189">會話初始通訊協定 (SIP) 回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="5b099-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="5b099-190">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="5b099-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5b099-191">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="5b099-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-193">int</span><span class="sxs-lookup"><span data-stu-id="5b099-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-194">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-196">int</span><span class="sxs-lookup"><span data-stu-id="5b099-196">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-197">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-198">用於此工作階段之前端伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="5b099-199">如需詳細資訊，請參閱 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-201">int</span><span class="sxs-lookup"><span data-stu-id="5b099-201">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-202">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-203">擷取工作階段所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b099-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="5b099-204">如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-206">int</span><span class="sxs-lookup"><span data-stu-id="5b099-206">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-207">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-208">通話所使用的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b099-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="5b099-209">如需詳細資訊，請參閱 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-211">int</span><span class="sxs-lookup"><span data-stu-id="5b099-211">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-212">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-213">通話所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="5b099-213">The gateway the call is using.</span></span> <span data-ttu-id="5b099-214">如需詳細資訊，請參閱 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-216">int</span><span class="sxs-lookup"><span data-stu-id="5b099-216">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-217">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-218">通話所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="5b099-218">The Edge Server the call is using.</span></span> <span data-ttu-id="5b099-219">如需詳細資訊，請參閱 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-221">int</span><span class="sxs-lookup"><span data-stu-id="5b099-221">int</span></span></p></td>
<td><p><span data-ttu-id="5b099-222">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-223">工作階段中所使用的內容類型。</span><span class="sxs-lookup"><span data-stu-id="5b099-223">Content type used in the session.</span></span> <span data-ttu-id="5b099-224">如需詳細資訊，請參閱 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5b099-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-226">datetime</span><span class="sxs-lookup"><span data-stu-id="5b099-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-227">第一個 INVITE 要求的時間。</span><span class="sxs-lookup"><span data-stu-id="5b099-227">The time of the first INVITE request.</span></span> <span data-ttu-id="5b099-228">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="5b099-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5b099-229">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="5b099-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-231">datetime</span><span class="sxs-lookup"><span data-stu-id="5b099-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-232">第一次 SIP 回應的時間。</span><span class="sxs-lookup"><span data-stu-id="5b099-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="5b099-233">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="5b099-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5b099-234">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="5b099-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-236">datetime</span><span class="sxs-lookup"><span data-stu-id="5b099-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-237">會話結束的時間。</span><span class="sxs-lookup"><span data-stu-id="5b099-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-239">Tinyint</span><span class="sxs-lookup"><span data-stu-id="5b099-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5b099-240">Foreign</span><span class="sxs-lookup"><span data-stu-id="5b099-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b099-241"><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 的 UriTypes 表格中</a>包含 MCU URI 類型值。</span><span class="sxs-lookup"><span data-stu-id="5b099-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="5b099-242">此欄位是用來改善查詢效能。</span><span class="sxs-lookup"><span data-stu-id="5b099-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="5b099-243">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5b099-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b099-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-245">Smallint</span><span class="sxs-lookup"><span data-stu-id="5b099-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-246">會指出使用者屬性的位組。</span><span class="sxs-lookup"><span data-stu-id="5b099-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="5b099-247">下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="5b099-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b099-248">與桌面電話-1 整合</span><span class="sxs-lookup"><span data-stu-id="5b099-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b099-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5b099-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5b099-250">Smallint</span><span class="sxs-lookup"><span data-stu-id="5b099-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b099-p125">指出通話屬性的位元設定。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="5b099-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b099-253">重新嘗試的會話-1</span><span class="sxs-lookup"><span data-stu-id="5b099-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5b099-254">\* 對於大部分的會話，SessionIdSeq 的值會是1。</span><span class="sxs-lookup"><span data-stu-id="5b099-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="5b099-255">如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="5b099-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

