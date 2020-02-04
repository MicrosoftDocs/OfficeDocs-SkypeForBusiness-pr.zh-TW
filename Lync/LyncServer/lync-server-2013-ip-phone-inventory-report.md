---
title: Lync Server 2013： IP 電話清點報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb9bb9a3ae48c8bf2fc9a5122e1b8004e0f6019
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="f8120-102">Lync Server 2013 中的 IP 電話清點報告</span><span class="sxs-lookup"><span data-stu-id="f8120-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8120-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="f8120-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="f8120-104">IP 電話清點報告會報告貴組織目前正在使用之 IP 電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f8120-104">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="f8120-105">IP 清點報告提供在指定報告期間內實際使用之 IP 手機的詳細清單。</span><span class="sxs-lookup"><span data-stu-id="f8120-105">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="f8120-106">在其他專案中，此報告可讓系統管理員知道是否有任何舊版、過時的手機仍在使用中，而這些電話應該會被取代;此外，它也可以提醒系統管理員在組織中有大量的電話很少使用的情況。</span><span class="sxs-lookup"><span data-stu-id="f8120-106">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="f8120-107">在購買新手機或重新發佈現有手機時，這類資訊可能很有用。</span><span class="sxs-lookup"><span data-stu-id="f8120-107">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="f8120-108">（例如，很少使用其昂貴手機的使用者，可能會要求您以更頻繁的方式，將手機更換為使用他或她的手機的使用者。）</span><span class="sxs-lookup"><span data-stu-id="f8120-108">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="f8120-109">請注意，此報告在作為真正的庫存報告時，會有一些限制。</span><span class="sxs-lookup"><span data-stu-id="f8120-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="f8120-110">在其中一種情況下，IP 電話報告只會列出在指定的時段內登入 Lync Server 的所有電話，並依其上次登入時間排序。</span><span class="sxs-lookup"><span data-stu-id="f8120-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="f8120-111">如果手機在指定的時段內沒有登入，則不會列于庫存報告中。</span><span class="sxs-lookup"><span data-stu-id="f8120-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="f8120-112">這包括在時間週期開始之前登入，且在指定的時間間隔期間仍登入的電話。</span><span class="sxs-lookup"><span data-stu-id="f8120-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="f8120-113">例如，假設您想要查看2012年7月的所有電話清點。</span><span class="sxs-lookup"><span data-stu-id="f8120-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="f8120-114">假設您也是在2012年6月30日登入 Lync Server 的數個電話，而且在7月1日仍登入。</span><span class="sxs-lookup"><span data-stu-id="f8120-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="f8120-115">這些手機不會顯示在7月1日的庫存報告上。</span><span class="sxs-lookup"><span data-stu-id="f8120-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="f8120-116">另外，請務必注意，庫存報告可能包含貴組織已不再使用的電話。</span><span class="sxs-lookup"><span data-stu-id="f8120-116">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="f8120-117">例如，假設您已在2012年7月1日登入系統的 Fabrikam 電話數。您的組織稍後會有5天的時間來移除所有這些 Fabrikam 手機，並以較新的 Contoso 模型取代。</span><span class="sxs-lookup"><span data-stu-id="f8120-117">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="f8120-118">Fabrikam 手機仍會出現在 [清查] 報表上，因為它們會在7月期間登入系統。</span><span class="sxs-lookup"><span data-stu-id="f8120-118">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="f8120-119">此外，IP 電話清點報告不會報告不同電話類型的摘要總數。</span><span class="sxs-lookup"><span data-stu-id="f8120-119">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="f8120-120">例如，假設您有 105 Polycom CX600 電話。</span><span class="sxs-lookup"><span data-stu-id="f8120-120">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="f8120-121">報告不會告知您有105以上的手機;相反地，您只會看到 105 Polycom Cx600 的個別專案。</span><span class="sxs-lookup"><span data-stu-id="f8120-121">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="f8120-122">若要知道 Polycom Cx600 有105專案，只需手動計算每個專案。</span><span class="sxs-lookup"><span data-stu-id="f8120-122">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f8120-123">或者，匯出資料並使用 Microsoft Excel 或 Windows PowerShell 來為您計算。</span><span class="sxs-lookup"><span data-stu-id="f8120-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="f8120-124">存取 IP 電話清點報告</span><span class="sxs-lookup"><span data-stu-id="f8120-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="f8120-125">[IP 電話清點] 報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="f8120-125">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="f8120-126">如果您按一下 [使用者 URI 規格]，您可以存取該使用者的使用者活動報告。</span><span class="sxs-lookup"><span data-stu-id="f8120-126">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="f8120-127">按一下對等呼叫的最後一個活動躍點數會將您帶到點對點工作階段詳細資料包告;按一下會議的同一個公制會將您帶到會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="f8120-127">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="f8120-128">充分利用 IP 電話清點報告</span><span class="sxs-lookup"><span data-stu-id="f8120-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="f8120-129">如果您只對某種特定類型手機的使用資訊感興趣（例如，「使用 Polycom CX600 電話的使用者頻率如何？」），您可以透過篩選特定類型的電話，直接從 IP 電話清點報告取得該資訊。</span><span class="sxs-lookup"><span data-stu-id="f8120-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="f8120-130">不過，如果您想要的是所有電話的摘要資訊（有多少人使用 Polycom CX600，還有多少是使用 LG-Nortel IP8540 等等），那麼您將需要匯出資料並使用另一個應用程式（例如 Windows PowerShell）來執行該類型的分析.</span><span class="sxs-lookup"><span data-stu-id="f8120-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="f8120-131">例如，假設您將資料匯出為逗點分隔值檔案（\\C：資料\\IP\_電話\_清點\_報表 .csv）。</span><span class="sxs-lookup"><span data-stu-id="f8120-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="f8120-132">在這種情況下，您可以使用這兩個命令，為您的所有手機提供摘要資料：</span><span class="sxs-lookup"><span data-stu-id="f8120-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="f8120-133">這樣會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="f8120-133">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="f8120-134">同樣地，這兩個命令會告知您登入系統的電話，但永遠不會實際用來撥打電話（最後一個活動指標的值為空白，表示沒有任何最後一個活動）：</span><span class="sxs-lookup"><span data-stu-id="f8120-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="f8120-135">針對每個尚未使用的電話，傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="f8120-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="f8120-136">使用 IP 電話清點報告的另一種有趣方式是：如果您有 IP 電話的 MAC 位址，您可以在 [MAC 位址] 文字方塊中輸入該位址，即可找出最後一次使用該手機的使用者。</span><span class="sxs-lookup"><span data-stu-id="f8120-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="f8120-137">接著，IP 電話清點報告會傳回與該手機通訊的使用者 SIP 位址（在其他專案中）。</span><span class="sxs-lookup"><span data-stu-id="f8120-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="f8120-138">或者，您也可以輸入使用者 SIP 位址（在 [使用者 URI 首碼] 方塊中），找出該使用者所使用的所有電話。</span><span class="sxs-lookup"><span data-stu-id="f8120-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f8120-139">濾鏡</span><span class="sxs-lookup"><span data-stu-id="f8120-139">Filters</span></span>

<span data-ttu-id="f8120-140">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="f8120-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="f8120-141">例如，IP 電話清點可讓您只查看特定公司生產的電話，甚至是那些手機的特定版本。</span><span class="sxs-lookup"><span data-stu-id="f8120-141">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="f8120-142">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="f8120-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="f8120-143">在這種情況下，登記會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="f8120-143">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f8120-144">下表列出您可搭配 IP 電話清點報告使用的篩選準則。</span><span class="sxs-lookup"><span data-stu-id="f8120-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="f8120-145">IP 電話清點報表篩選</span><span class="sxs-lookup"><span data-stu-id="f8120-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8120-146">名稱</span><span class="sxs-lookup"><span data-stu-id="f8120-146">Name</span></span></th>
<th><span data-ttu-id="f8120-147">說明</span><span class="sxs-lookup"><span data-stu-id="f8120-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8120-148"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-149">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="f8120-149">Start date/time for the time range.</span></span> <span data-ttu-id="f8120-150">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f8120-150">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f8120-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f8120-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f8120-152">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="f8120-152">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="f8120-153">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="f8120-153">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f8120-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f8120-154">7/7/2012</span></span></p>
<p><span data-ttu-id="f8120-155">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="f8120-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f8120-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f8120-156">7/3/2012</span></span></p>
<p><span data-ttu-id="f8120-157">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="f8120-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-158"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-159">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="f8120-159">End date/time for the time range.</span></span> <span data-ttu-id="f8120-160">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f8120-160">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f8120-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f8120-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f8120-162">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="f8120-162">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="f8120-163">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="f8120-163">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f8120-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f8120-164">7/7/2012</span></span></p>
<p><span data-ttu-id="f8120-165">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="f8120-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f8120-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f8120-166">7/3/2012</span></span></p>
<p><span data-ttu-id="f8120-167">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="f8120-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8120-168"><strong>製造商</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-169">製造 IP 電話的公司名稱。</span><span class="sxs-lookup"><span data-stu-id="f8120-169">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="f8120-170">此篩選的值會根據目前在資料庫中的 IP 電話自動填入。</span><span class="sxs-lookup"><span data-stu-id="f8120-170">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-171"><strong>硬體版本</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-172">IP 電話的版本號碼;使用製造商和硬體版本篩選，您可以唯一識別特定類型的手機。</span><span class="sxs-lookup"><span data-stu-id="f8120-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="f8120-173">此篩選的值會根據目前在資料庫中的 IP 電話自動填入。</span><span class="sxs-lookup"><span data-stu-id="f8120-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8120-174"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-175">IP 電話使用的軟體識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8120-175">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="f8120-176">此篩選的值會根據目前資料庫中的 IP 電話自動填入。</span><span class="sxs-lookup"><span data-stu-id="f8120-176">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-177"><strong>MAC 位址</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-178">IP 電話上網路介面的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8120-178">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="f8120-179">媒體存取控制（MAC）位址通常是在撥打電話並固定在裝置硬體中時指派。</span><span class="sxs-lookup"><span data-stu-id="f8120-179">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="f8120-180">若要搜尋與特定 MAC 位址相關的記錄，只要輸入該位址即可。</span><span class="sxs-lookup"><span data-stu-id="f8120-180">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="f8120-181">例如：</span><span class="sxs-lookup"><span data-stu-id="f8120-181">For example:</span></span></p>
<p><span data-ttu-id="f8120-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="f8120-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="f8120-183">您必須輸入完整的位址。</span><span class="sxs-lookup"><span data-stu-id="f8120-183">You must enter the complete address.</span></span> <span data-ttu-id="f8120-184">部分位址（例如 00-08-5D）不會傳回任何資料。</span><span class="sxs-lookup"><span data-stu-id="f8120-184">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8120-185"><strong>天數前的最後一個活動</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-186">選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="f8120-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="f8120-187">同時</span><span class="sxs-lookup"><span data-stu-id="f8120-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="f8120-188">第</span><span class="sxs-lookup"><span data-stu-id="f8120-188">10</span></span></p></li>
<li><p><span data-ttu-id="f8120-189">20</span><span class="sxs-lookup"><span data-stu-id="f8120-189">20</span></span></p></li>
<li><p><span data-ttu-id="f8120-190">為期</span><span class="sxs-lookup"><span data-stu-id="f8120-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-191"><strong>上次登出時間（天之前）</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-192">選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="f8120-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="f8120-193">同時</span><span class="sxs-lookup"><span data-stu-id="f8120-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="f8120-194">第</span><span class="sxs-lookup"><span data-stu-id="f8120-194">10</span></span></p></li>
<li><p><span data-ttu-id="f8120-195">20</span><span class="sxs-lookup"><span data-stu-id="f8120-195">20</span></span></p></li>
<li><p><span data-ttu-id="f8120-196">為期</span><span class="sxs-lookup"><span data-stu-id="f8120-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8120-197"><strong>使用者 URI 首碼</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-198">使用 IP 電話的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="f8120-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f8120-199">指標</span><span class="sxs-lookup"><span data-stu-id="f8120-199">Metrics</span></span>

<span data-ttu-id="f8120-200">下表列出 IP 電話清點報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="f8120-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="f8120-201">IP 電話清點報告度量單位</span><span class="sxs-lookup"><span data-stu-id="f8120-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8120-202">名稱</span><span class="sxs-lookup"><span data-stu-id="f8120-202">Name</span></span></th>
<th><span data-ttu-id="f8120-203">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="f8120-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f8120-204">說明</span><span class="sxs-lookup"><span data-stu-id="f8120-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8120-205"><strong>製造商</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-206">是</span><span class="sxs-lookup"><span data-stu-id="f8120-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-207">製造 IP 電話的公司名稱。</span><span class="sxs-lookup"><span data-stu-id="f8120-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-208"><strong>硬體版本</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-209">是</span><span class="sxs-lookup"><span data-stu-id="f8120-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-210">IP 電話的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="f8120-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8120-211"><strong>MAC 位址</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-212">是</span><span class="sxs-lookup"><span data-stu-id="f8120-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-213">IP 電話上網路介面的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8120-213">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="f8120-214">MAC 位址通常是在撥打電話並將它硬連接至裝置硬體時指派。</span><span class="sxs-lookup"><span data-stu-id="f8120-214">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-215"><strong>使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-216">是</span><span class="sxs-lookup"><span data-stu-id="f8120-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-217">使用 IP 電話的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="f8120-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8120-218"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-219">是</span><span class="sxs-lookup"><span data-stu-id="f8120-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-220">IP 電話使用的軟體識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8120-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-221"><strong>上次登入時間</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-222">是</span><span class="sxs-lookup"><span data-stu-id="f8120-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-223">IP 電話上次登入 Lync Server 的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="f8120-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8120-224"><strong>上次登出時間</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-225">是</span><span class="sxs-lookup"><span data-stu-id="f8120-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-226">IP 電話上次從 Lync Server 登出的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="f8120-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8120-227"><strong>上次活動</strong></span><span class="sxs-lookup"><span data-stu-id="f8120-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="f8120-228">是</span><span class="sxs-lookup"><span data-stu-id="f8120-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="f8120-229">上次使用 IP 電話的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="f8120-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

