---
title: Lync Server 2013：tblADUpdates
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
ms.openlocfilehash: cb4b5b73fb74c2337eeaa6b065396253a2cb0be4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="17390-102">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="17390-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17390-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="17390-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="17390-104">tblADUpdates 包含 Active Directory 網域服務的變更，這些變更尚未經過後續的 Active Directory 同步處理步驟使用。</span><span class="sxs-lookup"><span data-stu-id="17390-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="17390-105">分欄</span><span class="sxs-lookup"><span data-stu-id="17390-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17390-106">左欄</span><span class="sxs-lookup"><span data-stu-id="17390-106">Column</span></span></th>
<th><span data-ttu-id="17390-107">類型</span><span class="sxs-lookup"><span data-stu-id="17390-107">Type</span></span></th>
<th><span data-ttu-id="17390-108">說明</span><span class="sxs-lookup"><span data-stu-id="17390-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17390-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="17390-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="17390-110">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="17390-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="17390-111">已變更之物件的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="17390-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17390-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="17390-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="17390-113">Nvarchar （384），not null</span><span class="sxs-lookup"><span data-stu-id="17390-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="17390-114">物件的判別名。</span><span class="sxs-lookup"><span data-stu-id="17390-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17390-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="17390-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="17390-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="17390-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="17390-117">如果物件至少有一個屬性已變更，則為 True。</span><span class="sxs-lookup"><span data-stu-id="17390-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17390-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="17390-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="17390-119">bit、not null</span><span class="sxs-lookup"><span data-stu-id="17390-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="17390-120">如果成員資格變更，則為 True。</span><span class="sxs-lookup"><span data-stu-id="17390-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17390-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="17390-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="17390-122">bit、not null</span><span class="sxs-lookup"><span data-stu-id="17390-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="17390-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="17390-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17390-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="17390-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="17390-125">bit、not null</span><span class="sxs-lookup"><span data-stu-id="17390-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="17390-126">如果已刪除物件，則為 True。</span><span class="sxs-lookup"><span data-stu-id="17390-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17390-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="17390-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="17390-128">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="17390-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="17390-129">插入列的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="17390-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

