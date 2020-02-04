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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="f84f7-102">Lync Server 2013 中的 [McuJoinsAndLeaves] 視圖</span><span class="sxs-lookup"><span data-stu-id="f84f7-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f84f7-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f84f7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f84f7-104">[McuJoinsAndLeaves] 視圖儲存有關使用者如何加入與離開一個會議服務器的資訊。</span><span class="sxs-lookup"><span data-stu-id="f84f7-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="f84f7-105">此視圖中的每一筆記錄都包含使用者加入或離開與會議服務器之一個組合的通話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f84f7-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="f84f7-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="f84f7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f84f7-107">左欄</span><span class="sxs-lookup"><span data-stu-id="f84f7-107">Column</span></span></th>
<th><span data-ttu-id="f84f7-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="f84f7-108">Data Type</span></span></th>
<th><span data-ttu-id="f84f7-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f84f7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f84f7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f84f7-112">會議實例的時間。</span><span class="sxs-lookup"><span data-stu-id="f84f7-112">Time of conference instance.</span></span> <span data-ttu-id="f84f7-113">與 SessionIdSeq 搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="f84f7-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="f84f7-114">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="f84f7-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-116">int</span><span class="sxs-lookup"><span data-stu-id="f84f7-116">int</span></span></p></td>
<td><p><span data-ttu-id="f84f7-117">識別會議實例的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="f84f7-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="f84f7-118">與 SessionIdTime 搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="f84f7-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="f84f7-119">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="f84f7-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-121">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="f84f7-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-122">使用者所連接之會議服務器的 URI。</span><span class="sxs-lookup"><span data-stu-id="f84f7-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-124">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="f84f7-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-125">使用者所連接之會議服務器的 URI。</span><span class="sxs-lookup"><span data-stu-id="f84f7-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="f84f7-126">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f84f7-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-128">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="f84f7-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-129">已捕獲會議服務器加入/離開資訊的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="f84f7-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-131">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="f84f7-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-132">已捕獲會議服務器加入/離開資訊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="f84f7-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="f84f7-133">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f84f7-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-135">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="f84f7-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-136">已捕獲會議服務器加入/離開資訊之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="f84f7-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="f84f7-137">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f84f7-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-139">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="f84f7-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-140">已捕獲會議服務器加入/離開資訊的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="f84f7-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-142">int</span><span class="sxs-lookup"><span data-stu-id="f84f7-142">int</span></span></p></td>
<td><p><span data-ttu-id="f84f7-143">已捕獲會議服務器加入/離開資訊的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="f84f7-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="f84f7-144">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f84f7-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-146">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="f84f7-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-147">已捕獲會議服務器加入/離開資訊之使用者所使用之用戶端的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="f84f7-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-149">int</span><span class="sxs-lookup"><span data-stu-id="f84f7-149">int</span></span></p></td>
<td><p><span data-ttu-id="f84f7-150">針對同時登入多個裝置的使用者，唯一識別使用者/裝置的組合。</span><span class="sxs-lookup"><span data-stu-id="f84f7-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-152">稍微</span><span class="sxs-lookup"><span data-stu-id="f84f7-152">bit</span></span></p></td>
<td><p><span data-ttu-id="f84f7-153">代表使用者是否為內部使用者的位。</span><span class="sxs-lookup"><span data-stu-id="f84f7-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-155">datetime</span><span class="sxs-lookup"><span data-stu-id="f84f7-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="f84f7-156">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="f84f7-156">Time of session request.</span></span> <span data-ttu-id="f84f7-157">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="f84f7-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f84f7-158">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f84f7-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-160">int</span><span class="sxs-lookup"><span data-stu-id="f84f7-160">int</span></span></p></td>
<td><p><span data-ttu-id="f84f7-161">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="f84f7-161">ID number to identify the session.</span></span> <span data-ttu-id="f84f7-162">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="f84f7-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f84f7-163">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f84f7-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-165">Varchar （775）</span><span class="sxs-lookup"><span data-stu-id="f84f7-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="f84f7-166">會話的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="f84f7-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="f84f7-167">格式為：對話方塊; 從標籤; 到標籤。</span><span class="sxs-lookup"><span data-stu-id="f84f7-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f84f7-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-169">datetime</span><span class="sxs-lookup"><span data-stu-id="f84f7-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="f84f7-170">使用者加入會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="f84f7-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f84f7-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="f84f7-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f84f7-172">datetime</span><span class="sxs-lookup"><span data-stu-id="f84f7-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="f84f7-173">使用者離開會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="f84f7-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

