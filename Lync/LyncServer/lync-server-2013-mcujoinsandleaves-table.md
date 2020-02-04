---
title: Lync Server 2013：McuJoinsAndLeaves 表格
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
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="2cef0-102">Lync Server 2013 中的 McuJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="2cef0-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cef0-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2cef0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2cef0-104">此表格中的每筆記錄都包含有關使用者加入或離開與會議服務器之一個組合的呼叫詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2cef0-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="2cef0-105">例如，如果使用者加入包含網路會議和音訊/視頻元素的會議，則會針對該使用者的網路會議加入建立一筆記錄，並會為使用者的音訊/視訊會議加入建立另一個記錄。</span><span class="sxs-lookup"><span data-stu-id="2cef0-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cef0-106">左欄</span><span class="sxs-lookup"><span data-stu-id="2cef0-106">Column</span></span></th>
<th><span data-ttu-id="2cef0-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="2cef0-107">Data Type</span></span></th>
<th><span data-ttu-id="2cef0-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="2cef0-108">Key/Index</span></span></th>
<th><span data-ttu-id="2cef0-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2cef0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cef0-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2cef0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2cef0-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="2cef0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cef0-113">會議實例的時間。</span><span class="sxs-lookup"><span data-stu-id="2cef0-113">Time of conference instance.</span></span> <span data-ttu-id="2cef0-114">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="2cef0-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2cef0-115">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="2cef0-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cef0-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-117">int</span><span class="sxs-lookup"><span data-stu-id="2cef0-117">int</span></span></p></td>
<td><p><span data-ttu-id="2cef0-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="2cef0-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cef0-119">識別會議實例的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="2cef0-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="2cef0-120">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="2cef0-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2cef0-121">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="2cef0-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cef0-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-123">int</span><span class="sxs-lookup"><span data-stu-id="2cef0-123">int</span></span></p></td>
<td><p><span data-ttu-id="2cef0-124">主要、外部</span><span class="sxs-lookup"><span data-stu-id="2cef0-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cef0-125">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="2cef0-125">Unique number identifying this user.</span></span> <span data-ttu-id="2cef0-126">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="2cef0-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cef0-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-128">int</span><span class="sxs-lookup"><span data-stu-id="2cef0-128">int</span></span></p></td>
<td><p><span data-ttu-id="2cef0-129">首選</span><span class="sxs-lookup"><span data-stu-id="2cef0-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="2cef0-130">如果使用者是一次在多部電腦或裝置上登入，McuUserInstance 會唯一識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="2cef0-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cef0-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-132">稍微</span><span class="sxs-lookup"><span data-stu-id="2cef0-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2cef0-133">使用者是否從 PSTN 加入。</span><span class="sxs-lookup"><span data-stu-id="2cef0-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cef0-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-135">int</span><span class="sxs-lookup"><span data-stu-id="2cef0-135">int</span></span></p></td>
<td><p><span data-ttu-id="2cef0-136">主要、外部</span><span class="sxs-lookup"><span data-stu-id="2cef0-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cef0-137">標識此會議服務器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="2cef0-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="2cef0-138">如需詳細資訊，請參閱<a href="lync-server-2013-mcus-table.md">Lync Server 2013 中</a>的 [Mcus] 資料表。</span><span class="sxs-lookup"><span data-stu-id="2cef0-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cef0-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-140">datetime</span><span class="sxs-lookup"><span data-stu-id="2cef0-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="2cef0-141">外</span><span class="sxs-lookup"><span data-stu-id="2cef0-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cef0-142">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="2cef0-142">Time of session request.</span></span> <span data-ttu-id="2cef0-143">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="2cef0-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2cef0-144">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="2cef0-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cef0-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-146">int</span><span class="sxs-lookup"><span data-stu-id="2cef0-146">int</span></span></p></td>
<td><p><span data-ttu-id="2cef0-147">外</span><span class="sxs-lookup"><span data-stu-id="2cef0-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cef0-148">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="2cef0-148">ID number to identify the session.</span></span> <span data-ttu-id="2cef0-149">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="2cef0-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2cef0-150">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="2cef0-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cef0-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-152">datetime</span><span class="sxs-lookup"><span data-stu-id="2cef0-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2cef0-153">此使用者加入此會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="2cef0-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cef0-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-155">datetime</span><span class="sxs-lookup"><span data-stu-id="2cef0-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2cef0-156">此使用者離開此會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="2cef0-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cef0-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="2cef0-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2cef0-158">int</span><span class="sxs-lookup"><span data-stu-id="2cef0-158">int</span></span></p></td>
<td><p><span data-ttu-id="2cef0-159">外</span><span class="sxs-lookup"><span data-stu-id="2cef0-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cef0-160">指定在會議中使用之用戶端軟體版本號碼的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2cef0-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="2cef0-161">如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="2cef0-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2cef0-162">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="2cef0-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

