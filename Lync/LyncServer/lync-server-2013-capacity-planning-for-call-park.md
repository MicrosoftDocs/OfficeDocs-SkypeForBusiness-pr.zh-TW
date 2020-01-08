---
title: Lync Server 2013：通話駐留的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe55e09c67e62676202def9e3def3454d7cbd33
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="cc42b-102">Lync Server 2013 中通話駐留的容量規劃</span><span class="sxs-lookup"><span data-stu-id="cc42b-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc42b-103">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="cc42b-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="cc42b-104">下表說明您可以用來做為容量規劃需求基礎的通話駐留使用者模型。</span><span class="sxs-lookup"><span data-stu-id="cc42b-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc42b-105">請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理兩個池中的通話駐留服務的工作負荷。</span><span class="sxs-lookup"><span data-stu-id="cc42b-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="cc42b-106">通話駐留使用者模型</span><span class="sxs-lookup"><span data-stu-id="cc42b-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc42b-107">衡量</span><span class="sxs-lookup"><span data-stu-id="cc42b-107">Metric</span></span></th>
<th><span data-ttu-id="cc42b-108">每個前臺端池（含8個前端伺服器）</span><span class="sxs-lookup"><span data-stu-id="cc42b-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="cc42b-109">每個標準版 server</span><span class="sxs-lookup"><span data-stu-id="cc42b-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc42b-110">公園工資率</span><span class="sxs-lookup"><span data-stu-id="cc42b-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="cc42b-111">每分鐘8筆</span><span class="sxs-lookup"><span data-stu-id="cc42b-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="cc42b-112">每分鐘1</span><span class="sxs-lookup"><span data-stu-id="cc42b-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc42b-113">檢索暫停的通話頻率</span><span class="sxs-lookup"><span data-stu-id="cc42b-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="cc42b-114">每分鐘8筆</span><span class="sxs-lookup"><span data-stu-id="cc42b-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="cc42b-115">每分鐘1</span><span class="sxs-lookup"><span data-stu-id="cc42b-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc42b-116">平均公園持續時間</span><span class="sxs-lookup"><span data-stu-id="cc42b-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="cc42b-117">60秒</span><span class="sxs-lookup"><span data-stu-id="cc42b-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="cc42b-118">60秒</span><span class="sxs-lookup"><span data-stu-id="cc42b-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

