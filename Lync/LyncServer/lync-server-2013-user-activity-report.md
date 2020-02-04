---
title: Lync Server 2013：使用者活動報告
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
ms.openlocfilehash: 583c647ac3cdab290f1833539abbbd033ea89410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="0182a-102">Lync Server 2013 中的使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="0182a-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0182a-103">_**主題上次修改日期：** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="0182a-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="0182a-104">[使用者活動] 報告提供您在指定時段內由使用者執行之對等與會議會話的詳細清單。</span><span class="sxs-lookup"><span data-stu-id="0182a-104">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period.</span></span> <span data-ttu-id="0182a-105">與許多監視報表不同，使用者活動報告會將每個呼叫與個別使用者相互結合。</span><span class="sxs-lookup"><span data-stu-id="0182a-105">Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users.</span></span> <span data-ttu-id="0182a-106">例如，點對點工作階段會指定啟動通話的人員的 SIP Uri （來自使用者）及呼叫者（To 使用者）。</span><span class="sxs-lookup"><span data-stu-id="0182a-106">For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user).</span></span> <span data-ttu-id="0182a-107">如果您展開會議的資訊，您會看到所有會議參與者的清單，以及他們為該會議所擔任的角色。</span><span class="sxs-lookup"><span data-stu-id="0182a-107">If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="0182a-108">使用者活動報告有時稱為「問訊台」報告。</span><span class="sxs-lookup"><span data-stu-id="0182a-108">The User Activity Report is sometimes referred to as the "help desk" report.</span></span> <span data-ttu-id="0182a-109">這是因為技術支援人員經常會使用報告來取得特定使用者的會話資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-109">That's because the report is often used by help desk personnel to retrieve session information for a specific user.</span></span> <span data-ttu-id="0182a-110">您只要在 [使用者 URI 首碼] 方塊中輸入使用者的 SIP URI，就可以篩選給個別使用者所撥或進行的通話。</span><span class="sxs-lookup"><span data-stu-id="0182a-110">You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="0182a-111">如果您這樣做，使用者活動報告會會傳回其 SIP URI 以指定字串開頭的任何使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="0182a-112">例如，如果您在 [URI] 方塊中輸入**ken** ，使用者活動報告會會找到**ken**。Myer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="0182a-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="0182a-113">不過，它也會尋找這些使用者：</span><span class="sxs-lookup"><span data-stu-id="0182a-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="0182a-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0182a-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="0182a-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0182a-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="0182a-116">**Ken**。Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0182a-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="0182a-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0182a-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="0182a-118">若要確保傳回 Ken Myer 的資訊，請在 [搜尋] 方塊中輸入他的完整 URI （Ken.Myer@litwareinc.com），或是至少要將其與您組織中的其他使用者區分開來。</span><span class="sxs-lookup"><span data-stu-id="0182a-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="0182a-119">例如：</span><span class="sxs-lookup"><span data-stu-id="0182a-119">For example:</span></span>

<span data-ttu-id="0182a-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="0182a-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="0182a-121">存取使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="0182a-121">To access the user activity report</span></span>

<span data-ttu-id="0182a-122">使用者活動報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="0182a-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0182a-123">您也可以按一下 [ [Lync Server 2013] 的 [IP 電話清點] 報告中](lync-server-2013-ip-phone-inventory-report.md)的使用者 URI 躍點數，以取得使用者活動報告。</span><span class="sxs-lookup"><span data-stu-id="0182a-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="0182a-124">在 [使用者活動] 報告中，按一下會議 URI （適用于會議）會將您帶到會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="0182a-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="0182a-125">同樣地，按一下對等通話的詳細資料規格會將您帶到[Lync Server 2013 的點對點工作階段詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="0182a-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="0182a-126">充分運用使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="0182a-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="0182a-127">雖然使用者活動報告中有許多有用的資訊，但有時可能難以找出該資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="0182a-128">例如，在指定期間內，您組織中發生的所有使用者活動，都會包含在使用者活動報告中;也就是說，在報表中，[隱藏] 是哪些使用者以某種方式實際使用 Microsoft Lync Server 2013 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0182a-129">從技術角度來看，有些使用者的活動可能會 unrecorded：當 Lync Server 努力保留所有電話通話的相關資訊時，就可以進行通話，而不需要將該通話寫入資料庫的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="0182a-130">Lync Server 的設計目的是提供極其精確的功能，但不一定能完全瞭解 Lync Server 2013 的使用方式。</span><span class="sxs-lookup"><span data-stu-id="0182a-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="0182a-131">（不保證所有通話的100% 都已記錄，說明為什麼 Lync Server monitoring 不應該用來做為帳單系統）。</span><span class="sxs-lookup"><span data-stu-id="0182a-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="0182a-132">第二，監視報告報告最多隻能顯示1000記錄。</span><span class="sxs-lookup"><span data-stu-id="0182a-132">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="0182a-133">根據您所擁有的使用者活動數量而定，這表示您的查詢可能不會傳回實際儲存在資料庫中的所有資料。</span><span class="sxs-lookup"><span data-stu-id="0182a-133">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="0182a-134">在此期間實際使用系統的使用者是哪一種？</span><span class="sxs-lookup"><span data-stu-id="0182a-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="0182a-135">在此期間，哪些使用者是最活躍的？</span><span class="sxs-lookup"><span data-stu-id="0182a-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="0182a-136">使用者是否也能撥打電話至最常接聽的訊息？</span><span class="sxs-lookup"><span data-stu-id="0182a-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="0182a-137">如果您需要回答如下所示的問題，您可以將監控報告所檢索的資料匯出至 Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="0182a-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="0182a-138">接著，您可以使用該試算表和/或逗號分隔值檔案，以使用者活動報告的方式來分析資料。</span><span class="sxs-lookup"><span data-stu-id="0182a-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="0182a-139">例如，假設您已將報表資料匯出至 Excel，然後匯出為逗號分隔值檔案。</span><span class="sxs-lookup"><span data-stu-id="0182a-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="0182a-140">在該位置，您可以匯入資料。在 Windows PowerShell 中使用類似以下的命令來執行 CSV 檔案：</span><span class="sxs-lookup"><span data-stu-id="0182a-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="0182a-141">匯入資料之後，您就可以使用簡單的 Windows PowerShell 命令來協助回答您的問題。</span><span class="sxs-lookup"><span data-stu-id="0182a-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="0182a-142">例如，此命令會傳回至少在一個會話中作為「寄件者」的唯一使用者清單：</span><span class="sxs-lookup"><span data-stu-id="0182a-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="0182a-143">換句話說：</span><span class="sxs-lookup"><span data-stu-id="0182a-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="0182a-144">這個命令會列出唯一的使用者（根據其參與的會話總數）：</span><span class="sxs-lookup"><span data-stu-id="0182a-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="0182a-145">傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="0182a-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="0182a-146">這個命令會將報告的會話限制為以模態形式包含的音訊：</span><span class="sxs-lookup"><span data-stu-id="0182a-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="0182a-147">如果您將滑鼠放在報表上顯示的任何診斷 ID 上，系統會顯示描述該識別碼的工具提示。</span><span class="sxs-lookup"><span data-stu-id="0182a-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0182a-148">濾鏡</span><span class="sxs-lookup"><span data-stu-id="0182a-148">Filters</span></span>

<span data-ttu-id="0182a-149">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="0182a-149">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="0182a-150">例如，使用者活動報告可讓您根據活動類型（也就是點對點工作階段或會議會話）或使用者的 SIP 位址（可讓您查看一位使用者的活動）來篩選傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="0182a-150">For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user).</span></span> <span data-ttu-id="0182a-151">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="0182a-151">You can also choose how data should be grouped.</span></span> <span data-ttu-id="0182a-152">在這種情況下，使用方式會依小時、日、周或月分組。</span><span class="sxs-lookup"><span data-stu-id="0182a-152">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0182a-153">下表列出可與使用者活動報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="0182a-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="0182a-154">使用者活動報表篩選</span><span class="sxs-lookup"><span data-stu-id="0182a-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0182a-155">名稱</span><span class="sxs-lookup"><span data-stu-id="0182a-155">Name</span></span></th>
<th><span data-ttu-id="0182a-156">說明</span><span class="sxs-lookup"><span data-stu-id="0182a-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0182a-157"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-158">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-158">Start date/time for the time range.</span></span> <span data-ttu-id="0182a-159">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0182a-159">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0182a-160">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0182a-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0182a-161">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="0182a-161">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="0182a-162">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="0182a-162">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0182a-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0182a-163">7/17/12012</span></span></p>
<p><span data-ttu-id="0182a-164">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0182a-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0182a-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0182a-165">7/13/2012</span></span></p>
<p><span data-ttu-id="0182a-166">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="0182a-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-167"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-168">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-168">End date/time for the time range.</span></span> <span data-ttu-id="0182a-169">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0182a-169">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0182a-170">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0182a-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0182a-171">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="0182a-171">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="0182a-172">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="0182a-172">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0182a-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0182a-173">7/17/12012</span></span></p>
<p><span data-ttu-id="0182a-174">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0182a-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0182a-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0182a-175">7/13/2012</span></span></p>
<p><span data-ttu-id="0182a-176">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="0182a-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-177"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-178">活動類型。</span><span class="sxs-lookup"><span data-stu-id="0182a-178">Type of activity.</span></span> <span data-ttu-id="0182a-179">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0182a-179">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0182a-180">同時</span><span class="sxs-lookup"><span data-stu-id="0182a-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="0182a-181">對等</span><span class="sxs-lookup"><span data-stu-id="0182a-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="0182a-182">會議</span><span class="sxs-lookup"><span data-stu-id="0182a-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-183"><strong>模態</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-184">視選取活動類型而定，您可以使用哪些模態。</span><span class="sxs-lookup"><span data-stu-id="0182a-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="0182a-185">如果活動類型是對等，您可以選取 [IM];檔案傳輸;應用程式共用;語音或 [影片] 做為模態。</span><span class="sxs-lookup"><span data-stu-id="0182a-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="0182a-186">如果活動類型是 [會議]，您可以選取 [IM 電話會議];Web 會議;應用程式共用;語音/視訊會議;或電話會議。</span><span class="sxs-lookup"><span data-stu-id="0182a-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-187"><strong>會話類別</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-188">指出問題中的活動是否已成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="0182a-188">Indicates whether the activity in question succeeded or failed.</span></span> <span data-ttu-id="0182a-189">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0182a-189">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0182a-190">同時</span><span class="sxs-lookup"><span data-stu-id="0182a-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="0182a-191">成功案例</span><span class="sxs-lookup"><span data-stu-id="0182a-191">Success</span></span></p></li>
<li><p><span data-ttu-id="0182a-192">預期失敗</span><span class="sxs-lookup"><span data-stu-id="0182a-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="0182a-193">意外失敗</span><span class="sxs-lookup"><span data-stu-id="0182a-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="0182a-194">&quot;預期的失敗&quot;是預期發生的失敗;例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="0182a-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="0182a-195">發生&quot;意外的&quot;失敗，就是看起來像是其他健康的系統。</span><span class="sxs-lookup"><span data-stu-id="0182a-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="0182a-196">例如，如果來電者停留在 [保留] 上，就不應該終止通話。</span><span class="sxs-lookup"><span data-stu-id="0182a-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="0182a-197">如果發生這種情況，就會將它標記為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="0182a-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-198"><strong>使用者 URI 首碼</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-199">使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0182a-199">SIP address for the user.</span></span> <span data-ttu-id="0182a-200">若要只針對使用者 Ken Myer 查看記錄，您必須輸入 Ken Myer 的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0182a-200">To view records only for the user Ken Myer you need to enter Ken Myer's SIP address.</span></span> <span data-ttu-id="0182a-201">例如：</span><span class="sxs-lookup"><span data-stu-id="0182a-201">For example:</span></span></p>
<p><span data-ttu-id="0182a-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0182a-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0182a-203">點對點工作階段的度量單位</span><span class="sxs-lookup"><span data-stu-id="0182a-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="0182a-204">下表列出點對點工作階段的使用者活動報告中所提供的資訊（也就是只涉及兩個參與者的會話）。</span><span class="sxs-lookup"><span data-stu-id="0182a-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0182a-205">點對點工作階段的度量單位</span><span class="sxs-lookup"><span data-stu-id="0182a-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0182a-206">名稱</span><span class="sxs-lookup"><span data-stu-id="0182a-206">Name</span></span></th>
<th><span data-ttu-id="0182a-207">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="0182a-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0182a-208">說明</span><span class="sxs-lookup"><span data-stu-id="0182a-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0182a-209"><strong>具體</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-210">否</span><span class="sxs-lookup"><span data-stu-id="0182a-210">No</span></span></p></td>
<td><p><span data-ttu-id="0182a-211">當您按一下此專案時，報告會顯示所選會話的點對點工作階段詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="0182a-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-212"><strong>從使用者</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-213">是</span><span class="sxs-lookup"><span data-stu-id="0182a-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-214">啟動點對點工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0182a-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-215"><strong>給使用者</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-216">是</span><span class="sxs-lookup"><span data-stu-id="0182a-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-217">加入點對點工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0182a-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-218"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-219">是</span><span class="sxs-lookup"><span data-stu-id="0182a-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-220">會話中使用的通訊類型。</span><span class="sxs-lookup"><span data-stu-id="0182a-220">Type of communication used in the session.</span></span> <span data-ttu-id="0182a-221">例如，IM、音訊或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="0182a-221">For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-222"><strong>邀請時間</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-223">是</span><span class="sxs-lookup"><span data-stu-id="0182a-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-224">開始加入點對點工作階段的初始邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-225"><strong>回應時間</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-226">是</span><span class="sxs-lookup"><span data-stu-id="0182a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-227">使用者接受會話邀請的日期和時間&quot; &quot;</span><span class="sxs-lookup"><span data-stu-id="0182a-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-228"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-229">是</span><span class="sxs-lookup"><span data-stu-id="0182a-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-230">點對點工作階段結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-231"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-232">是</span><span class="sxs-lookup"><span data-stu-id="0182a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-233">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-233">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="0182a-234">診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="0182a-234">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0182a-235">會議會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="0182a-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="0182a-236">下表列出會議會話的使用者活動報告中所提供的資訊（也就是與三個或更多參與者相關的會話）。</span><span class="sxs-lookup"><span data-stu-id="0182a-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0182a-237">會議會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="0182a-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0182a-238">名稱</span><span class="sxs-lookup"><span data-stu-id="0182a-238">Name</span></span></th>
<th><span data-ttu-id="0182a-239">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="0182a-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0182a-240">說明</span><span class="sxs-lookup"><span data-stu-id="0182a-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0182a-241"><strong>會議 URI</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-242">是</span><span class="sxs-lookup"><span data-stu-id="0182a-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-243">唯一的會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="0182a-243">Unique conference identifier.</span></span> <span data-ttu-id="0182a-244">當您按一下此專案時，報告會顯示所選會話的會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="0182a-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="0182a-245">展開此專案時，報告會顯示會議參與者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="0182a-246">如需詳細資訊， &quot;請參閱本主題&quot;稍後的會議參與者的度量資料一節。</span><span class="sxs-lookup"><span data-stu-id="0182a-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-247"><strong>召集人</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-248">是</span><span class="sxs-lookup"><span data-stu-id="0182a-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-249">組織會議的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0182a-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-250"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-251">是</span><span class="sxs-lookup"><span data-stu-id="0182a-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-252">在會議中使用的邊緣伺服器（如果有的話）的名稱。</span><span class="sxs-lookup"><span data-stu-id="0182a-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-253"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-254">是</span><span class="sxs-lookup"><span data-stu-id="0182a-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-255">會議開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-256"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-257">是</span><span class="sxs-lookup"><span data-stu-id="0182a-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="0182a-258">會議結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="0182a-259">會議參與者的度量單位</span><span class="sxs-lookup"><span data-stu-id="0182a-259">Metrics for conference participants</span></span>

<span data-ttu-id="0182a-260">下表列出使用者活動報告中提供的資訊，提供給會議中的每個參與者。</span><span class="sxs-lookup"><span data-stu-id="0182a-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="0182a-261">會議參與者的度量單位</span><span class="sxs-lookup"><span data-stu-id="0182a-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0182a-262">名稱</span><span class="sxs-lookup"><span data-stu-id="0182a-262">Name</span></span></th>
<th><span data-ttu-id="0182a-263">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="0182a-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0182a-264">說明</span><span class="sxs-lookup"><span data-stu-id="0182a-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0182a-265"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-266">否</span><span class="sxs-lookup"><span data-stu-id="0182a-266">No</span></span></p></td>
<td><p><span data-ttu-id="0182a-267">使用者的會議角色（例如，簡報者）。</span><span class="sxs-lookup"><span data-stu-id="0182a-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-268"><strong>參加</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-269">否</span><span class="sxs-lookup"><span data-stu-id="0182a-269">No</span></span></p></td>
<td><p><span data-ttu-id="0182a-270">使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0182a-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-271"><strong>連通</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-272">否</span><span class="sxs-lookup"><span data-stu-id="0182a-272">No</span></span></p></td>
<td><p><span data-ttu-id="0182a-273">網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="0182a-273">Network connection type.</span></span> <span data-ttu-id="0182a-274">例如&quot;，內部連線&quot;的內部或&quot;撥入使用者&quot;的 PSTN。</span><span class="sxs-lookup"><span data-stu-id="0182a-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-275"><strong>加入時間</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-276">否</span><span class="sxs-lookup"><span data-stu-id="0182a-276">No</span></span></p></td>
<td><p><span data-ttu-id="0182a-277">使用者加入會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0182a-278"><strong>休假時間</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-279">否</span><span class="sxs-lookup"><span data-stu-id="0182a-279">No</span></span></p></td>
<td><p><span data-ttu-id="0182a-280">使用者離開會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0182a-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0182a-281"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="0182a-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0182a-282">否</span><span class="sxs-lookup"><span data-stu-id="0182a-282">No</span></span></p></td>
<td><p><span data-ttu-id="0182a-283">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="0182a-283">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="0182a-284">診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="0182a-284">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

