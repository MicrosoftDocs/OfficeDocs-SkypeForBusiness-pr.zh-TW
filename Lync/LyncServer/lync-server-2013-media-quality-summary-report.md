---
title: Lync Server 2013：媒體質量摘要報告
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
ms.openlocfilehash: 6980168a2d509bc32b9aa48f30167bca8721fef2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="6d3a6-102">Lync Server 2013 中的 [媒體質量摘要] 報表</span><span class="sxs-lookup"><span data-stu-id="6d3a6-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d3a6-103">_**主題上次修改日期：** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="6d3a6-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="6d3a6-104">媒體質量摘要報告可能是您在組織中分析通話品質的最佳做法：此報告提供詳細的體驗品質（QoE）通話度量單位，分為下列類別：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="6d3a6-105">UC 對等呼叫（例如 Microsoft Lync 2013 至 Microsoft Lync 2013 通話）</span><span class="sxs-lookup"><span data-stu-id="6d3a6-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="6d3a6-106">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="6d3a6-107">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="6d3a6-108">PSTN 電話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="6d3a6-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="6d3a6-109">PSTN 通話（非旁路）： UC 腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="6d3a6-110">PSTN 通話（非旁路）：閘道腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="6d3a6-111">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="6d3a6-111">Other Call Types</span></span>

<span data-ttu-id="6d3a6-112">當您第一次開啟報表時，您會看到每個類別的摘要資訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="6d3a6-113">您可以在不離開報表的情況下展開每個類別，以查看子類別，例如從 Office Communicator 2007 R2 撥打到 Lync 2013 的情況。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="6d3a6-114">接著，您可以向下切入這些子類別，以查看在該子類別中所做的每個通話的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="6d3a6-115">在 Microsoft Lync Server 2013 中，媒體質量摘要報告會進一步將資料分解為三種通話類型：語音通話、視頻通話和應用程式共用通話。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="6d3a6-116">每個通話類型在報表中都有自己的區段，以及自己的自訂通話測量指標集合。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="6d3a6-117">[媒體質量摘要] 報告也可讓您套用篩選，讓您可以比較有線通話的通話品質與無線通話、內部通話與外部通話，以及 VPN 通話與非 VPN 通話。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="6d3a6-118">存取媒體質量摘要報告</span><span class="sxs-lookup"><span data-stu-id="6d3a6-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="6d3a6-119">[媒體質量摘要] 報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="6d3a6-120">您可以按一下下列其中一個度量，[在 Lync Server 2013 中](lync-server-2013-call-list-report.md)向下切入至 [通話清單] 報告：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="6d3a6-121">通話量</span><span class="sxs-lookup"><span data-stu-id="6d3a6-121">Call volume</span></span>

  - <span data-ttu-id="6d3a6-122">通話百分比太差</span><span class="sxs-lookup"><span data-stu-id="6d3a6-122">Poor call percentage</span></span>

<span data-ttu-id="6d3a6-123">此外，您可以按一下下列任何一種音訊通話指標，以存取媒體質量度量分佈報告：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="6d3a6-124">往返行程（毫秒）</span><span class="sxs-lookup"><span data-stu-id="6d3a6-124">Round trip (ms)</span></span>

  - <span data-ttu-id="6d3a6-125">下降（MOS）</span><span class="sxs-lookup"><span data-stu-id="6d3a6-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="6d3a6-126">資料包遺失</span><span class="sxs-lookup"><span data-stu-id="6d3a6-126">Packet loss</span></span>

  - <span data-ttu-id="6d3a6-127">抖動（毫秒）</span><span class="sxs-lookup"><span data-stu-id="6d3a6-127">Jitter (ms)</span></span>

  - <span data-ttu-id="6d3a6-128">Healer 隱藏比例</span><span class="sxs-lookup"><span data-stu-id="6d3a6-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="6d3a6-129">Healer 延伸比率</span><span class="sxs-lookup"><span data-stu-id="6d3a6-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="6d3a6-130">Healer 壓縮比率</span><span class="sxs-lookup"><span data-stu-id="6d3a6-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6d3a6-131">濾鏡</span><span class="sxs-lookup"><span data-stu-id="6d3a6-131">Filters</span></span>

<span data-ttu-id="6d3a6-132">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-132">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="6d3a6-133">例如，媒體質量摘要報告可讓您篩選傳回的資料，例如存取類型（也就是間隔存取與外部存取）或有線/無線網路連線等。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-133">For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="6d3a6-134">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-134">You can also choose how data should be grouped.</span></span> <span data-ttu-id="6d3a6-135">在這種情況下，通話會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-135">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="6d3a6-136">下表列出您可搭配媒體質量摘要報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="6d3a6-137">媒體質量摘要報表篩選</span><span class="sxs-lookup"><span data-stu-id="6d3a6-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d3a6-138">名稱</span><span class="sxs-lookup"><span data-stu-id="6d3a6-138">Name</span></span></th>
<th><span data-ttu-id="6d3a6-139">說明</span><span class="sxs-lookup"><span data-stu-id="6d3a6-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-140"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-141">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-141">Start date/time for the time range.</span></span> <span data-ttu-id="6d3a6-142">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-142">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6d3a6-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6d3a6-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6d3a6-144">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-144">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="6d3a6-145">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-145">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6d3a6-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6d3a6-146">7/7/2012</span></span></p>
<p><span data-ttu-id="6d3a6-147">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6d3a6-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6d3a6-148">7/3/2012</span></span></p>
<p><span data-ttu-id="6d3a6-149">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-150"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-151">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-151">End date/time for the time range.</span></span> <span data-ttu-id="6d3a6-152">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-152">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6d3a6-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6d3a6-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6d3a6-154">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-154">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="6d3a6-155">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-155">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6d3a6-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6d3a6-156">7/7/2012</span></span></p>
<p><span data-ttu-id="6d3a6-157">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6d3a6-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6d3a6-158">7/3/2012</span></span></p>
<p><span data-ttu-id="6d3a6-159">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-160"><strong>Access 類型</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-161">指出撥打電話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-161">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="6d3a6-162">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-162">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d3a6-163">同時</span><span class="sxs-lookup"><span data-stu-id="6d3a6-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-164">內部</span><span class="sxs-lookup"><span data-stu-id="6d3a6-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-165">外來</span><span class="sxs-lookup"><span data-stu-id="6d3a6-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-166"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-167">指出撥打電話時，用戶端連線到的網路類型。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-167">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="6d3a6-168">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-168">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d3a6-169">同時</span><span class="sxs-lookup"><span data-stu-id="6d3a6-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-170">有線</span><span class="sxs-lookup"><span data-stu-id="6d3a6-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-171">無線</span><span class="sxs-lookup"><span data-stu-id="6d3a6-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-172"><strong>點對點</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-173">指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-173">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="6d3a6-174">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d3a6-175">同時</span><span class="sxs-lookup"><span data-stu-id="6d3a6-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-176">點對點</span><span class="sxs-lookup"><span data-stu-id="6d3a6-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="6d3a6-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6d3a6-178">指標</span><span class="sxs-lookup"><span data-stu-id="6d3a6-178">Metrics</span></span>

<span data-ttu-id="6d3a6-179">下表列出 [媒體質量摘要] 報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="6d3a6-180">媒體質量摘要報表度量單位：語音通話摘要</span><span class="sxs-lookup"><span data-stu-id="6d3a6-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d3a6-181">名稱</span><span class="sxs-lookup"><span data-stu-id="6d3a6-181">Name</span></span></th>
<th><span data-ttu-id="6d3a6-182">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="6d3a6-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6d3a6-183">說明</span><span class="sxs-lookup"><span data-stu-id="6d3a6-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-184"><strong>呼叫類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-185">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-185">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-186">當您按一下此專案時，報告會根據該類型顯示通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-186">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="6d3a6-187">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-187">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d3a6-188">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-189">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-190">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-191">PSTN 電話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="6d3a6-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-192">PSTN 通話（非旁路）： UC 腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-193">PSTN 通話（非旁路）：閘道腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-194">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="6d3a6-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-195"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-196">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-196">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-197">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-198"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-199">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-199">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-200">分類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-200">Total number of calls classified as poor.</span></span> <span data-ttu-id="6d3a6-201">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-201">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-202"><strong>通話音量（無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-203">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-203">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-204">已使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-205"><strong>通話量（VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-206">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-206">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-207">已使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-208"><strong>通話音量（外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-209">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-209">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-210">使用外部連線的呼叫數量（也就是內部網路以外的連線）。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-211"><strong>往返行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-212">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-212">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-213">即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-213">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="6d3a6-214">100毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-214">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="6d3a6-215">高往返值可能是由國際呼叫路由、路由配置錯誤或超載媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-215">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="6d3a6-216">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-216">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-217"><strong>下降（MOS）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-218">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-218">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-219">通話期間平均觀念得分（MOS）的平均數量下降。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="6d3a6-220">降級值的範圍可從低0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="6d3a6-221">0.5 或較低的值代表可接受的下降。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="6d3a6-222">過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="6d3a6-223">在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="6d3a6-224">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-224">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="6d3a6-225">高品質的結果會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-225">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-226"><strong>資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-227">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-227">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-228">RTP 資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-228">Average rate of RTP packet loss.</span></span> <span data-ttu-id="6d3a6-229">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-229">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="6d3a6-230">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-230">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-231"><strong>抖動（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-232">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-232">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-233">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6d3a6-234">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-235"><strong>Healer 隱藏比例</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-236">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-236">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-237">隱藏的音訊樣本與總樣本數的平均比率。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-237">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="6d3a6-238">（隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-238">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-239"><strong>Healer 延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-240">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-240">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-241">延伸音訊樣本的平均比例與總樣本數的總和。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-241">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="6d3a6-242">（已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-242">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-243"><strong>Healer 壓縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-244">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-244">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-245">壓縮之音訊樣本的平均比率為樣本總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-245">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="6d3a6-246">（壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-246">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="6d3a6-247">媒體質量摘要報表度量單位：影片通話摘要</span><span class="sxs-lookup"><span data-stu-id="6d3a6-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d3a6-248">名稱</span><span class="sxs-lookup"><span data-stu-id="6d3a6-248">Name</span></span></th>
<th><span data-ttu-id="6d3a6-249">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="6d3a6-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6d3a6-250">說明</span><span class="sxs-lookup"><span data-stu-id="6d3a6-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-251"><strong>呼叫類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-252">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-252">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-253">當您按一下此專案時，報告會根據該類型顯示通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-253">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="6d3a6-254">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-254">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d3a6-255">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-256">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-257">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-258">PSTN 電話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="6d3a6-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-259">PSTN 通話（非旁路）： UC 腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-260">PSTN 通話（非旁路）：閘道腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-261">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="6d3a6-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-262"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-263">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-263">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-264">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-265"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-266">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-266">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-267">分類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-267">Total number of calls classified as poor.</span></span> <span data-ttu-id="6d3a6-268">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-268">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-269"><strong>通話音量（無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-270">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-270">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-271">已使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-272"><strong>通話量（VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-273">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-273">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-274">已使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-275"><strong>通話音量（外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-276">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-276">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-277">使用外部連線的呼叫數量（也就是內部網路以外的連線）。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-278"><strong>平均比對率（Kbits/s）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-279">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-279">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-280">平均視頻位元速率（以千位數/秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-281"><strong>低位比率%</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-282">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-282">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-283">位元速率低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-284"><strong>輸出資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-285">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-285">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-286">輸出資料包的即時傳輸通訊協定（RTP）資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-286">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="6d3a6-287">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-287">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="6d3a6-288">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-288">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-289"><strong>凍結的畫面%</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-290">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-290">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-291">「凍結」畫面的百分比。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-291">Percentage of “frozen” frames.</span></span> <span data-ttu-id="6d3a6-292">在凍結的畫面中，當通話的音訊部分繼續時，影片會停止向前進行。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-292">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-293"><strong>輸出平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-294">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-294">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-295">通話期間輸出傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-296"><strong>輸入平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-297">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-297">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-298">通話期間內送傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-299"><strong>輸入低畫面播放速率%</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-300">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-300">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-301">傳入影片的位元速率低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-302"><strong>用戶端健康情況%</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d3a6-303">表示通話期間用戶端裝置的相對健康情況。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="6d3a6-304">媒體質量摘要報告規格：應用程式共用通話摘要</span><span class="sxs-lookup"><span data-stu-id="6d3a6-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d3a6-305">名稱</span><span class="sxs-lookup"><span data-stu-id="6d3a6-305">Name</span></span></th>
<th><span data-ttu-id="6d3a6-306">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="6d3a6-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6d3a6-307">說明</span><span class="sxs-lookup"><span data-stu-id="6d3a6-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-308"><strong>呼叫類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-309">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-309">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-310">當您按一下此專案時，報告會根據該類型顯示通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-310">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="6d3a6-311">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="6d3a6-311">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d3a6-312">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-313">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-314">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="6d3a6-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-315">PSTN 電話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="6d3a6-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-316">PSTN 通話（非旁路）： UC 腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-317">PSTN 通話（非旁路）：閘道腿</span><span class="sxs-lookup"><span data-stu-id="6d3a6-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6d3a6-318">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="6d3a6-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-319"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-320">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-320">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-321">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-322"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-323">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-323">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-324">分類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-324">Total number of calls classified as poor.</span></span> <span data-ttu-id="6d3a6-325">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-325">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-326"><strong>通話音量（無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-327">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-327">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-328">已使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-329"><strong>通話量（VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-330">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-330">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-331">已使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-332"><strong>通話音量（外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-333">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-333">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-334">使用外部連線的呼叫數量（也就是內部網路以外的連線）。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-335"><strong>抖動（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-336">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-336">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-337">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6d3a6-338">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-339"><strong>平均相對單向</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-340">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-340">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-341">兩個媒體端點之間的平均相對單向延遲。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-341">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="6d3a6-342">這是一個單跳躍延遲測量。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-342">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d3a6-343"><strong>平均 .RDP 磚處理延遲時間</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-344">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-344">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-345">在查看會話期間，AS 會議服務器中的 [作為會議中的平均 RDP 磚處理延遲]。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="6d3a6-346">高平均值會在觀賞體驗中反映較長的延遲時間，並包含網路延遲。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="6d3a6-347">超負荷的會議服務器可能會遇到較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d3a6-348"><strong>總 spoiled 磚%</strong></span><span class="sxs-lookup"><span data-stu-id="6d3a6-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="6d3a6-349">否</span><span class="sxs-lookup"><span data-stu-id="6d3a6-349">No</span></span></p></td>
<td><p><span data-ttu-id="6d3a6-350">Spoiled RDP 磚的總百分比。</span><span class="sxs-lookup"><span data-stu-id="6d3a6-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

