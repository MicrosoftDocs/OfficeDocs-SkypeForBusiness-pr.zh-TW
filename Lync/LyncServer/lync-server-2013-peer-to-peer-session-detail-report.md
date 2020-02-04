---
title: Lync Server 2013：點對點工作階段詳細資料包告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bff140db52a98e0b442ca65bbbb8b148282c5755
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="6db09-102">Lync Server 2013 中的點對點工作階段詳細資料包表</span><span class="sxs-lookup"><span data-stu-id="6db09-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6db09-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="6db09-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="6db09-104">點對點工作階段詳細資料包告會傳回點對點工作階段的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6db09-104">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="6db09-105">例如，如果您選取 [立即訊息] 會話，報告就會告訴您會話中兩位使用者傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="6db09-105">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="6db09-106">存取點對點工作階段詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="6db09-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="6db09-107">您可以從下列任何報告存取點對點工作階段詳細資料包告（所有這些報告都可以從 [監控報告] 首頁存取）：</span><span class="sxs-lookup"><span data-stu-id="6db09-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="6db09-108">IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="6db09-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="6db09-109">使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="6db09-109">User Activity Report</span></span>

  - <span data-ttu-id="6db09-110">通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="6db09-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="6db09-111">失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="6db09-111">Failure List Report</span></span>

<span data-ttu-id="6db09-112">從點對點工作階段詳細資料包告中，按一下 [診斷報告（詳細資料）] 度量，即可存取[Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="6db09-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="6db09-113">您也可以按一下以下兩個指標中的任何一個，以存取 [熱門失敗] 報告：</span><span class="sxs-lookup"><span data-stu-id="6db09-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="6db09-114">應對</span><span class="sxs-lookup"><span data-stu-id="6db09-114">Response</span></span>

  - <span data-ttu-id="6db09-115">診斷識別碼</span><span class="sxs-lookup"><span data-stu-id="6db09-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="6db09-116">充分運用點對點工作階段詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="6db09-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="6db09-117">點對點工作階段詳細資料包告包含大量的度量單位，而系統管理員可能不熟悉其中許多規格。</span><span class="sxs-lookup"><span data-stu-id="6db09-117">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="6db09-118">不過，通常只要將滑鼠放在公制標籤上，就可以查看工具提示，以提供該標準的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="6db09-118">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="6db09-119">請注意，指定報告上顯示的實際度量單位將取決於您所選取的點對點工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="6db09-119">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="6db09-120">音訊/視頻會話會報告一組不同的度量值，而不是立即訊息會話。</span><span class="sxs-lookup"><span data-stu-id="6db09-120">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="6db09-121">您也可以將滑鼠放在回應程式碼和診斷 ID 指標中，以取得這些值的描述：</span><span class="sxs-lookup"><span data-stu-id="6db09-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6db09-122">濾鏡</span><span class="sxs-lookup"><span data-stu-id="6db09-122">Filters</span></span>

<span data-ttu-id="6db09-123">無。</span><span class="sxs-lookup"><span data-stu-id="6db09-123">None.</span></span> <span data-ttu-id="6db09-124">您無法篩選點對點工作階段詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="6db09-124">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="6db09-125">會話資訊度量單位</span><span class="sxs-lookup"><span data-stu-id="6db09-125">Session Information Metrics</span></span>

<span data-ttu-id="6db09-126">下表列出每個會話的點對點工作階段詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="6db09-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="6db09-127">會話資訊度量單位</span><span class="sxs-lookup"><span data-stu-id="6db09-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6db09-128">名稱</span><span class="sxs-lookup"><span data-stu-id="6db09-128">Name</span></span></th>
<th><span data-ttu-id="6db09-129">說明</span><span class="sxs-lookup"><span data-stu-id="6db09-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6db09-130"><strong>池 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-131">會話中所涉及的註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="6db09-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-132"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-133">最初傳送會話邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="6db09-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-134"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-135">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="6db09-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-136"><strong>從使用者</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-137">啟動會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="6db09-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-138"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-139">啟動會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="6db09-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-140"><strong>是來自使用者內部</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-141">指出啟動會話的使用者是否已登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="6db09-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-142"><strong>是來自與手機整合的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-143">指出啟動會話的使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="6db09-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-144"><strong>會話優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-145">指派給會話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="6db09-145">Priority assigned to the session.</span></span> <span data-ttu-id="6db09-146">有效的優先順序為：未知;非緊急;標準非常以及緊急情況。</span><span class="sxs-lookup"><span data-stu-id="6db09-146">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-147"><strong>回應代碼</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-148">在會話失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="6db09-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-149"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-150">在會議中使用的前端伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="6db09-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-151"><strong>捕獲時間</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-152">記錄會話資訊的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="6db09-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-153"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-154">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="6db09-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-155"><strong>給使用者</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-156">受邀者加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="6db09-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-157"><strong>給使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-158">受邀者參與會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="6db09-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-159"><strong>是對使用者內部</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-160">指出受邀加入會話的使用者是否已登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="6db09-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-161"><strong>是與手機整合的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-162">表示受邀者加入會話的使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="6db09-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-163"><strong>[重試] 會話</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-164">指出會話是否嘗試重試先前失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="6db09-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-165"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-166">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="6db09-166">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="6db09-167">將滑鼠停留在識別碼編號上方，即可查看該識別碼的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6db09-167">Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="6db09-168">形式的度量單位</span><span class="sxs-lookup"><span data-stu-id="6db09-168">Metrics for Modalities</span></span>

<span data-ttu-id="6db09-169">下表列出每個會話模態的點對點工作階段詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="6db09-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="6db09-170">形式的度量單位</span><span class="sxs-lookup"><span data-stu-id="6db09-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6db09-171">名稱</span><span class="sxs-lookup"><span data-stu-id="6db09-171">Name</span></span></th>
<th><span data-ttu-id="6db09-172">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="6db09-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6db09-173">說明</span><span class="sxs-lookup"><span data-stu-id="6db09-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6db09-174"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-175">否</span><span class="sxs-lookup"><span data-stu-id="6db09-175">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-176">在會話中使用的形式。</span><span class="sxs-lookup"><span data-stu-id="6db09-176">Modalities used in the session.</span></span> <span data-ttu-id="6db09-177">例如，立即訊息（IM）或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="6db09-177">For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-178"><strong>從使用者郵件</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-179">否</span><span class="sxs-lookup"><span data-stu-id="6db09-179">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-180">啟動會話的使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="6db09-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-181"><strong>給使用者訊息</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-182">否</span><span class="sxs-lookup"><span data-stu-id="6db09-182">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-183">受邀加入會話的使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="6db09-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="6db09-184">診斷報告的度量單位</span><span class="sxs-lookup"><span data-stu-id="6db09-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="6db09-185">下表列出每個診斷報告的點對點工作階段詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="6db09-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="6db09-186">診斷報告的度量單位</span><span class="sxs-lookup"><span data-stu-id="6db09-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6db09-187">名稱</span><span class="sxs-lookup"><span data-stu-id="6db09-187">Name</span></span></th>
<th><span data-ttu-id="6db09-188">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="6db09-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6db09-189">說明</span><span class="sxs-lookup"><span data-stu-id="6db09-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6db09-190"><strong>具體</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-191">否</span><span class="sxs-lookup"><span data-stu-id="6db09-191">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-192">當您按一下此專案時，報告會顯示該會話的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="6db09-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-193"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-194">否</span><span class="sxs-lookup"><span data-stu-id="6db09-194">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-195">記錄報告的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="6db09-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-196"><strong>徵求</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-197">否</span><span class="sxs-lookup"><span data-stu-id="6db09-197">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-198">SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="6db09-198">SIP request type.</span></span> <span data-ttu-id="6db09-199">例如，[邀請] 或 [再見]。</span><span class="sxs-lookup"><span data-stu-id="6db09-199">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-200"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-201">否</span><span class="sxs-lookup"><span data-stu-id="6db09-201">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-202">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="6db09-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6db09-203"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-204">否</span><span class="sxs-lookup"><span data-stu-id="6db09-204">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-205">在會議中使用的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="6db09-205">Type of media content used in the conference.</span></span> <span data-ttu-id="6db09-206">例如，常見的內容類型是 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="6db09-206">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="6db09-207">會話描述通訊協定（SDP）是一種標準的網際網路通訊協定，用於會話宣告、會話邀請以及其他多媒體會話啟動的形式。</span><span class="sxs-lookup"><span data-stu-id="6db09-207">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6db09-208"><strong>報告者</strong></span><span class="sxs-lookup"><span data-stu-id="6db09-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="6db09-209">否</span><span class="sxs-lookup"><span data-stu-id="6db09-209">No</span></span></p></td>
<td><p><span data-ttu-id="6db09-210">報告問題的電腦（即用戶端或伺服器）。</span><span class="sxs-lookup"><span data-stu-id="6db09-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

