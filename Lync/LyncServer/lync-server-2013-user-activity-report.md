---
title: Lync Server 2013：使用者活動報告
description: Lync Server 2013：使用者活動報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e959020e6ace6c72ecd570039d30a9ecc174c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569829"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="eef2e-103">Lync Server 2013 中的使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="eef2e-103">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef2e-104">_**主題上次修改日期：** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="eef2e-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="eef2e-p101">「使用者活動報告」提供了指定期間內使用者執行之對等及會議工作階段的詳細清單。不同於多數「監控報告」，「使用者活動報告」將每通通話牽繫到個別使用者。例如，對等工作階段會指定發話者 (來源使用者) 及受話者 (目標使用者) 的 SIP URI。如展開關於會議的資訊，則會顯示所有會議參與者及其在該會議中所扮演角色的清單。</span><span class="sxs-lookup"><span data-stu-id="eef2e-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="eef2e-p102">「使用者活動報告」有時稱為「服務台」報告。這是因為此報告常被服務台人員用來擷取特定使用者的工作階段資訊。在 [使用者 URI 首碼] 方塊中輸入使用者的 SIP URI，即可篩選個別使用者所接收或發出的通話。</span><span class="sxs-lookup"><span data-stu-id="eef2e-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="eef2e-112">如果您這麼做，使用者活動報告會傳回其 SIP URI 以指定字串開頭的任何使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="eef2e-112">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="eef2e-113">例如，如果您在 [URI] 方塊中輸入 **ken** ，使用者活動報告就會找到 **ken**。Myer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="eef2e-113">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="eef2e-114">不過，它也會找到下列使用者：</span><span class="sxs-lookup"><span data-stu-id="eef2e-114">However, it will also locate these users:</span></span>

  - <span data-ttu-id="eef2e-115">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eef2e-115">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="eef2e-116">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eef2e-116">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="eef2e-117">**Ken**。Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eef2e-117">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="eef2e-118">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eef2e-118">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="eef2e-119">為了確保只會傳回 Ken Myer 的資訊，請在搜尋方塊中輸入他的完整 URI (Ken.Myer@litwareinc.com) 或至少有足夠類型的 Ken URI，以唯一地區分開他與組織中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="eef2e-119">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="eef2e-120">例如：</span><span class="sxs-lookup"><span data-stu-id="eef2e-120">For example:</span></span>

<span data-ttu-id="eef2e-121">Ken.my</span><span class="sxs-lookup"><span data-stu-id="eef2e-121">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="eef2e-122">存取使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="eef2e-122">To access the user activity report</span></span>

<span data-ttu-id="eef2e-123">從「監控報告」首頁可存取「使用者活動報告」。</span><span class="sxs-lookup"><span data-stu-id="eef2e-123">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="eef2e-124">您也可以在 [ [Lync Server 2013] 的 [IP 電話清查] 報告](lync-server-2013-ip-phone-inventory-report.md)上，按一下 [使用者] URI 度量，以到達 [使用者活動] 報告。</span><span class="sxs-lookup"><span data-stu-id="eef2e-124">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="eef2e-125">從「使用者活動報告」中，按一下 [會議 URI] (針對會議) 會移至「會議詳細資料報告」。</span><span class="sxs-lookup"><span data-stu-id="eef2e-125">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="eef2e-126">同樣地，按一下對等通話的詳細資料度量，會帶您前往 [Lync Server 2013 中的 Peer-to-Peer 會話詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="eef2e-126">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="eef2e-127">充分運用使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="eef2e-127">Making the best use of the user activity report</span></span>

<span data-ttu-id="eef2e-128">雖然「使用者活動報告」中有許多有用的資訊，但是有時候很難找到所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="eef2e-128">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="eef2e-129">例如，在指定期間內，組織中發生的所有使用者活動都會包含在使用者活動報告中;這表示在報表內，會有一些使用者實際使用 Microsoft Lync Server 2013 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="eef2e-129">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="eef2e-130">從技術上而言，有些使用者活動可能會 unrecorded：雖然 Lync Server 盡力保留所有電話通話的資訊，但只要該呼叫的相關資訊未寫入資料庫中，就可以進行通話。</span><span class="sxs-lookup"><span data-stu-id="eef2e-130">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="eef2e-131">Lync Server 的設計目的是要提供極好的準確性，但不一定要瞭解如何使用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="eef2e-131">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="eef2e-132"> (不保證所有通話呼叫的100% 的事實，說明為何 Lync Server monitoring 不應該當作帳單系統使用。 ) </span><span class="sxs-lookup"><span data-stu-id="eef2e-132">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="eef2e-p108">第二，「監控報告」中的報告最多僅可顯示 1,000 筆記錄。所以，取決於使用者活動的多寡及工作期間，您的查詢可能不會傳回資料庫中所有實際儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="eef2e-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="eef2e-135">在此期間內哪些使用者確實使用系統？</span><span class="sxs-lookup"><span data-stu-id="eef2e-135">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="eef2e-136">在此期間內我的哪些使用者最為活躍？</span><span class="sxs-lookup"><span data-stu-id="eef2e-136">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="eef2e-137">通話最多的使用者也是參與最多立即訊息工作階段的使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="eef2e-137">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="eef2e-138">如果您需要回答此類問題，可以將「監控報告」擷取的資料匯出到 Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="eef2e-138">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="eef2e-139">然後使用該試算表及 (或) 逗點分隔值檔案，以「使用者活動報告」無法做到的方式來分析資料。</span><span class="sxs-lookup"><span data-stu-id="eef2e-139">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="eef2e-140">例如，假設您已將報告資料匯出到 Excel，再儲存為逗點分隔值檔案。</span><span class="sxs-lookup"><span data-stu-id="eef2e-140">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="eef2e-141">在該點，您可以匯入資料。CSV 檔案至 Windows PowerShell，其使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="eef2e-141">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="eef2e-142">在匯入資料後，您就可以使用簡易的 Windows PowerShell 命令，協助您回答問題。</span><span class="sxs-lookup"><span data-stu-id="eef2e-142">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="eef2e-143">例如，以下命令會傳回至少在一個工作階段中擔任「來源使用者」的唯一使用者清單：</span><span class="sxs-lookup"><span data-stu-id="eef2e-143">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="eef2e-144">換句話說：</span><span class="sxs-lookup"><span data-stu-id="eef2e-144">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="eef2e-145">此命令會列出唯一使用者 (根據他們參與的工作階段總數)：</span><span class="sxs-lookup"><span data-stu-id="eef2e-145">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="eef2e-146">這會傳回如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="eef2e-146">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="eef2e-147">此命令會將報告的工作階段限制為包含音訊形式的工作階段：</span><span class="sxs-lookup"><span data-stu-id="eef2e-147">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="eef2e-148">如果將滑鼠停留在報告上顯示的任何 [診斷識別碼] 上，說明該識別碼的工具提示就會顯示。</span><span class="sxs-lookup"><span data-stu-id="eef2e-148">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="eef2e-149">篩選</span><span class="sxs-lookup"><span data-stu-id="eef2e-149">Filters</span></span>

<span data-ttu-id="eef2e-p111">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，使用者活動報告可讓您依據活動類型之類的項目 (也就是，對等工作階段或會議工作階段)，或是依使用者的 SIP 位址 (可讓您檢視一位使用者的活動)，篩選傳回的資料。您也可以選擇資料的分組方式。在這種情況下，使用量會按照小時、日、星期或月加以分組。</span><span class="sxs-lookup"><span data-stu-id="eef2e-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="eef2e-154">下表列出您可以用於使用者活動報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="eef2e-154">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="eef2e-155">使用者活動報告篩選</span><span class="sxs-lookup"><span data-stu-id="eef2e-155">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eef2e-156">名稱</span><span class="sxs-lookup"><span data-stu-id="eef2e-156">Name</span></span></th>
<th><span data-ttu-id="eef2e-157">描述</span><span class="sxs-lookup"><span data-stu-id="eef2e-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-158"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-158"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-p112">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="eef2e-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="eef2e-161">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="eef2e-161">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="eef2e-p113">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="eef2e-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="eef2e-164">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="eef2e-164">7/17/12012</span></span></p>
<p><span data-ttu-id="eef2e-165">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="eef2e-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="eef2e-166">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="eef2e-166">7/13/2012</span></span></p>
<p><span data-ttu-id="eef2e-167">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="eef2e-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-168"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-168"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-p114">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="eef2e-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="eef2e-171">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="eef2e-171">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="eef2e-p115">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="eef2e-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="eef2e-174">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="eef2e-174">7/17/12012</span></span></p>
<p><span data-ttu-id="eef2e-175">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="eef2e-175">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="eef2e-176">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="eef2e-176">7/13/2012</span></span></p>
<p><span data-ttu-id="eef2e-177">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="eef2e-177">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-178"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-178"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-p116">活動的類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="eef2e-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="eef2e-181">一切</span><span class="sxs-lookup"><span data-stu-id="eef2e-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="eef2e-182">對等</span><span class="sxs-lookup"><span data-stu-id="eef2e-182">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="eef2e-183">會議</span><span class="sxs-lookup"><span data-stu-id="eef2e-183">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-184"><strong>形態</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-184"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-185">您可以使用的模態視選取活動類型而定。</span><span class="sxs-lookup"><span data-stu-id="eef2e-185">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="eef2e-186">如果活動類型為 Peer-to-Peer，您可以選取 [IM];檔案傳輸;應用程式共用;口音或像是模態的影片。</span><span class="sxs-lookup"><span data-stu-id="eef2e-186">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="eef2e-187">如果活動類型為 [會議]，您可以選取 [IM 電話] 會議;Web 會議;應用程式共用;語音/視訊會議;或電話語音會議。</span><span class="sxs-lookup"><span data-stu-id="eef2e-187">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-188"><strong>工作階段類別</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-188"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-p118">指出有疑問的活動為成功或失敗。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="eef2e-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="eef2e-191">一切</span><span class="sxs-lookup"><span data-stu-id="eef2e-191">[All]</span></span></p></li>
<li><p><span data-ttu-id="eef2e-192">成功</span><span class="sxs-lookup"><span data-stu-id="eef2e-192">Success</span></span></p></li>
<li><p><span data-ttu-id="eef2e-193">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="eef2e-193">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="eef2e-194">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="eef2e-194">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="eef2e-195">&quot;預期的失敗 &quot; 是預期會發生的失敗; 例如，如果使用者已將其狀態設為 [請勿打擾]，則您預期該使用者的任何呼叫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="eef2e-195">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="eef2e-196">未 &quot; 預期的失敗 &quot; 是指出現在其他狀況良好之系統上的失敗。</span><span class="sxs-lookup"><span data-stu-id="eef2e-196">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="eef2e-197">例如，當發話者處於保留狀態時，不應掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="eef2e-197">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="eef2e-198">當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="eef2e-198">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-199"><strong>使用者 URI 字首</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-199"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-p120">使用者的 SIP 位址。如果只要檢視使用者 Ken Myer 的記錄，則需要輸入 Ken Myer 的 SIP 位址。例如：</span><span class="sxs-lookup"><span data-stu-id="eef2e-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="eef2e-203">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eef2e-203">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="eef2e-204">對等工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="eef2e-204">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="eef2e-205">下表列出使用者活動報告中提供的對等工作階段資訊 (也就是只有兩個參與者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="eef2e-205">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="eef2e-206">對等工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="eef2e-206">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eef2e-207">姓名</span><span class="sxs-lookup"><span data-stu-id="eef2e-207">Name</span></span></th>
<th><span data-ttu-id="eef2e-208">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="eef2e-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="eef2e-209">描述</span><span class="sxs-lookup"><span data-stu-id="eef2e-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-210"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-210"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-211">否</span><span class="sxs-lookup"><span data-stu-id="eef2e-211">No</span></span></p></td>
<td><p><span data-ttu-id="eef2e-212">當您按一下此項目，報告即顯示所選取之工作階段的對等工作階段詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="eef2e-212">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-213"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-213"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-214">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-215">啟動對等工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="eef2e-215">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-216"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-216"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-217">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-218">參與對等工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="eef2e-218">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-219"><strong>方式</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-219"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-220">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-p121">工作階段中所使用的通訊類型。例如 IM、音訊或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="eef2e-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-223"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-223"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-224">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-225">初始邀請加入對等工作階段時，傳送邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="eef2e-225">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-226"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-226"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-227">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-228">&quot;至 &quot; 使用者接受會話邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="eef2e-228">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-229"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-229"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-230">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-231">對等工作階段結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="eef2e-231">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-232"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-232"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-233">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-p122">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="eef2e-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="eef2e-236">會議工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="eef2e-236">Metrics for conferencing sessions</span></span>

<span data-ttu-id="eef2e-237">下表列出使用者活動報告中提供的會議工作階段資訊 (也就是有三個以上參與者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="eef2e-237">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="eef2e-238">會議工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="eef2e-238">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eef2e-239">姓名</span><span class="sxs-lookup"><span data-stu-id="eef2e-239">Name</span></span></th>
<th><span data-ttu-id="eef2e-240">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="eef2e-240">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="eef2e-241">描述</span><span class="sxs-lookup"><span data-stu-id="eef2e-241">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-242"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-242"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-243">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-243">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-244">唯一會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="eef2e-244">Unique conference identifier.</span></span> <span data-ttu-id="eef2e-245">當您按一下此項目，報告即顯示所選取之工作階段的會議詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="eef2e-245">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="eef2e-246">當您展開此項目，報告會顯示會議參與者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="eef2e-246">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="eef2e-247">如需詳細資訊，請參閱 &quot; 本主題稍後的會議參與者的計量 &quot; 區一節。</span><span class="sxs-lookup"><span data-stu-id="eef2e-247">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-248"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-248"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-249">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-249">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-250">召開會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="eef2e-250">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-251"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-251"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-252">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-252">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-253">會議中使用的 Edge Server 名稱 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="eef2e-253">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-254"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-254"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-255">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-255">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-256">會議開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="eef2e-256">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-257"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-257"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-258">是</span><span class="sxs-lookup"><span data-stu-id="eef2e-258">Yes</span></span></p></td>
<td><p><span data-ttu-id="eef2e-259">會議結束的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="eef2e-259">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="eef2e-260">會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="eef2e-260">Metrics for conference participants</span></span>

<span data-ttu-id="eef2e-261">下表列出使用者活動報告中為會議每位參與者提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="eef2e-261">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="eef2e-262">會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="eef2e-262">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eef2e-263">姓名</span><span class="sxs-lookup"><span data-stu-id="eef2e-263">Name</span></span></th>
<th><span data-ttu-id="eef2e-264">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="eef2e-264">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="eef2e-265">描述</span><span class="sxs-lookup"><span data-stu-id="eef2e-265">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-266"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-266"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-267">否</span><span class="sxs-lookup"><span data-stu-id="eef2e-267">No</span></span></p></td>
<td><p><span data-ttu-id="eef2e-268">使用者的會議角色 (例如簡報者)。</span><span class="sxs-lookup"><span data-stu-id="eef2e-268">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-269"><strong>參與者</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-269"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-270">否</span><span class="sxs-lookup"><span data-stu-id="eef2e-270">No</span></span></p></td>
<td><p><span data-ttu-id="eef2e-271">使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="eef2e-271">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-272"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-272"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-273">否</span><span class="sxs-lookup"><span data-stu-id="eef2e-273">No</span></span></p></td>
<td><p><span data-ttu-id="eef2e-274">網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="eef2e-274">Network connection type.</span></span> <span data-ttu-id="eef2e-275">例如， &quot; 來自內部連線 &quot; 或 &quot; 從 PSTN &quot; 針對撥號使用者。</span><span class="sxs-lookup"><span data-stu-id="eef2e-275">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-276"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-276"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-277">否</span><span class="sxs-lookup"><span data-stu-id="eef2e-277">No</span></span></p></td>
<td><p><span data-ttu-id="eef2e-278">使用者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="eef2e-278">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef2e-279"><strong>離開時間</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-279"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-280">否</span><span class="sxs-lookup"><span data-stu-id="eef2e-280">No</span></span></p></td>
<td><p><span data-ttu-id="eef2e-281">使用者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="eef2e-281">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef2e-282"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="eef2e-282"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="eef2e-283">否</span><span class="sxs-lookup"><span data-stu-id="eef2e-283">No</span></span></p></td>
<td><p><span data-ttu-id="eef2e-p125">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="eef2e-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

