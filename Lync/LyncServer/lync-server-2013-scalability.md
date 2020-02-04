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
ms.openlocfilehash: e6ff4828bdfddbfca7734836fdfdbe24f0b90c4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="55741-102">使用 Lync Server 2013 的延展性</span><span class="sxs-lookup"><span data-stu-id="55741-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55741-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="55741-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="55741-104">Lync Server 提供兩種版本，即企業版和標準版。</span><span class="sxs-lookup"><span data-stu-id="55741-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="55741-105">不同的版本主要用於不同的組織大小。</span><span class="sxs-lookup"><span data-stu-id="55741-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="55741-106">如下表所示，這兩種版本都支援所有工作負載中的所有功能，除了高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="55741-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55741-107">功能</span><span class="sxs-lookup"><span data-stu-id="55741-107">Feature</span></span></th>
<th><span data-ttu-id="55741-108">在企業版中受到支援嗎？</span><span class="sxs-lookup"><span data-stu-id="55741-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="55741-109">在標準版中受到支援嗎？</span><span class="sxs-lookup"><span data-stu-id="55741-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55741-110">立即訊息（IM）與目前狀態</span><span class="sxs-lookup"><span data-stu-id="55741-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="55741-111">是</span><span class="sxs-lookup"><span data-stu-id="55741-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="55741-112">是</span><span class="sxs-lookup"><span data-stu-id="55741-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55741-113">會議</span><span class="sxs-lookup"><span data-stu-id="55741-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="55741-114">是</span><span class="sxs-lookup"><span data-stu-id="55741-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="55741-115">是</span><span class="sxs-lookup"><span data-stu-id="55741-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55741-116">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="55741-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="55741-117">是</span><span class="sxs-lookup"><span data-stu-id="55741-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="55741-118">是</span><span class="sxs-lookup"><span data-stu-id="55741-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55741-119">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="55741-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="55741-120">是</span><span class="sxs-lookup"><span data-stu-id="55741-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="55741-121">是</span><span class="sxs-lookup"><span data-stu-id="55741-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55741-122">企業語音</span><span class="sxs-lookup"><span data-stu-id="55741-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="55741-123">是</span><span class="sxs-lookup"><span data-stu-id="55741-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="55741-124">是</span><span class="sxs-lookup"><span data-stu-id="55741-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55741-125">虛擬</span><span class="sxs-lookup"><span data-stu-id="55741-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="55741-126">是</span><span class="sxs-lookup"><span data-stu-id="55741-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="55741-127">是</span><span class="sxs-lookup"><span data-stu-id="55741-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55741-128">高可用性、容錯移轉及災害復原</span><span class="sxs-lookup"><span data-stu-id="55741-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="55741-129">是</span><span class="sxs-lookup"><span data-stu-id="55741-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="55741-130">否</span><span class="sxs-lookup"><span data-stu-id="55741-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

