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
ms.openlocfilehash: e75c8079b4093290846321340b21248b9f8882ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="4b799-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="4b799-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b799-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="4b799-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4b799-104">tblADUpdates 表格包含的更新版本的 Active Directory 同步處理步驟尚未處理的 Active Directory 網域服務變更。</span><span class="sxs-lookup"><span data-stu-id="4b799-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="4b799-105">Columns</span><span class="sxs-lookup"><span data-stu-id="4b799-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b799-106">欄</span><span class="sxs-lookup"><span data-stu-id="4b799-106">Column</span></span></th>
<th><span data-ttu-id="4b799-107">類型	</span><span class="sxs-lookup"><span data-stu-id="4b799-107">Type</span></span></th>
<th><span data-ttu-id="4b799-108">描述</span><span class="sxs-lookup"><span data-stu-id="4b799-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b799-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="4b799-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="4b799-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="4b799-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="4b799-111">已變更物件的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="4b799-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b799-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="4b799-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="4b799-113">nvarchar (384)，非 null</span><span class="sxs-lookup"><span data-stu-id="4b799-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="4b799-114">物件的辨別的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b799-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b799-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="4b799-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="4b799-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="4b799-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4b799-117">如果至少一個物件的屬性變更，則為 true。</span><span class="sxs-lookup"><span data-stu-id="4b799-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b799-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="4b799-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="4b799-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="4b799-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4b799-120">如果成員資格變更，則為 true。</span><span class="sxs-lookup"><span data-stu-id="4b799-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b799-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="4b799-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="4b799-122">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="4b799-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4b799-123">不會使用。</span><span class="sxs-lookup"><span data-stu-id="4b799-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b799-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="4b799-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="4b799-125">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="4b799-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4b799-126">如果物件已被刪除，則為 true。</span><span class="sxs-lookup"><span data-stu-id="4b799-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b799-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="4b799-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="4b799-128">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="4b799-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4b799-129">插入列時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="4b799-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

