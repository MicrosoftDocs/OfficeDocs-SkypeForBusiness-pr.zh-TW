---
title: Lync Server 2013 延展性
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
ms.openlocfilehash: 130b1958b418aa2b09e572f137598487dc2c3401
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="f4a9c-102">搭配 Lync Server 2013 的延展性</span><span class="sxs-lookup"><span data-stu-id="f4a9c-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4a9c-103">_**主題上次修改日期：** 2012年-06-25_</span><span class="sxs-lookup"><span data-stu-id="f4a9c-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f4a9c-104">Lync Server 被提供兩種版本，Enterprise Edition 與 Standard Edition。</span><span class="sxs-lookup"><span data-stu-id="f4a9c-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="f4a9c-105">不同版本主要適用於不同規模的組織。</span><span class="sxs-lookup"><span data-stu-id="f4a9c-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="f4a9c-106">如下表所示，兩種版本都支援除高可用性和災害復原外的所有工作負載中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="f4a9c-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4a9c-107">功能</span><span class="sxs-lookup"><span data-stu-id="f4a9c-107">Feature</span></span></th>
<th><span data-ttu-id="f4a9c-108">Enterprise Edition 是否支援？</span><span class="sxs-lookup"><span data-stu-id="f4a9c-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="f4a9c-109">Standard Edition 是否支援？</span><span class="sxs-lookup"><span data-stu-id="f4a9c-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4a9c-110">立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="f4a9c-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-111">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-112">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4a9c-113">會議</span><span class="sxs-lookup"><span data-stu-id="f4a9c-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-114">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-115">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4a9c-116">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="f4a9c-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-117">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-118">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4a9c-119">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="f4a9c-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-120">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-121">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4a9c-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f4a9c-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-123">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-124">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4a9c-125">虛擬化</span><span class="sxs-lookup"><span data-stu-id="f4a9c-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-126">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-127">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4a9c-128">高可用性、容錯移轉及災害復原</span><span class="sxs-lookup"><span data-stu-id="f4a9c-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-129">是</span><span class="sxs-lookup"><span data-stu-id="f4a9c-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="f4a9c-130">否</span><span class="sxs-lookup"><span data-stu-id="f4a9c-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

