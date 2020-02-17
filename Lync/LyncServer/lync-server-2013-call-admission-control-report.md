---
title: Lync Server 2013： 通話許可控制報告
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
ms.openlocfilehash: ba5b643adf6a8208285aeba66304ddd1657afdfa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="0e2a5-102">Lync Server 2013 中通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="0e2a5-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e2a5-103">_**主題上次修改日期：** 2012年-06-29_</span><span class="sxs-lookup"><span data-stu-id="0e2a5-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="0e2a5-104">通話許可控制報告提供的端對端的相關資訊和 [限制] 下所進行的會議工作階段設定中的通話許可控制的地方。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="0e2a5-105">通話許可控制，在 Microsoft Lync Server 2010 中引進，讓系統管理員允許 （或不允許） 的通訊工作階段為基礎的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="0e2a5-106">例如，管理員可以建立加諸的適用於語音和視訊通話頻寬限制的原則。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="0e2a5-107">如果已達到該頻寬限制，然後沒有新的語音或視訊通話可以放直到下列其中一個目前的呼叫已結束並釋出所需的網路資源。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="0e2a5-108">存取通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="0e2a5-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="0e2a5-109">通話許可控制報告是從監視報告首頁存取。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0e2a5-110">從 [通話許可控制報告中您可以向下其中一個下列報告切入：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="0e2a5-111">會議詳細資料報告： 要存取這份報告，請按一下 [從會議工作階段的詳細資料計量。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="0e2a5-112">端對端工作階段詳細資料報告： 要存取這份報告，請按一下 [詳細資料] 計量的端對端工作階段。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="0e2a5-113">通話許可控制報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="0e2a5-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="0e2a5-114">若要取得的失敗，因為沒有足夠的頻寬的呼叫清單，選取 [因為呼叫類別下拉式清單中的通話許可控制而拒絕通話]。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="0e2a5-115">大部分的傳回呼叫可能會有 5 的診斷識別碼：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="0e2a5-116">若要建立工作階段的頻寬不足。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="0e2a5-117">嘗試 PSTN 重新路由傳送。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="0e2a5-118">這表示該通話許可控制限制所導致無法從 VoIP 網路上進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0e2a5-119">篩選</span><span class="sxs-lookup"><span data-stu-id="0e2a5-119">Filters</span></span>

<span data-ttu-id="0e2a5-120">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="0e2a5-121">例如，通話許可控制報告可讓您篩選由撥打通話之使用者或已被呼叫使用者的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="0e2a5-122">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="0e2a5-123">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0e2a5-124">下表列出您可以搭配通話許可控制報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="0e2a5-125">通話許可控制報告篩選器</span><span class="sxs-lookup"><span data-stu-id="0e2a5-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e2a5-126">名稱</span><span class="sxs-lookup"><span data-stu-id="0e2a5-126">Name</span></span></th>
<th><span data-ttu-id="0e2a5-127">描述</span><span class="sxs-lookup"><span data-stu-id="0e2a5-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0e2a5-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0e2a5-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0e2a5-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0e2a5-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0e2a5-134">7/17/12012</span></span></p>
<p><span data-ttu-id="0e2a5-135">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0e2a5-136">2012/7/13</span><span class="sxs-lookup"><span data-stu-id="0e2a5-136">7/13/2012</span></span></p>
<p><span data-ttu-id="0e2a5-137">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0e2a5-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0e2a5-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0e2a5-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0e2a5-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0e2a5-144">7/17/12012</span></span></p>
<p><span data-ttu-id="0e2a5-145">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0e2a5-146">2012/7/13</span><span class="sxs-lookup"><span data-stu-id="0e2a5-146">7/13/2012</span></span></p>
<p><span data-ttu-id="0e2a5-147">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-p110">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-152"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-153">活動的類型。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-153">Type of activity.</span></span> <span data-ttu-id="0e2a5-154">選取下列其中一個下列活動：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e2a5-155">[全部]</span><span class="sxs-lookup"><span data-stu-id="0e2a5-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="0e2a5-156">端對端</span><span class="sxs-lookup"><span data-stu-id="0e2a5-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="0e2a5-157">會議</span><span class="sxs-lookup"><span data-stu-id="0e2a5-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-158"><strong>通話類別</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-159">會指出 CAC 已用於通話的原因。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="0e2a5-160">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0e2a5-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e2a5-161">[全部]</span><span class="sxs-lookup"><span data-stu-id="0e2a5-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="0e2a5-162">因通話許可控制而拒絕通話</span><span class="sxs-lookup"><span data-stu-id="0e2a5-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="0e2a5-163">因通話許可控制而透過 PSTN 重新路由</span><span class="sxs-lookup"><span data-stu-id="0e2a5-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0e2a5-164">端對端工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="0e2a5-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="0e2a5-165">下表列出對等端對端工作階段 （也就是工作階段只有兩個參與者） 通話許可控制報告內所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0e2a5-166">端對端工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="0e2a5-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e2a5-167">名稱</span><span class="sxs-lookup"><span data-stu-id="0e2a5-167">Name</span></span></th>
<th><span data-ttu-id="0e2a5-168">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="0e2a5-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0e2a5-169">描述</span><span class="sxs-lookup"><span data-stu-id="0e2a5-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-170"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-171">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-171">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-172">當您按一下此項目時，報告顯示您對等工作階段詳細資料報告的指定的工作階段。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-173"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-174">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-175">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-176"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-177">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-178">獲邀加入工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-179"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-180">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-181">溝通形式 （如音訊或視訊） 工作階段期間所用。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-182"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-183">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-184">日期和時間初始工作階段邀請傳送至 「 從 」 使用者。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-185"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-186">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-187">日期和時間收到的邀請接受度。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-188"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-189">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-190">日期和工作階段結束的時間。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-191"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-192">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-p113">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0e2a5-195">會議工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="0e2a5-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="0e2a5-196">下表列出會議工作階段 （也就是參與者的工作階段三個或多個） 的通話許可控制報告內所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0e2a5-197">會議工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="0e2a5-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e2a5-198">名稱</span><span class="sxs-lookup"><span data-stu-id="0e2a5-198">Name</span></span></th>
<th><span data-ttu-id="0e2a5-199">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="0e2a5-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0e2a5-200">描述</span><span class="sxs-lookup"><span data-stu-id="0e2a5-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-201"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-202">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-203">會議的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-203">Unique identifier for the conference.</span></span> <span data-ttu-id="0e2a5-204">當您按一下此項目時，「 報告 」 顯示個別參與者。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-205"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-206">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-207">召開會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-209">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-210">會議中使用的 edge Server。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-211"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-212">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-213">會議開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-214"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-215">是</span><span class="sxs-lookup"><span data-stu-id="0e2a5-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-216">會議結束的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="0e2a5-217">個別會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="0e2a5-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="0e2a5-218">下表列出個別參與者的通話許可控制報告內所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="0e2a5-219">個別會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="0e2a5-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e2a5-220">名稱</span><span class="sxs-lookup"><span data-stu-id="0e2a5-220">Name</span></span></th>
<th><span data-ttu-id="0e2a5-221">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="0e2a5-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0e2a5-222">描述</span><span class="sxs-lookup"><span data-stu-id="0e2a5-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-223"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-224">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-224">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-225">會議參與者所扮演的角色 (例如，簡報者)。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-226"><strong>參與者</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-227">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-227">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-228">會議參與者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-229"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-230">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-230">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-231">參與者的網路連線 (一般來說是從內部或從外部)。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-232"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-233">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-233">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-234">會議類型 (例如，A / V 會議)。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-235"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-236">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-236">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-237">參與者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e2a5-238"><strong>離開時間</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-239">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-239">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-240">參與者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e2a5-241"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="0e2a5-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0e2a5-242">否</span><span class="sxs-lookup"><span data-stu-id="0e2a5-242">No</span></span></p></td>
<td><p><span data-ttu-id="0e2a5-p115">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e2a5-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

