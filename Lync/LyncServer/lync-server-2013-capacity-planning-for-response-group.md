---
title: Lync Server 2013：回應群組的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="1ec89-102">Lync Server 2013 中的回應群組的容量規劃</span><span class="sxs-lookup"><span data-stu-id="1ec89-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ec89-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1ec89-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="1ec89-104">下表說明您可以用來做為容量規劃需求基礎的 [回應群組] 使用者模型。</span><span class="sxs-lookup"><span data-stu-id="1ec89-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ec89-105">下表中的數位假設您針對所有回應群組音訊檔案使用 16 kHz、單聲道、16位波（.wav）檔案。</span><span class="sxs-lookup"><span data-stu-id="1ec89-105">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="1ec89-106">如果您使用其他檔案格式（例如，Windows Media Audio （.wma）），這些數位可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="1ec89-106">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ec89-107">請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理兩個池中所有回應群組的工作量。</span><span class="sxs-lookup"><span data-stu-id="1ec89-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="1ec89-108">回應群組使用者模型</span><span class="sxs-lookup"><span data-stu-id="1ec89-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ec89-109">衡量</span><span class="sxs-lookup"><span data-stu-id="1ec89-109">Metric</span></span></th>
<th><span data-ttu-id="1ec89-110">每個企業版池（含8個前端伺服器）</span><span class="sxs-lookup"><span data-stu-id="1ec89-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="1ec89-111">每個標準版 server</span><span class="sxs-lookup"><span data-stu-id="1ec89-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ec89-112">每秒來電數</span><span class="sxs-lookup"><span data-stu-id="1ec89-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="1ec89-113">位</span><span class="sxs-lookup"><span data-stu-id="1ec89-113">16</span></span></p></td>
<td><p><span data-ttu-id="1ec89-114">pplx-2</span><span class="sxs-lookup"><span data-stu-id="1ec89-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ec89-115">連線到 IVR 或 MoH 的並行呼叫</span><span class="sxs-lookup"><span data-stu-id="1ec89-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="1ec89-116">480</span><span class="sxs-lookup"><span data-stu-id="1ec89-116">480</span></span></p></td>
<td><p><span data-ttu-id="1ec89-117">60</span><span class="sxs-lookup"><span data-stu-id="1ec89-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ec89-118">並行匿名會話（無 IM）</span><span class="sxs-lookup"><span data-stu-id="1ec89-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="1ec89-119">224</span><span class="sxs-lookup"><span data-stu-id="1ec89-119">224</span></span></p></td>
<td><p><span data-ttu-id="1ec89-120">28</span><span class="sxs-lookup"><span data-stu-id="1ec89-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ec89-121">並行匿名會話（與 IM）</span><span class="sxs-lookup"><span data-stu-id="1ec89-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="1ec89-122">64</span><span class="sxs-lookup"><span data-stu-id="1ec89-122">64</span></span></p></td>
<td><p><span data-ttu-id="1ec89-123">型</span><span class="sxs-lookup"><span data-stu-id="1ec89-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ec89-124">使用中的代理程式（正式與非正式）</span><span class="sxs-lookup"><span data-stu-id="1ec89-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="1ec89-125">1200</span><span class="sxs-lookup"><span data-stu-id="1ec89-125">1200</span></span></p></td>
<td><p><span data-ttu-id="1ec89-126">1200</span><span class="sxs-lookup"><span data-stu-id="1ec89-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ec89-127">查尋群組的數目</span><span class="sxs-lookup"><span data-stu-id="1ec89-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="1ec89-128">400</span><span class="sxs-lookup"><span data-stu-id="1ec89-128">400</span></span></p></td>
<td><p><span data-ttu-id="1ec89-129">400</span><span class="sxs-lookup"><span data-stu-id="1ec89-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ec89-130">IVR 群組數（使用語音辨識）</span><span class="sxs-lookup"><span data-stu-id="1ec89-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="1ec89-131">200</span><span class="sxs-lookup"><span data-stu-id="1ec89-131">200</span></span></p></td>
<td><p><span data-ttu-id="1ec89-132">200</span><span class="sxs-lookup"><span data-stu-id="1ec89-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

