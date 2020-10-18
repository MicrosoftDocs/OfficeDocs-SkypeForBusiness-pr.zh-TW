---
title: Lync Server 2013： FocusJoinsAndLeaves view
description: Lync Server 2013： FocusJoinsAndLeaves view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577449"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="5e254-103">Lync Server 2013 中的 FocusJoinsAndLeaves 視圖</span><span class="sxs-lookup"><span data-stu-id="5e254-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e254-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5e254-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5e254-105">FocusJoinsAndLeaves 檢視可儲存會議的加入和離開相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5e254-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="5e254-106">每次有使用者加入和離開某場會議時，此檢視中的該場會議都會有一筆撰寫記錄來表示。</span><span class="sxs-lookup"><span data-stu-id="5e254-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="5e254-107">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="5e254-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e254-108">欄</span><span class="sxs-lookup"><span data-stu-id="5e254-108">Column</span></span></th>
<th><span data-ttu-id="5e254-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="5e254-109">Data Type</span></span></th>
<th><span data-ttu-id="5e254-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="5e254-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e254-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5e254-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e254-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="5e254-113">Time of conference instance.</span></span> <span data-ttu-id="5e254-114">會與 SessionIdSeq 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="5e254-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="5e254-115">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="5e254-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-117">int</span><span class="sxs-lookup"><span data-stu-id="5e254-117">int</span></span></p></td>
<td><p><span data-ttu-id="5e254-118">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="5e254-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="5e254-119">會與 SessionIDTime 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="5e254-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="5e254-120">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="5e254-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-122">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="5e254-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5e254-123">已擷取其加入/離開會議資訊之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="5e254-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-124"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-125">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5e254-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5e254-126">已擷取其加入/離開會議資訊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="5e254-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5e254-127">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5e254-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-128"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-129">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5e254-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5e254-130">已擷取其加入/離開會議資訊之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="5e254-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5e254-131">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5e254-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-132"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-133">唯一</span><span class="sxs-lookup"><span data-stu-id="5e254-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5e254-134">已擷取其加入/離開會議資訊之使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="5e254-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-136">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5e254-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5e254-137">已擷取其加入/離開會議資訊之使用者所用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="5e254-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-138"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-139">int</span><span class="sxs-lookup"><span data-stu-id="5e254-139">int</span></span></p></td>
<td><p><span data-ttu-id="5e254-140">已擷取其加入/離開會議資訊之使用者所用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="5e254-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5e254-141">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5e254-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-143">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="5e254-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5e254-144">已擷取其加入/離開會議資訊之使用者所用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="5e254-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-146">int</span><span class="sxs-lookup"><span data-stu-id="5e254-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-148">位</span><span class="sxs-lookup"><span data-stu-id="5e254-148">bit</span></span></p></td>
<td><p><span data-ttu-id="5e254-149">代表使用者是否為內部使用者的位元。</span><span class="sxs-lookup"><span data-stu-id="5e254-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-151">datetime</span><span class="sxs-lookup"><span data-stu-id="5e254-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e254-152">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="5e254-152">Time of session request.</span></span> <span data-ttu-id="5e254-153">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="5e254-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5e254-154">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="5e254-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-156">int</span><span class="sxs-lookup"><span data-stu-id="5e254-156">int</span></span></p></td>
<td><p><span data-ttu-id="5e254-157">若使用者同時登入多部電腦或裝置，會使用 UserInstance 專門識別使用者/裝置的組合。</span><span class="sxs-lookup"><span data-stu-id="5e254-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-159">Varchar (775) </span><span class="sxs-lookup"><span data-stu-id="5e254-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5e254-p108">工作階段的 SIP 對話方塊識別碼，格式為：dialog;from-tag;to-tag。</span><span class="sxs-lookup"><span data-stu-id="5e254-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-162"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-163">datetime</span><span class="sxs-lookup"><span data-stu-id="5e254-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e254-164">使用者加入會議的時間。</span><span class="sxs-lookup"><span data-stu-id="5e254-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e254-165"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-166">datetime</span><span class="sxs-lookup"><span data-stu-id="5e254-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e254-167">使用者離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="5e254-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e254-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="5e254-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="5e254-169">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5e254-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5e254-170">此使用者在會議中的角色，例如簡報者或是出席者。</span><span class="sxs-lookup"><span data-stu-id="5e254-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

