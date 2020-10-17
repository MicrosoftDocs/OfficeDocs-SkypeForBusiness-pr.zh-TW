---
title: Lync Server 2013：通話駐留的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 079d1517afa72eeff607920d86b093ac01d673de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512830"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="4950e-102">Lync Server 2013 中通話駐留的容量規劃</span><span class="sxs-lookup"><span data-stu-id="4950e-102">Capacity planning for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4950e-103">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="4950e-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="4950e-104">下表說明您可以用來作為容量規劃需求基礎的通話駐留使用者模型。</span><span class="sxs-lookup"><span data-stu-id="4950e-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4950e-105">請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中的通話駐留服務工作負載。</span><span class="sxs-lookup"><span data-stu-id="4950e-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="4950e-106">通話駐留使用者模型</span><span class="sxs-lookup"><span data-stu-id="4950e-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4950e-107">計量</span><span class="sxs-lookup"><span data-stu-id="4950e-107">Metric</span></span></th>
<th><span data-ttu-id="4950e-108">每個前端伺服器集區 (8 部前端伺服器) </span><span class="sxs-lookup"><span data-stu-id="4950e-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="4950e-109">每個 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="4950e-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4950e-110">駐留率</span><span class="sxs-lookup"><span data-stu-id="4950e-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="4950e-111">每分鐘 8 個</span><span class="sxs-lookup"><span data-stu-id="4950e-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="4950e-112">每分鐘 1 個</span><span class="sxs-lookup"><span data-stu-id="4950e-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4950e-113">擷取駐留通話率</span><span class="sxs-lookup"><span data-stu-id="4950e-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="4950e-114">每分鐘 8 個</span><span class="sxs-lookup"><span data-stu-id="4950e-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="4950e-115">每分鐘 1 個</span><span class="sxs-lookup"><span data-stu-id="4950e-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4950e-116">平均駐留持續時間</span><span class="sxs-lookup"><span data-stu-id="4950e-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="4950e-117">60 秒</span><span class="sxs-lookup"><span data-stu-id="4950e-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="4950e-118">60 秒</span><span class="sxs-lookup"><span data-stu-id="4950e-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

