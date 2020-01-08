---
title: Lync Server 2013：FocusJoinsAndLeaves 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="79957-102">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="79957-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79957-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="79957-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="79957-104">此資料表中的每一筆記錄都包含一個使用者加入的 CDR 資訊，並留下一個會議的資訊。</span><span class="sxs-lookup"><span data-stu-id="79957-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="79957-105">每個會議都會在每次使用者加入並離開會議時，由一筆記錄在這個資料表中顯示。</span><span class="sxs-lookup"><span data-stu-id="79957-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79957-106">左欄</span><span class="sxs-lookup"><span data-stu-id="79957-106">Column</span></span></th>
<th><span data-ttu-id="79957-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="79957-107">Data Type</span></span></th>
<th><span data-ttu-id="79957-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="79957-108">Key/Index</span></span></th>
<th><span data-ttu-id="79957-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="79957-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79957-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="79957-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-111">datetime</span><span class="sxs-lookup"><span data-stu-id="79957-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="79957-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="79957-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="79957-113">會議實例的時間。</span><span class="sxs-lookup"><span data-stu-id="79957-113">Time of conference instance.</span></span> <span data-ttu-id="79957-114">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="79957-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="79957-115">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="79957-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79957-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="79957-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-117">int</span><span class="sxs-lookup"><span data-stu-id="79957-117">int</span></span></p></td>
<td><p><span data-ttu-id="79957-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="79957-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="79957-119">識別會議實例的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="79957-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="79957-120">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="79957-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="79957-121">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="79957-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79957-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="79957-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-123">datetime</span><span class="sxs-lookup"><span data-stu-id="79957-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="79957-124">主要、外部</span><span class="sxs-lookup"><span data-stu-id="79957-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="79957-125">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="79957-125">Time of session request.</span></span> <span data-ttu-id="79957-126">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="79957-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="79957-127">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="79957-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79957-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="79957-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-129">int</span><span class="sxs-lookup"><span data-stu-id="79957-129">int</span></span></p></td>
<td><p><span data-ttu-id="79957-130">主要、外部</span><span class="sxs-lookup"><span data-stu-id="79957-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="79957-131">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="79957-131">ID number to identify the session.</span></span> <span data-ttu-id="79957-132">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="79957-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="79957-133">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="79957-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79957-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="79957-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-135">int</span><span class="sxs-lookup"><span data-stu-id="79957-135">int</span></span></p></td>
<td><p><span data-ttu-id="79957-136">外</span><span class="sxs-lookup"><span data-stu-id="79957-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="79957-137">標識此使用者的唯一編號，從<a href="lync-server-2013-users-table.md">Lync Server 2013 的 [使用者] 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="79957-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79957-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="79957-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-139">int</span><span class="sxs-lookup"><span data-stu-id="79957-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79957-140">如果使用者是同時在多部電腦或裝置上登入，則<strong>UserInstance</strong>會用來唯一識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="79957-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79957-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="79957-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-142">稍微</span><span class="sxs-lookup"><span data-stu-id="79957-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="79957-143">使用者是否已從內部登入。</span><span class="sxs-lookup"><span data-stu-id="79957-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79957-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="79957-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-145">int</span><span class="sxs-lookup"><span data-stu-id="79957-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="79957-146">此使用者在會議中的角色，例如 [簡報者] 或 [出席者]。</span><span class="sxs-lookup"><span data-stu-id="79957-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79957-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="79957-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-148">datetime</span><span class="sxs-lookup"><span data-stu-id="79957-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="79957-149">此使用者加入會議的時間。</span><span class="sxs-lookup"><span data-stu-id="79957-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79957-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="79957-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-151">datetime</span><span class="sxs-lookup"><span data-stu-id="79957-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="79957-152">此使用者離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="79957-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79957-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="79957-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-154">int</span><span class="sxs-lookup"><span data-stu-id="79957-154">int</span></span></p></td>
<td><p><span data-ttu-id="79957-155">外</span><span class="sxs-lookup"><span data-stu-id="79957-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="79957-156">使用者的用戶端軟體版本，<a href="lync-server-2013-clientversions-table.md">在 Lync Server 2013 中參照至 ClientVersions 資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="79957-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79957-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="79957-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="79957-158">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="79957-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79957-159">在會議中使用之端點的全域唯一識別碼（GUID）。</span><span class="sxs-lookup"><span data-stu-id="79957-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="79957-160">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="79957-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

