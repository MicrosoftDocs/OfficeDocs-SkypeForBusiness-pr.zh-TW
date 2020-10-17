---
title: Lync Server 2013：通話許可控制報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c1ff2b667c0529dfb7a90291dba7ad5ab154a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517960"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="166e0-102">Lync Server 2013 中的通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="166e0-102">Call Admission Control Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="166e0-103">_**主題上次修改日期：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="166e0-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="166e0-104">通話許可控制報告可提供對等和會議會話的相關資訊，這些會話是在「通話許可控制」設定的限制下進行的。</span><span class="sxs-lookup"><span data-stu-id="166e0-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="166e0-105">Microsoft Lync Server 2010 所引進的通話許可控制可讓系統管理員允許 (或不允許根據頻寬限制進行) 通訊會話。</span><span class="sxs-lookup"><span data-stu-id="166e0-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="166e0-106">例如，系統管理員可以建立原則限制可用於語音和影片通話的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="166e0-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="166e0-107">如果已達到頻寬限制，則直到其中一個目前的通話結束並釋放必要的網路資源時，才可以放入新的語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="166e0-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="166e0-108">存取通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="166e0-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="166e0-109">通話許可控制報告可從監控報告的首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="166e0-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="166e0-110">從通話許可控制報告中，您可以深入查看下列任一報告：</span><span class="sxs-lookup"><span data-stu-id="166e0-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="166e0-111">會議詳細資料包告–若要存取此報告，請按一下會議會話中的詳細資料度量。</span><span class="sxs-lookup"><span data-stu-id="166e0-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="166e0-112">Peer-to-Peer 會話詳細資料包告–若要存取此報告，請按一下點對點工作階段的詳細資料度量。</span><span class="sxs-lookup"><span data-stu-id="166e0-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="166e0-113">充分利用通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="166e0-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="166e0-114">若要取得因頻寬不足而失敗的來電清單，請在 [呼叫類別] 下拉式清單中，選取 [通話許可控制拒絕的來電]。</span><span class="sxs-lookup"><span data-stu-id="166e0-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="166e0-115">大多數傳回的呼叫可能會有5個診斷識別碼：</span><span class="sxs-lookup"><span data-stu-id="166e0-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="166e0-116">沒有足夠的頻寬來建立會話。</span><span class="sxs-lookup"><span data-stu-id="166e0-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="166e0-117">嘗試 PSTN 重新路由傳送。</span><span class="sxs-lookup"><span data-stu-id="166e0-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="166e0-118">這表示通話許可控制限制阻礙在 VoIP 網路上進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="166e0-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="166e0-119">篩選</span><span class="sxs-lookup"><span data-stu-id="166e0-119">Filters</span></span>

<span data-ttu-id="166e0-120">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="166e0-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="166e0-121">例如，通話許可控制報告可讓您篩選撥打通話之使用者的電話，或由呼叫的使用者來篩選來電。</span><span class="sxs-lookup"><span data-stu-id="166e0-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="166e0-122">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="166e0-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="166e0-123">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="166e0-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="166e0-124">下表列出您可以搭配通話許可控制報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="166e0-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="166e0-125">通話許可控制報告篩選器</span><span class="sxs-lookup"><span data-stu-id="166e0-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="166e0-126">名稱</span><span class="sxs-lookup"><span data-stu-id="166e0-126">Name</span></span></th>
<th><span data-ttu-id="166e0-127">描述</span><span class="sxs-lookup"><span data-stu-id="166e0-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="166e0-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="166e0-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="166e0-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="166e0-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="166e0-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="166e0-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="166e0-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="166e0-134">7/17/12012</span></span></p>
<p><span data-ttu-id="166e0-135">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="166e0-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="166e0-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="166e0-136">7/13/2012</span></span></p>
<p><span data-ttu-id="166e0-137">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="166e0-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="166e0-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="166e0-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="166e0-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="166e0-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="166e0-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="166e0-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="166e0-144">7/17/12012</span></span></p>
<p><span data-ttu-id="166e0-145">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="166e0-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="166e0-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="166e0-146">7/13/2012</span></span></p>
<p><span data-ttu-id="166e0-147">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="166e0-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-148"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-p110">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="166e0-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-152"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-153">活動的類型。</span><span class="sxs-lookup"><span data-stu-id="166e0-153">Type of activity.</span></span> <span data-ttu-id="166e0-154">選取下列其中一個活動：</span><span class="sxs-lookup"><span data-stu-id="166e0-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="166e0-155">一切</span><span class="sxs-lookup"><span data-stu-id="166e0-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="166e0-156">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="166e0-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="166e0-157">會議</span><span class="sxs-lookup"><span data-stu-id="166e0-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-158"><strong>通話類別</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-159">指出用於通話的 CAC 的原因。</span><span class="sxs-lookup"><span data-stu-id="166e0-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="166e0-160">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="166e0-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="166e0-161">一切</span><span class="sxs-lookup"><span data-stu-id="166e0-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="166e0-162">因通話許可控制而拒絕通話</span><span class="sxs-lookup"><span data-stu-id="166e0-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="166e0-163">通話透過 PSTN 重新路由傳送，因為通話許可控制</span><span class="sxs-lookup"><span data-stu-id="166e0-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="166e0-164">Peer-to-Peer 會話的計量</span><span class="sxs-lookup"><span data-stu-id="166e0-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="166e0-165">下表列出點對點工作階段的通話許可控制報告中所提供的資訊 (也就是說，只涉及兩位參與者的會話) 。</span><span class="sxs-lookup"><span data-stu-id="166e0-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="166e0-166">Peer-to-Peer 會話的計量</span><span class="sxs-lookup"><span data-stu-id="166e0-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="166e0-167">姓名</span><span class="sxs-lookup"><span data-stu-id="166e0-167">Name</span></span></th>
<th><span data-ttu-id="166e0-168">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="166e0-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="166e0-169">描述</span><span class="sxs-lookup"><span data-stu-id="166e0-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="166e0-170"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-171">否</span><span class="sxs-lookup"><span data-stu-id="166e0-171">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-172">當您按一下此專案時，報告會顯示指定之會話的 Peer-to-Peer 會話詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="166e0-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-173"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-174">是</span><span class="sxs-lookup"><span data-stu-id="166e0-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-175">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="166e0-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-176"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-177">是</span><span class="sxs-lookup"><span data-stu-id="166e0-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-178">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="166e0-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-179"><strong>方式</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-180">是</span><span class="sxs-lookup"><span data-stu-id="166e0-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-181">通訊形式 (例如在會話期間使用的音訊和影片) 。</span><span class="sxs-lookup"><span data-stu-id="166e0-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-182"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-183">是</span><span class="sxs-lookup"><span data-stu-id="166e0-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-184">初始會話邀請傳送給寄件者的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="166e0-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-185"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-186">是</span><span class="sxs-lookup"><span data-stu-id="166e0-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-187">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="166e0-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-188"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-189">是</span><span class="sxs-lookup"><span data-stu-id="166e0-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-190">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="166e0-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-191"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-192">是</span><span class="sxs-lookup"><span data-stu-id="166e0-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-p113">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="166e0-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="166e0-195">會議會話的計量</span><span class="sxs-lookup"><span data-stu-id="166e0-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="166e0-196">下表列出會議會話的通話許可控制報告中所提供的資訊 (也就是說，涉及三個或更多參與者) 的會話。</span><span class="sxs-lookup"><span data-stu-id="166e0-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="166e0-197">會議會話的計量</span><span class="sxs-lookup"><span data-stu-id="166e0-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="166e0-198">姓名</span><span class="sxs-lookup"><span data-stu-id="166e0-198">Name</span></span></th>
<th><span data-ttu-id="166e0-199">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="166e0-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="166e0-200">描述</span><span class="sxs-lookup"><span data-stu-id="166e0-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="166e0-201"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-202">是</span><span class="sxs-lookup"><span data-stu-id="166e0-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-203">會議的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="166e0-203">Unique identifier for the conference.</span></span> <span data-ttu-id="166e0-204">當您按一下此專案時，報表會顯示個別的會議參與者。</span><span class="sxs-lookup"><span data-stu-id="166e0-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-205"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-206">是</span><span class="sxs-lookup"><span data-stu-id="166e0-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-207">召開會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="166e0-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-208"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-209">是</span><span class="sxs-lookup"><span data-stu-id="166e0-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-210">會議中所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="166e0-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-211"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-212">是</span><span class="sxs-lookup"><span data-stu-id="166e0-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-213">會議開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="166e0-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-214"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-215">是</span><span class="sxs-lookup"><span data-stu-id="166e0-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="166e0-216">會議結束的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="166e0-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="166e0-217">個別會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="166e0-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="166e0-218">下表列出個別會議參與者通話許可控制報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="166e0-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="166e0-219">個別會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="166e0-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="166e0-220">姓名</span><span class="sxs-lookup"><span data-stu-id="166e0-220">Name</span></span></th>
<th><span data-ttu-id="166e0-221">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="166e0-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="166e0-222">描述</span><span class="sxs-lookup"><span data-stu-id="166e0-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="166e0-223"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-224">否</span><span class="sxs-lookup"><span data-stu-id="166e0-224">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-225">會議參與者所扮演的角色 (例如，簡報者)。</span><span class="sxs-lookup"><span data-stu-id="166e0-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-226"><strong>參與者</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-227">否</span><span class="sxs-lookup"><span data-stu-id="166e0-227">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-228">會議參與者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="166e0-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-229"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-230">否</span><span class="sxs-lookup"><span data-stu-id="166e0-230">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-231">參與者的網路連線 (一般來說是從內部或從外部)。</span><span class="sxs-lookup"><span data-stu-id="166e0-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-232"><strong>形態</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-233">否</span><span class="sxs-lookup"><span data-stu-id="166e0-233">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-234">會議類型 (例如，A/V 會議) 。</span><span class="sxs-lookup"><span data-stu-id="166e0-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-235"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-236">否</span><span class="sxs-lookup"><span data-stu-id="166e0-236">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-237">參與者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="166e0-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="166e0-238"><strong>離開時間</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-239">否</span><span class="sxs-lookup"><span data-stu-id="166e0-239">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-240">參與者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="166e0-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="166e0-241"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="166e0-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="166e0-242">否</span><span class="sxs-lookup"><span data-stu-id="166e0-242">No</span></span></p></td>
<td><p><span data-ttu-id="166e0-p115">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="166e0-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

