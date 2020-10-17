---
title: Lync Server 2013 可擴充性
description: Lync Server 2013 可擴充性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543789"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="72e77-103">可擴充性搭配 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e77-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72e77-104">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="72e77-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="72e77-105">Lync Server 是在兩個版本的 Enterprise Edition 和 Standard Edition 中提供。</span><span class="sxs-lookup"><span data-stu-id="72e77-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="72e77-106">不同版本主要適用於不同規模的組織。</span><span class="sxs-lookup"><span data-stu-id="72e77-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="72e77-107">如下表所示，兩種版本都支援除高可用性和災害復原外的所有工作負載中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="72e77-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72e77-108">功能</span><span class="sxs-lookup"><span data-stu-id="72e77-108">Feature</span></span></th>
<th><span data-ttu-id="72e77-109">Enterprise Edition 是否支援？</span><span class="sxs-lookup"><span data-stu-id="72e77-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="72e77-110">Standard Edition 是否支援？</span><span class="sxs-lookup"><span data-stu-id="72e77-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72e77-111">立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="72e77-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="72e77-112">是</span><span class="sxs-lookup"><span data-stu-id="72e77-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="72e77-113">是</span><span class="sxs-lookup"><span data-stu-id="72e77-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e77-114">會議</span><span class="sxs-lookup"><span data-stu-id="72e77-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="72e77-115">是</span><span class="sxs-lookup"><span data-stu-id="72e77-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="72e77-116">是</span><span class="sxs-lookup"><span data-stu-id="72e77-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72e77-117">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="72e77-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="72e77-118">是</span><span class="sxs-lookup"><span data-stu-id="72e77-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="72e77-119">是</span><span class="sxs-lookup"><span data-stu-id="72e77-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e77-120">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="72e77-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="72e77-121">是</span><span class="sxs-lookup"><span data-stu-id="72e77-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="72e77-122">是</span><span class="sxs-lookup"><span data-stu-id="72e77-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72e77-123">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="72e77-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="72e77-124">是</span><span class="sxs-lookup"><span data-stu-id="72e77-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="72e77-125">是</span><span class="sxs-lookup"><span data-stu-id="72e77-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e77-126">虛擬化</span><span class="sxs-lookup"><span data-stu-id="72e77-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="72e77-127">是</span><span class="sxs-lookup"><span data-stu-id="72e77-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="72e77-128">是</span><span class="sxs-lookup"><span data-stu-id="72e77-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72e77-129">高可用性、容錯移轉及災害復原</span><span class="sxs-lookup"><span data-stu-id="72e77-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="72e77-130">是</span><span class="sxs-lookup"><span data-stu-id="72e77-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="72e77-131">否</span><span class="sxs-lookup"><span data-stu-id="72e77-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

