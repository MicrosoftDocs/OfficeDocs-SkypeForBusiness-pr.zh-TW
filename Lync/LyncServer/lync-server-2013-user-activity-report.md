---
title: Lync Server 2013： 使用者活動報告
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
ms.openlocfilehash: 38df7f9f8c457ac68ee441a6806b87f37b10539b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="d1c9e-102">Lync Server 2013 中的使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="d1c9e-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c9e-103">_**主題上次修改日期：** 2015 年 02 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="d1c9e-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="d1c9e-p101">「使用者活動報告」提供了指定期間內使用者執行之對等及會議工作階段的詳細清單。不同於多數「監控報告」，「使用者活動報告」將每通通話牽繫到個別使用者。例如，對等工作階段會指定發話者 (來源使用者) 及受話者 (目標使用者) 的 SIP URI。如展開關於會議的資訊，則會顯示所有會議參與者及其在該會議中所扮演角色的清單。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="d1c9e-p102">「使用者活動報告」有時稱為「服務台」報告。這是因為此報告常被服務台人員用來擷取特定使用者的工作階段資訊。在 [使用者 URI 首碼] 方塊中輸入使用者的 SIP URI，即可篩選個別使用者所接收或發出的通話。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="d1c9e-111">如果您這麼做時，使用者活動報告將會傳回對其 SIP URI 以指定字串開頭的任何使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="d1c9e-112">例如，如果您輸入**ken**的 URI] 中，使用者活動報告會找出**Ken**。Myer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="d1c9e-113">不過，它也會尋找這些使用者：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="d1c9e-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d1c9e-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="d1c9e-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d1c9e-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="d1c9e-116">**Ken**。Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d1c9e-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="d1c9e-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d1c9e-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="d1c9e-118">若要確保只是傳回 Ken myer 的使用者，其完整的 URI (Ken.Myer@litwareinc.com) 在輸入 [搜尋] 方塊或 Ken 的至少足夠類型的資訊以唯一區別他與您組織中其他使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="d1c9e-119">例如：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-119">For example:</span></span>

<span data-ttu-id="d1c9e-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="d1c9e-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="d1c9e-121">存取使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="d1c9e-121">To access the user activity report</span></span>

<span data-ttu-id="d1c9e-122">從「監控報告」首頁可存取「使用者活動報告」。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="d1c9e-123">您也可以[在 Lync Server 2013 中的 IP 電話清查報告](lync-server-2013-ip-phone-inventory-report.md)上的 [使用者 URI] 計量，即可達到使用者活動報告。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="d1c9e-124">從「使用者活動報告」中，按一下 [會議 URI] (針對會議) 會移至「會議詳細資料報告」。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="d1c9e-125">同樣地，按一下 [對等通話詳細資料] 計量會帶您至[Lync Server 2013 中的端對端工作階段詳細資料報告](lync-server-2013-peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="d1c9e-126">使用者活動報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="d1c9e-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="d1c9e-127">雖然「使用者活動報告」中有許多有用的資訊，但是有時候很難找到所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="d1c9e-128">例如，會發生在指定期間內貴組織中的所有使用者活動都隨附於使用者活動報告。表示、 遭到，報表內哪些使用者確實使用 Microsoft Lync Server 2013 以某種方式的資訊。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d1c9e-129">技術上而言，很可能有些使用者活動可能移程： Lync Server 致力於保持所有通話的相關資訊時有可能，來電可能有所沒有寫入至資料庫該通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="d1c9e-130">Lync Server 的設計目的是提供極精確，但不是一定完美查看如何使用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="d1c9e-131">（100%的所有呼叫會記錄不保證的事實說明為什麼 Lync 伺服器監視不應為帳單系統）。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="d1c9e-p108">第二，「監控報告」中的報告最多僅可顯示 1,000 筆記錄。所以，取決於使用者活動的多寡及工作期間，您的查詢可能不會傳回資料庫中所有實際儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="d1c9e-134">在此期間內哪些使用者確實使用系統？</span><span class="sxs-lookup"><span data-stu-id="d1c9e-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="d1c9e-135">在此期間內我的哪些使用者最為活躍？</span><span class="sxs-lookup"><span data-stu-id="d1c9e-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="d1c9e-136">通話最多的使用者也是參與最多立即訊息工作階段的使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="d1c9e-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="d1c9e-137">如果您需要回答此類問題，可以將「監控報告」擷取的資料匯出到 Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="d1c9e-138">然後使用該試算表及 (或) 逗點分隔值檔案，以「使用者活動報告」無法做到的方式來分析資料。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="d1c9e-139">例如，假設您已將報告資料匯出到 Excel，再儲存為逗點分隔值檔案。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="d1c9e-140">此時，您可以匯入的資料。CSV 檔案，以 Windows PowerShell 使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="d1c9e-141">資料已匯入之後您可以再使用簡單的 Windows PowerShell 命令來幫助回答您的問題。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="d1c9e-142">例如，以下命令會傳回至少在一個工作階段中擔任「來源使用者」的唯一使用者清單：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="d1c9e-143">換句話說：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="d1c9e-144">此命令會列出唯一使用者 (根據他們參與的工作階段總數)：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="d1c9e-145">這會傳回如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="d1c9e-146">此命令會將報告的工作階段限制為包含音訊形式的工作階段：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="d1c9e-147">如果將滑鼠停留在報告上顯示的任何 [診斷識別碼] 上，說明該識別碼的工具提示就會顯示。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d1c9e-148">篩選</span><span class="sxs-lookup"><span data-stu-id="d1c9e-148">Filters</span></span>

<span data-ttu-id="d1c9e-p111">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，使用者活動報告可讓您依據活動類型之類的項目 (也就是，對等工作階段或會議工作階段)，或是依使用者的 SIP 位址 (可讓您檢視一位使用者的活動)，篩選傳回的資料。您也可以選擇資料的分組方式。在這種情況下，使用量會按照小時、日、星期或月加以分組。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d1c9e-153">下表列出您可以用於使用者活動報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="d1c9e-154">使用者活動報告篩選</span><span class="sxs-lookup"><span data-stu-id="d1c9e-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1c9e-155">名稱</span><span class="sxs-lookup"><span data-stu-id="d1c9e-155">Name</span></span></th>
<th><span data-ttu-id="d1c9e-156">描述</span><span class="sxs-lookup"><span data-stu-id="d1c9e-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-157"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p112">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d1c9e-160">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d1c9e-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d1c9e-p113">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d1c9e-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d1c9e-163">7/17/12012</span></span></p>
<p><span data-ttu-id="d1c9e-164">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d1c9e-165">2012/7/13</span><span class="sxs-lookup"><span data-stu-id="d1c9e-165">7/13/2012</span></span></p>
<p><span data-ttu-id="d1c9e-166">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p114">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d1c9e-170">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d1c9e-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d1c9e-p115">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d1c9e-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d1c9e-173">7/17/12012</span></span></p>
<p><span data-ttu-id="d1c9e-174">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d1c9e-175">2012/7/13</span><span class="sxs-lookup"><span data-stu-id="d1c9e-175">7/13/2012</span></span></p>
<p><span data-ttu-id="d1c9e-176">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-177"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p116">活動的類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1c9e-180">[全部]</span><span class="sxs-lookup"><span data-stu-id="d1c9e-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="d1c9e-181">端對端</span><span class="sxs-lookup"><span data-stu-id="d1c9e-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="d1c9e-182">會議</span><span class="sxs-lookup"><span data-stu-id="d1c9e-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-183"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-184">您可以使用形式會視選取活動類型而有所不同。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="d1c9e-185">對等活動類型時，您可以選取 IM;檔案傳輸。應用程式共用;語音;或視訊作為形式。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="d1c9e-186">會議活動類型時，您可以選取 IM 電話會議;Web 會議;應用程式共用;語音/視訊會議;或電話語音會議。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-187"><strong>工作階段類別</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p118">指出有疑問的活動為成功或失敗。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1c9e-190">[全部]</span><span class="sxs-lookup"><span data-stu-id="d1c9e-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="d1c9e-191">成功</span><span class="sxs-lookup"><span data-stu-id="d1c9e-191">Success</span></span></p></li>
<li><p><span data-ttu-id="d1c9e-192">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="d1c9e-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="d1c9e-193">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="d1c9e-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="d1c9e-194">&quot;預期失敗&quot;是發生; 預期的失敗例如，如果使用者已將他/她的狀態設為 [請勿打擾] 您所預期該使用者的任何呼叫失敗。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="d1c9e-195">&quot;未預期的失敗&quot;是在項目會顯示為否則狀況良好的系統，就會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="d1c9e-196">例如，當發話者處於保留狀態時，不應掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="d1c9e-197">當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-198"><strong>使用者 URI 字首</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p120">使用者的 SIP 位址。如果只要檢視使用者 Ken Myer 的記錄，則需要輸入 Ken Myer 的 SIP 位址。例如：</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="d1c9e-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d1c9e-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="d1c9e-203">對等工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="d1c9e-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="d1c9e-204">下表列出使用者活動報告中提供的對等工作階段資訊 (也就是只有兩個參與者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="d1c9e-205">對等工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="d1c9e-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1c9e-206">名稱</span><span class="sxs-lookup"><span data-stu-id="d1c9e-206">Name</span></span></th>
<th><span data-ttu-id="d1c9e-207">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="d1c9e-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d1c9e-208">描述</span><span class="sxs-lookup"><span data-stu-id="d1c9e-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-209"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-210">否</span><span class="sxs-lookup"><span data-stu-id="d1c9e-210">No</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-211">當您按一下此項目，報告即顯示所選取之工作階段的對等工作階段詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-212"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-213">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-214">啟動對等工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-215"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-216">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-217">參與對等工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-218"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-219">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p121">工作階段中所使用的通訊類型。例如 IM、音訊或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-222"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-223">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-224">初始邀請加入對等工作階段時，傳送邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-225"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-226">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-227">日期與時間，&quot;以&quot;使用者接受工作階段邀請。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-228"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-229">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-230">對等工作階段結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-231"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-232">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p122">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="d1c9e-235">會議工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="d1c9e-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="d1c9e-236">下表列出使用者活動報告中提供的會議工作階段資訊 (也就是有三個以上參與者的工作階段)。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="d1c9e-237">會議工作階段的計量</span><span class="sxs-lookup"><span data-stu-id="d1c9e-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1c9e-238">名稱</span><span class="sxs-lookup"><span data-stu-id="d1c9e-238">Name</span></span></th>
<th><span data-ttu-id="d1c9e-239">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="d1c9e-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d1c9e-240">描述</span><span class="sxs-lookup"><span data-stu-id="d1c9e-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-241"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-242">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-243">唯一會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-243">Unique conference identifier.</span></span> <span data-ttu-id="d1c9e-244">當您按一下此項目，報告即顯示所選取之工作階段的會議詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="d1c9e-245">當您展開此項目，報告會顯示會議參與者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="d1c9e-246">如需詳細資訊，請參閱&quot;會議參與者的計量&quot;本主題稍後的區段。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-247"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-248">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-249">召開會議之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-251">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-252">會議中使用的 Edge Server 名稱 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-253"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-254">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-255">會議開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-256"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-257">是</span><span class="sxs-lookup"><span data-stu-id="d1c9e-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-258">會議結束的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="d1c9e-259">會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="d1c9e-259">Metrics for conference participants</span></span>

<span data-ttu-id="d1c9e-260">下表列出使用者活動報告中為會議每位參與者提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="d1c9e-261">會議參與者的計量</span><span class="sxs-lookup"><span data-stu-id="d1c9e-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1c9e-262">名稱</span><span class="sxs-lookup"><span data-stu-id="d1c9e-262">Name</span></span></th>
<th><span data-ttu-id="d1c9e-263">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="d1c9e-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d1c9e-264">描述</span><span class="sxs-lookup"><span data-stu-id="d1c9e-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-265"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-266">否</span><span class="sxs-lookup"><span data-stu-id="d1c9e-266">No</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-267">使用者的會議角色 (例如簡報者)。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-268"><strong>參與者</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-269">否</span><span class="sxs-lookup"><span data-stu-id="d1c9e-269">No</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-270">使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-271"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-272">否</span><span class="sxs-lookup"><span data-stu-id="d1c9e-272">No</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-273">網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-273">Network connection type.</span></span> <span data-ttu-id="d1c9e-274">例如&quot;從內部&quot;內部連線或&quot;從 PSTN&quot;電話撥入式使用者。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-275"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-276">否</span><span class="sxs-lookup"><span data-stu-id="d1c9e-276">No</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-277">使用者加入會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c9e-278"><strong>離開時間</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-279">否</span><span class="sxs-lookup"><span data-stu-id="d1c9e-279">No</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-280">使用者離開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c9e-281"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="d1c9e-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c9e-282">否</span><span class="sxs-lookup"><span data-stu-id="d1c9e-282">No</span></span></p></td>
<td><p><span data-ttu-id="d1c9e-p125">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="d1c9e-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

