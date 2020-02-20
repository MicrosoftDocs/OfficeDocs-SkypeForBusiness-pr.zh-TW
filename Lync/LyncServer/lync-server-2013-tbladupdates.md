---
title: 'Lync Server 2013: tblADUpdates'
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
ms.openlocfilehash: ee3f0d881e26c3d26773b1b59feca3d1d02665dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="315f2-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="315f2-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="315f2-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="315f2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="315f2-104">tblADUpdates 表格包含的更新版本的 Active Directory 同步處理步驟尚未處理的 Active Directory 網域服務變更。</span><span class="sxs-lookup"><span data-stu-id="315f2-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="315f2-105">Columns</span><span class="sxs-lookup"><span data-stu-id="315f2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="315f2-106">欄</span><span class="sxs-lookup"><span data-stu-id="315f2-106">Column</span></span></th>
<th><span data-ttu-id="315f2-107">類型	</span><span class="sxs-lookup"><span data-stu-id="315f2-107">Type</span></span></th>
<th><span data-ttu-id="315f2-108">描述</span><span class="sxs-lookup"><span data-stu-id="315f2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="315f2-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="315f2-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="315f2-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="315f2-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="315f2-111">已變更物件的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="315f2-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315f2-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="315f2-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="315f2-113">nvarchar (384)，非 null</span><span class="sxs-lookup"><span data-stu-id="315f2-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="315f2-114">物件的辨別的名稱。</span><span class="sxs-lookup"><span data-stu-id="315f2-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="315f2-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="315f2-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="315f2-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="315f2-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="315f2-117">如果至少一個物件的屬性變更，則為 true。</span><span class="sxs-lookup"><span data-stu-id="315f2-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315f2-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="315f2-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="315f2-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="315f2-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="315f2-120">如果成員資格變更，則為 true。</span><span class="sxs-lookup"><span data-stu-id="315f2-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="315f2-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="315f2-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="315f2-122">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="315f2-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="315f2-123">不會使用。</span><span class="sxs-lookup"><span data-stu-id="315f2-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315f2-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="315f2-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="315f2-125">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="315f2-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="315f2-126">如果物件已被刪除，則為 true。</span><span class="sxs-lookup"><span data-stu-id="315f2-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="315f2-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="315f2-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="315f2-128">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="315f2-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="315f2-129">插入列時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="315f2-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

