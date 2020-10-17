---
title: Lync Server 2013： Peer-to-Peer 會話詳細資料包告
description: Lync Server 2013： Peer-to-Peer 會話詳細資料包告。
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
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557279"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="41d96-103">Lync Server 2013 中的 Peer-to-Peer 會話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="41d96-103">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d96-104">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="41d96-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="41d96-105">Peer-to-Peer 會話詳細資料包告會傳回點對點工作階段的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="41d96-105">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="41d96-106">例如，如果您選取立即訊息會話，該報告將會告訴您會話中的兩位使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="41d96-106">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="41d96-107">存取 Peer-to-Peer 會話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="41d96-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="41d96-108">您可以從下列任何報告中存取 Peer-to-Peer 會話詳細資料包告 (所有可從監控報告首頁存取的報告) ：</span><span class="sxs-lookup"><span data-stu-id="41d96-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="41d96-109">IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="41d96-109">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="41d96-110">使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="41d96-110">User Activity Report</span></span>

  - <span data-ttu-id="41d96-111">通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="41d96-111">Call Admission Control Report</span></span>

  - <span data-ttu-id="41d96-112">失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="41d96-112">Failure List Report</span></span>

<span data-ttu-id="41d96-113">在 [Peer-to-Peer 會話詳細資料包告] 中，按一下 [診斷報告 (詳細資料]) 指標，即可存取 [Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="41d96-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="41d96-114">您也可以按一下下列兩個度量，以存取最上層失敗報告：</span><span class="sxs-lookup"><span data-stu-id="41d96-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="41d96-115">回應</span><span class="sxs-lookup"><span data-stu-id="41d96-115">Response</span></span>

  - <span data-ttu-id="41d96-116">診斷識別碼</span><span class="sxs-lookup"><span data-stu-id="41d96-116">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="41d96-117">Peer-to-Peer 會話詳細資料包告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="41d96-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="41d96-118">「Peer-to-Peer 會話詳細資料包告」包括大量的計量，許多系統管理員可能都不熟悉。</span><span class="sxs-lookup"><span data-stu-id="41d96-118">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="41d96-119">不過，您通常可以查看工具提示，只要將滑鼠放在「規格」標籤上方，就能提供該度量的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="41d96-119">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="41d96-120">請注意，顯示在特定報告上的實際度量值將取決於您所選取的點對點工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="41d96-120">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="41d96-121">音訊/視頻會話會報告一組不同于立即訊息會話的計量。</span><span class="sxs-lookup"><span data-stu-id="41d96-121">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="41d96-122">您也可以將滑鼠停留在回應程式碼和診斷識別碼計量中，以取得這些值的描述：</span><span class="sxs-lookup"><span data-stu-id="41d96-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="41d96-123">篩選</span><span class="sxs-lookup"><span data-stu-id="41d96-123">Filters</span></span>

<span data-ttu-id="41d96-124">無。</span><span class="sxs-lookup"><span data-stu-id="41d96-124">None.</span></span> <span data-ttu-id="41d96-125">您無法篩選 Peer-to-Peer 會話詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="41d96-125">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="41d96-126">會話資訊計量</span><span class="sxs-lookup"><span data-stu-id="41d96-126">Session Information Metrics</span></span>

<span data-ttu-id="41d96-127">下表列出每個會話的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="41d96-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="41d96-128">會話資訊計量</span><span class="sxs-lookup"><span data-stu-id="41d96-128">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41d96-129">名稱</span><span class="sxs-lookup"><span data-stu-id="41d96-129">Name</span></span></th>
<th><span data-ttu-id="41d96-130">描述</span><span class="sxs-lookup"><span data-stu-id="41d96-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41d96-131"><strong>集區 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-131"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-132">與會話有關之註冊區集區或 Edge Server 的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="41d96-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-133"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-133"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-134">最初傳送會話邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="41d96-134">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-135"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-135"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-136">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="41d96-136">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-137"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-137"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-138">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="41d96-138">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-139"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-139"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-140">啟動會話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="41d96-140">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-141"><strong>來自使用者內部</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-141"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-142">會指出起始會話的使用者是否登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="41d96-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-143"><strong>來源於與電話機整合的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-143"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-144">會指出起始會話之使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="41d96-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-145"><strong>會話優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-145"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-146">指派給會話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="41d96-146">Priority assigned to the session.</span></span> <span data-ttu-id="41d96-147">有效的優先順序如下： Unknown;非緊急;一般緊迫和緊急。</span><span class="sxs-lookup"><span data-stu-id="41d96-147">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-148"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-148"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-149">會話失敗時傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="41d96-149">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-150"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-150"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-151">會議中所使用的前端伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="41d96-151">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-152"><strong>拍攝時間</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-152"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-153">記錄會話資訊的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="41d96-153">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-154"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-154"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-155">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="41d96-155">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-156"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-156"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-157">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="41d96-157">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-158"><strong>至使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-158"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-159">受邀加入會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="41d96-159">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-160"><strong>是使用者內部使用者</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-160"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-161">會指出被邀加入會話的使用者是否登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="41d96-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-162"><strong>是與電話機整合的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-162"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-163">會指出受邀加入會話之使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="41d96-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-164"><strong>會重試會話</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-164"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-165">會指出會話是否嘗試重試先前失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="41d96-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-166"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-166"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-167">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="41d96-167">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="41d96-168">將滑鼠停留在識別碼號碼上方，以查看有關該識別碼的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="41d96-168">Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="41d96-169">形式的計量</span><span class="sxs-lookup"><span data-stu-id="41d96-169">Metrics for Modalities</span></span>

<span data-ttu-id="41d96-170">下表列出每個會話模態的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="41d96-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="41d96-171">形式的計量</span><span class="sxs-lookup"><span data-stu-id="41d96-171">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41d96-172">姓名</span><span class="sxs-lookup"><span data-stu-id="41d96-172">Name</span></span></th>
<th><span data-ttu-id="41d96-173">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="41d96-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="41d96-174">描述</span><span class="sxs-lookup"><span data-stu-id="41d96-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41d96-175"><strong>方式</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-175"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-176">否</span><span class="sxs-lookup"><span data-stu-id="41d96-176">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-177">會話中使用的形式。</span><span class="sxs-lookup"><span data-stu-id="41d96-177">Modalities used in the session.</span></span> <span data-ttu-id="41d96-178">例如，立即訊息 (IM) 或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="41d96-178">For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-179"><strong>從使用者郵件</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-179"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-180">否</span><span class="sxs-lookup"><span data-stu-id="41d96-180">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-181">啟動會話之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="41d96-181">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-182"><strong>使用者訊息</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-182"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-183">否</span><span class="sxs-lookup"><span data-stu-id="41d96-183">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-184">受邀加入會話之使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="41d96-184">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="41d96-185">診斷報告的計量</span><span class="sxs-lookup"><span data-stu-id="41d96-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="41d96-186">下表列出每個診斷報告的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="41d96-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="41d96-187">診斷報告的計量</span><span class="sxs-lookup"><span data-stu-id="41d96-187">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41d96-188">姓名</span><span class="sxs-lookup"><span data-stu-id="41d96-188">Name</span></span></th>
<th><span data-ttu-id="41d96-189">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="41d96-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="41d96-190">描述</span><span class="sxs-lookup"><span data-stu-id="41d96-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41d96-191"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-191"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-192">否</span><span class="sxs-lookup"><span data-stu-id="41d96-192">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-193">當您按一下此專案時，報告會顯示會話的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="41d96-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-194"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-194"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-195">否</span><span class="sxs-lookup"><span data-stu-id="41d96-195">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-196">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="41d96-196">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-197"><strong>請求</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-197"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-198">否</span><span class="sxs-lookup"><span data-stu-id="41d96-198">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-199">SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="41d96-199">SIP request type.</span></span> <span data-ttu-id="41d96-200">例如，INVITE 或再見。</span><span class="sxs-lookup"><span data-stu-id="41d96-200">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-201"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-201"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-202">否</span><span class="sxs-lookup"><span data-stu-id="41d96-202">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-203">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="41d96-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d96-204"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-204"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-205">否</span><span class="sxs-lookup"><span data-stu-id="41d96-205">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-206">會議中所使用的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="41d96-206">Type of media content used in the conference.</span></span> <span data-ttu-id="41d96-207">例如，常見的內容類型為 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="41d96-207">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="41d96-208">Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</span><span class="sxs-lookup"><span data-stu-id="41d96-208">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d96-209"><strong>報告者</strong></span><span class="sxs-lookup"><span data-stu-id="41d96-209"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="41d96-210">否</span><span class="sxs-lookup"><span data-stu-id="41d96-210">No</span></span></p></td>
<td><p><span data-ttu-id="41d96-211">電腦 (，也就是報告問題的用戶端或伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="41d96-211">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

