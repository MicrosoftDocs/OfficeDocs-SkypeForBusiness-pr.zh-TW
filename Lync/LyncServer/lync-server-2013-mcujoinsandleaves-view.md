---
title: Lync Server 2013： McuJoinsAndLeaves view
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
ms.openlocfilehash: 329396549a02a354939b166c8785b875faee2f78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524720"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="3aa2b-102">Lync Server 2013 中的 McuJoinsAndLeaves 視圖</span><span class="sxs-lookup"><span data-stu-id="3aa2b-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aa2b-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3aa2b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3aa2b-104">McuJoinsAndLeaves 檢視會儲存使用者加入或離開一個會議伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="3aa2b-105">這個檢視中的每筆記錄都包含一組使用者加入或離開會議伺服器的通話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="3aa2b-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3aa2b-107">欄</span><span class="sxs-lookup"><span data-stu-id="3aa2b-107">Column</span></span></th>
<th><span data-ttu-id="3aa2b-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="3aa2b-108">Data Type</span></span></th>
<th><span data-ttu-id="3aa2b-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="3aa2b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-112">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-112">Time of conference instance.</span></span> <span data-ttu-id="3aa2b-113">會與 SessionIdSeq 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="3aa2b-114">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-116">int</span><span class="sxs-lookup"><span data-stu-id="3aa2b-116">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-117">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="3aa2b-118">會與 SessionIDTime 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="3aa2b-119">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-121">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-122">使用者連線至會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-124">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-125">使用者連線至會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="3aa2b-126">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-128">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-129">擷取會議伺服器加入/離開資訊之使用者的 URI 。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-131">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-132">擷取會議伺服器加入/離開資訊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="3aa2b-133">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-135">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-136">擷取會議伺服器加入/離開資訊之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="3aa2b-137">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-139">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-140">擷取會議伺服器加入/離開資訊之使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-142">int</span><span class="sxs-lookup"><span data-stu-id="3aa2b-142">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-143">擷取會議伺服器加入/離開資訊之使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="3aa2b-144">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-146">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-147">擷取會議伺服器加入/離開資訊之使用者所使用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-149">int</span><span class="sxs-lookup"><span data-stu-id="3aa2b-149">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-150">唯一識別使用者同時登入多個裝置的使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-152">位</span><span class="sxs-lookup"><span data-stu-id="3aa2b-152">bit</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-153">代表使用者是否為內部使用者的位元。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-155">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2b-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-156">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-156">Time of session request.</span></span> <span data-ttu-id="3aa2b-157">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="3aa2b-158">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-160">int</span><span class="sxs-lookup"><span data-stu-id="3aa2b-160">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-161">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-161">ID number to identify the session.</span></span> <span data-ttu-id="3aa2b-162">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="3aa2b-163">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-165">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="3aa2b-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-p110">工作階段的 SIP 對話方塊識別碼，格式為：dialog;from-tag;to-tag。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2b-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-169">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2b-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-170">使用者加入會議伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2b-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2b-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2b-172">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2b-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aa2b-173">使用者離開會議伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="3aa2b-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

