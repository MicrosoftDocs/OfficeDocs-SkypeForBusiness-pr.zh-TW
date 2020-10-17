---
title: Lync Server 2013： McuJoinsAndLeaves view
description: Lync Server 2013： McuJoinsAndLeaves view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556489"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="0049d-103">Lync Server 2013 中的 McuJoinsAndLeaves 視圖</span><span class="sxs-lookup"><span data-stu-id="0049d-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0049d-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0049d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0049d-105">McuJoinsAndLeaves 檢視會儲存使用者加入或離開一個會議伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0049d-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="0049d-106">這個檢視中的每筆記錄都包含一組使用者加入或離開會議伺服器的通話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0049d-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="0049d-107">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0049d-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0049d-108">欄</span><span class="sxs-lookup"><span data-stu-id="0049d-108">Column</span></span></th>
<th><span data-ttu-id="0049d-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="0049d-109">Data Type</span></span></th>
<th><span data-ttu-id="0049d-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="0049d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0049d-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0049d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="0049d-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="0049d-113">Time of conference instance.</span></span> <span data-ttu-id="0049d-114">會與 SessionIdSeq 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="0049d-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="0049d-115">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="0049d-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-117">int</span><span class="sxs-lookup"><span data-stu-id="0049d-117">int</span></span></p></td>
<td><p><span data-ttu-id="0049d-118">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="0049d-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="0049d-119">會與 SessionIDTime 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="0049d-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="0049d-120">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="0049d-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-122">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="0049d-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0049d-123">使用者連線至會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="0049d-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-124"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-125">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="0049d-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0049d-126">使用者連線至會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="0049d-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="0049d-127">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0049d-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-129">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="0049d-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0049d-130">擷取會議伺服器加入/離開資訊之使用者的 URI 。</span><span class="sxs-lookup"><span data-stu-id="0049d-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-131"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-132">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="0049d-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0049d-133">擷取會議伺服器加入/離開資訊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="0049d-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="0049d-134">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0049d-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-135"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-136">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="0049d-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0049d-137">擷取會議伺服器加入/離開資訊之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="0049d-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="0049d-138">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="0049d-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-140">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="0049d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0049d-141">擷取會議伺服器加入/離開資訊之使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="0049d-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-143">int</span><span class="sxs-lookup"><span data-stu-id="0049d-143">int</span></span></p></td>
<td><p><span data-ttu-id="0049d-144">擷取會議伺服器加入/離開資訊之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="0049d-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="0049d-145">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0049d-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-147">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="0049d-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0049d-148">擷取會議伺服器加入/離開資訊之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="0049d-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-150">int</span><span class="sxs-lookup"><span data-stu-id="0049d-150">int</span></span></p></td>
<td><p><span data-ttu-id="0049d-151">唯一識別使用者同時登入多個裝置的使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="0049d-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-153">位</span><span class="sxs-lookup"><span data-stu-id="0049d-153">bit</span></span></p></td>
<td><p><span data-ttu-id="0049d-154">代表使用者是否為內部使用者的位元。</span><span class="sxs-lookup"><span data-stu-id="0049d-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-156">datetime</span><span class="sxs-lookup"><span data-stu-id="0049d-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="0049d-157">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="0049d-157">Time of session request.</span></span> <span data-ttu-id="0049d-158">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="0049d-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="0049d-159">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0049d-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-161">int</span><span class="sxs-lookup"><span data-stu-id="0049d-161">int</span></span></p></td>
<td><p><span data-ttu-id="0049d-162">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="0049d-162">ID number to identify the session.</span></span> <span data-ttu-id="0049d-163">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="0049d-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="0049d-164">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0049d-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-166">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="0049d-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="0049d-p110">工作階段的 SIP 對話方塊識別碼，格式為：dialog;from-tag;to-tag。</span><span class="sxs-lookup"><span data-stu-id="0049d-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0049d-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-170">datetime</span><span class="sxs-lookup"><span data-stu-id="0049d-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="0049d-171">使用者加入會議伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="0049d-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0049d-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="0049d-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0049d-173">datetime</span><span class="sxs-lookup"><span data-stu-id="0049d-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="0049d-174">使用者離開會議伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="0049d-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

