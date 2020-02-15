---
title: 'Lync Server 2013: McuJoinsAndLeaves 表格'
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
ms.openlocfilehash: a398c0b860cd5b4043ee766b702b1b7e8e904552
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="21c68-102">Lync Server 2013 中的 McuJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="21c68-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21c68-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="21c68-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="21c68-104">此表格中的每一筆記錄包含一個組合的使用者加入或離開及會議伺服器的通話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="21c68-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="21c68-105">例如，如果使用者加入會議，其中包含 web 會議與音訊/視訊的項目，會針對該使用者的 web 會議加入，建立一筆記錄，另一筆記錄會加以建立使用者的音訊/視訊會議加入。</span><span class="sxs-lookup"><span data-stu-id="21c68-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21c68-106">欄</span><span class="sxs-lookup"><span data-stu-id="21c68-106">Column</span></span></th>
<th><span data-ttu-id="21c68-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="21c68-107">Data Type</span></span></th>
<th><span data-ttu-id="21c68-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="21c68-108">Key/Index</span></span></th>
<th><span data-ttu-id="21c68-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="21c68-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21c68-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-111">datetime</span><span class="sxs-lookup"><span data-stu-id="21c68-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="21c68-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="21c68-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="21c68-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="21c68-113">Time of conference instance.</span></span> <span data-ttu-id="21c68-114"><strong>SessionIdSeq</strong>搭配使用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="21c68-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="21c68-115">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="21c68-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c68-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-117">int</span><span class="sxs-lookup"><span data-stu-id="21c68-117">int</span></span></p></td>
<td><p><span data-ttu-id="21c68-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="21c68-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="21c68-119">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="21c68-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="21c68-120">搭配<strong>SessionIdTime</strong>用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="21c68-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="21c68-121">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="21c68-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c68-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-123">int</span><span class="sxs-lookup"><span data-stu-id="21c68-123">int</span></span></p></td>
<td><p><span data-ttu-id="21c68-124">主要、外部</span><span class="sxs-lookup"><span data-stu-id="21c68-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="21c68-125">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="21c68-125">Unique number identifying this user.</span></span> <span data-ttu-id="21c68-126">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="21c68-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c68-127"><strong>Mcuuserinstance 會</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-128">int</span><span class="sxs-lookup"><span data-stu-id="21c68-128">int</span></span></p></td>
<td><p><span data-ttu-id="21c68-129">主要</span><span class="sxs-lookup"><span data-stu-id="21c68-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="21c68-130">如果使用者登入多部電腦或裝置一次，mcuuserinstance 會識別唯一的使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="21c68-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c68-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-132">位元</span><span class="sxs-lookup"><span data-stu-id="21c68-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21c68-133">是否使用者從 PSTN 加入與否。</span><span class="sxs-lookup"><span data-stu-id="21c68-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c68-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-135">int</span><span class="sxs-lookup"><span data-stu-id="21c68-135">int</span></span></p></td>
<td><p><span data-ttu-id="21c68-136">主要、外部</span><span class="sxs-lookup"><span data-stu-id="21c68-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="21c68-137">用於識別此會議伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="21c68-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="21c68-138">請參閱<a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="21c68-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c68-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-140">datetime</span><span class="sxs-lookup"><span data-stu-id="21c68-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="21c68-141">Foreign</span><span class="sxs-lookup"><span data-stu-id="21c68-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21c68-142">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="21c68-142">Time of session request.</span></span> <span data-ttu-id="21c68-143">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="21c68-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="21c68-144"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="21c68-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c68-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-146">int</span><span class="sxs-lookup"><span data-stu-id="21c68-146">int</span></span></p></td>
<td><p><span data-ttu-id="21c68-147">Foreign</span><span class="sxs-lookup"><span data-stu-id="21c68-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21c68-148">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="21c68-148">ID number to identify the session.</span></span> <span data-ttu-id="21c68-149">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="21c68-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="21c68-150"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="21c68-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c68-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-152">datetime</span><span class="sxs-lookup"><span data-stu-id="21c68-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21c68-153">此使用者加入此會議伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="21c68-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21c68-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-155">datetime</span><span class="sxs-lookup"><span data-stu-id="21c68-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21c68-156">此使用者離開此會議伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="21c68-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21c68-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="21c68-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="21c68-158">int</span><span class="sxs-lookup"><span data-stu-id="21c68-158">int</span></span></p></td>
<td><p><span data-ttu-id="21c68-159">Foreign</span><span class="sxs-lookup"><span data-stu-id="21c68-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="21c68-160">在會議中使用指定的用戶端軟體版本號碼的識別碼。</span><span class="sxs-lookup"><span data-stu-id="21c68-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="21c68-161">請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="21c68-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="21c68-162">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="21c68-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

