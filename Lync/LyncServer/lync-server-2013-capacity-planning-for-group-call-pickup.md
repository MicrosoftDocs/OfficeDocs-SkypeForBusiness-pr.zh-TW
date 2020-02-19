---
title: Lync Server 2013： 容量規劃群組來電接聽
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
ms.openlocfilehash: 1ee25eb942a044840fac6aef0f5126f06b03cd9f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="7e223-102">容量規劃的 Lync Server 2013 中的 [群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="7e223-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e223-103">_**上次修改主題：** 2013年-02-12_</span><span class="sxs-lookup"><span data-stu-id="7e223-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="7e223-104">下表說明您可以使用容量規劃需求為基礎的群組來電接聽使用者模型。</span><span class="sxs-lookup"><span data-stu-id="7e223-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e223-105">群組來電接聽為基礎的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="7e223-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="7e223-106">請記住，災害復原容量規劃，配對集區的每個集區應該能夠處理通話駐留服務，包括群組來電接聽，在兩個集區中的工作負載。</span><span class="sxs-lookup"><span data-stu-id="7e223-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="7e223-107">群組通話收取] 目錄的使用者模型</span><span class="sxs-lookup"><span data-stu-id="7e223-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e223-108">評量</span><span class="sxs-lookup"><span data-stu-id="7e223-108">Metric</span></span></th>
<th><span data-ttu-id="7e223-109">每個前端集區 （使用 8 前端伺服器）</span><span class="sxs-lookup"><span data-stu-id="7e223-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="7e223-110">每個 Standard Edition 伺服器</span><span class="sxs-lookup"><span data-stu-id="7e223-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e223-111">建議的每個群組的使用者數目</span><span class="sxs-lookup"><span data-stu-id="7e223-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="7e223-112">50</span><span class="sxs-lookup"><span data-stu-id="7e223-112">50</span></span></p></td>
<td><p><span data-ttu-id="7e223-113">50</span><span class="sxs-lookup"><span data-stu-id="7e223-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e223-114">建議的群組數目</span><span class="sxs-lookup"><span data-stu-id="7e223-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="7e223-115">500</span><span class="sxs-lookup"><span data-stu-id="7e223-115">500</span></span></p></td>
<td><p><span data-ttu-id="7e223-116">60</span><span class="sxs-lookup"><span data-stu-id="7e223-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e223-117">每個啟用群組來電接聽的集區的使用者數目上限</span><span class="sxs-lookup"><span data-stu-id="7e223-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="7e223-118">25,000</span><span class="sxs-lookup"><span data-stu-id="7e223-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="7e223-119">3000</span><span class="sxs-lookup"><span data-stu-id="7e223-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e223-120">來電至群組來電接聽啟用每個每分鐘的集區的使用者總數的最大速率</span><span class="sxs-lookup"><span data-stu-id="7e223-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="7e223-121">500</span><span class="sxs-lookup"><span data-stu-id="7e223-121">500</span></span></p></td>
<td><p><span data-ttu-id="7e223-122">60</span><span class="sxs-lookup"><span data-stu-id="7e223-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e223-123">擷取的每個每分鐘的集區的使用者與群組來電接聽通話的最大速率</span><span class="sxs-lookup"><span data-stu-id="7e223-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="7e223-124">200</span><span class="sxs-lookup"><span data-stu-id="7e223-124">200</span></span></p></td>
<td><p><span data-ttu-id="7e223-125">25</span><span class="sxs-lookup"><span data-stu-id="7e223-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="7e223-126">針對擁有少於八個前端伺服器的前端集區，請以線性方式計算度量。</span><span class="sxs-lookup"><span data-stu-id="7e223-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="7e223-127">例如，如果您的前端集區有一部前端伺服器，計算的最高負載為 1/8 表格中所顯示的值。</span><span class="sxs-lookup"><span data-stu-id="7e223-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="7e223-128">您可以增加或減少建議的每個群組的使用者數目和群組的數目，只要您不能超過的每個集區的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="7e223-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="7e223-129">例如，Standard Edition server 可以有 120 群組有 25 位使用者每個群組，因為仍在使用者模型最大值 （亦即 120 群組次數 25 位使用者為已啟用群組來電接聽 3000 使用者） 是已啟用群組來電接聽的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="7e223-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

