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
ms.openlocfilehash: ad3ef2afaa162219d140a4eaef204dc6e1e2ab02
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="524c9-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="524c9-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="524c9-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="524c9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="524c9-104">tblADUpdates 表格包含的更新版本的 Active Directory 同步處理步驟尚未處理的 Active Directory 網域服務變更。</span><span class="sxs-lookup"><span data-stu-id="524c9-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="524c9-105">Columns</span><span class="sxs-lookup"><span data-stu-id="524c9-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="524c9-106">欄</span><span class="sxs-lookup"><span data-stu-id="524c9-106">Column</span></span></th>
<th><span data-ttu-id="524c9-107">類型	</span><span class="sxs-lookup"><span data-stu-id="524c9-107">Type</span></span></th>
<th><span data-ttu-id="524c9-108">描述</span><span class="sxs-lookup"><span data-stu-id="524c9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="524c9-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="524c9-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="524c9-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="524c9-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="524c9-111">已變更物件的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="524c9-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="524c9-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="524c9-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="524c9-113">nvarchar (384)，非 null</span><span class="sxs-lookup"><span data-stu-id="524c9-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="524c9-114">物件的辨別的名稱。</span><span class="sxs-lookup"><span data-stu-id="524c9-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="524c9-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="524c9-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="524c9-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="524c9-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="524c9-117">如果至少一個物件的屬性變更，則為 true。</span><span class="sxs-lookup"><span data-stu-id="524c9-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="524c9-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="524c9-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="524c9-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="524c9-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="524c9-120">如果成員資格變更，則為 true。</span><span class="sxs-lookup"><span data-stu-id="524c9-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="524c9-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="524c9-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="524c9-122">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="524c9-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="524c9-123">不會使用。</span><span class="sxs-lookup"><span data-stu-id="524c9-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="524c9-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="524c9-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="524c9-125">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="524c9-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="524c9-126">如果物件已被刪除，則為 true。</span><span class="sxs-lookup"><span data-stu-id="524c9-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="524c9-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="524c9-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="524c9-128">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="524c9-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="524c9-129">插入列時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="524c9-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

