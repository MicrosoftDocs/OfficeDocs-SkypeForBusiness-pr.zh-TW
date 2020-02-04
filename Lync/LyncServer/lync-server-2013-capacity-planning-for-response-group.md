---
title: Lync Server 2013：回應群組的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efb1b928ce7b4bafbbff20ad31872fe12735fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="6466f-102">Lync Server 2013 中的回應群組的容量規劃</span><span class="sxs-lookup"><span data-stu-id="6466f-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6466f-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6466f-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="6466f-104">下表說明您可以用來做為容量規劃需求基礎的 [回應群組] 使用者模型。</span><span class="sxs-lookup"><span data-stu-id="6466f-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6466f-105">下表中的數位假設您針對所有回應群組音訊檔案使用 16 kHz、單聲道、16位波（.wav）檔案。</span><span class="sxs-lookup"><span data-stu-id="6466f-105">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="6466f-106">如果您使用其他檔案格式（例如，Windows Media Audio （.wma）），這些數位可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="6466f-106">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6466f-107">請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理兩個池中所有回應群組的工作量。</span><span class="sxs-lookup"><span data-stu-id="6466f-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="6466f-108">回應群組使用者模型</span><span class="sxs-lookup"><span data-stu-id="6466f-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6466f-109">衡量</span><span class="sxs-lookup"><span data-stu-id="6466f-109">Metric</span></span></th>
<th><span data-ttu-id="6466f-110">每個企業版池（含8個前端伺服器）</span><span class="sxs-lookup"><span data-stu-id="6466f-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="6466f-111">每個標準版 server</span><span class="sxs-lookup"><span data-stu-id="6466f-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6466f-112">每秒來電數</span><span class="sxs-lookup"><span data-stu-id="6466f-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="6466f-113">位</span><span class="sxs-lookup"><span data-stu-id="6466f-113">16</span></span></p></td>
<td><p><span data-ttu-id="6466f-114">2</span><span class="sxs-lookup"><span data-stu-id="6466f-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6466f-115">連線到 IVR 或 MoH 的並行呼叫</span><span class="sxs-lookup"><span data-stu-id="6466f-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="6466f-116">480</span><span class="sxs-lookup"><span data-stu-id="6466f-116">480</span></span></p></td>
<td><p><span data-ttu-id="6466f-117">60</span><span class="sxs-lookup"><span data-stu-id="6466f-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6466f-118">並行匿名會話（無 IM）</span><span class="sxs-lookup"><span data-stu-id="6466f-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="6466f-119">224</span><span class="sxs-lookup"><span data-stu-id="6466f-119">224</span></span></p></td>
<td><p><span data-ttu-id="6466f-120">28</span><span class="sxs-lookup"><span data-stu-id="6466f-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6466f-121">並行匿名會話（與 IM）</span><span class="sxs-lookup"><span data-stu-id="6466f-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="6466f-122">64</span><span class="sxs-lookup"><span data-stu-id="6466f-122">64</span></span></p></td>
<td><p><span data-ttu-id="6466f-123">型</span><span class="sxs-lookup"><span data-stu-id="6466f-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6466f-124">使用中的代理程式（正式與非正式）</span><span class="sxs-lookup"><span data-stu-id="6466f-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="6466f-125">1200</span><span class="sxs-lookup"><span data-stu-id="6466f-125">1200</span></span></p></td>
<td><p><span data-ttu-id="6466f-126">1200</span><span class="sxs-lookup"><span data-stu-id="6466f-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6466f-127">查尋群組的數目</span><span class="sxs-lookup"><span data-stu-id="6466f-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="6466f-128">400</span><span class="sxs-lookup"><span data-stu-id="6466f-128">400</span></span></p></td>
<td><p><span data-ttu-id="6466f-129">400</span><span class="sxs-lookup"><span data-stu-id="6466f-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6466f-130">IVR 群組數（使用語音辨識）</span><span class="sxs-lookup"><span data-stu-id="6466f-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="6466f-131">200</span><span class="sxs-lookup"><span data-stu-id="6466f-131">200</span></span></p></td>
<td><p><span data-ttu-id="6466f-132">200</span><span class="sxs-lookup"><span data-stu-id="6466f-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

