---
title: Lync Server 2013： Peer-to-Peer 會話詳細資料包告
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
ms.openlocfilehash: 93558a56962f34a38b80ebca8a0fd668394a4386
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524360"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="71212-102">Lync Server 2013 中的 Peer-to-Peer 會話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="71212-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71212-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="71212-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="71212-104">Peer-to-Peer 會話詳細資料包告會傳回點對點工作階段的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="71212-104">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="71212-105">例如，如果您選取立即訊息會話，該報告將會告訴您會話中的兩位使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="71212-105">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="71212-106">存取 Peer-to-Peer 會話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="71212-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="71212-107">您可以從下列任何報告中存取 Peer-to-Peer 會話詳細資料包告 (所有可從監控報告首頁存取的報告) ：</span><span class="sxs-lookup"><span data-stu-id="71212-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="71212-108">IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="71212-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="71212-109">使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="71212-109">User Activity Report</span></span>

  - <span data-ttu-id="71212-110">通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="71212-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="71212-111">失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="71212-111">Failure List Report</span></span>

<span data-ttu-id="71212-112">在 [Peer-to-Peer 會話詳細資料包告] 中，按一下 [診斷報告 (詳細資料]) 指標，即可存取 [Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="71212-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="71212-113">您也可以按一下下列兩個度量，以存取最上層失敗報告：</span><span class="sxs-lookup"><span data-stu-id="71212-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="71212-114">回應</span><span class="sxs-lookup"><span data-stu-id="71212-114">Response</span></span>

  - <span data-ttu-id="71212-115">診斷識別碼</span><span class="sxs-lookup"><span data-stu-id="71212-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="71212-116">Peer-to-Peer 會話詳細資料包告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="71212-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="71212-117">「Peer-to-Peer 會話詳細資料包告」包括大量的計量，許多系統管理員可能都不熟悉。</span><span class="sxs-lookup"><span data-stu-id="71212-117">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="71212-118">不過，您通常可以查看工具提示，只要將滑鼠放在「規格」標籤上方，就能提供該度量的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="71212-118">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="71212-119">請注意，顯示在特定報告上的實際度量值將取決於您所選取的點對點工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="71212-119">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="71212-120">音訊/視頻會話會報告一組不同于立即訊息會話的計量。</span><span class="sxs-lookup"><span data-stu-id="71212-120">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="71212-121">您也可以將滑鼠停留在回應程式碼和診斷識別碼計量中，以取得這些值的描述：</span><span class="sxs-lookup"><span data-stu-id="71212-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="71212-122">篩選</span><span class="sxs-lookup"><span data-stu-id="71212-122">Filters</span></span>

<span data-ttu-id="71212-123">無。</span><span class="sxs-lookup"><span data-stu-id="71212-123">None.</span></span> <span data-ttu-id="71212-124">您無法篩選 Peer-to-Peer 會話詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="71212-124">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="71212-125">會話資訊計量</span><span class="sxs-lookup"><span data-stu-id="71212-125">Session Information Metrics</span></span>

<span data-ttu-id="71212-126">下表列出每個會話的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="71212-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="71212-127">會話資訊計量</span><span class="sxs-lookup"><span data-stu-id="71212-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71212-128">名稱</span><span class="sxs-lookup"><span data-stu-id="71212-128">Name</span></span></th>
<th><span data-ttu-id="71212-129">描述</span><span class="sxs-lookup"><span data-stu-id="71212-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71212-130"><strong>集區 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="71212-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-131">與會話有關之註冊區集區或 Edge Server 的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="71212-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-132"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="71212-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-133">最初傳送會話邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="71212-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-134"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="71212-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-135">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="71212-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-136"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="71212-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-137">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="71212-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-138"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="71212-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-139">啟動會話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="71212-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-140"><strong>來自使用者內部</strong></span><span class="sxs-lookup"><span data-stu-id="71212-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-141">會指出起始會話的使用者是否登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="71212-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-142"><strong>來源於與電話機整合的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="71212-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-143">會指出起始會話之使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="71212-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-144"><strong>會話優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="71212-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-145">指派給會話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="71212-145">Priority assigned to the session.</span></span> <span data-ttu-id="71212-146">有效的優先順序如下： Unknown;非緊急;一般緊迫和緊急。</span><span class="sxs-lookup"><span data-stu-id="71212-146">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-147"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="71212-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-148">會話失敗時傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="71212-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-149"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="71212-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-150">會議中所使用的前端伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="71212-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-151"><strong>拍攝時間</strong></span><span class="sxs-lookup"><span data-stu-id="71212-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-152">記錄會話資訊的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="71212-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-153"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="71212-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-154">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="71212-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-155"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="71212-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-156">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="71212-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-157"><strong>至使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="71212-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-158">受邀加入會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="71212-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-159"><strong>是使用者內部使用者</strong></span><span class="sxs-lookup"><span data-stu-id="71212-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-160">會指出被邀加入會話的使用者是否登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="71212-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-161"><strong>是與電話機整合的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="71212-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-162">會指出受邀加入會話之使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="71212-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-163"><strong>會重試會話</strong></span><span class="sxs-lookup"><span data-stu-id="71212-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-164">會指出會話是否嘗試重試先前失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="71212-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-165"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="71212-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-166">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="71212-166">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="71212-167">將滑鼠停留在識別碼號碼上方，以查看有關該識別碼的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="71212-167">Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="71212-168">形式的計量</span><span class="sxs-lookup"><span data-stu-id="71212-168">Metrics for Modalities</span></span>

<span data-ttu-id="71212-169">下表列出每個會話模態的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="71212-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="71212-170">形式的計量</span><span class="sxs-lookup"><span data-stu-id="71212-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71212-171">姓名</span><span class="sxs-lookup"><span data-stu-id="71212-171">Name</span></span></th>
<th><span data-ttu-id="71212-172">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="71212-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="71212-173">描述</span><span class="sxs-lookup"><span data-stu-id="71212-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71212-174"><strong>方式</strong></span><span class="sxs-lookup"><span data-stu-id="71212-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-175">否</span><span class="sxs-lookup"><span data-stu-id="71212-175">No</span></span></p></td>
<td><p><span data-ttu-id="71212-176">會話中使用的形式。</span><span class="sxs-lookup"><span data-stu-id="71212-176">Modalities used in the session.</span></span> <span data-ttu-id="71212-177">例如，立即訊息 (IM) 或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="71212-177">For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-178"><strong>從使用者郵件</strong></span><span class="sxs-lookup"><span data-stu-id="71212-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-179">否</span><span class="sxs-lookup"><span data-stu-id="71212-179">No</span></span></p></td>
<td><p><span data-ttu-id="71212-180">啟動會話之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="71212-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-181"><strong>使用者訊息</strong></span><span class="sxs-lookup"><span data-stu-id="71212-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-182">否</span><span class="sxs-lookup"><span data-stu-id="71212-182">No</span></span></p></td>
<td><p><span data-ttu-id="71212-183">受邀加入會話之使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="71212-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="71212-184">診斷報告的計量</span><span class="sxs-lookup"><span data-stu-id="71212-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="71212-185">下表列出每個診斷報告的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="71212-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="71212-186">診斷報告的計量</span><span class="sxs-lookup"><span data-stu-id="71212-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71212-187">姓名</span><span class="sxs-lookup"><span data-stu-id="71212-187">Name</span></span></th>
<th><span data-ttu-id="71212-188">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="71212-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="71212-189">描述</span><span class="sxs-lookup"><span data-stu-id="71212-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71212-190"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="71212-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-191">否</span><span class="sxs-lookup"><span data-stu-id="71212-191">No</span></span></p></td>
<td><p><span data-ttu-id="71212-192">當您按一下此專案時，報告會顯示會話的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="71212-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-193"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="71212-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-194">否</span><span class="sxs-lookup"><span data-stu-id="71212-194">No</span></span></p></td>
<td><p><span data-ttu-id="71212-195">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="71212-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-196"><strong>請求</strong></span><span class="sxs-lookup"><span data-stu-id="71212-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-197">否</span><span class="sxs-lookup"><span data-stu-id="71212-197">No</span></span></p></td>
<td><p><span data-ttu-id="71212-198">SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="71212-198">SIP request type.</span></span> <span data-ttu-id="71212-199">例如，INVITE 或再見。</span><span class="sxs-lookup"><span data-stu-id="71212-199">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-200"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="71212-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-201">否</span><span class="sxs-lookup"><span data-stu-id="71212-201">No</span></span></p></td>
<td><p><span data-ttu-id="71212-202">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="71212-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71212-203"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="71212-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-204">否</span><span class="sxs-lookup"><span data-stu-id="71212-204">No</span></span></p></td>
<td><p><span data-ttu-id="71212-205">會議中所使用的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="71212-205">Type of media content used in the conference.</span></span> <span data-ttu-id="71212-206">例如，常見的內容類型為 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="71212-206">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="71212-207">Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</span><span class="sxs-lookup"><span data-stu-id="71212-207">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71212-208"><strong>報告者</strong></span><span class="sxs-lookup"><span data-stu-id="71212-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="71212-209">否</span><span class="sxs-lookup"><span data-stu-id="71212-209">No</span></span></p></td>
<td><p><span data-ttu-id="71212-210">電腦 (，也就是報告問題的用戶端或伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="71212-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

