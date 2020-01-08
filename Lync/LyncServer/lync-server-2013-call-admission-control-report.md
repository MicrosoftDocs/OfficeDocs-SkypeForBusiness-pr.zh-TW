---
title: Lync Server 2013：呼叫許可控制報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f31159742757b7ef8b6889b7961bad747b1f6d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="a4e8b-102">Lync Server 2013 中的呼叫許可控制報告</span><span class="sxs-lookup"><span data-stu-id="a4e8b-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4e8b-103">_**主題上次修改日期：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="a4e8b-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="a4e8b-104">[通話許可控制] 報告會提供對等及會議會話的相關資訊，這些會話是在 [呼叫許可控制] 設定的 [限制] 下進行。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="a4e8b-105">在 Microsoft Lync Server 2010 中引進的呼叫許可控制，提供讓系統管理員允許（或不允許）根據頻寬限制進行通訊會話的方式。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="a4e8b-106">例如，管理員可以建立原則，限制語音和視頻通話可用的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="a4e8b-107">如果已達到頻寬限制，則在其中一個目前的通話結束並釋放所需的網路資源前，不會放置新的語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="a4e8b-108">存取 [通話許可控制] 報告</span><span class="sxs-lookup"><span data-stu-id="a4e8b-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="a4e8b-109">[通話許可控制] 報告可從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="a4e8b-110">從 [呼叫許可控制] 報告中，您可以向下切入至下列其中一項報告：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="a4e8b-111">會議詳細資料包告：若要存取此報告，請按一下會議會話中的詳細資料指標。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="a4e8b-112">點對點工作階段詳細資料包告-若要存取此報告，請按一下點對點工作階段的詳細資料規格。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="a4e8b-113">充分利用 [呼叫許可控制] 報告</span><span class="sxs-lookup"><span data-stu-id="a4e8b-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="a4e8b-114">若要取得因頻寬不足而失敗的通話清單，請選取 [呼叫類別] 下拉式清單中的 [呼叫許可控制]。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="a4e8b-115">大多數傳回的通話可能會有5的診斷識別碼：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="a4e8b-116">頻寬不足，無法建立會話。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="a4e8b-117">嘗試 PSTN 重新路由。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="a4e8b-118">這表示呼叫許可控制限制是無法在 VoIP 網路上進行通話。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a4e8b-119">濾鏡</span><span class="sxs-lookup"><span data-stu-id="a4e8b-119">Filters</span></span>

<span data-ttu-id="a4e8b-120">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="a4e8b-121">例如，[通話許可控制] 報告可讓您依啟動通話的使用者或呼叫的使用者來篩選通話。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="a4e8b-122">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="a4e8b-123">在這種情況下，通話會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a4e8b-124">下表列出可與 [通話許可控制] 報告搭配使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="a4e8b-125">呼叫許可控制報告篩選器</span><span class="sxs-lookup"><span data-stu-id="a4e8b-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4e8b-126">名稱</span><span class="sxs-lookup"><span data-stu-id="a4e8b-126">Name</span></span></th>
<th><span data-ttu-id="a4e8b-127">描述</span><span class="sxs-lookup"><span data-stu-id="a4e8b-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-128"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-129">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-129">Start date/time for the time range.</span></span> <span data-ttu-id="a4e8b-130">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-130">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a4e8b-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a4e8b-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="a4e8b-132">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-132">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="a4e8b-133">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-133">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a4e8b-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="a4e8b-134">7/17/12012</span></span></p>
<p><span data-ttu-id="a4e8b-135">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a4e8b-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="a4e8b-136">7/13/2012</span></span></p>
<p><span data-ttu-id="a4e8b-137">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-138"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-139">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-139">End date/time for the time range.</span></span> <span data-ttu-id="a4e8b-140">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-140">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a4e8b-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a4e8b-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="a4e8b-142">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-142">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="a4e8b-143">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-143">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a4e8b-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="a4e8b-144">7/17/12012</span></span></p>
<p><span data-ttu-id="a4e8b-145">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a4e8b-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="a4e8b-146">7/13/2012</span></span></p>
<p><span data-ttu-id="a4e8b-147">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-148"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-149">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-149">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="a4e8b-150">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-150">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="a4e8b-151">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-151">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-152"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-153">活動類型。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-153">Type of activity.</span></span> <span data-ttu-id="a4e8b-154">選取下列其中一個活動：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="a4e8b-155">同時</span><span class="sxs-lookup"><span data-stu-id="a4e8b-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="a4e8b-156">對等</span><span class="sxs-lookup"><span data-stu-id="a4e8b-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="a4e8b-157">會議</span><span class="sxs-lookup"><span data-stu-id="a4e8b-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-158"><strong>通話類別</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-159">指出此通話使用 CAC 的原因。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="a4e8b-160">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a4e8b-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a4e8b-161">同時</span><span class="sxs-lookup"><span data-stu-id="a4e8b-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="a4e8b-162">呼叫被拒絕，因為通話許可控制</span><span class="sxs-lookup"><span data-stu-id="a4e8b-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="a4e8b-163">呼叫在 PSTN 進行重新路由的呼叫，因為呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="a4e8b-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="a4e8b-164">點對點工作階段的度量單位</span><span class="sxs-lookup"><span data-stu-id="a4e8b-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="a4e8b-165">下表列出點對點工作階段的呼叫許可控制報告中所提供的資訊（也就是只涉及兩個參與者的會話）。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="a4e8b-166">點對點工作階段的度量單位</span><span class="sxs-lookup"><span data-stu-id="a4e8b-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4e8b-167">名稱</span><span class="sxs-lookup"><span data-stu-id="a4e8b-167">Name</span></span></th>
<th><span data-ttu-id="a4e8b-168">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="a4e8b-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a4e8b-169">描述</span><span class="sxs-lookup"><span data-stu-id="a4e8b-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-170"><strong>具體</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-171">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-171">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-172">當您按一下此專案時，報告會顯示指定會話的點對點工作階段詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-173"><strong>從使用者</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-174">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-175">啟動會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-176"><strong>給使用者</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-177">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-178">受邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-179"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-180">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-181">在會話期間使用的通訊形式（例如音訊與影片）。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-182"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-183">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-184">將初始會話邀請傳送給 [寄件者] 使用者的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-185"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-186">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-187">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-188"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-189">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-190">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-191"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-192">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-193">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-193">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="a4e8b-194">診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-194">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="a4e8b-195">會議會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="a4e8b-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="a4e8b-196">下表列出會議會話的通話許可控制報告中所提供的資訊（也就是與三個或更多參與者相關的會話）。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="a4e8b-197">會議會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="a4e8b-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4e8b-198">名稱</span><span class="sxs-lookup"><span data-stu-id="a4e8b-198">Name</span></span></th>
<th><span data-ttu-id="a4e8b-199">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="a4e8b-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a4e8b-200">描述</span><span class="sxs-lookup"><span data-stu-id="a4e8b-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-201"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-202">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-203">會議的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-203">Unique identifier for the conference.</span></span> <span data-ttu-id="a4e8b-204">當您按一下此專案時，報告會顯示個別的會議參與者。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-205"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-206">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-207">組織會議的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-208"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-209">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-210">在會議中使用的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-211"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-212">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-213">會議開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-214"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-215">是</span><span class="sxs-lookup"><span data-stu-id="a4e8b-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-216">會議結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="a4e8b-217">個別會議參與者的度量單位</span><span class="sxs-lookup"><span data-stu-id="a4e8b-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="a4e8b-218">下表列出個別會議參與者的通話許可控制報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="a4e8b-219">個別會議參與者的度量單位</span><span class="sxs-lookup"><span data-stu-id="a4e8b-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4e8b-220">名稱</span><span class="sxs-lookup"><span data-stu-id="a4e8b-220">Name</span></span></th>
<th><span data-ttu-id="a4e8b-221">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="a4e8b-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a4e8b-222">描述</span><span class="sxs-lookup"><span data-stu-id="a4e8b-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-223"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-224">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-224">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-225">會議參與者所扮演的角色（例如，簡報者）。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-226"><strong>參加</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-227">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-227">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-228">會議參與者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-229"><strong>連通</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-230">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-230">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-231">參與者的網路連線（通常是內部或外部的網路連線）。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-232"><strong>模態</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-233">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-233">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-234">會議類型（例如，A/V 會議）。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-235"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-236">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-236">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-237">參與者加入會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e8b-238"><strong>休假時間</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-239">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-239">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-240">參與者離開會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e8b-241"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="a4e8b-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e8b-242">否</span><span class="sxs-lookup"><span data-stu-id="a4e8b-242">No</span></span></p></td>
<td><p><span data-ttu-id="a4e8b-243">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-243">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="a4e8b-244">診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="a4e8b-244">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

