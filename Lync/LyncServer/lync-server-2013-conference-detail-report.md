---
title: Lync Server 2013： 會議詳細資料報告
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
ms.openlocfilehash: 670696a0945464486e0872b17df330a6ca8140b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="daa13-102">Lync Server 2013 中的會議詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="daa13-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daa13-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="daa13-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="daa13-p101">「會議詳細資料報告」可提供參與會議之使用者的詳細資訊。例如，您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間，以及用來將使用者與會議連線的端點使用者代理程式之類的資訊。您也可以查看使用者在每個會議中的角色 (例如，簡報者或是出席者)。更重要的是，您可以更快速地查看哪些使用者已順利加入並完成會議，而哪些使用者無法順利加入並完成會議。</span><span class="sxs-lookup"><span data-stu-id="daa13-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="daa13-108">存取會議詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="daa13-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="daa13-109">您可從下列報告來存取會議詳細資料報告：</span><span class="sxs-lookup"><span data-stu-id="daa13-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="daa13-110">[Lync Server 2013 中通話許可控制報告](lync-server-2013-call-admission-control-report.md)(按一下會議詳細資料] 計量）</span><span class="sxs-lookup"><span data-stu-id="daa13-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="daa13-111">[Lync Server 2013 中的 Failure List Report](lync-server-2013-failure-list-report.md) (按一下 [會議] 計量）</span><span class="sxs-lookup"><span data-stu-id="daa13-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="daa13-112">[Lync Server 2013 中的使用者活動報告](lync-server-2013-user-activity-report.md)(按一下 [會議 URI] 計量）</span><span class="sxs-lookup"><span data-stu-id="daa13-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="daa13-113">您可以從會議詳細資料報告診斷報告 （詳細資料） 計量，即可存取[Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="daa13-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="daa13-114">篩選</span><span class="sxs-lookup"><span data-stu-id="daa13-114">Filters</span></span>

<span data-ttu-id="daa13-p102">無。您無法篩選會議詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="daa13-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="daa13-117">計量</span><span class="sxs-lookup"><span data-stu-id="daa13-117">Metrics</span></span>

<span data-ttu-id="daa13-118">下表列出會議詳細資料報告的「會議資訊」區段中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="daa13-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="daa13-119">會議資訊計量</span><span class="sxs-lookup"><span data-stu-id="daa13-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa13-120">名稱</span><span class="sxs-lookup"><span data-stu-id="daa13-120">Name</span></span></th>
<th><span data-ttu-id="daa13-121">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="daa13-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="daa13-122">說明</span><span class="sxs-lookup"><span data-stu-id="daa13-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa13-123"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-p103">指派給會議的 URI。例如：</span><span class="sxs-lookup"><span data-stu-id="daa13-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="daa13-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="daa13-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa13-127"><strong>集區 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-128">工作階段所涉及的登錄器集區或 Edge Server 的完整網域名稱。</span><span class="sxs-lookup"><span data-stu-id="daa13-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa13-129"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-130">會議開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="daa13-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa13-131"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-132">召開會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="daa13-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa13-133"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-134">會議結束的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="daa13-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="daa13-135">下表列出會議詳細資料報告的「會議參與區段」中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="daa13-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="daa13-136">會議參與計量</span><span class="sxs-lookup"><span data-stu-id="daa13-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa13-137">名稱</span><span class="sxs-lookup"><span data-stu-id="daa13-137">Name</span></span></th>
<th><span data-ttu-id="daa13-138">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="daa13-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="daa13-139">說明</span><span class="sxs-lookup"><span data-stu-id="daa13-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa13-140"><strong>使用者</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-141">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="daa13-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa13-142"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-143">會議參與者所扮演的角色 (例如，簡報者)。</span><span class="sxs-lookup"><span data-stu-id="daa13-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa13-144"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-145">參與者的網路連線 (一般來說是從內部或從外部)。</span><span class="sxs-lookup"><span data-stu-id="daa13-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa13-146">加入時間</span><span class="sxs-lookup"><span data-stu-id="daa13-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-147">參與者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="daa13-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa13-148"><strong>離開時間</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-149">參與者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="daa13-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa13-150"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-151">參與者端點所使用的軟體識別碼。</span><span class="sxs-lookup"><span data-stu-id="daa13-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa13-152"><strong>診斷報告</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-p104">可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="daa13-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="daa13-155">下表列出會議詳細資料報告的會議形式 」 區段中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="daa13-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="daa13-156">會議形式計量</span><span class="sxs-lookup"><span data-stu-id="daa13-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa13-157">名稱</span><span class="sxs-lookup"><span data-stu-id="daa13-157">Name</span></span></th>
<th><span data-ttu-id="daa13-158">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="daa13-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="daa13-159">說明</span><span class="sxs-lookup"><span data-stu-id="daa13-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa13-160"><strong>使用者</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-161">參與會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="daa13-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa13-162"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-163">參與者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="daa13-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa13-164"><strong>離開時間</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-165">參與者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="daa13-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa13-166"><strong>會議伺服器 URI</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-167">會議中所使用之會議伺服器的 URI。</span><span class="sxs-lookup"><span data-stu-id="daa13-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa13-168"><strong>診斷報告</strong></span><span class="sxs-lookup"><span data-stu-id="daa13-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="daa13-p105">可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="daa13-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

