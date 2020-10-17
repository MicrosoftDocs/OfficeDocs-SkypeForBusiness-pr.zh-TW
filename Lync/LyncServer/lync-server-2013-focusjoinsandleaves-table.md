---
title: Lync Server 2013： FocusJoinsAndLeaves 表格
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
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500830"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="ef876-102">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="ef876-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef876-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ef876-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ef876-104">此表格中的每一筆記錄都包含有關一位使用者的加入的 CDR 資訊，並留下一次會議的資訊。</span><span class="sxs-lookup"><span data-stu-id="ef876-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="ef876-105">每個會議都會在每次使用者加入和離開會議時，以一筆記錄呈現在此表格中。</span><span class="sxs-lookup"><span data-stu-id="ef876-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef876-106">欄</span><span class="sxs-lookup"><span data-stu-id="ef876-106">Column</span></span></th>
<th><span data-ttu-id="ef876-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="ef876-107">Data Type</span></span></th>
<th><span data-ttu-id="ef876-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="ef876-108">Key/Index</span></span></th>
<th><span data-ttu-id="ef876-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ef876-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef876-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ef876-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ef876-112">主要，外部</span><span class="sxs-lookup"><span data-stu-id="ef876-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef876-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="ef876-113">Time of conference instance.</span></span> <span data-ttu-id="ef876-114">與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="ef876-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ef876-115">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="ef876-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef876-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-117">int</span><span class="sxs-lookup"><span data-stu-id="ef876-117">int</span></span></p></td>
<td><p><span data-ttu-id="ef876-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ef876-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef876-119">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="ef876-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="ef876-120">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="ef876-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ef876-121">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="ef876-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef876-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-123">datetime</span><span class="sxs-lookup"><span data-stu-id="ef876-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="ef876-124">主要，外部</span><span class="sxs-lookup"><span data-stu-id="ef876-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef876-125">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="ef876-125">Time of session request.</span></span> <span data-ttu-id="ef876-126">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="ef876-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ef876-127">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ef876-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef876-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-129">int</span><span class="sxs-lookup"><span data-stu-id="ef876-129">int</span></span></p></td>
<td><p><span data-ttu-id="ef876-130">主要，外部</span><span class="sxs-lookup"><span data-stu-id="ef876-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef876-131">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="ef876-131">ID number to identify the session.</span></span> <span data-ttu-id="ef876-132">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="ef876-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ef876-133">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ef876-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef876-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-135">int</span><span class="sxs-lookup"><span data-stu-id="ef876-135">int</span></span></p></td>
<td><p><span data-ttu-id="ef876-136">Foreign</span><span class="sxs-lookup"><span data-stu-id="ef876-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef876-137">用於識別此使用者的唯一號碼， <a href="lync-server-2013-users-table.md">在 Lync Server 2013 的 [使用者] 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="ef876-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef876-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-139">int</span><span class="sxs-lookup"><span data-stu-id="ef876-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef876-140">如果使用者同時在多部電腦或裝置上登入，則會使用 <strong>UserInstance</strong> 來唯一地識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="ef876-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef876-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-142">位</span><span class="sxs-lookup"><span data-stu-id="ef876-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ef876-143">使用者是否從內部登入。</span><span class="sxs-lookup"><span data-stu-id="ef876-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef876-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-145">int</span><span class="sxs-lookup"><span data-stu-id="ef876-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ef876-146">此使用者在會議中的角色，例如簡報者或出席者。</span><span class="sxs-lookup"><span data-stu-id="ef876-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef876-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-148">datetime</span><span class="sxs-lookup"><span data-stu-id="ef876-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ef876-149">此使用者加入會議的時間。</span><span class="sxs-lookup"><span data-stu-id="ef876-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef876-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-151">datetime</span><span class="sxs-lookup"><span data-stu-id="ef876-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ef876-152">此使用者離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="ef876-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef876-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-154">int</span><span class="sxs-lookup"><span data-stu-id="ef876-154">int</span></span></p></td>
<td><p><span data-ttu-id="ef876-155">Foreign</span><span class="sxs-lookup"><span data-stu-id="ef876-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef876-156">使用者的用戶端軟體版本，參考 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="ef876-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef876-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ef876-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef876-158">唯一</span><span class="sxs-lookup"><span data-stu-id="ef876-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef876-159">會議中所使用之端點的全域唯一識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="ef876-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="ef876-160">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ef876-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

