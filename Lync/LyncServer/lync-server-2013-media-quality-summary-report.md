---
title: Lync Server 2013： 媒體品質摘要報告
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
ms.openlocfilehash: 89a5046ba15534d40c81e1e3b8a4f310873a9e1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="259ea-102">Lync Server 2013 中的媒體品質摘要報告</span><span class="sxs-lookup"><span data-stu-id="259ea-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="259ea-103">_**主題上次修改日期：** 2016年-06-29_</span><span class="sxs-lookup"><span data-stu-id="259ea-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="259ea-104">媒體品質摘要報告或許是您分析您的組織中的通話品質的最佳選擇： 這份報告提供詳細的經驗品質 (QoE) 通話衡量標準，向下切分為下列類別：</span><span class="sxs-lookup"><span data-stu-id="259ea-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="259ea-105">UC 對等通話 （例如 Microsoft Lync 2013 呼叫 Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="259ea-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="259ea-106">UC 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="259ea-107">PSTN 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="259ea-108">PSTN 通話： 媒體旁路</span><span class="sxs-lookup"><span data-stu-id="259ea-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="259ea-109">PSTN 通話 （非旁路）： UC Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="259ea-110">PSTN 通話 （非旁路）： 閘道 Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="259ea-111">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="259ea-111">Other Call Types</span></span>

<span data-ttu-id="259ea-112">當您第一次開啟報表時，您會看到每個類別的摘要資訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="259ea-113">不需要離開報表，您可以展開每個類別，查看子類別，例如從 Office Communicator 2007 R2 至 Lync 2013 進行的通話。</span><span class="sxs-lookup"><span data-stu-id="259ea-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="259ea-114">接著，您可以再向下鑽研至若要查看每個內的子類別所進行的通話詳細這些子類別。</span><span class="sxs-lookup"><span data-stu-id="259ea-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="259ea-115">在 [Microsoft Lync Server 2013 媒體品質摘要報告進一步會向下資料分成三種通話類型： 音訊通話、 視訊通話及應用程式共用通話。</span><span class="sxs-lookup"><span data-stu-id="259ea-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="259ea-116">每個通話類型都有其專屬報告區段中，而且它自己的自訂設定的通話衡量標準。</span><span class="sxs-lookup"><span data-stu-id="259ea-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="259ea-117">Media Quality Summary Report 也可讓您套用篩選器，可讓您比較有線的撥打與無線通話、 內部撥打與外部通話，以及和非 VPN 通話比較 VPN 通話的通話品質。</span><span class="sxs-lookup"><span data-stu-id="259ea-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="259ea-118">存取媒體品質摘要報告</span><span class="sxs-lookup"><span data-stu-id="259ea-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="259ea-119">從監視報告首頁存取媒體品質摘要報告。</span><span class="sxs-lookup"><span data-stu-id="259ea-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="259ea-120">您可以按一下向下切入[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)的下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="259ea-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="259ea-121">[通話數</span><span class="sxs-lookup"><span data-stu-id="259ea-121">Call volume</span></span>

  - <span data-ttu-id="259ea-122">通話不良百分比</span><span class="sxs-lookup"><span data-stu-id="259ea-122">Poor call percentage</span></span>

<span data-ttu-id="259ea-123">此外，您可以按一下任何下列的音訊通話衡量標準來存取媒體品質計量散佈報告：</span><span class="sxs-lookup"><span data-stu-id="259ea-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="259ea-124">往返時間 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="259ea-124">Round trip (ms)</span></span>

  - <span data-ttu-id="259ea-125">降低 (MOS)</span><span class="sxs-lookup"><span data-stu-id="259ea-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="259ea-126">封包遺失</span><span class="sxs-lookup"><span data-stu-id="259ea-126">Packet loss</span></span>

  - <span data-ttu-id="259ea-127">抖動 (ms)</span><span class="sxs-lookup"><span data-stu-id="259ea-127">Jitter (ms)</span></span>

  - <span data-ttu-id="259ea-128">修復隱藏比率</span><span class="sxs-lookup"><span data-stu-id="259ea-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="259ea-129">修復延伸的比率</span><span class="sxs-lookup"><span data-stu-id="259ea-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="259ea-130">修復壓縮的比率</span><span class="sxs-lookup"><span data-stu-id="259ea-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="259ea-131">篩選</span><span class="sxs-lookup"><span data-stu-id="259ea-131">Filters</span></span>

<span data-ttu-id="259ea-132">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="259ea-132">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="259ea-133">例如，媒體品質摘要報告可讓您存取類型 （也就是與外部存取的時間間隔存取） 等事項或是有線/無線網路連線篩選傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="259ea-133">For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="259ea-134">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="259ea-134">You can also choose how data should be grouped.</span></span> <span data-ttu-id="259ea-135">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="259ea-135">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="259ea-136">下表列出您可以搭配媒體品質摘要報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="259ea-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="259ea-137">媒體品質摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="259ea-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="259ea-138">名稱</span><span class="sxs-lookup"><span data-stu-id="259ea-138">Name</span></span></th>
<th><span data-ttu-id="259ea-139">描述</span><span class="sxs-lookup"><span data-stu-id="259ea-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="259ea-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="259ea-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="259ea-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="259ea-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="259ea-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="259ea-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="259ea-146">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="259ea-146">7/7/2012</span></span></p>
<p><span data-ttu-id="259ea-147">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="259ea-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="259ea-148">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="259ea-148">7/3/2012</span></span></p>
<p><span data-ttu-id="259ea-149">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="259ea-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="259ea-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="259ea-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="259ea-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="259ea-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="259ea-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="259ea-156">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="259ea-156">7/7/2012</span></span></p>
<p><span data-ttu-id="259ea-157">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="259ea-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="259ea-158">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="259ea-158">7/3/2012</span></span></p>
<p><span data-ttu-id="259ea-159">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="259ea-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-160"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-p109">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="259ea-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="259ea-163">[全部]</span><span class="sxs-lookup"><span data-stu-id="259ea-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="259ea-164">內部</span><span class="sxs-lookup"><span data-stu-id="259ea-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="259ea-165">External</span><span class="sxs-lookup"><span data-stu-id="259ea-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-166"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-p110">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="259ea-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="259ea-169">[全部]</span><span class="sxs-lookup"><span data-stu-id="259ea-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="259ea-170">有線</span><span class="sxs-lookup"><span data-stu-id="259ea-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="259ea-171">無線</span><span class="sxs-lookup"><span data-stu-id="259ea-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-p111">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="259ea-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="259ea-175">[全部]</span><span class="sxs-lookup"><span data-stu-id="259ea-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="259ea-176">VPN</span><span class="sxs-lookup"><span data-stu-id="259ea-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="259ea-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="259ea-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="259ea-178">計量</span><span class="sxs-lookup"><span data-stu-id="259ea-178">Metrics</span></span>

<span data-ttu-id="259ea-179">下表列出媒體品質摘要報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="259ea-180">媒體品質摘要報告衡量標準： 音訊通話摘要</span><span class="sxs-lookup"><span data-stu-id="259ea-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="259ea-181">姓名</span><span class="sxs-lookup"><span data-stu-id="259ea-181">Name</span></span></th>
<th><span data-ttu-id="259ea-182">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="259ea-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="259ea-183">描述</span><span class="sxs-lookup"><span data-stu-id="259ea-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="259ea-184"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-185">否</span><span class="sxs-lookup"><span data-stu-id="259ea-185">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-186">當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-186">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="259ea-187">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="259ea-187">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="259ea-188">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="259ea-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="259ea-189">UC 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="259ea-190">PSTN 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="259ea-191">PSTN 通話： 媒體旁路</span><span class="sxs-lookup"><span data-stu-id="259ea-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="259ea-192">PSTN 通話 （非旁路）： UC Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="259ea-193">PSTN 通話 （非旁路）： 閘道 Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="259ea-194">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="259ea-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-195"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-196">否</span><span class="sxs-lookup"><span data-stu-id="259ea-196">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-197">每一種通話類型通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-198"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-199">否</span><span class="sxs-lookup"><span data-stu-id="259ea-199">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-200">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-200">Total number of calls classified as poor.</span></span> <span data-ttu-id="259ea-201">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="259ea-201">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-202"><strong>通話數 （無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-203">否</span><span class="sxs-lookup"><span data-stu-id="259ea-203">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-204">使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-205"><strong>通話數 （VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-206">否</span><span class="sxs-lookup"><span data-stu-id="259ea-206">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-207">使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-208"><strong>通話數 （外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-209">否</span><span class="sxs-lookup"><span data-stu-id="259ea-209">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-210">使用外部連線 （亦即內部網路外部連接） 的通話數。</span><span class="sxs-lookup"><span data-stu-id="259ea-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-211"><strong>往返時間 （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-212">否</span><span class="sxs-lookup"><span data-stu-id="259ea-212">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-213">平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。</span><span class="sxs-lookup"><span data-stu-id="259ea-213">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="259ea-214">100 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="259ea-214">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="259ea-215">高的來回行程值可以是國際電話路由，路由設定錯誤或已多載的媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="259ea-215">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="259ea-216">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="259ea-216">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-217"><strong>降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-218">否</span><span class="sxs-lookup"><span data-stu-id="259ea-218">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-219">平均量平均意見分數 (MOS) 降低在通話期間發生。</span><span class="sxs-lookup"><span data-stu-id="259ea-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="259ea-220">為 [高] 的 5.0，降低值可介於 0.0 的低。</span><span class="sxs-lookup"><span data-stu-id="259ea-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="259ea-221">為 0.5 或更低的值代表可接受的效能下降。</span><span class="sxs-lookup"><span data-stu-id="259ea-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="259ea-222">在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。</span><span class="sxs-lookup"><span data-stu-id="259ea-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="259ea-223">在 Lync Server 中，Lync Server 會使用一組演算法來預測如何使用者會有分級通話。</span><span class="sxs-lookup"><span data-stu-id="259ea-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="259ea-224">高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="259ea-224">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="259ea-225">高降低的情形會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-225">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-226"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-227">否</span><span class="sxs-lookup"><span data-stu-id="259ea-227">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-228">RTP 封包遺失平均速率。</span><span class="sxs-lookup"><span data-stu-id="259ea-228">Average rate of RTP packet loss.</span></span> <span data-ttu-id="259ea-229">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="259ea-229">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="259ea-230">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-230">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-231"><strong>抖動 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-232">否</span><span class="sxs-lookup"><span data-stu-id="259ea-232">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-233">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="259ea-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="259ea-234">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-235"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-236">否</span><span class="sxs-lookup"><span data-stu-id="259ea-236">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-237">之隱藏樣本總數總計的音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="259ea-237">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="259ea-238">（隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-238">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-239"><strong>修復延伸的比率</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-240">否</span><span class="sxs-lookup"><span data-stu-id="259ea-240">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-241">範例總數總計的延伸音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="259ea-241">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="259ea-242">（延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</span><span class="sxs-lookup"><span data-stu-id="259ea-242">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-243"><strong>修復壓縮的比率</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-244">否</span><span class="sxs-lookup"><span data-stu-id="259ea-244">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-245">範例總數的壓縮音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="259ea-245">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="259ea-246">（壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</span><span class="sxs-lookup"><span data-stu-id="259ea-246">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="259ea-247">媒體品質摘要報告衡量標準： 視訊通話摘要</span><span class="sxs-lookup"><span data-stu-id="259ea-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="259ea-248">姓名</span><span class="sxs-lookup"><span data-stu-id="259ea-248">Name</span></span></th>
<th><span data-ttu-id="259ea-249">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="259ea-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="259ea-250">描述</span><span class="sxs-lookup"><span data-stu-id="259ea-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="259ea-251"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-252">否</span><span class="sxs-lookup"><span data-stu-id="259ea-252">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-253">當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-253">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="259ea-254">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="259ea-254">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="259ea-255">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="259ea-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="259ea-256">UC 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="259ea-257">PSTN 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="259ea-258">PSTN 通話： 媒體旁路</span><span class="sxs-lookup"><span data-stu-id="259ea-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="259ea-259">PSTN 通話 （非旁路）： UC Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="259ea-260">PSTN 通話 （非旁路）： 閘道 Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="259ea-261">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="259ea-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-262"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-263">否</span><span class="sxs-lookup"><span data-stu-id="259ea-263">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-264">每一種通話類型通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-265"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-266">否</span><span class="sxs-lookup"><span data-stu-id="259ea-266">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-267">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-267">Total number of calls classified as poor.</span></span> <span data-ttu-id="259ea-268">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="259ea-268">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-269"><strong>通話數 （無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-270">否</span><span class="sxs-lookup"><span data-stu-id="259ea-270">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-271">使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-272"><strong>通話數 （VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-273">否</span><span class="sxs-lookup"><span data-stu-id="259ea-273">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-274">使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-275"><strong>通話數 （外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-276">否</span><span class="sxs-lookup"><span data-stu-id="259ea-276">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-277">使用外部連線 （亦即內部網路外部連接） 的通話數。</span><span class="sxs-lookup"><span data-stu-id="259ea-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-278"><strong>平均位元速率 （Kb/秒）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-279">否</span><span class="sxs-lookup"><span data-stu-id="259ea-279">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-280">平均視訊位元速率 （每秒的 kb）。</span><span class="sxs-lookup"><span data-stu-id="259ea-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-281"><strong>低位元速率 %]</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-282">否</span><span class="sxs-lookup"><span data-stu-id="259ea-282">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-283">其中的位元速率較低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="259ea-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-284"><strong>輸出封包遺漏</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-285">否</span><span class="sxs-lookup"><span data-stu-id="259ea-285">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-286">輸出封包的即時傳輸通訊協定 (RTP) 封包遺失。</span><span class="sxs-lookup"><span data-stu-id="259ea-286">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="259ea-287">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="259ea-287">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="259ea-288">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-288">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-289"><strong>[凍結的畫面 %]</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-290">否</span><span class="sxs-lookup"><span data-stu-id="259ea-290">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-291">「 凍結 」 畫面的百分比。</span><span class="sxs-lookup"><span data-stu-id="259ea-291">Percentage of “frozen” frames.</span></span> <span data-ttu-id="259ea-292">在 [凍結的畫面，影片會停止前進時通話的音訊部分會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="259ea-292">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-293"><strong>輸出平均播放速率]</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-294">否</span><span class="sxs-lookup"><span data-stu-id="259ea-294">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-295">通話期間輸出傳輸的平均播放速率。</span><span class="sxs-lookup"><span data-stu-id="259ea-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-296"><strong>輸入的平均播放速率]</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-297">否</span><span class="sxs-lookup"><span data-stu-id="259ea-297">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-298">通話期間輸入傳輸的平均播放速率。</span><span class="sxs-lookup"><span data-stu-id="259ea-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-299"><strong>輸入低播放速率 %]</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-300">否</span><span class="sxs-lookup"><span data-stu-id="259ea-300">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-301">其中傳入的視訊的位元速率較低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="259ea-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-302"><strong>用戶端健康情況 %]</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="259ea-303">通話期間會指出用戶端裝置的相關健康情況。</span><span class="sxs-lookup"><span data-stu-id="259ea-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="259ea-304">媒體品質摘要報告衡量標準： 應用程式共用通話摘要</span><span class="sxs-lookup"><span data-stu-id="259ea-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="259ea-305">姓名</span><span class="sxs-lookup"><span data-stu-id="259ea-305">Name</span></span></th>
<th><span data-ttu-id="259ea-306">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="259ea-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="259ea-307">描述</span><span class="sxs-lookup"><span data-stu-id="259ea-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="259ea-308"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-309">否</span><span class="sxs-lookup"><span data-stu-id="259ea-309">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-310">當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-310">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="259ea-311">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="259ea-311">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="259ea-312">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="259ea-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="259ea-313">UC 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="259ea-314">PSTN 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="259ea-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="259ea-315">PSTN 通話： 媒體旁路</span><span class="sxs-lookup"><span data-stu-id="259ea-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="259ea-316">PSTN 通話 （非旁路）： UC Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="259ea-317">PSTN 通話 （非旁路）： 閘道 Leg</span><span class="sxs-lookup"><span data-stu-id="259ea-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="259ea-318">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="259ea-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-319"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-320">否</span><span class="sxs-lookup"><span data-stu-id="259ea-320">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-321">每一種通話類型通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-322"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-323">否</span><span class="sxs-lookup"><span data-stu-id="259ea-323">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-324">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-324">Total number of calls classified as poor.</span></span> <span data-ttu-id="259ea-325">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="259ea-325">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-326"><strong>通話數 （無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-327">否</span><span class="sxs-lookup"><span data-stu-id="259ea-327">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-328">使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-329"><strong>通話數 （VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-330">否</span><span class="sxs-lookup"><span data-stu-id="259ea-330">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-331">使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="259ea-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-332"><strong>通話數 （外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-333">否</span><span class="sxs-lookup"><span data-stu-id="259ea-333">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-334">使用外部連線 （亦即內部網路外部連接） 的通話數。</span><span class="sxs-lookup"><span data-stu-id="259ea-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-335"><strong>抖動 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-336">否</span><span class="sxs-lookup"><span data-stu-id="259ea-336">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-337">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="259ea-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="259ea-338">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="259ea-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-339"><strong>平均相對的其中一種方式</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-340">否</span><span class="sxs-lookup"><span data-stu-id="259ea-340">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-341">平均相對單向之間的延遲兩個媒體端點。</span><span class="sxs-lookup"><span data-stu-id="259ea-341">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="259ea-342">此為單一躍點延遲措施。</span><span class="sxs-lookup"><span data-stu-id="259ea-342">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="259ea-343"><strong>平均 RDP 並排顯示處理延遲</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-344">否</span><span class="sxs-lookup"><span data-stu-id="259ea-344">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-345">平均 RDP 並排檢視工作階段的持續時間內 AS 會議伺服器的處理延遲。</span><span class="sxs-lookup"><span data-stu-id="259ea-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="259ea-346">高平均反映觀賞體驗，請在較長延遲，並包含網路延遲。</span><span class="sxs-lookup"><span data-stu-id="259ea-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="259ea-347">負載過重的會議伺服器可能會發生較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="259ea-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="259ea-348"><strong>總毀損之並排顯示 %</strong></span><span class="sxs-lookup"><span data-stu-id="259ea-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="259ea-349">否</span><span class="sxs-lookup"><span data-stu-id="259ea-349">No</span></span></p></td>
<td><p><span data-ttu-id="259ea-350">毀損之 RDP 並排顯示的總百分比。</span><span class="sxs-lookup"><span data-stu-id="259ea-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

