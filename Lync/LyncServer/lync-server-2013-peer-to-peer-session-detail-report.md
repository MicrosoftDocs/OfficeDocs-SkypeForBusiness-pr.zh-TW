---
title: Lync Server 2013： 端對端工作階段詳細資料報告
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
ms.openlocfilehash: fe04005d616a97a1fff4c84dbe43a5edb8e3cdba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="32da9-102">Lync Server 2013 中的端對端工作階段詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="32da9-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32da9-103">_**主題上次修改日期：** 2012年-06-06_</span><span class="sxs-lookup"><span data-stu-id="32da9-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="32da9-104">端對端工作階段詳細資料報表會傳回對等工作階段的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="32da9-104">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="32da9-105">例如，如果您選取 [立即訊息工作階段，報表會告訴您所兩位使用者每個工作階段中傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="32da9-105">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="32da9-106">存取對等工作階段詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="32da9-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="32da9-107">端對端工作階段詳細資料報告可從任何下列報告 （這些元件可從監視報告首頁）：</span><span class="sxs-lookup"><span data-stu-id="32da9-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="32da9-108">IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="32da9-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="32da9-109">使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="32da9-109">User Activity Report</span></span>

  - <span data-ttu-id="32da9-110">通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="32da9-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="32da9-111">失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="32da9-111">Failure List Report</span></span>

<span data-ttu-id="32da9-112">端對端工作階段詳細資料報告中您可以從存取[診斷報告在 Lync Server 2013 中](lync-server-2013-diagnostic-report.md)按一下 [診斷報告 （詳細資料） 計量。</span><span class="sxs-lookup"><span data-stu-id="32da9-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="32da9-113">您也可以按一下任一這些兩個評量，以存取最大失敗報告：</span><span class="sxs-lookup"><span data-stu-id="32da9-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="32da9-114">回應</span><span class="sxs-lookup"><span data-stu-id="32da9-114">Response</span></span>

  - <span data-ttu-id="32da9-115">診斷識別碼</span><span class="sxs-lookup"><span data-stu-id="32da9-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="32da9-116">端對端工作階段詳細資料報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="32da9-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="32da9-117">端對端工作階段詳細資料報表包含大量的評量，其中有許多可能不熟悉系統管理員。</span><span class="sxs-lookup"><span data-stu-id="32da9-117">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="32da9-118">大多時候，不過，您可以檢視只要按住滑鼠移到計量標籤提供該計量的簡短描述的工具提示。</span><span class="sxs-lookup"><span data-stu-id="32da9-118">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="32da9-119">請注意，顯示在指定的報表上的實際評量取決於您所選取的端對端工作階段的類型。</span><span class="sxs-lookup"><span data-stu-id="32da9-119">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="32da9-120">音訊/視訊工作階段會報告一組不同的比立即訊息工作階段的計量。</span><span class="sxs-lookup"><span data-stu-id="32da9-120">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="32da9-121">您可以也將滑鼠停留在回應代碼和診斷 ID 計量以取得那些值的描述：</span><span class="sxs-lookup"><span data-stu-id="32da9-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="32da9-122">篩選</span><span class="sxs-lookup"><span data-stu-id="32da9-122">Filters</span></span>

<span data-ttu-id="32da9-123">無。</span><span class="sxs-lookup"><span data-stu-id="32da9-123">None.</span></span> <span data-ttu-id="32da9-124">您無法篩選端對端工作階段詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="32da9-124">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="32da9-125">工作階段資訊計量</span><span class="sxs-lookup"><span data-stu-id="32da9-125">Session Information Metrics</span></span>

<span data-ttu-id="32da9-126">下表列出每個工作階段端對端工作階段詳細資料報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="32da9-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="32da9-127">工作階段資訊計量</span><span class="sxs-lookup"><span data-stu-id="32da9-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32da9-128">名稱</span><span class="sxs-lookup"><span data-stu-id="32da9-128">Name</span></span></th>
<th><span data-ttu-id="32da9-129">描述</span><span class="sxs-lookup"><span data-stu-id="32da9-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32da9-130"><strong>集區 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-131">完整網域名稱 (FQDN) 的登錄器集區或 Edge Server 參與工作階段。</span><span class="sxs-lookup"><span data-stu-id="32da9-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-132"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-133">日期和時間工作階段邀請最初發送。</span><span class="sxs-lookup"><span data-stu-id="32da9-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-134"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-135">日期和時間收到的邀請接受度。</span><span class="sxs-lookup"><span data-stu-id="32da9-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-136"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-137">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="32da9-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-138"><strong>來源使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-139">起始工作階段之使用者端點所用的軟體。</span><span class="sxs-lookup"><span data-stu-id="32da9-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-140"><strong>是來源使用者內部</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-141">指出起始工作階段之使用者是否已在內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="32da9-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-142"><strong>是與電話機整合的來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-143">指出起始工作階段之使用者所用的端點是否整合與他或她桌上電話。</span><span class="sxs-lookup"><span data-stu-id="32da9-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-144"><strong>工作階段優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-145">指派給工作階段的優先順序。</span><span class="sxs-lookup"><span data-stu-id="32da9-145">Priority assigned to the session.</span></span> <span data-ttu-id="32da9-146">有效的優先順序： 未知;非緊急;正常;緊急;和緊急。</span><span class="sxs-lookup"><span data-stu-id="32da9-146">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-147"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-148">SIP 工作階段失敗時傳送的回應碼。</span><span class="sxs-lookup"><span data-stu-id="32da9-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-149"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-150">前端伺服器在會議中使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="32da9-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-151"><strong>擷取時間</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-152">日期和時間的資訊記錄在工作階段。</span><span class="sxs-lookup"><span data-stu-id="32da9-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-153"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-154">日期與時間工作階段結束。</span><span class="sxs-lookup"><span data-stu-id="32da9-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-155"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-156">獲邀加入工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="32da9-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-157"><strong>目標使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-158">獲邀加入工作階段之使用者端點所用的軟體。</span><span class="sxs-lookup"><span data-stu-id="32da9-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-159"><strong>是目標使用者內部</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-160">指出獲邀加入工作階段的使用者是否已在內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="32da9-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-161"><strong>是與電話機整合的目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-162">指出獲邀加入工作階段之使用者所使用的端點是否整合與他或她桌上電話。</span><span class="sxs-lookup"><span data-stu-id="32da9-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-163"><strong>重試工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-164">會指出是否工作階段 」 會嘗試重試先前失敗的工作階段。</span><span class="sxs-lookup"><span data-stu-id="32da9-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-165"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-166">唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="32da9-166">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="32da9-167">滑鼠停留的識別碼，若要檢視該識別碼的其他資訊</span><span class="sxs-lookup"><span data-stu-id="32da9-167">Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="32da9-168">形式的計量</span><span class="sxs-lookup"><span data-stu-id="32da9-168">Metrics for Modalities</span></span>

<span data-ttu-id="32da9-169">下表列出每個工作階段形式端對端工作階段詳細資料報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="32da9-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="32da9-170">形式的計量</span><span class="sxs-lookup"><span data-stu-id="32da9-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32da9-171">名稱</span><span class="sxs-lookup"><span data-stu-id="32da9-171">Name</span></span></th>
<th><span data-ttu-id="32da9-172">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="32da9-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="32da9-173">說明</span><span class="sxs-lookup"><span data-stu-id="32da9-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32da9-174"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-175">否</span><span class="sxs-lookup"><span data-stu-id="32da9-175">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-176">工作階段中所使用的形式。</span><span class="sxs-lookup"><span data-stu-id="32da9-176">Modalities used in the session.</span></span> <span data-ttu-id="32da9-177">例如，可以立即訊息 (IM) 後或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="32da9-177">For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-178"><strong>來源使用者訊息</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-179">否</span><span class="sxs-lookup"><span data-stu-id="32da9-179">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-180">起始工作階段之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="32da9-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-181"><strong>目標使用者訊息</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-182">否</span><span class="sxs-lookup"><span data-stu-id="32da9-182">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-183">獲邀加入工作階段之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="32da9-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="32da9-184">診斷報告的計量</span><span class="sxs-lookup"><span data-stu-id="32da9-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="32da9-185">下表列出每份診斷報告端對端工作階段詳細資料報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="32da9-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="32da9-186">診斷報告的計量</span><span class="sxs-lookup"><span data-stu-id="32da9-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32da9-187">名稱</span><span class="sxs-lookup"><span data-stu-id="32da9-187">Name</span></span></th>
<th><span data-ttu-id="32da9-188">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="32da9-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="32da9-189">說明</span><span class="sxs-lookup"><span data-stu-id="32da9-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32da9-190"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-191">否</span><span class="sxs-lookup"><span data-stu-id="32da9-191">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-192">當您按一下此項目時，報告就會顯示 [診斷報告工作階段。</span><span class="sxs-lookup"><span data-stu-id="32da9-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-193"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-194">否</span><span class="sxs-lookup"><span data-stu-id="32da9-194">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-195">日期和時間報告的記錄。</span><span class="sxs-lookup"><span data-stu-id="32da9-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-196"><strong>要求</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-197">否</span><span class="sxs-lookup"><span data-stu-id="32da9-197">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-198">SIP 要求的類型。</span><span class="sxs-lookup"><span data-stu-id="32da9-198">SIP request type.</span></span> <span data-ttu-id="32da9-199">例如，邀請或 BYE。</span><span class="sxs-lookup"><span data-stu-id="32da9-199">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-200"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-201">否</span><span class="sxs-lookup"><span data-stu-id="32da9-201">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-202">唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="32da9-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32da9-203"><strong>內容類型</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-204">否</span><span class="sxs-lookup"><span data-stu-id="32da9-204">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-205">會議中使用的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="32da9-205">Type of media content used in the conference.</span></span> <span data-ttu-id="32da9-206">例如，常見的內容類型是應用程式/sdp。</span><span class="sxs-lookup"><span data-stu-id="32da9-206">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="32da9-207">工作階段描述通訊協定 (SDP) 是用於工作階段公告、 工作階段邀請和其他形式的多媒體工作階段初始標準網際網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="32da9-207">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32da9-208"><strong>由報告</strong></span><span class="sxs-lookup"><span data-stu-id="32da9-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="32da9-209">否</span><span class="sxs-lookup"><span data-stu-id="32da9-209">No</span></span></p></td>
<td><p><span data-ttu-id="32da9-210">電腦 （亦即，用戶端或伺服器），回報的問題。</span><span class="sxs-lookup"><span data-stu-id="32da9-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

