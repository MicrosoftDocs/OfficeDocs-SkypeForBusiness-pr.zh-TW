---
title: Lync Server 2013： FocusJoinsAndLeaves 表格
description: Lync Server 2013： FocusJoinsAndLeaves 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5796de16ed204ce4f33935d937cbaa425d63a67f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577439"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="1739d-103">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="1739d-103">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1739d-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1739d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1739d-105">此表格中的每一筆記錄都包含有關一位使用者的加入的 CDR 資訊，並留下一次會議的資訊。</span><span class="sxs-lookup"><span data-stu-id="1739d-105">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="1739d-106">每個會議都會在每次使用者加入和離開會議時，以一筆記錄呈現在此表格中。</span><span class="sxs-lookup"><span data-stu-id="1739d-106">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1739d-107">欄</span><span class="sxs-lookup"><span data-stu-id="1739d-107">Column</span></span></th>
<th><span data-ttu-id="1739d-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="1739d-108">Data Type</span></span></th>
<th><span data-ttu-id="1739d-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="1739d-109">Key/Index</span></span></th>
<th><span data-ttu-id="1739d-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1739d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1739d-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1739d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1739d-113">主要，外部</span><span class="sxs-lookup"><span data-stu-id="1739d-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1739d-114">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="1739d-114">Time of conference instance.</span></span> <span data-ttu-id="1739d-115">與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="1739d-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="1739d-116">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="1739d-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1739d-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-118">int</span><span class="sxs-lookup"><span data-stu-id="1739d-118">int</span></span></p></td>
<td><p><span data-ttu-id="1739d-119">主要、外部</span><span class="sxs-lookup"><span data-stu-id="1739d-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1739d-120">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="1739d-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="1739d-121">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="1739d-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="1739d-122">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="1739d-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1739d-123"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-123"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-124">datetime</span><span class="sxs-lookup"><span data-stu-id="1739d-124">datetime</span></span></p></td>
<td><p><span data-ttu-id="1739d-125">主要，外部</span><span class="sxs-lookup"><span data-stu-id="1739d-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1739d-126">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="1739d-126">Time of session request.</span></span> <span data-ttu-id="1739d-127">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="1739d-127">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1739d-128">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="1739d-128">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1739d-129"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-129"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-130">int</span><span class="sxs-lookup"><span data-stu-id="1739d-130">int</span></span></p></td>
<td><p><span data-ttu-id="1739d-131">主要，外部</span><span class="sxs-lookup"><span data-stu-id="1739d-131">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1739d-132">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="1739d-132">ID number to identify the session.</span></span> <span data-ttu-id="1739d-133">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="1739d-133">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1739d-134">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="1739d-134">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1739d-135"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-135"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-136">int</span><span class="sxs-lookup"><span data-stu-id="1739d-136">int</span></span></p></td>
<td><p><span data-ttu-id="1739d-137">Foreign</span><span class="sxs-lookup"><span data-stu-id="1739d-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1739d-138">用於識別此使用者的唯一號碼， <a href="lync-server-2013-users-table.md">在 Lync Server 2013 的 [使用者] 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="1739d-138">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1739d-139"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-139"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-140">int</span><span class="sxs-lookup"><span data-stu-id="1739d-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1739d-141">如果使用者同時在多部電腦或裝置上登入，則會使用 <strong>UserInstance</strong> 來唯一地識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="1739d-141">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1739d-142"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-142"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-143">位</span><span class="sxs-lookup"><span data-stu-id="1739d-143">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1739d-144">使用者是否從內部登入。</span><span class="sxs-lookup"><span data-stu-id="1739d-144">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1739d-145"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-145"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-146">int</span><span class="sxs-lookup"><span data-stu-id="1739d-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1739d-147">此使用者在會議中的角色，例如簡報者或出席者。</span><span class="sxs-lookup"><span data-stu-id="1739d-147">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1739d-148"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-148"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-149">datetime</span><span class="sxs-lookup"><span data-stu-id="1739d-149">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1739d-150">此使用者加入會議的時間。</span><span class="sxs-lookup"><span data-stu-id="1739d-150">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1739d-151"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-151"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-152">datetime</span><span class="sxs-lookup"><span data-stu-id="1739d-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1739d-153">此使用者離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="1739d-153">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1739d-154"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-154"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-155">int</span><span class="sxs-lookup"><span data-stu-id="1739d-155">int</span></span></p></td>
<td><p><span data-ttu-id="1739d-156">Foreign</span><span class="sxs-lookup"><span data-stu-id="1739d-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1739d-157">使用者的用戶端軟體版本，參考 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="1739d-157">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1739d-158"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="1739d-158"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1739d-159">唯一</span><span class="sxs-lookup"><span data-stu-id="1739d-159">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1739d-160">會議中所使用之端點的全域唯一識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="1739d-160">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="1739d-161">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1739d-161">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

