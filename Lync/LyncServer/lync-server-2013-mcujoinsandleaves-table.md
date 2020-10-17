---
title: Lync Server 2013： McuJoinsAndLeaves 表格
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
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524730"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="83932-102">Lync Server 2013 中的 McuJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="83932-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83932-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="83932-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="83932-104">此表格中的每一筆記錄都包含有關使用者加入或離開和會議服務器之一種結合的呼叫詳細資料。</span><span class="sxs-lookup"><span data-stu-id="83932-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="83932-105">例如，如果使用者加入包含 web 會議及音訊/視頻元素的會議，則會為該使用者的 web 會議加入建立一個記錄，並為使用者的音訊/視訊會議加入建立另一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="83932-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83932-106">欄</span><span class="sxs-lookup"><span data-stu-id="83932-106">Column</span></span></th>
<th><span data-ttu-id="83932-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="83932-107">Data Type</span></span></th>
<th><span data-ttu-id="83932-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="83932-108">Key/Index</span></span></th>
<th><span data-ttu-id="83932-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="83932-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83932-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="83932-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-111">datetime</span><span class="sxs-lookup"><span data-stu-id="83932-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="83932-112">主要，外部</span><span class="sxs-lookup"><span data-stu-id="83932-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="83932-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="83932-113">Time of conference instance.</span></span> <span data-ttu-id="83932-114">與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="83932-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="83932-115">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="83932-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83932-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="83932-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-117">int</span><span class="sxs-lookup"><span data-stu-id="83932-117">int</span></span></p></td>
<td><p><span data-ttu-id="83932-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="83932-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="83932-119">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="83932-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="83932-120">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="83932-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="83932-121">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="83932-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83932-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="83932-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-123">int</span><span class="sxs-lookup"><span data-stu-id="83932-123">int</span></span></p></td>
<td><p><span data-ttu-id="83932-124">主要、外部</span><span class="sxs-lookup"><span data-stu-id="83932-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="83932-125">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="83932-125">Unique number identifying this user.</span></span> <span data-ttu-id="83932-126">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="83932-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83932-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="83932-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-128">int</span><span class="sxs-lookup"><span data-stu-id="83932-128">int</span></span></p></td>
<td><p><span data-ttu-id="83932-129">主要</span><span class="sxs-lookup"><span data-stu-id="83932-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="83932-130">如果使用者同時在多部電腦或裝置上登入，McuUserInstance 會唯一識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="83932-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83932-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="83932-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-132">位</span><span class="sxs-lookup"><span data-stu-id="83932-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="83932-133">使用者是否從 PSTN 加入。</span><span class="sxs-lookup"><span data-stu-id="83932-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83932-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="83932-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-135">int</span><span class="sxs-lookup"><span data-stu-id="83932-135">int</span></span></p></td>
<td><p><span data-ttu-id="83932-136">主要、外部</span><span class="sxs-lookup"><span data-stu-id="83932-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="83932-137">用於識別此會議服務器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="83932-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="83932-138">如需詳細資訊，請參閱 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="83932-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83932-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="83932-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-140">datetime</span><span class="sxs-lookup"><span data-stu-id="83932-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="83932-141">Foreign</span><span class="sxs-lookup"><span data-stu-id="83932-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="83932-142">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="83932-142">Time of session request.</span></span> <span data-ttu-id="83932-143">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="83932-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="83932-144">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="83932-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83932-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="83932-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-146">int</span><span class="sxs-lookup"><span data-stu-id="83932-146">int</span></span></p></td>
<td><p><span data-ttu-id="83932-147">Foreign</span><span class="sxs-lookup"><span data-stu-id="83932-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="83932-148">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="83932-148">ID number to identify the session.</span></span> <span data-ttu-id="83932-149">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="83932-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="83932-150">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="83932-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83932-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="83932-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-152">datetime</span><span class="sxs-lookup"><span data-stu-id="83932-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="83932-153">此使用者加入此會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="83932-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83932-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="83932-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-155">datetime</span><span class="sxs-lookup"><span data-stu-id="83932-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="83932-156">此使用者離開此會議服務器的時間。</span><span class="sxs-lookup"><span data-stu-id="83932-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83932-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="83932-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="83932-158">int</span><span class="sxs-lookup"><span data-stu-id="83932-158">int</span></span></p></td>
<td><p><span data-ttu-id="83932-159">Foreign</span><span class="sxs-lookup"><span data-stu-id="83932-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="83932-160">指定會議中用戶端軟體使用版本號碼的識別碼。</span><span class="sxs-lookup"><span data-stu-id="83932-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="83932-161">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="83932-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="83932-162">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="83932-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

