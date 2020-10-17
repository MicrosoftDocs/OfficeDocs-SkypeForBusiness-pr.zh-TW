---
title: Lync Server 2013： tblRoleType
description: Lync Server 2013： tblRoleType。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f458259acaee7821d5f6a7339b993c70fe65f595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568539"
---
# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="90ab9-103">Lync Server 2013 中的 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="90ab9-103">tblRoleType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90ab9-104">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="90ab9-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="90ab9-105">tblRoleType 表格是一種靜態查閱表格，其中含有角色類型與其相關的權限組。</span><span class="sxs-lookup"><span data-stu-id="90ab9-105">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="90ab9-106">Columns</span><span class="sxs-lookup"><span data-stu-id="90ab9-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90ab9-107">欄</span><span class="sxs-lookup"><span data-stu-id="90ab9-107">Column</span></span></th>
<th><span data-ttu-id="90ab9-108">類型</span><span class="sxs-lookup"><span data-stu-id="90ab9-108">Type</span></span></th>
<th><span data-ttu-id="90ab9-109">描述</span><span class="sxs-lookup"><span data-stu-id="90ab9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ab9-110">rtypeID</span><span class="sxs-lookup"><span data-stu-id="90ab9-110">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="90ab9-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="90ab9-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="90ab9-112">角色類型識別碼。</span><span class="sxs-lookup"><span data-stu-id="90ab9-112">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90ab9-113">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="90ab9-113">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="90ab9-114">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="90ab9-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="90ab9-p101">角色類型描述。以下是四個可用的角色：</span><span class="sxs-lookup"><span data-stu-id="90ab9-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="90ab9-117">Member：聊天室成員</span><span class="sxs-lookup"><span data-stu-id="90ab9-117">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="90ab9-118">Manager：聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="90ab9-118">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="90ab9-119">Voiced：視聽中心聊天室簡報者</span><span class="sxs-lookup"><span data-stu-id="90ab9-119">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="90ab9-120">Creator：可建立聊天室</span><span class="sxs-lookup"><span data-stu-id="90ab9-120">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90ab9-121">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="90ab9-121">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="90ab9-122">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="90ab9-122">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="90ab9-p102">角色的權限組。使用的位元如下：</span><span class="sxs-lookup"><span data-stu-id="90ab9-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="90ab9-125">2: 若角色可管理節點則為 True。</span><span class="sxs-lookup"><span data-stu-id="90ab9-125">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="90ab9-126">4: 若角色可建立子節點則為 True。</span><span class="sxs-lookup"><span data-stu-id="90ab9-126">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="90ab9-127">7: 若角色可加入聊天室 (或類別的子聊天室) 則為 True。</span><span class="sxs-lookup"><span data-stu-id="90ab9-127">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="90ab9-128">8: 若角色可在聊天室 (或類別的子聊天室) 中交談則為 True。</span><span class="sxs-lookup"><span data-stu-id="90ab9-128">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="90ab9-129">10: 若角色可讀取聊天記錄則為 True (即使未加入聊天室時亦可)。</span><span class="sxs-lookup"><span data-stu-id="90ab9-129">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="90ab9-p103">11: 若角色可看到聊天室則為 True (可進一步依據範圍和可見度等因素來調整)。</span><span class="sxs-lookup"><span data-stu-id="90ab9-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="90ab9-132">12: 若角色可在視聽中心聊天室中交談則為 True。</span><span class="sxs-lookup"><span data-stu-id="90ab9-132">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="90ab9-133">13: 若角色可在檢視節點時略過可見度規則則為 True。</span><span class="sxs-lookup"><span data-stu-id="90ab9-133">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="90ab9-134">索引鍵</span><span class="sxs-lookup"><span data-stu-id="90ab9-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90ab9-135">欄</span><span class="sxs-lookup"><span data-stu-id="90ab9-135">Column</span></span></th>
<th><span data-ttu-id="90ab9-136">描述</span><span class="sxs-lookup"><span data-stu-id="90ab9-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90ab9-137">rtypeID</span><span class="sxs-lookup"><span data-stu-id="90ab9-137">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="90ab9-138">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="90ab9-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

