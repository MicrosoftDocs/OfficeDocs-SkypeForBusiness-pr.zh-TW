---
title: Lync Server 2013： tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd93043a9120a6de5a0f1da6ad3af64a2a6d38f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523720"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="9644f-102">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="9644f-102">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9644f-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="9644f-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="9644f-104">tblPrincipalInvites 包含所有提供給啟動自動邀請的所有節點之佈建使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="9644f-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="9644f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="9644f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9644f-106">欄</span><span class="sxs-lookup"><span data-stu-id="9644f-106">Column</span></span></th>
<th><span data-ttu-id="9644f-107">類型</span><span class="sxs-lookup"><span data-stu-id="9644f-107">Type</span></span></th>
<th><span data-ttu-id="9644f-108">描述</span><span class="sxs-lookup"><span data-stu-id="9644f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9644f-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="9644f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="9644f-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="9644f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9644f-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="9644f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9644f-112">尹雯德</span><span class="sxs-lookup"><span data-stu-id="9644f-112">invID</span></span></p></td>
<td><p><span data-ttu-id="9644f-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="9644f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9644f-114">從 tblLastInviteId 表格產生的唯一序號 (每個主體識別碼)。</span><span class="sxs-lookup"><span data-stu-id="9644f-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9644f-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="9644f-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9644f-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="9644f-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9644f-117">節點識別碼 (僅限聊天室)。</span><span class="sxs-lookup"><span data-stu-id="9644f-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9644f-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="9644f-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="9644f-119">日期時間，非 null</span><span class="sxs-lookup"><span data-stu-id="9644f-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="9644f-120">建立的時間。</span><span class="sxs-lookup"><span data-stu-id="9644f-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9644f-121">索引鍵</span><span class="sxs-lookup"><span data-stu-id="9644f-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9644f-122">欄</span><span class="sxs-lookup"><span data-stu-id="9644f-122">Column</span></span></th>
<th><span data-ttu-id="9644f-123">描述</span><span class="sxs-lookup"><span data-stu-id="9644f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9644f-124">&lt;Tblprincipal.prinid，nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="9644f-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9644f-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9644f-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9644f-126">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="9644f-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="9644f-127">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9644f-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9644f-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="9644f-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9644f-129">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9644f-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

