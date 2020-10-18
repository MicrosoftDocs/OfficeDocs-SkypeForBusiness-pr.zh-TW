---
title: Lync Server 2013： tblADUpdates
description: Lync Server 2013： tblADUpdates。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573679"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="f4ea9-103">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="f4ea9-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4ea9-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f4ea9-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f4ea9-105">tblADUpdates 包含後續 Active Directory 同步步驟尚未處理的 Active Directory 網域服務變更。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="f4ea9-106">Columns</span><span class="sxs-lookup"><span data-stu-id="f4ea9-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4ea9-107">欄</span><span class="sxs-lookup"><span data-stu-id="f4ea9-107">Column</span></span></th>
<th><span data-ttu-id="f4ea9-108">類型</span><span class="sxs-lookup"><span data-stu-id="f4ea9-108">Type</span></span></th>
<th><span data-ttu-id="f4ea9-109">描述</span><span class="sxs-lookup"><span data-stu-id="f4ea9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4ea9-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f4ea9-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-111">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="f4ea9-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-112">已變更之物件的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4ea9-113">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f4ea9-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-114">Nvarchar (384) ，非 null</span><span class="sxs-lookup"><span data-stu-id="f4ea9-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-115">物件的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4ea9-116">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="f4ea9-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-117">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="f4ea9-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-118">True 是表示如果物件的至少一個屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4ea9-119">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="f4ea9-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-120">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="f4ea9-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-121">True 是表示如果成員資格變更。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4ea9-122">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="f4ea9-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-123">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="f4ea9-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-124">不會使用。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4ea9-125">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f4ea9-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-126">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="f4ea9-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-127">True 是表示如果物件已刪除。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4ea9-128">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="f4ea9-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-129">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="f4ea9-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ea9-130">插入列時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="f4ea9-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

