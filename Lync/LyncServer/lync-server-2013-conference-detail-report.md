---
title: Lync Server 2013：會議詳細資料包表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e2cd992e83adb29c43935d4b4c7f223580d53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="5e3a0-102">Lync Server 2013 中的會議詳細資料包表</span><span class="sxs-lookup"><span data-stu-id="5e3a0-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e3a0-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5e3a0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5e3a0-104">[會議詳細資料] 報告提供參與會議之所有使用者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-104">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="5e3a0-105">例如，您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間，以及用來將該使用者連線到會議的端點使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-105">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="5e3a0-106">您也可以在每個會議中查看使用者角色的資訊（例如，簡報者或出席者）。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-106">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="5e3a0-107">最重要的是，您會快速看到哪些使用者成功加入並完成會議，哪些使用者無法順利加入並完成會議。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-107">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="5e3a0-108">存取會議詳細資料包表</span><span class="sxs-lookup"><span data-stu-id="5e3a0-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="5e3a0-109">您可以從下列報表存取會議詳細資料包告：</span><span class="sxs-lookup"><span data-stu-id="5e3a0-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="5e3a0-110">[Lync Server 2013 中的呼叫許可控制報告](lync-server-2013-call-admission-control-report.md)（按一下會議的詳細資料）</span><span class="sxs-lookup"><span data-stu-id="5e3a0-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="5e3a0-111">[Lync Server 2013 中的 [失敗清單] 報告](lync-server-2013-failure-list-report.md)（按一下會議躍點數）</span><span class="sxs-lookup"><span data-stu-id="5e3a0-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="5e3a0-112">[Lync Server 2013 中的使用者活動報告](lync-server-2013-user-activity-report.md)（按一下會議 URI 躍點數）</span><span class="sxs-lookup"><span data-stu-id="5e3a0-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="5e3a0-113">在 [會議詳細資料] 報告中，您可以按一下診斷報告（詳細資料）度量，[以存取 Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5e3a0-114">濾鏡</span><span class="sxs-lookup"><span data-stu-id="5e3a0-114">Filters</span></span>

<span data-ttu-id="5e3a0-115">無。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-115">None.</span></span> <span data-ttu-id="5e3a0-116">您無法在會議詳細資料包表中篩選。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-116">You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5e3a0-117">指標</span><span class="sxs-lookup"><span data-stu-id="5e3a0-117">Metrics</span></span>

<span data-ttu-id="5e3a0-118">下表列出在會議詳細資料包表的 [會議資訊] 區段中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="5e3a0-119">會議資訊度量單位</span><span class="sxs-lookup"><span data-stu-id="5e3a0-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e3a0-120">名稱</span><span class="sxs-lookup"><span data-stu-id="5e3a0-120">Name</span></span></th>
<th><span data-ttu-id="5e3a0-121">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="5e3a0-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5e3a0-122">說明</span><span class="sxs-lookup"><span data-stu-id="5e3a0-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-123"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-124">指派給會議的 URI。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-124">URI assigned to the conference.</span></span> <span data-ttu-id="5e3a0-125">例如：</span><span class="sxs-lookup"><span data-stu-id="5e3a0-125">For example:</span></span></p>
<p><span data-ttu-id="5e3a0-126">sip： kmyer@litwareinc .com; gruu; 不透明 = 應用程式：會議：焦點： id： drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="5e3a0-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e3a0-127"><strong>池 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-128">會話中所涉及的註冊機構池或邊緣伺服器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-129"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-130">會議開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e3a0-131"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-132">組織會議的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-133"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-134">會議結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e3a0-135">下表列出會議詳細資料包表之會議參與區段中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="5e3a0-136">會議參與指標</span><span class="sxs-lookup"><span data-stu-id="5e3a0-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e3a0-137">名稱</span><span class="sxs-lookup"><span data-stu-id="5e3a0-137">Name</span></span></th>
<th><span data-ttu-id="5e3a0-138">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="5e3a0-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5e3a0-139">說明</span><span class="sxs-lookup"><span data-stu-id="5e3a0-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-140"><strong>使用者</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-141">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e3a0-142"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-143">會議參與者所扮演的角色（例如，簡報者）。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-144"><strong>連通</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-145">參與者的網路連線（通常是內部或外部的網路連線）。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e3a0-146">加入時間</span><span class="sxs-lookup"><span data-stu-id="5e3a0-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-147">參與者加入會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-148"><strong>休假時間</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-149">參與者離開會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e3a0-150"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-151">參與者終點所使用之軟體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-152"><strong>診斷報告</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-153">提供診斷及疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-153">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="5e3a0-154">包括 SIP 回應代碼、診斷標頭、會議加入時間，以及失敗會話的診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-154">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e3a0-155">下表列出在會議詳細資料包表的 [會議形式] 區段中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="5e3a0-156">會議形式度量單位</span><span class="sxs-lookup"><span data-stu-id="5e3a0-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e3a0-157">名稱</span><span class="sxs-lookup"><span data-stu-id="5e3a0-157">Name</span></span></th>
<th><span data-ttu-id="5e3a0-158">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="5e3a0-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5e3a0-159">說明</span><span class="sxs-lookup"><span data-stu-id="5e3a0-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-160"><strong>使用者</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-161">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e3a0-162"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-163">參與者加入會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-164"><strong>休假時間</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-165">參與者離開會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e3a0-166"><strong>會議服務器 URI</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-167">在會議中使用的會議服務器 URI。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e3a0-168"><strong>診斷報告</strong></span><span class="sxs-lookup"><span data-stu-id="5e3a0-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e3a0-169">提供診斷及疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-169">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="5e3a0-170">包括 SIP 回應代碼、診斷標頭、會議加入時間，以及失敗會話的診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="5e3a0-170">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

