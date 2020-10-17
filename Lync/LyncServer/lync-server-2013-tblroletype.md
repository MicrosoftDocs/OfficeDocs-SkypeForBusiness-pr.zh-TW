---
title: Lync Server 2013： tblRoleType
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
ms.openlocfilehash: fc32fe1142094d750b947a789b1e8c473eac8937
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536300"
---
# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="8e37f-102">Lync Server 2013 中的 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="8e37f-102">tblRoleType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e37f-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8e37f-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8e37f-104">tblRoleType 表格是一種靜態查閱表格，其中含有角色類型與其相關的權限組。</span><span class="sxs-lookup"><span data-stu-id="8e37f-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="8e37f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="8e37f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e37f-106">欄</span><span class="sxs-lookup"><span data-stu-id="8e37f-106">Column</span></span></th>
<th><span data-ttu-id="8e37f-107">類型</span><span class="sxs-lookup"><span data-stu-id="8e37f-107">Type</span></span></th>
<th><span data-ttu-id="8e37f-108">描述</span><span class="sxs-lookup"><span data-stu-id="8e37f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e37f-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="8e37f-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="8e37f-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="8e37f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8e37f-111">角色類型識別碼。</span><span class="sxs-lookup"><span data-stu-id="8e37f-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e37f-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="8e37f-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="8e37f-113">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="8e37f-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="8e37f-p101">角色類型描述。以下是四個可用的角色：</span><span class="sxs-lookup"><span data-stu-id="8e37f-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e37f-116">Member：聊天室成員</span><span class="sxs-lookup"><span data-stu-id="8e37f-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="8e37f-117">Manager：聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="8e37f-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="8e37f-118">Voiced：視聽中心聊天室簡報者</span><span class="sxs-lookup"><span data-stu-id="8e37f-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="8e37f-119">Creator：可建立聊天室</span><span class="sxs-lookup"><span data-stu-id="8e37f-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e37f-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="8e37f-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="8e37f-121">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="8e37f-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="8e37f-p102">角色的權限組。使用的位元如下：</span><span class="sxs-lookup"><span data-stu-id="8e37f-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e37f-124">2: 若角色可管理節點則為 True。</span><span class="sxs-lookup"><span data-stu-id="8e37f-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="8e37f-125">4: 若角色可建立子節點則為 True。</span><span class="sxs-lookup"><span data-stu-id="8e37f-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="8e37f-126">7: 若角色可加入聊天室 (或類別的子聊天室) 則為 True。</span><span class="sxs-lookup"><span data-stu-id="8e37f-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="8e37f-127">8: 若角色可在聊天室 (或類別的子聊天室) 中交談則為 True。</span><span class="sxs-lookup"><span data-stu-id="8e37f-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="8e37f-128">10: 若角色可讀取聊天記錄則為 True (即使未加入聊天室時亦可)。</span><span class="sxs-lookup"><span data-stu-id="8e37f-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="8e37f-p103">11: 若角色可看到聊天室則為 True (可進一步依據範圍和可見度等因素來調整)。</span><span class="sxs-lookup"><span data-stu-id="8e37f-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="8e37f-131">12: 若角色可在視聽中心聊天室中交談則為 True。</span><span class="sxs-lookup"><span data-stu-id="8e37f-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="8e37f-132">13: 若角色可在檢視節點時略過可見度規則則為 True。</span><span class="sxs-lookup"><span data-stu-id="8e37f-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="8e37f-133">索引鍵</span><span class="sxs-lookup"><span data-stu-id="8e37f-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e37f-134">欄</span><span class="sxs-lookup"><span data-stu-id="8e37f-134">Column</span></span></th>
<th><span data-ttu-id="8e37f-135">描述</span><span class="sxs-lookup"><span data-stu-id="8e37f-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e37f-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="8e37f-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="8e37f-137">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="8e37f-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

