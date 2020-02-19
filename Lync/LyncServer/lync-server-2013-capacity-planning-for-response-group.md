---
title: Lync Server 2013： 容量規劃回應群組
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
ms.openlocfilehash: bc7c17146c3cd5913ae82c84b8d7ae292db990f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="564b1-102">容量規劃的 Lync Server 2013 中的回應群組</span><span class="sxs-lookup"><span data-stu-id="564b1-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="564b1-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="564b1-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="564b1-104">下表說明您可以使用容量規劃需求為基礎的回應群組使用者模型。</span><span class="sxs-lookup"><span data-stu-id="564b1-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="564b1-105">下表中的數字假設，您使用 16 kHz 單音的 16 位元 Wave (.wav) 檔案的所有回應群組音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="564b1-105">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="564b1-106">如果您使用其他檔案格式，例如 Windows Media Audio (.wma) 數字可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="564b1-106">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="564b1-107">請記住，災害復原容量規劃，配對集區的每個集區應該能夠處理兩個集區中的所有回應群組的工作負載。</span><span class="sxs-lookup"><span data-stu-id="564b1-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="564b1-108">回應群組使用者模型</span><span class="sxs-lookup"><span data-stu-id="564b1-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="564b1-109">評量</span><span class="sxs-lookup"><span data-stu-id="564b1-109">Metric</span></span></th>
<th><span data-ttu-id="564b1-110">每個 Enterprise Edition 集區 （使用 8 前端伺服器）</span><span class="sxs-lookup"><span data-stu-id="564b1-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="564b1-111">每個 Standard Edition 伺服器</span><span class="sxs-lookup"><span data-stu-id="564b1-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="564b1-112">每秒來電</span><span class="sxs-lookup"><span data-stu-id="564b1-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="564b1-113">16 </span><span class="sxs-lookup"><span data-stu-id="564b1-113">16</span></span></p></td>
<td><p><span data-ttu-id="564b1-114">2</span><span class="sxs-lookup"><span data-stu-id="564b1-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564b1-115">連線至 IVR 或 MoH 的並行通話</span><span class="sxs-lookup"><span data-stu-id="564b1-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="564b1-116">480</span><span class="sxs-lookup"><span data-stu-id="564b1-116">480</span></span></p></td>
<td><p><span data-ttu-id="564b1-117">60</span><span class="sxs-lookup"><span data-stu-id="564b1-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="564b1-118">並行匿名工作階段數 （不含 IM)</span><span class="sxs-lookup"><span data-stu-id="564b1-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="564b1-119">224</span><span class="sxs-lookup"><span data-stu-id="564b1-119">224</span></span></p></td>
<td><p><span data-ttu-id="564b1-120">28</span><span class="sxs-lookup"><span data-stu-id="564b1-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564b1-121">並行匿名工作階段數 （包含 IM)</span><span class="sxs-lookup"><span data-stu-id="564b1-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="564b1-122">64</span><span class="sxs-lookup"><span data-stu-id="564b1-122">64</span></span></p></td>
<td><p><span data-ttu-id="564b1-123">8 </span><span class="sxs-lookup"><span data-stu-id="564b1-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="564b1-124">作用中的代理程式 （正式和非正式）</span><span class="sxs-lookup"><span data-stu-id="564b1-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="564b1-125">1200</span><span class="sxs-lookup"><span data-stu-id="564b1-125">1200</span></span></p></td>
<td><p><span data-ttu-id="564b1-126">1200</span><span class="sxs-lookup"><span data-stu-id="564b1-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564b1-127">群組搜尋數目</span><span class="sxs-lookup"><span data-stu-id="564b1-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="564b1-128">400</span><span class="sxs-lookup"><span data-stu-id="564b1-128">400</span></span></p></td>
<td><p><span data-ttu-id="564b1-129">400</span><span class="sxs-lookup"><span data-stu-id="564b1-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="564b1-130">（使用語音辨識） IVR 群組數</span><span class="sxs-lookup"><span data-stu-id="564b1-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="564b1-131">200</span><span class="sxs-lookup"><span data-stu-id="564b1-131">200</span></span></p></td>
<td><p><span data-ttu-id="564b1-132">200</span><span class="sxs-lookup"><span data-stu-id="564b1-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

