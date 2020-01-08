---
title: Lync Server 2013：tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="20f33-102">Lync Server 2013 中的 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="20f33-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20f33-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="20f33-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="20f33-104">tblRoleType 是一個靜態查閱表格，其中包含角色類型及其關聯的許可權集。</span><span class="sxs-lookup"><span data-stu-id="20f33-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="20f33-105">分欄</span><span class="sxs-lookup"><span data-stu-id="20f33-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20f33-106">左欄</span><span class="sxs-lookup"><span data-stu-id="20f33-106">Column</span></span></th>
<th><span data-ttu-id="20f33-107">類型</span><span class="sxs-lookup"><span data-stu-id="20f33-107">Type</span></span></th>
<th><span data-ttu-id="20f33-108">描述</span><span class="sxs-lookup"><span data-stu-id="20f33-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20f33-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="20f33-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="20f33-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="20f33-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="20f33-111">角色類型 ID。</span><span class="sxs-lookup"><span data-stu-id="20f33-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20f33-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="20f33-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="20f33-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="20f33-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="20f33-114">角色類型描述。</span><span class="sxs-lookup"><span data-stu-id="20f33-114">Role type description.</span></span> <span data-ttu-id="20f33-115">共有四個可用的角色：</span><span class="sxs-lookup"><span data-stu-id="20f33-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="20f33-116">成員：聊天室成員</span><span class="sxs-lookup"><span data-stu-id="20f33-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="20f33-117">管理員：聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="20f33-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="20f33-118">濁音： auditorium 聊天室的簡報者</span><span class="sxs-lookup"><span data-stu-id="20f33-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="20f33-119">建立者：可以建立聊天室</span><span class="sxs-lookup"><span data-stu-id="20f33-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20f33-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="20f33-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="20f33-121">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="20f33-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="20f33-122">角色的許可權集。</span><span class="sxs-lookup"><span data-stu-id="20f33-122">Permission set for the role.</span></span> <span data-ttu-id="20f33-123">已使用的位數如下：</span><span class="sxs-lookup"><span data-stu-id="20f33-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="20f33-124">2：如果角色可以管理節點，則為 True。</span><span class="sxs-lookup"><span data-stu-id="20f33-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="20f33-125">4：如果角色可以建立子節點，則為 True。</span><span class="sxs-lookup"><span data-stu-id="20f33-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="20f33-126">7：如果角色可以加入聊天室（或類別的子聊天室），則為 True。</span><span class="sxs-lookup"><span data-stu-id="20f33-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="20f33-127">8：如果角色可以在聊天室（或在子類別的 [兒童聊天室] 聊天室）中聊天，則為 True。</span><span class="sxs-lookup"><span data-stu-id="20f33-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="20f33-128">10： True，如果角色可以讀取聊天記錄，即使未加入聊天室也一樣。</span><span class="sxs-lookup"><span data-stu-id="20f33-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="20f33-129">11：如果角色可以查看聊天室，則為 True。</span><span class="sxs-lookup"><span data-stu-id="20f33-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="20f33-130">（例如範圍和可見度等因素進一步改進。）</span><span class="sxs-lookup"><span data-stu-id="20f33-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="20f33-131">12：如果角色可以在 auditorium 聊天室中聊天，則為 True。</span><span class="sxs-lookup"><span data-stu-id="20f33-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="20f33-132">13：如果角色在查看節點時可以略過可見度規則，則為 True。</span><span class="sxs-lookup"><span data-stu-id="20f33-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="20f33-133">機碼</span><span class="sxs-lookup"><span data-stu-id="20f33-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20f33-134">左欄</span><span class="sxs-lookup"><span data-stu-id="20f33-134">Column</span></span></th>
<th><span data-ttu-id="20f33-135">描述</span><span class="sxs-lookup"><span data-stu-id="20f33-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20f33-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="20f33-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="20f33-137">主鍵。</span><span class="sxs-lookup"><span data-stu-id="20f33-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

