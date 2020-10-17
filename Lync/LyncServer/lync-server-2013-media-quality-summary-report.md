---
title: Lync Server 2013：媒體質量摘要報告
description: Lync Server 2013：媒體質量摘要報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2616b7e3cdea9df7b004745a5c407188870903c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558069"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="cd9eb-103">Lync Server 2013 中的媒體質量摘要報告</span><span class="sxs-lookup"><span data-stu-id="cd9eb-103">Media Quality Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd9eb-104">_**主題上次修改日期：** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="cd9eb-104">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="cd9eb-105">媒體質量摘要報告也許是在您的組織中分析通話品質的首選：此報告可提供詳細的經驗品質 (QoE 會分解為下列類別) 的呼叫計量。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-105">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="cd9eb-106">UC 對等通話 (例如 Microsoft Lync 2013 至 Microsoft Lync 2013 通話) </span><span class="sxs-lookup"><span data-stu-id="cd9eb-106">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="cd9eb-107">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-107">UC Conference Sessions</span></span>

  - <span data-ttu-id="cd9eb-108">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-108">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="cd9eb-109">PSTN 通話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="cd9eb-109">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="cd9eb-110">PSTN 通話 (Non-Bypass) ： UC 腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-110">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="cd9eb-111">PSTN 通話 (Non-Bypass) ：閘道腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-111">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="cd9eb-112">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="cd9eb-112">Other Call Types</span></span>

<span data-ttu-id="cd9eb-113">當您第一次開啟報表時，您會看到每個類別的摘要資訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-113">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="cd9eb-114">在未離開報告的情況下，您可以展開每個類別，以查看子類別，例如從 Office Communicator 2007 R2 進行的呼叫至 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-114">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="cd9eb-115">接著，您可以在這些子類別中深入查看，以查看該子類別中所進行之每個通話的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-115">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="cd9eb-116">在 Microsoft Lync Server 2013 中，媒體質量摘要報告會進一步將資料分解為三種通話類型：音訊通話、影片通話和應用程式共用通話。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-116">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="cd9eb-117">每個通話類型在報告中都有其自己的區段，以及其自己的自訂呼叫計量集。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-117">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="cd9eb-118">媒體質量摘要報告也可讓您套用篩選器，讓您能夠比較有線通話的通話品質與無線通話、內部通話與外部通話，以及 VPN 呼叫與非 VPN 通話。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-118">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="cd9eb-119">存取媒體質量摘要報告</span><span class="sxs-lookup"><span data-stu-id="cd9eb-119">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="cd9eb-120">媒體質量摘要報告可從監控報告的首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-120">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="cd9eb-121">您可以按一下下列其中一個計量，以深入瞭解 [Lync Server 2013 中的通話清單報告](lync-server-2013-call-list-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-121">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="cd9eb-122">通話數量</span><span class="sxs-lookup"><span data-stu-id="cd9eb-122">Call volume</span></span>

  - <span data-ttu-id="cd9eb-123">通話百分比不佳</span><span class="sxs-lookup"><span data-stu-id="cd9eb-123">Poor call percentage</span></span>

<span data-ttu-id="cd9eb-124">此外，您可以按一下下列任何音訊撥號計量，以存取媒體質量計量散佈報告：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-124">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="cd9eb-125">來回行程 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="cd9eb-125">Round trip (ms)</span></span>

  - <span data-ttu-id="cd9eb-126">MOS) 降級 (</span><span class="sxs-lookup"><span data-stu-id="cd9eb-126">Degradation (MOS)</span></span>

  - <span data-ttu-id="cd9eb-127">封包遺失</span><span class="sxs-lookup"><span data-stu-id="cd9eb-127">Packet loss</span></span>

  - <span data-ttu-id="cd9eb-128">抖動 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="cd9eb-128">Jitter (ms)</span></span>

  - <span data-ttu-id="cd9eb-129">修復隱藏比率</span><span class="sxs-lookup"><span data-stu-id="cd9eb-129">Healer concealed ratio</span></span>

  - <span data-ttu-id="cd9eb-130">修復延伸比率</span><span class="sxs-lookup"><span data-stu-id="cd9eb-130">Healer stretched ratio</span></span>

  - <span data-ttu-id="cd9eb-131">修復壓縮比例</span><span class="sxs-lookup"><span data-stu-id="cd9eb-131">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="cd9eb-132">篩選</span><span class="sxs-lookup"><span data-stu-id="cd9eb-132">Filters</span></span>

<span data-ttu-id="cd9eb-133">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-133">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="cd9eb-134">例如，媒體質量摘要報告可讓您篩選傳回的資料，例如存取類型 (例如，「間隔存取」與「外部存取」) 或有線/無線網路連線。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-134">For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="cd9eb-135">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-135">You can also choose how data should be grouped.</span></span> <span data-ttu-id="cd9eb-136">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-136">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="cd9eb-137">下表列出您可以搭配媒體質量摘要報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-137">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="cd9eb-138">媒體質量摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="cd9eb-138">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd9eb-139">名稱</span><span class="sxs-lookup"><span data-stu-id="cd9eb-139">Name</span></span></th>
<th><span data-ttu-id="cd9eb-140">描述</span><span class="sxs-lookup"><span data-stu-id="cd9eb-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-141"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-141"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cd9eb-144">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cd9eb-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cd9eb-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cd9eb-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cd9eb-147">7/7/2012</span></span></p>
<p><span data-ttu-id="cd9eb-148">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cd9eb-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cd9eb-149">7/3/2012</span></span></p>
<p><span data-ttu-id="cd9eb-150">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-151"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-151"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cd9eb-154">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cd9eb-154">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cd9eb-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cd9eb-157">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cd9eb-157">7/7/2012</span></span></p>
<p><span data-ttu-id="cd9eb-158">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-158">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cd9eb-159">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cd9eb-159">7/3/2012</span></span></p>
<p><span data-ttu-id="cd9eb-160">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-160">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-161"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-161"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-p109">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd9eb-164">一切</span><span class="sxs-lookup"><span data-stu-id="cd9eb-164">[All]</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-165">內部</span><span class="sxs-lookup"><span data-stu-id="cd9eb-165">Internal</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-166">外部</span><span class="sxs-lookup"><span data-stu-id="cd9eb-166">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-167"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-167"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-p110">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd9eb-170">一切</span><span class="sxs-lookup"><span data-stu-id="cd9eb-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-171">有線</span><span class="sxs-lookup"><span data-stu-id="cd9eb-171">Wired</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-172">無線</span><span class="sxs-lookup"><span data-stu-id="cd9eb-172">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-p111">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd9eb-176">一切</span><span class="sxs-lookup"><span data-stu-id="cd9eb-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-177">VPN</span><span class="sxs-lookup"><span data-stu-id="cd9eb-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-178">非 VPN</span><span class="sxs-lookup"><span data-stu-id="cd9eb-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cd9eb-179">指標</span><span class="sxs-lookup"><span data-stu-id="cd9eb-179">Metrics</span></span>

<span data-ttu-id="cd9eb-180">下表列出媒體質量摘要報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-180">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="cd9eb-181">媒體質量摘要報告計量：音訊通話摘要</span><span class="sxs-lookup"><span data-stu-id="cd9eb-181">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd9eb-182">姓名</span><span class="sxs-lookup"><span data-stu-id="cd9eb-182">Name</span></span></th>
<th><span data-ttu-id="cd9eb-183">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="cd9eb-183">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cd9eb-184">描述</span><span class="sxs-lookup"><span data-stu-id="cd9eb-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-185"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-185"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-186">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-186">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-187">當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-187">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="cd9eb-188">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-188">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd9eb-189">UC Peer-to-Peer 通話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-189">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-190">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-190">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-191">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-191">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-192">PSTN 通話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="cd9eb-192">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-193">PSTN 通話 (Non-Bypass) ： UC 腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-193">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-194">PSTN 通話 (Non-Bypass) ：閘道腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-194">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-195">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="cd9eb-195">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-196"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-196"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-197">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-197">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-198">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-198">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-199"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-200">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-200">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-201">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-201">Total number of calls classified as poor.</span></span> <span data-ttu-id="cd9eb-202">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-202">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-203"><strong> (無線通話的電話量) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-203"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-204">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-204">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-205">使用無線連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-205">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-206"><strong> (VPN 呼叫的通話量) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-206"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-207">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-207">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-208">使用 VPN 連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-208">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-209"><strong>通話量 (外部呼叫) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-209"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-210">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-210">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-211">使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-211">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-212"><strong>來回行程 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-212"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-213">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-213">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-214">即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-214">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="cd9eb-215">在100毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-215">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="cd9eb-216">高來回行程值可能是由國際通話路由、路由配置錯誤或超載的媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-216">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="cd9eb-217">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-217">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-218"><strong>MOS) 降級 (</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-218"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-219">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-219">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-220">通話期間 (MOS) 效能的平均平均觀點量。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-220">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="cd9eb-221">降級值的範圍從低0.0 到高5.0。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-221">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="cd9eb-222">值0.5 或更少代表可接受的降級。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-222">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="cd9eb-223">在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-223">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="cd9eb-224">在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-224">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="cd9eb-225">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-225">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="cd9eb-226">高降級導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-226">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-227"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-227"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-228">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-228">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-229">RTP 封包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-229">Average rate of RTP packet loss.</span></span> <span data-ttu-id="cd9eb-230">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-230">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="cd9eb-231">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-231">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-232"><strong>抖動 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-232"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-233">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-233">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-234">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-234">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="cd9eb-235"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-235">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-236"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-236"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-237">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-237">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-238">隱藏音訊樣本的平均比率與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-238">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="cd9eb-239"> (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-239">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-240"><strong>修復延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-240"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-241">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-241">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-242">延伸音訊樣本的平均比例與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-242">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="cd9eb-243"> (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-243">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-244"><strong>修復壓縮比例</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-244"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-245">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-245">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-246">壓縮音訊樣本的平均比率與樣本總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-246">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="cd9eb-247"> (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-247">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="cd9eb-248">媒體質量摘要報告計量：影片通話摘要</span><span class="sxs-lookup"><span data-stu-id="cd9eb-248">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd9eb-249">姓名</span><span class="sxs-lookup"><span data-stu-id="cd9eb-249">Name</span></span></th>
<th><span data-ttu-id="cd9eb-250">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="cd9eb-250">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cd9eb-251">描述</span><span class="sxs-lookup"><span data-stu-id="cd9eb-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-252"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-252"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-253">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-253">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-254">當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-254">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="cd9eb-255">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-255">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd9eb-256">UC Peer-to-Peer 通話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-256">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-257">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-257">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-258">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-258">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-259">PSTN 通話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="cd9eb-259">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-260">PSTN 通話 (Non-Bypass) ： UC 腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-260">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-261">PSTN 通話 (Non-Bypass) ：閘道腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-261">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-262">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="cd9eb-262">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-263"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-263"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-264">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-264">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-265">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-265">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-266"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-266"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-267">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-267">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-268">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-268">Total number of calls classified as poor.</span></span> <span data-ttu-id="cd9eb-269">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-269">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-270"><strong> (無線通話的電話量) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-270"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-271">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-271">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-272">使用無線連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-272">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-273"><strong> (VPN 呼叫的通話量) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-273"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-274">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-274">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-275">使用 VPN 連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-275">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-276"><strong>通話量 (外部呼叫) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-276"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-277">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-277">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-278">使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-278">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-279"><strong>平均位元速率 (Kb/s) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-279"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-280">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-280">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-281">平均影片位元速率 (以每秒千位數) 。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-281">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-282"><strong>低位率%</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-282"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-283">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-283">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-284">位元速率低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-284">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-285"><strong>輸出封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-285"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-286">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-286">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-287">Real-Time 傳輸通訊協定 (RTP) 輸出封包遺失。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-287">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="cd9eb-288">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-288">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="cd9eb-289">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-289">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-290"><strong>凍結的圖文框%</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-290"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-291">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-291">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-292">「凍結」框架的百分比。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-292">Percentage of “frozen” frames.</span></span> <span data-ttu-id="cd9eb-293">在凍結的框架中，當繼續通話的音訊部分時，影片會停止向前。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-293">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-294"><strong>輸出平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-294"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-295">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-295">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-296">通話期間輸出傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-296">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-297"><strong>輸入平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-297"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-298">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-298">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-299">通話期間傳入傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-299">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-300"><strong>輸入低框架速率%</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-300"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-301">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-301">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-302">傳入影片的位元速率很低之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-302">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-303"><strong>用戶端狀況%</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-303"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd9eb-304">會指出通話期間用戶端裝置的相對健康情況。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-304">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="cd9eb-305">媒體質量摘要報告計量：應用程式共用通話摘要</span><span class="sxs-lookup"><span data-stu-id="cd9eb-305">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd9eb-306">姓名</span><span class="sxs-lookup"><span data-stu-id="cd9eb-306">Name</span></span></th>
<th><span data-ttu-id="cd9eb-307">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="cd9eb-307">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cd9eb-308">描述</span><span class="sxs-lookup"><span data-stu-id="cd9eb-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-309"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-309"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-310">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-310">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-311">當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-311">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="cd9eb-312">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="cd9eb-312">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd9eb-313">UC Peer-to-Peer 通話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-313">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-314">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-314">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-315">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="cd9eb-315">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-316">PSTN 通話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="cd9eb-316">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-317">PSTN 通話 (Non-Bypass) ： UC 腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-317">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-318">PSTN 通話 (Non-Bypass) ：閘道腿</span><span class="sxs-lookup"><span data-stu-id="cd9eb-318">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="cd9eb-319">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="cd9eb-319">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-320"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-320"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-321">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-321">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-322">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-322">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-323"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-323"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-324">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-324">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-325">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-325">Total number of calls classified as poor.</span></span> <span data-ttu-id="cd9eb-326">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-326">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-327"><strong> (無線通話的電話量) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-327"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-328">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-328">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-329">使用無線連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-329">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-330"><strong> (VPN 呼叫的通話量) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-330"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-331">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-331">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-332">使用 VPN 連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-332">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-333"><strong>通話量 (外部呼叫) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-333"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-334">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-334">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-335">使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-335">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-336"><strong>抖動 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-336"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-337">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-337">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-338">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-338">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="cd9eb-339"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-339">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-340"><strong>平均相對單向方式</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-340"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-341">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-341">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-342">兩個媒體端點之間的平均相對單向延遲。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-342">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="cd9eb-343">此為單一躍點延遲措施。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-343">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9eb-344"><strong>平均 .RDP 磚處理延遲</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-344"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-345">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-345">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-346">在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-346">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="cd9eb-347">高平均反映的觀賞體驗中的延遲較長，包含網路延遲。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-347">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="cd9eb-348">負載過重的會議伺服器可能會發生較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-348">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9eb-349"><strong>Spoiled 磚的總數%</strong></span><span class="sxs-lookup"><span data-stu-id="cd9eb-349"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="cd9eb-350">否</span><span class="sxs-lookup"><span data-stu-id="cd9eb-350">No</span></span></p></td>
<td><p><span data-ttu-id="cd9eb-351">Spoiled RDP 磚的總百分比。</span><span class="sxs-lookup"><span data-stu-id="cd9eb-351">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

