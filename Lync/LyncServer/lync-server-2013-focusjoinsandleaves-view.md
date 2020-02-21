---
title: 'Lync Server 2013: FocusJoinsAndLeaves 檢視'
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
ms.openlocfilehash: 9e97346929851bec53ab228988d72fb4813316d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="f9180-102">Lync Server 2013 中的 FocusJoinsAndLeaves 檢視</span><span class="sxs-lookup"><span data-stu-id="f9180-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9180-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="f9180-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f9180-104">FocusJoinsAndLeaves 檢視可儲存會議的加入和離開相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f9180-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="f9180-105">每次有使用者加入和離開某場會議時，此檢視中的該場會議都會有一筆撰寫記錄來表示。</span><span class="sxs-lookup"><span data-stu-id="f9180-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="f9180-106">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="f9180-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9180-107">欄</span><span class="sxs-lookup"><span data-stu-id="f9180-107">Column</span></span></th>
<th><span data-ttu-id="f9180-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="f9180-108">Data Type</span></span></th>
<th><span data-ttu-id="f9180-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f9180-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9180-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f9180-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f9180-112">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="f9180-112">Time of conference instance.</span></span> <span data-ttu-id="f9180-113">會與 SessionIdSeq 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="f9180-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="f9180-114">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f9180-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-116">int</span><span class="sxs-lookup"><span data-stu-id="f9180-116">int</span></span></p></td>
<td><p><span data-ttu-id="f9180-117">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="f9180-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="f9180-118">會與 SessionIDTime 搭配使用，專門用於識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="f9180-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="f9180-119">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f9180-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-121">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="f9180-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f9180-122">已擷取其加入/離開會議資訊之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="f9180-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f9180-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9180-125">已擷取其加入/離開會議資訊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="f9180-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="f9180-126">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f9180-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f9180-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9180-129">已擷取其加入/離開會議資訊之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="f9180-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="f9180-130">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f9180-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-132">唯一</span><span class="sxs-lookup"><span data-stu-id="f9180-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f9180-133">已擷取其加入/離開會議資訊之使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9180-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f9180-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9180-136">已擷取其加入/離開會議資訊之使用者所用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="f9180-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-138">int</span><span class="sxs-lookup"><span data-stu-id="f9180-138">int</span></span></p></td>
<td><p><span data-ttu-id="f9180-139">已擷取其加入/離開會議資訊之使用者所用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="f9180-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="f9180-140">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="f9180-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-142">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="f9180-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f9180-143">已擷取其加入/離開會議資訊之使用者所用的用戶端類別名稱。</span><span class="sxs-lookup"><span data-stu-id="f9180-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-145">int</span><span class="sxs-lookup"><span data-stu-id="f9180-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-147">位元</span><span class="sxs-lookup"><span data-stu-id="f9180-147">bit</span></span></p></td>
<td><p><span data-ttu-id="f9180-148">代表使用者是否為內部使用者的位元。</span><span class="sxs-lookup"><span data-stu-id="f9180-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-150">datetime</span><span class="sxs-lookup"><span data-stu-id="f9180-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="f9180-151">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="f9180-151">Time of session request.</span></span> <span data-ttu-id="f9180-152">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="f9180-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f9180-153"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="f9180-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-155">int</span><span class="sxs-lookup"><span data-stu-id="f9180-155">int</span></span></p></td>
<td><p><span data-ttu-id="f9180-156">若使用者同時登入多部電腦或裝置，會使用 UserInstance 專門識別使用者/裝置的組合。</span><span class="sxs-lookup"><span data-stu-id="f9180-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-158">varchar(775)</span><span class="sxs-lookup"><span data-stu-id="f9180-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="f9180-p108">工作階段的 SIP 對話方塊識別碼，格式為：dialog;from-tag;to-tag。</span><span class="sxs-lookup"><span data-stu-id="f9180-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-162">datetime</span><span class="sxs-lookup"><span data-stu-id="f9180-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="f9180-163">使用者加入會議的時間。</span><span class="sxs-lookup"><span data-stu-id="f9180-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9180-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-165">datetime</span><span class="sxs-lookup"><span data-stu-id="f9180-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="f9180-166">使用者離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="f9180-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9180-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="f9180-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="f9180-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f9180-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9180-169">此使用者在會議中的角色，例如簡報者或是出席者。</span><span class="sxs-lookup"><span data-stu-id="f9180-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

