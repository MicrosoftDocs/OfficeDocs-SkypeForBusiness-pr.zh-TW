---
title: Lync Server 2013：回應群組的容量規劃
description: Lync Server 2013：回應群組的容量規劃。
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
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544429"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="7e19e-103">在 Lync Server 2013 中規劃回應群組的容量</span><span class="sxs-lookup"><span data-stu-id="7e19e-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e19e-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="7e19e-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="7e19e-105">下表說明您可以用來作為容量規劃需求之基礎的回應群組使用者模型。</span><span class="sxs-lookup"><span data-stu-id="7e19e-105">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e19e-106">下表中的數位是假設您使用 16 kHz、mono、16位 ( 波形) 所有回應群組音訊檔案的檔案。</span><span class="sxs-lookup"><span data-stu-id="7e19e-106">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="7e19e-107">如果您使用其他檔案格式，例如 Windows Media Audio ( .wma) ，這些數位可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="7e19e-107">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e19e-108">請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中所有回應群組的工作量。</span><span class="sxs-lookup"><span data-stu-id="7e19e-108">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="7e19e-109">回應群組使用者模型</span><span class="sxs-lookup"><span data-stu-id="7e19e-109">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e19e-110">計量</span><span class="sxs-lookup"><span data-stu-id="7e19e-110">Metric</span></span></th>
<th><span data-ttu-id="7e19e-111">每個 Enterprise Edition 集區 (，含8部前端伺服器) </span><span class="sxs-lookup"><span data-stu-id="7e19e-111">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="7e19e-112">每個 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="7e19e-112">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e19e-113">每秒來電數</span><span class="sxs-lookup"><span data-stu-id="7e19e-113">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="7e19e-114">16 </span><span class="sxs-lookup"><span data-stu-id="7e19e-114">16</span></span></p></td>
<td><p><span data-ttu-id="7e19e-115">第</span><span class="sxs-lookup"><span data-stu-id="7e19e-115">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e19e-116">連線至 IVR 或 MoH 的並行通話</span><span class="sxs-lookup"><span data-stu-id="7e19e-116">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="7e19e-117">480</span><span class="sxs-lookup"><span data-stu-id="7e19e-117">480</span></span></p></td>
<td><p><span data-ttu-id="7e19e-118">60</span><span class="sxs-lookup"><span data-stu-id="7e19e-118">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e19e-119"> (沒有 IM) 的併發匿名會話</span><span class="sxs-lookup"><span data-stu-id="7e19e-119">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="7e19e-120">224</span><span class="sxs-lookup"><span data-stu-id="7e19e-120">224</span></span></p></td>
<td><p><span data-ttu-id="7e19e-121">日</span><span class="sxs-lookup"><span data-stu-id="7e19e-121">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e19e-122">使用 IM)  (同時匿名會話</span><span class="sxs-lookup"><span data-stu-id="7e19e-122">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="7e19e-123">64</span><span class="sxs-lookup"><span data-stu-id="7e19e-123">64</span></span></p></td>
<td><p><span data-ttu-id="7e19e-124">8 </span><span class="sxs-lookup"><span data-stu-id="7e19e-124">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e19e-125">主動代理 (正式和非正式) </span><span class="sxs-lookup"><span data-stu-id="7e19e-125">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="7e19e-126">1200</span><span class="sxs-lookup"><span data-stu-id="7e19e-126">1200</span></span></p></td>
<td><p><span data-ttu-id="7e19e-127">1200</span><span class="sxs-lookup"><span data-stu-id="7e19e-127">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e19e-128">群組搜尋數目</span><span class="sxs-lookup"><span data-stu-id="7e19e-128">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="7e19e-129">400</span><span class="sxs-lookup"><span data-stu-id="7e19e-129">400</span></span></p></td>
<td><p><span data-ttu-id="7e19e-130">400</span><span class="sxs-lookup"><span data-stu-id="7e19e-130">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e19e-131">IVR 群組 (使用語音辨識的數目) </span><span class="sxs-lookup"><span data-stu-id="7e19e-131">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="7e19e-132">200</span><span class="sxs-lookup"><span data-stu-id="7e19e-132">200</span></span></p></td>
<td><p><span data-ttu-id="7e19e-133">200</span><span class="sxs-lookup"><span data-stu-id="7e19e-133">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

