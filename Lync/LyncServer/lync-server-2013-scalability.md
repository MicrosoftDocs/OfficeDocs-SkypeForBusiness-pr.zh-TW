---
title: Lync Server 2013 可擴充性
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
ms.openlocfilehash: d2b26f8f7b7b254a8576a08e9b24fdeb2da633b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510956"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="6880d-102">可擴充性搭配 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6880d-102">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6880d-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="6880d-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="6880d-104">Lync Server 是在兩個版本的 Enterprise Edition 和 Standard Edition 中提供。</span><span class="sxs-lookup"><span data-stu-id="6880d-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="6880d-105">不同版本主要適用於不同規模的組織。</span><span class="sxs-lookup"><span data-stu-id="6880d-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="6880d-106">如下表所示，兩種版本都支援除高可用性和災害復原外的所有工作負載中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="6880d-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6880d-107">功能</span><span class="sxs-lookup"><span data-stu-id="6880d-107">Feature</span></span></th>
<th><span data-ttu-id="6880d-108">Enterprise Edition 是否支援？</span><span class="sxs-lookup"><span data-stu-id="6880d-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="6880d-109">Standard Edition 是否支援？</span><span class="sxs-lookup"><span data-stu-id="6880d-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6880d-110">立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="6880d-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="6880d-111">是</span><span class="sxs-lookup"><span data-stu-id="6880d-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="6880d-112">是</span><span class="sxs-lookup"><span data-stu-id="6880d-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6880d-113">會議</span><span class="sxs-lookup"><span data-stu-id="6880d-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="6880d-114">是</span><span class="sxs-lookup"><span data-stu-id="6880d-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="6880d-115">是</span><span class="sxs-lookup"><span data-stu-id="6880d-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6880d-116">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="6880d-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="6880d-117">是</span><span class="sxs-lookup"><span data-stu-id="6880d-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="6880d-118">是</span><span class="sxs-lookup"><span data-stu-id="6880d-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6880d-119">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="6880d-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="6880d-120">是</span><span class="sxs-lookup"><span data-stu-id="6880d-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="6880d-121">是</span><span class="sxs-lookup"><span data-stu-id="6880d-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6880d-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6880d-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="6880d-123">是</span><span class="sxs-lookup"><span data-stu-id="6880d-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="6880d-124">是</span><span class="sxs-lookup"><span data-stu-id="6880d-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6880d-125">虛擬化</span><span class="sxs-lookup"><span data-stu-id="6880d-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="6880d-126">是</span><span class="sxs-lookup"><span data-stu-id="6880d-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="6880d-127">是</span><span class="sxs-lookup"><span data-stu-id="6880d-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6880d-128">高可用性、容錯移轉及災害復原</span><span class="sxs-lookup"><span data-stu-id="6880d-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="6880d-129">是</span><span class="sxs-lookup"><span data-stu-id="6880d-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="6880d-130">否</span><span class="sxs-lookup"><span data-stu-id="6880d-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

