---
title: Lync Server 2013：群組呼叫裝貨的容量規劃
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
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="527c1-102">Lync Server 2013 中的群組通話裝貨產能規劃</span><span class="sxs-lookup"><span data-stu-id="527c1-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="527c1-103">_**主題上次修改日期：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="527c1-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="527c1-104">下表說明您可以用來做為容量規劃需求基礎的 [群組呼叫挑選使用者模型]。</span><span class="sxs-lookup"><span data-stu-id="527c1-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="527c1-105">[群組呼叫挑選] 是以 [通話駐留] 應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="527c1-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="527c1-106">請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理通話駐留服務的工作負荷，包括兩個池中的群組呼叫。</span><span class="sxs-lookup"><span data-stu-id="527c1-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="527c1-107">群組呼叫使用者模型</span><span class="sxs-lookup"><span data-stu-id="527c1-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="527c1-108">衡量</span><span class="sxs-lookup"><span data-stu-id="527c1-108">Metric</span></span></th>
<th><span data-ttu-id="527c1-109">每個前臺端池（含8個前端伺服器）</span><span class="sxs-lookup"><span data-stu-id="527c1-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="527c1-110">每個標準版 server</span><span class="sxs-lookup"><span data-stu-id="527c1-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="527c1-111">建議的每個群組使用者數</span><span class="sxs-lookup"><span data-stu-id="527c1-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="527c1-112">50</span><span class="sxs-lookup"><span data-stu-id="527c1-112">50</span></span></p></td>
<td><p><span data-ttu-id="527c1-113">50</span><span class="sxs-lookup"><span data-stu-id="527c1-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="527c1-114">建議的群組數</span><span class="sxs-lookup"><span data-stu-id="527c1-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="527c1-115">500</span><span class="sxs-lookup"><span data-stu-id="527c1-115">500</span></span></p></td>
<td><p><span data-ttu-id="527c1-116">60</span><span class="sxs-lookup"><span data-stu-id="527c1-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="527c1-117">針對群組呼叫挑選啟用的每個池的使用者數目上限</span><span class="sxs-lookup"><span data-stu-id="527c1-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="527c1-118">25000</span><span class="sxs-lookup"><span data-stu-id="527c1-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="527c1-119">3,000</span><span class="sxs-lookup"><span data-stu-id="527c1-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="527c1-120">每分鐘針對每個群組呼叫啟用群組通話的最大來電率</span><span class="sxs-lookup"><span data-stu-id="527c1-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="527c1-121">500</span><span class="sxs-lookup"><span data-stu-id="527c1-121">500</span></span></p></td>
<td><p><span data-ttu-id="527c1-122">60</span><span class="sxs-lookup"><span data-stu-id="527c1-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="527c1-123">每分鐘由每個群組呼叫每個群組的使用者所檢索來電的最大比率</span><span class="sxs-lookup"><span data-stu-id="527c1-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="527c1-124">200</span><span class="sxs-lookup"><span data-stu-id="527c1-124">200</span></span></p></td>
<td><p><span data-ttu-id="527c1-125">位</span><span class="sxs-lookup"><span data-stu-id="527c1-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="527c1-126">對於不超過八個前端伺服器的前端池，請線性地計算度量單位。</span><span class="sxs-lookup"><span data-stu-id="527c1-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="527c1-127">例如，如果您的前端池有一個前端伺服器，請將最大負載計算為表格中顯示的值1/8。</span><span class="sxs-lookup"><span data-stu-id="527c1-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="527c1-128">只要您不超過每個池中的使用者數目上限，您就可以增加或減少每個群組的使用者數和群組數。</span><span class="sxs-lookup"><span data-stu-id="527c1-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="527c1-129">例如，您的標準版伺服器可以有120個群組，每個群組含25個使用者，因為為群組通話挑選啟用的使用者數目仍在使用者模型最大值（也就是，120群組乘以25個3000使用者為群組通話挑選的使用者）。</span><span class="sxs-lookup"><span data-stu-id="527c1-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

