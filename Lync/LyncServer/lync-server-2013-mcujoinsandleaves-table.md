---
title: Lync Server 2013： McuJoinsAndLeaves 表格
description: Lync Server 2013： McuJoinsAndLeaves 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556499"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="f8911-103">Lync Server 2013 中的 McuJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="f8911-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8911-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f8911-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f8911-105">此表格中的每一筆記錄都包含有關使用者加入或離開和會議服務器之一種結合的呼叫詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f8911-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="f8911-106">例如，如果使用者加入包含 web 會議及音訊/視頻元素的會議，則會為該使用者的 web 會議加入建立一個記錄，並為使用者的音訊/視訊會議加入建立另一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="f8911-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8911-107">欄</span><span class="sxs-lookup"><span data-stu-id="f8911-107">Column</span></span></th>
<th><span data-ttu-id="f8911-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="f8911-108">Data Type</span></span></th>
<th><span data-ttu-id="f8911-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="f8911-109">Key/Index</span></span></th>
<th><span data-ttu-id="f8911-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f8911-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8911-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f8911-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f8911-113">主要，外部</span><span class="sxs-lookup"><span data-stu-id="f8911-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f8911-114">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="f8911-114">Time of conference instance.</span></span> <span data-ttu-id="f8911-115">與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="f8911-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f8911-116">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="f8911-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8911-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-118">int</span><span class="sxs-lookup"><span data-stu-id="f8911-118">int</span></span></p></td>
<td><p><span data-ttu-id="f8911-119">主要、外部</span><span class="sxs-lookup"><span data-stu-id="f8911-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f8911-120">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="f8911-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="f8911-121">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="f8911-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f8911-122">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="f8911-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8911-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-124">int</span><span class="sxs-lookup"><span data-stu-id="f8911-124">int</span></span></p></td>
<td><p><span data-ttu-id="f8911-125">主要、外部</span><span class="sxs-lookup"><span data-stu-id="f8911-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f8911-126">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f8911-126">Unique number identifying this user.</span></span> <span data-ttu-id="f8911-127">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f8911-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8911-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-129">int</span><span class="sxs-lookup"><span data-stu-id="f8911-129">int</span></span></p></td>
<td><p><span data-ttu-id="f8911-130">主要</span><span class="sxs-lookup"><span data-stu-id="f8911-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="f8911-131">如果使用者同時在多部電腦或裝置上登入，McuUserInstance 會唯一識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="f8911-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8911-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-133">位</span><span class="sxs-lookup"><span data-stu-id="f8911-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8911-134">使用者是否從 PSTN 加入。</span><span class="sxs-lookup"><span data-stu-id="f8911-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8911-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-136">int</span><span class="sxs-lookup"><span data-stu-id="f8911-136">int</span></span></p></td>
<td><p><span data-ttu-id="f8911-137">主要、外部</span><span class="sxs-lookup"><span data-stu-id="f8911-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f8911-138">用於識別此會議服務器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f8911-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="f8911-139">如需詳細資訊，請參閱 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f8911-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8911-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-141">datetime</span><span class="sxs-lookup"><span data-stu-id="f8911-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="f8911-142">Foreign</span><span class="sxs-lookup"><span data-stu-id="f8911-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f8911-143">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="f8911-143">Time of session request.</span></span> <span data-ttu-id="f8911-144">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="f8911-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f8911-145">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f8911-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8911-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-147">int</span><span class="sxs-lookup"><span data-stu-id="f8911-147">int</span></span></p></td>
<td><p><span data-ttu-id="f8911-148">Foreign</span><span class="sxs-lookup"><span data-stu-id="f8911-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f8911-149">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8911-149">ID number to identify the session.</span></span> <span data-ttu-id="f8911-150">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="f8911-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f8911-151">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f8911-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8911-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-153">datetime</span><span class="sxs-lookup"><span data-stu-id="f8911-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8911-154">此使用者加入此會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="f8911-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8911-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-156">datetime</span><span class="sxs-lookup"><span data-stu-id="f8911-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8911-157">此使用者離開此會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="f8911-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8911-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="f8911-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f8911-159">int</span><span class="sxs-lookup"><span data-stu-id="f8911-159">int</span></span></p></td>
<td><p><span data-ttu-id="f8911-160">Foreign</span><span class="sxs-lookup"><span data-stu-id="f8911-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f8911-161">指定會議中用戶端軟體使用版本號碼的識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8911-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="f8911-162">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f8911-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f8911-163">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f8911-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

