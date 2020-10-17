---
title: Lync Server 2013： tblADUpdates
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
ms.openlocfilehash: 27fbbc6bb2fe68c2f4bfff91b999934069548d00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509480"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="d02ff-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="d02ff-102">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d02ff-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d02ff-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d02ff-104">tblADUpdates 包含後續 Active Directory 同步步驟尚未處理的 Active Directory 網域服務變更。</span><span class="sxs-lookup"><span data-stu-id="d02ff-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="d02ff-105">Columns</span><span class="sxs-lookup"><span data-stu-id="d02ff-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d02ff-106">欄</span><span class="sxs-lookup"><span data-stu-id="d02ff-106">Column</span></span></th>
<th><span data-ttu-id="d02ff-107">類型</span><span class="sxs-lookup"><span data-stu-id="d02ff-107">Type</span></span></th>
<th><span data-ttu-id="d02ff-108">描述</span><span class="sxs-lookup"><span data-stu-id="d02ff-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d02ff-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d02ff-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="d02ff-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="d02ff-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d02ff-111">已變更之物件的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="d02ff-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d02ff-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="d02ff-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="d02ff-113">Nvarchar (384) ，非 null</span><span class="sxs-lookup"><span data-stu-id="d02ff-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="d02ff-114">物件的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="d02ff-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d02ff-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="d02ff-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="d02ff-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="d02ff-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d02ff-117">True 是表示如果物件的至少一個屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="d02ff-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d02ff-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="d02ff-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="d02ff-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="d02ff-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d02ff-120">True 是表示如果成員資格變更。</span><span class="sxs-lookup"><span data-stu-id="d02ff-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d02ff-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="d02ff-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="d02ff-122">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="d02ff-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d02ff-123">不會使用。</span><span class="sxs-lookup"><span data-stu-id="d02ff-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d02ff-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d02ff-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="d02ff-125">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="d02ff-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d02ff-126">True 是表示如果物件已刪除。</span><span class="sxs-lookup"><span data-stu-id="d02ff-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d02ff-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="d02ff-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="d02ff-128">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="d02ff-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="d02ff-129">插入列時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d02ff-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

