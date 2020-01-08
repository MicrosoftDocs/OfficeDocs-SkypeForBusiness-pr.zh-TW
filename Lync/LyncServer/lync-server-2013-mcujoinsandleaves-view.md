---
title: Lync Server 2013： McuJoinsAndLeaves view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="70d37-102">Lync Server 2013 中的 [McuJoinsAndLeaves] 視圖</span><span class="sxs-lookup"><span data-stu-id="70d37-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70d37-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="70d37-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="70d37-104">[McuJoinsAndLeaves] 視圖儲存有關使用者如何加入與離開一個會議服務器的資訊。</span><span class="sxs-lookup"><span data-stu-id="70d37-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="70d37-105">此視圖中的每一筆記錄都包含使用者加入或離開與會議服務器之一個組合的通話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="70d37-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="70d37-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="70d37-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70d37-107">左欄</span><span class="sxs-lookup"><span data-stu-id="70d37-107">Column</span></span></th>
<th><span data-ttu-id="70d37-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="70d37-108">Data Type</span></span></th>
<th><span data-ttu-id="70d37-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="70d37-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70d37-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-111">datetime</span><span class="sxs-lookup"><span data-stu-id="70d37-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="70d37-112">會議實例的時間。</span><span class="sxs-lookup"><span data-stu-id="70d37-112">Time of conference instance.</span></span> <span data-ttu-id="70d37-113">與 SessionIdSeq 搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="70d37-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="70d37-114">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="70d37-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-116">int</span><span class="sxs-lookup"><span data-stu-id="70d37-116">int</span></span></p></td>
<td><p><span data-ttu-id="70d37-117">識別會議實例的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="70d37-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="70d37-118">與 SessionIdTime 搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="70d37-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="70d37-119">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="70d37-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-121">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="70d37-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70d37-122">使用者所連接之會議服務器的 URI。</span><span class="sxs-lookup"><span data-stu-id="70d37-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-124">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="70d37-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70d37-125">使用者所連接之會議服務器的 URI。</span><span class="sxs-lookup"><span data-stu-id="70d37-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="70d37-126">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="70d37-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-128">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="70d37-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="70d37-129">已捕獲會議服務器加入/離開資訊的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="70d37-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-131">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="70d37-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70d37-132">已捕獲會議服務器加入/離開資訊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="70d37-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="70d37-133">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="70d37-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-135">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="70d37-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70d37-136">已捕獲會議服務器加入/離開資訊之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="70d37-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="70d37-137">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="70d37-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-139">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="70d37-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70d37-140">已捕獲會議服務器加入/離開資訊的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="70d37-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-142">int</span><span class="sxs-lookup"><span data-stu-id="70d37-142">int</span></span></p></td>
<td><p><span data-ttu-id="70d37-143">已捕獲會議服務器加入/離開資訊的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="70d37-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="70d37-144">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="70d37-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-146">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="70d37-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="70d37-147">已捕獲會議服務器加入/離開資訊之使用者所使用之用戶端的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="70d37-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-149">int</span><span class="sxs-lookup"><span data-stu-id="70d37-149">int</span></span></p></td>
<td><p><span data-ttu-id="70d37-150">針對同時登入多個裝置的使用者，唯一識別使用者/裝置的組合。</span><span class="sxs-lookup"><span data-stu-id="70d37-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-152">稍微</span><span class="sxs-lookup"><span data-stu-id="70d37-152">bit</span></span></p></td>
<td><p><span data-ttu-id="70d37-153">代表使用者是否為內部使用者的位。</span><span class="sxs-lookup"><span data-stu-id="70d37-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-155">datetime</span><span class="sxs-lookup"><span data-stu-id="70d37-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="70d37-156">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="70d37-156">Time of session request.</span></span> <span data-ttu-id="70d37-157">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="70d37-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="70d37-158">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="70d37-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-160">int</span><span class="sxs-lookup"><span data-stu-id="70d37-160">int</span></span></p></td>
<td><p><span data-ttu-id="70d37-161">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="70d37-161">ID number to identify the session.</span></span> <span data-ttu-id="70d37-162">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="70d37-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="70d37-163">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="70d37-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-165">Varchar （775）</span><span class="sxs-lookup"><span data-stu-id="70d37-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="70d37-166">會話的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="70d37-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="70d37-167">格式為：對話方塊; 從標籤; 到標籤。</span><span class="sxs-lookup"><span data-stu-id="70d37-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70d37-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-169">datetime</span><span class="sxs-lookup"><span data-stu-id="70d37-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="70d37-170">使用者加入會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="70d37-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70d37-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="70d37-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="70d37-172">datetime</span><span class="sxs-lookup"><span data-stu-id="70d37-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="70d37-173">使用者離開會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="70d37-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

