---
title: Lync Server 2013：通話許可控制報告
description: Lync Server 2013：通話許可控制報告。
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
ms.openlocfilehash: 8764e51603e7097095894bc1230c2a2bb1126b9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572359"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="803e8-103">Lync Server 2013 中的通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="803e8-103">Call Admission Control Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="803e8-104">_**主題上次修改日期：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="803e8-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="803e8-105">通話許可控制報告可提供對等和會議會話的相關資訊，這些會話是在「通話許可控制」設定的限制下進行的。</span><span class="sxs-lookup"><span data-stu-id="803e8-105">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="803e8-106">Microsoft Lync Server 2010 所引進的通話許可控制可讓系統管理員允許 (或不允許根據頻寬限制進行) 通訊會話。</span><span class="sxs-lookup"><span data-stu-id="803e8-106">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="803e8-107">例如，系統管理員可以建立原則限制可用於語音和影片通話的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="803e8-107">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="803e8-108">如果已達到頻寬限制，則直到其中一個目前的通話結束並釋放必要的網路資源時，才可以放入新的語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="803e8-108">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="803e8-109">存取通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="803e8-109">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="803e8-110">通話許可控制報告可從監控報告的首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="803e8-110">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="803e8-111">從通話許可控制報告中，您可以深入查看下列任一報告：</span><span class="sxs-lookup"><span data-stu-id="803e8-111">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="803e8-112">會議詳細資料包告–若要存取此報告，請按一下會議會話中的詳細資料度量。</span><span class="sxs-lookup"><span data-stu-id="803e8-112">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="803e8-113">Peer-to-Peer 會話詳細資料包告–若要存取此報告，請按一下點對點工作階段的詳細資料度量。</span><span class="sxs-lookup"><span data-stu-id="803e8-113">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="803e8-114">充分利用通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="803e8-114">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="803e8-115">若要取得因頻寬不足而失敗的來電清單，請在 [呼叫類別] 下拉式清單中，選取 [通話許可控制拒絕的來電]。</span><span class="sxs-lookup"><span data-stu-id="803e8-115">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="803e8-116">大多數傳回的呼叫可能會有5個診斷識別碼：</span><span class="sxs-lookup"><span data-stu-id="803e8-116">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="803e8-117">沒有足夠的頻寬來建立會話。</span><span class="sxs-lookup"><span data-stu-id="803e8-117">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="803e8-118">嘗試 PSTN 重新路由傳送。</span><span class="sxs-lookup"><span data-stu-id="803e8-118">Attempt PSTN re-route.</span></span>

<span data-ttu-id="803e8-119">這表示通話許可控制限制阻礙在 VoIP 網路上進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="803e8-119">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="803e8-120">篩選</span><span class="sxs-lookup"><span data-stu-id="803e8-120">Filters</span></span>

<span data-ttu-id="803e8-121">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="803e8-121">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="803e8-122">例如，通話許可控制報告可讓您篩選撥打通話之使用者的電話，或由呼叫的使用者來篩選來電。</span><span class="sxs-lookup"><span data-stu-id="803e8-122">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="803e8-123">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="803e8-123">You can also choose how data should be grouped.</span></span> <span data-ttu-id="803e8-124">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="803e8-124">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="803e8-125">下表列出您可以搭配通話許可控制報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="803e8-125">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="803e8-126">通話許可控制報告篩選器</span><span class="sxs-lookup"><span data-stu-id="803e8-126">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="803e8-127">名稱</span><span class="sxs-lookup"><span data-stu-id="803e8-127">Name</span></span></th>
<th><span data-ttu-id="803e8-128">描述</span><span class="sxs-lookup"><span data-stu-id="803e8-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="803e8-129"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-129"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="803e8-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="803e8-132">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="803e8-132">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="803e8-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="803e8-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="803e8-135">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="803e8-135">7/17/12012</span></span></p>
<p><span data-ttu-id="803e8-136">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="803e8-136">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="803e8-137">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="803e8-137">7/13/2012</span></span></p>
<p><span data-ttu-id="803e8-138">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="803e8-138">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-139"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-139"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="803e8-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="803e8-142">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="803e8-142">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="803e8-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="803e8-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="803e8-145">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="803e8-145">7/17/12012</span></span></p>
<p><span data-ttu-id="803e8-146">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="803e8-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="803e8-147">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="803e8-147">7/13/2012</span></span></p>
<p><span data-ttu-id="803e8-148">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="803e8-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-149"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-149"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-p110">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="803e8-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-153"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-153"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-154">活動的類型。</span><span class="sxs-lookup"><span data-stu-id="803e8-154">Type of activity.</span></span> <span data-ttu-id="803e8-155">選取下列其中一個活動：</span><span class="sxs-lookup"><span data-stu-id="803e8-155">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="803e8-156">一切</span><span class="sxs-lookup"><span data-stu-id="803e8-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="803e8-157">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="803e8-157">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="803e8-158">會議</span><span class="sxs-lookup"><span data-stu-id="803e8-158">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-159"><strong>通話類別</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-159"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-160">指出用於通話的 CAC 的原因。</span><span class="sxs-lookup"><span data-stu-id="803e8-160">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="803e8-161">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="803e8-161">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="803e8-162">一切</span><span class="sxs-lookup"><span data-stu-id="803e8-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="803e8-163">因通話許可控制而拒絕通話</span><span class="sxs-lookup"><span data-stu-id="803e8-163">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="803e8-164">通話透過 PSTN 重新路由傳送，因為通話許可控制</span><span class="sxs-lookup"><span data-stu-id="803e8-164">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="803e8-165">Peer-to-Peer 會話的計量</span><span class="sxs-lookup"><span data-stu-id="803e8-165">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="803e8-166">下表列出點對點工作階段的通話許可控制報告中所提供的資訊 (也就是說，只涉及兩位參與者的會話) 。</span><span class="sxs-lookup"><span data-stu-id="803e8-166">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="803e8-167">Peer-to-Peer 會話的計量</span><span class="sxs-lookup"><span data-stu-id="803e8-167">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="803e8-168">姓名</span><span class="sxs-lookup"><span data-stu-id="803e8-168">Name</span></span></th>
<th><span data-ttu-id="803e8-169">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="803e8-169">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="803e8-170">描述</span><span class="sxs-lookup"><span data-stu-id="803e8-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="803e8-171"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-171"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-172">否</span><span class="sxs-lookup"><span data-stu-id="803e8-172">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-173">當您按一下此專案時，報告會顯示指定之會話的 Peer-to-Peer 會話詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="803e8-173">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-174"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-174"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-175">是</span><span class="sxs-lookup"><span data-stu-id="803e8-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-176">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="803e8-176">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-177"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-177"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-178">是</span><span class="sxs-lookup"><span data-stu-id="803e8-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-179">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="803e8-179">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-180"><strong>方式</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-180"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-181">是</span><span class="sxs-lookup"><span data-stu-id="803e8-181">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-182">通訊形式 (例如在會話期間使用的音訊和影片) 。</span><span class="sxs-lookup"><span data-stu-id="803e8-182">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-183"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-183"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-184">是</span><span class="sxs-lookup"><span data-stu-id="803e8-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-185">初始會話邀請傳送給寄件者的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="803e8-185">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-186"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-186"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-187">是</span><span class="sxs-lookup"><span data-stu-id="803e8-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-188">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="803e8-188">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-189"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-189"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-190">是</span><span class="sxs-lookup"><span data-stu-id="803e8-190">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-191">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="803e8-191">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-192"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-192"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-193">是</span><span class="sxs-lookup"><span data-stu-id="803e8-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-p113">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="803e8-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="803e8-196">會議會話的計量</span><span class="sxs-lookup"><span data-stu-id="803e8-196">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="803e8-197">下表列出會議會話的通話許可控制報告中所提供的資訊 (也就是說，涉及三個或更多參與者) 的會話。</span><span class="sxs-lookup"><span data-stu-id="803e8-197">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="803e8-198">會議會話的計量</span><span class="sxs-lookup"><span data-stu-id="803e8-198">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="803e8-199">姓名</span><span class="sxs-lookup"><span data-stu-id="803e8-199">Name</span></span></th>
<th><span data-ttu-id="803e8-200">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="803e8-200">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="803e8-201">描述</span><span class="sxs-lookup"><span data-stu-id="803e8-201">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="803e8-202"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-202"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-203">是</span><span class="sxs-lookup"><span data-stu-id="803e8-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-204">會議的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="803e8-204">Unique identifier for the conference.</span></span> <span data-ttu-id="803e8-205">當您按一下此專案時，報表會顯示個別的會議參與者。</span><span class="sxs-lookup"><span data-stu-id="803e8-205">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-206"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-206"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-207">是</span><span class="sxs-lookup"><span data-stu-id="803e8-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-208">召開會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="803e8-208">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-209"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-209"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-210">是</span><span class="sxs-lookup"><span data-stu-id="803e8-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-211">會議中所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="803e8-211">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-212"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-212"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-213">是</span><span class="sxs-lookup"><span data-stu-id="803e8-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-214">會議開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="803e8-214">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-215"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-215"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-216">是</span><span class="sxs-lookup"><span data-stu-id="803e8-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="803e8-217">會議結束的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="803e8-217">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="803e8-218">個別會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="803e8-218">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="803e8-219">下表列出個別會議參與者通話許可控制報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="803e8-219">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="803e8-220">個別會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="803e8-220">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="803e8-221">姓名</span><span class="sxs-lookup"><span data-stu-id="803e8-221">Name</span></span></th>
<th><span data-ttu-id="803e8-222">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="803e8-222">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="803e8-223">描述</span><span class="sxs-lookup"><span data-stu-id="803e8-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="803e8-224"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-224"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-225">否</span><span class="sxs-lookup"><span data-stu-id="803e8-225">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-226">會議參與者所扮演的角色 (例如，簡報者)。</span><span class="sxs-lookup"><span data-stu-id="803e8-226">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-227"><strong>參與者</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-227"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-228">否</span><span class="sxs-lookup"><span data-stu-id="803e8-228">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-229">會議參與者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="803e8-229">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-230"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-230"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-231">否</span><span class="sxs-lookup"><span data-stu-id="803e8-231">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-232">參與者的網路連線 (一般來說是從內部或從外部)。</span><span class="sxs-lookup"><span data-stu-id="803e8-232">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-233"><strong>形態</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-233"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-234">否</span><span class="sxs-lookup"><span data-stu-id="803e8-234">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-235">會議類型 (例如，A/V 會議) 。</span><span class="sxs-lookup"><span data-stu-id="803e8-235">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-236"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-236"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-237">否</span><span class="sxs-lookup"><span data-stu-id="803e8-237">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-238">參與者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="803e8-238">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="803e8-239"><strong>離開時間</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-239"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-240">否</span><span class="sxs-lookup"><span data-stu-id="803e8-240">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-241">參與者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="803e8-241">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="803e8-242"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="803e8-242"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="803e8-243">否</span><span class="sxs-lookup"><span data-stu-id="803e8-243">No</span></span></p></td>
<td><p><span data-ttu-id="803e8-p115">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="803e8-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

