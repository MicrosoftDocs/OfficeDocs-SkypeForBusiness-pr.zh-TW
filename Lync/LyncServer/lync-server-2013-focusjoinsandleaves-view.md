---
title: Lync Server 2013： FocusJoinsAndLeaves view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="43276-102">Lync Server 2013 中的 [FocusJoinsAndLeaves] 視圖</span><span class="sxs-lookup"><span data-stu-id="43276-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43276-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="43276-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="43276-104">[FocusJoinsAndLeaves] 視圖儲存有關加入會議的資訊，並留下一個會議的資訊。</span><span class="sxs-lookup"><span data-stu-id="43276-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="43276-105">每個會議都會在每次使用者加入並離開會議時所撰寫的記錄在這個視圖中顯示。</span><span class="sxs-lookup"><span data-stu-id="43276-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="43276-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="43276-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43276-107">左欄</span><span class="sxs-lookup"><span data-stu-id="43276-107">Column</span></span></th>
<th><span data-ttu-id="43276-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="43276-108">Data Type</span></span></th>
<th><span data-ttu-id="43276-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="43276-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43276-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="43276-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-111">datetime</span><span class="sxs-lookup"><span data-stu-id="43276-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="43276-112">會議實例的時間。</span><span class="sxs-lookup"><span data-stu-id="43276-112">Time of conference instance.</span></span> <span data-ttu-id="43276-113">與 SessionIdSeq 搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="43276-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="43276-114">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="43276-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="43276-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-116">int</span><span class="sxs-lookup"><span data-stu-id="43276-116">int</span></span></p></td>
<td><p><span data-ttu-id="43276-117">識別會議實例的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="43276-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="43276-118">與 SessionIdTime 搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="43276-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="43276-119">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="43276-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="43276-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-121">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="43276-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="43276-122">已捕獲會議加入/離開資訊之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="43276-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="43276-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-124">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="43276-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="43276-125">已捕獲會議加入/離開資訊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="43276-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="43276-126">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="43276-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="43276-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-128">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="43276-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="43276-129">已捕獲會議加入/離開資訊之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="43276-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="43276-130">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="43276-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="43276-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="43276-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="43276-133">已捕獲會議加入/離開資訊之使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="43276-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="43276-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-135">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="43276-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="43276-136">已捕獲會議加入/離開資訊的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="43276-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="43276-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-138">int</span><span class="sxs-lookup"><span data-stu-id="43276-138">int</span></span></p></td>
<td><p><span data-ttu-id="43276-139">已捕獲會議加入/離開資訊的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="43276-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="43276-140">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="43276-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="43276-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-142">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="43276-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="43276-143">已捕獲會議加入/離開資訊之使用者所使用之用戶端類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="43276-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="43276-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-145">int</span><span class="sxs-lookup"><span data-stu-id="43276-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="43276-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-147">稍微</span><span class="sxs-lookup"><span data-stu-id="43276-147">bit</span></span></p></td>
<td><p><span data-ttu-id="43276-148">代表使用者是否為內部使用者的位。</span><span class="sxs-lookup"><span data-stu-id="43276-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="43276-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-150">datetime</span><span class="sxs-lookup"><span data-stu-id="43276-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="43276-151">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="43276-151">Time of session request.</span></span> <span data-ttu-id="43276-152">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="43276-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="43276-153">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="43276-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="43276-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-155">int</span><span class="sxs-lookup"><span data-stu-id="43276-155">int</span></span></p></td>
<td><p><span data-ttu-id="43276-156">如果使用者是同時在多部電腦或裝置上登入，則 UserInstance 會用來唯一識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="43276-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="43276-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-158">Varchar （775）</span><span class="sxs-lookup"><span data-stu-id="43276-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="43276-159">會話的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="43276-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="43276-160">格式為：對話方塊; 從標籤; 到標籤。</span><span class="sxs-lookup"><span data-stu-id="43276-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="43276-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-162">datetime</span><span class="sxs-lookup"><span data-stu-id="43276-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="43276-163">使用者加入會議的時間。</span><span class="sxs-lookup"><span data-stu-id="43276-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43276-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="43276-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-165">datetime</span><span class="sxs-lookup"><span data-stu-id="43276-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="43276-166">使用者離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="43276-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43276-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="43276-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="43276-168">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="43276-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="43276-169">使用者在會議中的角色，例如 [簡報者] 或 [出席者]。</span><span class="sxs-lookup"><span data-stu-id="43276-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

