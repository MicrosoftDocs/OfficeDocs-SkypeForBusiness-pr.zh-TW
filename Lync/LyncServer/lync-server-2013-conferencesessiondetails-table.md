---
title: 'Lync Server 2013: ConferenceSessionDetails 表格'
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
ms.openlocfilehash: 3e991f6240d9c21815299a3ef169c5824cf5ef3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="9d54b-102">Lync Server 2013 中的 ConferenceSessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="9d54b-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d54b-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="9d54b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9d54b-104">每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。</span><span class="sxs-lookup"><span data-stu-id="9d54b-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d54b-105">欄</span><span class="sxs-lookup"><span data-stu-id="9d54b-105">Column</span></span></th>
<th><span data-ttu-id="9d54b-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="9d54b-106">Data Type</span></span></th>
<th><span data-ttu-id="9d54b-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="9d54b-107">Key/Index</span></span></th>
<th><span data-ttu-id="9d54b-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="9d54b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="9d54b-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="9d54b-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="9d54b-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-112">工作階段要求;<strong>SessionIdSeq</strong>搭配使用來唯一地識別會議工作階段。</span><span class="sxs-lookup"><span data-stu-id="9d54b-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="9d54b-113"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="9d54b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-115">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-115">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-116">主要，外部</span><span class="sxs-lookup"><span data-stu-id="9d54b-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-117">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-117">ID number to identify the session.</span></span> <span data-ttu-id="9d54b-118">搭配<strong>SessionIdTime</strong>用來唯一地識別會議工作階段。</span><span class="sxs-lookup"><span data-stu-id="9d54b-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="9d54b-119"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="9d54b-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-121">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-121">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-123">此工作階段相關焦點會議 URI。</span><span class="sxs-lookup"><span data-stu-id="9d54b-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="9d54b-124">請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="9d54b-125">此 URI 是基於 Focus 的會議 URI。</span><span class="sxs-lookup"><span data-stu-id="9d54b-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-127">唯一</span><span class="sxs-lookup"><span data-stu-id="9d54b-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-128">可區分週期性會議的執行個體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="9d54b-129">每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="9d54b-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="9d54b-130">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="9d54b-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-132">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-132">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-133">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-134">會議伺服器會議 URI 相關此工作階段。</span><span class="sxs-lookup"><span data-stu-id="9d54b-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="9d54b-135">請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="9d54b-136">此 URI 是會議伺服器型會議 URI。</span><span class="sxs-lookup"><span data-stu-id="9d54b-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="9d54b-137">焦點會議工作階段，此欄都是 null。</span><span class="sxs-lookup"><span data-stu-id="9d54b-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-139">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-139">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-140">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-141">在會議工作階段中的一位使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-141">ID of one user in the conference session.</span></span> <span data-ttu-id="9d54b-142">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="9d54b-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-144">唯一</span><span class="sxs-lookup"><span data-stu-id="9d54b-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-145">GUID，以識別端點的執行個體。</span><span class="sxs-lookup"><span data-stu-id="9d54b-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="9d54b-146">例如，如果不同的電腦，以相同的帳戶登入一位使用者，然後每一部機器會有不同的端點識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-148">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-148">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-149">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-150">指出來電者所代表之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="9d54b-151">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="9d54b-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-153">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-153">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-154">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-155">轉接此通話之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="9d54b-156">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="9d54b-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-158">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-158">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-159">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-160">會議使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="9d54b-160">Client version used by the conference user.</span></span> <span data-ttu-id="9d54b-161">請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-163">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-163">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-164">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-165">會議伺服器所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="9d54b-165">Client version used by the conference server.</span></span> <span data-ttu-id="9d54b-166">請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-168">datetime</span><span class="sxs-lookup"><span data-stu-id="9d54b-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="9d54b-169">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-170">用來識別目前工作階段所取代之對話的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="9d54b-171"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="9d54b-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-173">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-173">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-174">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-175">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-175">ID number to identify the session.</span></span> <span data-ttu-id="9d54b-176">其會與 <strong>ReplacesDialogIdTime</strong> 搭配使用，專門用於識別此工作階段所取代的工作階段。</span><span class="sxs-lookup"><span data-stu-id="9d54b-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="9d54b-177"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="9d54b-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-179">位元</span><span class="sxs-lookup"><span data-stu-id="9d54b-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-180">會指出由會議伺服器是否啟動工作階段。</span><span class="sxs-lookup"><span data-stu-id="9d54b-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-182">位元</span><span class="sxs-lookup"><span data-stu-id="9d54b-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-183">會指出是否工作階段結束透過會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d54b-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-185">位元</span><span class="sxs-lookup"><span data-stu-id="9d54b-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-186">是否使用者登入從內部或不。</span><span class="sxs-lookup"><span data-stu-id="9d54b-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-188">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-189">工作階段初始通訊協定 (SIP) 工作階段邀請的回應碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="9d54b-190">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="9d54b-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9d54b-191">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="9d54b-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-193">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-194">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-196">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-196">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-197">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-198">用於此工作階段之前端伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="9d54b-199">請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-201">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-201">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-202">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-203">擷取工作階段所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9d54b-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="9d54b-204">請參閱如需詳細資訊，<a href="lync-server-2013-pools-table.md">在 Lync Server 2013 中的集區資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="9d54b-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-206">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-206">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-207">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-208">中繼伺服器通話使用。</span><span class="sxs-lookup"><span data-stu-id="9d54b-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="9d54b-209">請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-211">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-211">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-212">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-213">使用通話的閘道。</span><span class="sxs-lookup"><span data-stu-id="9d54b-213">The gateway the call is using.</span></span> <span data-ttu-id="9d54b-214">請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-216">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-216">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-217">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-218">使用 Edge Server 通話。</span><span class="sxs-lookup"><span data-stu-id="9d54b-218">The Edge Server the call is using.</span></span> <span data-ttu-id="9d54b-219">請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-221">int</span><span class="sxs-lookup"><span data-stu-id="9d54b-221">int</span></span></p></td>
<td><p><span data-ttu-id="9d54b-222">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-223">工作階段中所使用的內容類型。</span><span class="sxs-lookup"><span data-stu-id="9d54b-223">Content type used in the session.</span></span> <span data-ttu-id="9d54b-224">請參閱<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9d54b-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-226">datetime</span><span class="sxs-lookup"><span data-stu-id="9d54b-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-227">第一個 INVITE 要求的時間。</span><span class="sxs-lookup"><span data-stu-id="9d54b-227">The time of the first INVITE request.</span></span> <span data-ttu-id="9d54b-228">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="9d54b-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9d54b-229">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="9d54b-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-231">datetime</span><span class="sxs-lookup"><span data-stu-id="9d54b-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-232">第一個 SIP 回應的時間。</span><span class="sxs-lookup"><span data-stu-id="9d54b-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="9d54b-233">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="9d54b-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9d54b-234">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="9d54b-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-236">datetime</span><span class="sxs-lookup"><span data-stu-id="9d54b-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-237">工作階段結束時的時間。</span><span class="sxs-lookup"><span data-stu-id="9d54b-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="9d54b-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9d54b-240">Foreign</span><span class="sxs-lookup"><span data-stu-id="9d54b-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d54b-241">包含<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>MCU 的 URI 類型值。</span><span class="sxs-lookup"><span data-stu-id="9d54b-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="9d54b-242">提升查詢效能會使用此欄位。</span><span class="sxs-lookup"><span data-stu-id="9d54b-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="9d54b-243">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="9d54b-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d54b-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-245">smallint</span><span class="sxs-lookup"><span data-stu-id="9d54b-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-246">這表示使用者屬性的位元。</span><span class="sxs-lookup"><span data-stu-id="9d54b-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="9d54b-247">下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="9d54b-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d54b-248">整合與桌上電話-1</span><span class="sxs-lookup"><span data-stu-id="9d54b-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d54b-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9d54b-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9d54b-250">smallint</span><span class="sxs-lookup"><span data-stu-id="9d54b-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d54b-p125">指出通話屬性的位元設定。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="9d54b-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d54b-253">重試工作階段-1</span><span class="sxs-lookup"><span data-stu-id="9d54b-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9d54b-254">\*對於大多數的工作階段，SessionIdSeq 會有 1 的值。</span><span class="sxs-lookup"><span data-stu-id="9d54b-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="9d54b-255">如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="9d54b-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

