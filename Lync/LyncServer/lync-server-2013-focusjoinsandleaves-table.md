---
title: 'Lync Server 2013: FocusJoinsAndLeaves 表格'
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
ms.openlocfilehash: 8e8d37023d30784d07d9ac74ce89aa8cc1fb43a9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="0e3da-102">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="0e3da-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e3da-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="0e3da-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0e3da-104">此表格中的每一筆記錄含有一位使用者加入 CDR 資訊以及離開一場會議資訊。</span><span class="sxs-lookup"><span data-stu-id="0e3da-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="0e3da-105">每個會議代表此表格中一筆記錄的每個使用者加入和離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="0e3da-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e3da-106">欄</span><span class="sxs-lookup"><span data-stu-id="0e3da-106">Column</span></span></th>
<th><span data-ttu-id="0e3da-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="0e3da-107">Data Type</span></span></th>
<th><span data-ttu-id="0e3da-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="0e3da-108">Key/Index</span></span></th>
<th><span data-ttu-id="0e3da-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="0e3da-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e3da-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-111">datetime</span><span class="sxs-lookup"><span data-stu-id="0e3da-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e3da-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="0e3da-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e3da-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="0e3da-113">Time of conference instance.</span></span> <span data-ttu-id="0e3da-114"><strong>SessionIdSeq</strong>搭配使用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="0e3da-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="0e3da-115">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0e3da-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3da-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-117">int</span><span class="sxs-lookup"><span data-stu-id="0e3da-117">int</span></span></p></td>
<td><p><span data-ttu-id="0e3da-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="0e3da-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e3da-119">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="0e3da-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="0e3da-120">搭配<strong>SessionIdTime</strong>用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="0e3da-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="0e3da-121">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0e3da-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3da-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-123">datetime</span><span class="sxs-lookup"><span data-stu-id="0e3da-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e3da-124">主要、外部</span><span class="sxs-lookup"><span data-stu-id="0e3da-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e3da-125">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="0e3da-125">Time of session request.</span></span> <span data-ttu-id="0e3da-126">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="0e3da-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0e3da-127"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0e3da-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3da-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-129">int</span><span class="sxs-lookup"><span data-stu-id="0e3da-129">int</span></span></p></td>
<td><p><span data-ttu-id="0e3da-130">主要，外部</span><span class="sxs-lookup"><span data-stu-id="0e3da-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e3da-131">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e3da-131">ID number to identify the session.</span></span> <span data-ttu-id="0e3da-132">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="0e3da-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0e3da-133"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0e3da-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3da-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-135">int</span><span class="sxs-lookup"><span data-stu-id="0e3da-135">int</span></span></p></td>
<td><p><span data-ttu-id="0e3da-136">Foreign</span><span class="sxs-lookup"><span data-stu-id="0e3da-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e3da-137">用於識別此使用者，參考來源：<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中資料表</a>的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="0e3da-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3da-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-139">int</span><span class="sxs-lookup"><span data-stu-id="0e3da-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e3da-140">如果使用者登入多部電腦或裝置在此同時，會使用<strong>UserInstance</strong>專門識別使用者/裝置組合。</span><span class="sxs-lookup"><span data-stu-id="0e3da-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3da-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-142">位元</span><span class="sxs-lookup"><span data-stu-id="0e3da-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e3da-143">是否使用者登入從內部或不。</span><span class="sxs-lookup"><span data-stu-id="0e3da-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3da-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-145">int</span><span class="sxs-lookup"><span data-stu-id="0e3da-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e3da-146">此使用者的會議中角色，例如簡報者或是出席者。</span><span class="sxs-lookup"><span data-stu-id="0e3da-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3da-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-148">datetime</span><span class="sxs-lookup"><span data-stu-id="0e3da-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e3da-149">此使用者加入會議的時間。</span><span class="sxs-lookup"><span data-stu-id="0e3da-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3da-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-151">datetime</span><span class="sxs-lookup"><span data-stu-id="0e3da-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e3da-152">此使用者離開會議的時間。</span><span class="sxs-lookup"><span data-stu-id="0e3da-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3da-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-154">int</span><span class="sxs-lookup"><span data-stu-id="0e3da-154">int</span></span></p></td>
<td><p><span data-ttu-id="0e3da-155">Foreign</span><span class="sxs-lookup"><span data-stu-id="0e3da-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e3da-156">使用者的用戶端軟體，參照到<a href="lync-server-2013-clientversions-table.md">ClientVersions 表格 Lync Server 2013 中的</a>使用的版本。</span><span class="sxs-lookup"><span data-stu-id="0e3da-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3da-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="0e3da-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e3da-158">唯一</span><span class="sxs-lookup"><span data-stu-id="0e3da-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e3da-159">會議中使用之端點的全域唯一識別碼 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="0e3da-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="0e3da-160">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="0e3da-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

