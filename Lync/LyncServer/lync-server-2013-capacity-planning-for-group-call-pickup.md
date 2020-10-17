---
title: Lync Server 2013：群組呼叫收取的容量規劃
description: Lync Server 2013：群組呼叫收取的容量規劃。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12648c57d1036a0ed27c60ef6399bf570c5dcd3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544529"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="251e1-103">Lync Server 2013 中群組呼叫收取的容量規劃</span><span class="sxs-lookup"><span data-stu-id="251e1-103">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="251e1-104">_**主題上次修改日期：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="251e1-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="251e1-105">下表說明您可以用來作為容量規劃需求基礎的群組呼叫收取使用者模型。</span><span class="sxs-lookup"><span data-stu-id="251e1-105">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="251e1-106">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="251e1-106">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="251e1-107">請記住，針對嚴重損壞修復容量規劃，成對集區的每個集區都應該可以處理通話駐留服務的工作負載，包括兩個集區中的群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="251e1-107">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="251e1-108">群組呼叫收取使用者模型</span><span class="sxs-lookup"><span data-stu-id="251e1-108">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="251e1-109">計量</span><span class="sxs-lookup"><span data-stu-id="251e1-109">Metric</span></span></th>
<th><span data-ttu-id="251e1-110">每個前端伺服器集區 (8 部前端伺服器) </span><span class="sxs-lookup"><span data-stu-id="251e1-110">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="251e1-111">每個 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="251e1-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="251e1-112">每個群組的使用者建議數量</span><span class="sxs-lookup"><span data-stu-id="251e1-112">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="251e1-113">50</span><span class="sxs-lookup"><span data-stu-id="251e1-113">50</span></span></p></td>
<td><p><span data-ttu-id="251e1-114">50</span><span class="sxs-lookup"><span data-stu-id="251e1-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251e1-115">建議的群組數目</span><span class="sxs-lookup"><span data-stu-id="251e1-115">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="251e1-116">500</span><span class="sxs-lookup"><span data-stu-id="251e1-116">500</span></span></p></td>
<td><p><span data-ttu-id="251e1-117">60</span><span class="sxs-lookup"><span data-stu-id="251e1-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251e1-118">群組呼叫收取啟用每個集區的使用者數目上限</span><span class="sxs-lookup"><span data-stu-id="251e1-118">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="251e1-119">25,000</span><span class="sxs-lookup"><span data-stu-id="251e1-119">25,000</span></span></p></td>
<td><p><span data-ttu-id="251e1-120">3000</span><span class="sxs-lookup"><span data-stu-id="251e1-120">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251e1-121">每分鐘針對每個集區啟用群組來電收取的總來電數上限</span><span class="sxs-lookup"><span data-stu-id="251e1-121">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="251e1-122">500</span><span class="sxs-lookup"><span data-stu-id="251e1-122">500</span></span></p></td>
<td><p><span data-ttu-id="251e1-123">60</span><span class="sxs-lookup"><span data-stu-id="251e1-123">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251e1-124">每分鐘由使用者每個集區呼叫一次，每個集區的呼叫率上限</span><span class="sxs-lookup"><span data-stu-id="251e1-124">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="251e1-125">200</span><span class="sxs-lookup"><span data-stu-id="251e1-125">200</span></span></p></td>
<td><p><span data-ttu-id="251e1-126">0.25</span><span class="sxs-lookup"><span data-stu-id="251e1-126">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="251e1-127">前端伺服器的前端集區少於8部，以線性方式計算度量。</span><span class="sxs-lookup"><span data-stu-id="251e1-127">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="251e1-128">例如，如果您的前端集區有一部前端伺服器，請將表格中所顯示的值的最大負載計算為1/8。</span><span class="sxs-lookup"><span data-stu-id="251e1-128">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="251e1-129">您可以增加或減少每個群組的使用者人數和群組數目，只要您不要超過每個集區的最大使用者數目。</span><span class="sxs-lookup"><span data-stu-id="251e1-129">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="251e1-130">例如，您的 Standard Edition server 可以每個群組有25位使用者的120群組，因為為群組呼叫收取的使用者人數仍然在使用者模型中的最大 (，也就是120群組乘以25位3000使用者為使用者啟用群組呼叫收取) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="251e1-130">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

