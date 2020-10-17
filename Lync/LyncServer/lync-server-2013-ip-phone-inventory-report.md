---
title: Lync Server 2013： IP 電話清查報告
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
ms.openlocfilehash: a0be055238c2e8db45337b9e66d936bb73c73e61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525200"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="0cca1-102">Lync Server 2013 中的 IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="0cca1-102">IP Phone Inventory Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cca1-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="0cca1-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="0cca1-104">IP 電話清查報告會報告您組織中目前使用之 IP 電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0cca1-104">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="0cca1-105">IP 清查報告提供在指定報告期間實際使用的 IP 電話詳細清單。</span><span class="sxs-lookup"><span data-stu-id="0cca1-105">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="0cca1-106">除了其他事項之外，此報告還可讓系統管理員知道是否仍在使用任何舊的過期電話，而這些電話是否仍在使用中;此外，它也可以警示系統管理員，因為組織中有很少使用的電話很昂貴。</span><span class="sxs-lookup"><span data-stu-id="0cca1-106">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="0cca1-107">當購買新的電話或重新發佈現有的電話時，該類型的資訊可能非常寶貴。</span><span class="sxs-lookup"><span data-stu-id="0cca1-107">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="0cca1-108"> (例如，很少使用他或她的昂貴電話的使用者，可能要求您將電話換用使用他或她之電話的使用者頻率較高。 ) </span><span class="sxs-lookup"><span data-stu-id="0cca1-108">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="0cca1-109">請注意，此報告在用來做為真正的庫存報告時，會有一些限制。</span><span class="sxs-lookup"><span data-stu-id="0cca1-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="0cca1-110">一方面，IP 電話報告只會列出在指定期間內登入 Lync Server 的所有電話，並依上次登入時間排序。</span><span class="sxs-lookup"><span data-stu-id="0cca1-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="0cca1-111">如果電話沒有在指定的時間期間登入，則不會在庫存報告中列出。</span><span class="sxs-lookup"><span data-stu-id="0cca1-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="0cca1-112">，包括在啟動期間之前登入的電話，而且在指定的時間間隔內仍會登入。</span><span class="sxs-lookup"><span data-stu-id="0cca1-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="0cca1-113">例如，假設您想要查看2012年7月的所有電話清點。</span><span class="sxs-lookup"><span data-stu-id="0cca1-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="0cca1-114">假設您也可以在2012年6月30日登入 Lync Server，並在7月1日之後仍登入。</span><span class="sxs-lookup"><span data-stu-id="0cca1-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="0cca1-115">這些電話在7月1日的庫存報告上不會顯示。</span><span class="sxs-lookup"><span data-stu-id="0cca1-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="0cca1-116">此外，請務必注意，庫存報告可以包含您的組織不再使用的電話。</span><span class="sxs-lookup"><span data-stu-id="0cca1-116">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="0cca1-117">例如，假設您在2012年7月1日在系統上登入的 Fabrikam 電話數目。5天之後您的組織會擺脫所有的 Fabrikam 電話，並以新的 Contoso 模型取代。</span><span class="sxs-lookup"><span data-stu-id="0cca1-117">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="0cca1-118">Fabrikam 電話仍會出現在「清查」報告上，因為它們是在七月期間登入系統。</span><span class="sxs-lookup"><span data-stu-id="0cca1-118">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="0cca1-119">此外，IP 電話清查報告不會報告不同電話類型的摘要總數。</span><span class="sxs-lookup"><span data-stu-id="0cca1-119">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="0cca1-120">例如，假設您有 105 Polycom CX600 電話。</span><span class="sxs-lookup"><span data-stu-id="0cca1-120">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="0cca1-121">報告不會告訴您，您有105以上的電話;相反地，您只會看到 Polycom Cx600 的105個別專案。</span><span class="sxs-lookup"><span data-stu-id="0cca1-121">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="0cca1-122">Polycom Cx600 的105專案的唯一方法，就是手動統計每個專案。</span><span class="sxs-lookup"><span data-stu-id="0cca1-122">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0cca1-123">或者，匯出資料，並使用 Microsoft Excel 或 Windows PowerShell 為您進行計算。</span><span class="sxs-lookup"><span data-stu-id="0cca1-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="0cca1-124">存取 IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="0cca1-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="0cca1-125">IP 電話清查報告可從監控報告的首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="0cca1-125">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0cca1-126">如果您按一下 [使用者 URI] 度量，您可以存取該使用者的使用者活動報告。</span><span class="sxs-lookup"><span data-stu-id="0cca1-126">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="0cca1-127">按一下對等通話的最後一個活動度量會帶您前往 Peer-to-Peer 會話詳細資料包告。按一下會議的相同公制會帶您前往會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="0cca1-127">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="0cca1-128">IP 電話清查報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="0cca1-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="0cca1-129">如果您只對一種特殊電話的使用資訊感興趣 (例如，「使用 Polycom CX600 電話的使用者頻率為何？」。) 您可以透過篩選該特定類型的電話，直接從 IP 電話清查報告取得資訊。</span><span class="sxs-lookup"><span data-stu-id="0cca1-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="0cca1-130">不過，如果您想要所有電話的摘要資訊 (多少人使用的是 Polycom CX600、使用 LG-Nortel IP8540 的數目，等等。 ) 之後，您將需要匯出資料，並使用另一個應用程式 (例如 Windows PowerShell) 來執行該類型的分析。</span><span class="sxs-lookup"><span data-stu-id="0cca1-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="0cca1-131">例如，假設您會將資料匯出到逗號分隔值檔案 (C： \\ 資料 \\ IP \_ 電話 \_ 清點 \_Report.csv) 。</span><span class="sxs-lookup"><span data-stu-id="0cca1-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="0cca1-132">在這種情況下，您可以使用這兩個命令，提供您所有電話的摘要資料：</span><span class="sxs-lookup"><span data-stu-id="0cca1-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="0cca1-133">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="0cca1-133">That will return data similar to this:</span></span>

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

<span data-ttu-id="0cca1-134">同樣地，這兩個命令會告訴您登入系統的電話，但永不實際用來撥打電話 (最後一個活動度量值為空白，表示沒有任何上一個活動) ：</span><span class="sxs-lookup"><span data-stu-id="0cca1-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="0cca1-135">針對每個尚未使用的電話，傳回類似以下的資料：</span><span class="sxs-lookup"><span data-stu-id="0cca1-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="0cca1-136">使用 IP 電話清查報告的另一種有趣方式是：如果您有 IP 電話的 MAC 位址，只要在 [MAC 位址] 文字方塊中輸入該位址，即可找出最近使用該電話的使用者。</span><span class="sxs-lookup"><span data-stu-id="0cca1-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="0cca1-137">然後，[IP 電話清點] 報告會向 (報告) 使用者上次登入該電話之使用者的 SIP 位址的其他事項。</span><span class="sxs-lookup"><span data-stu-id="0cca1-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="0cca1-138">或者，您也可以在 [使用者 URI 前置詞] 方塊中輸入使用者 SIP 位址 (，) 以找出該使用者已使用的所有電話。</span><span class="sxs-lookup"><span data-stu-id="0cca1-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0cca1-139">篩選</span><span class="sxs-lookup"><span data-stu-id="0cca1-139">Filters</span></span>

<span data-ttu-id="0cca1-140">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="0cca1-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="0cca1-141">例如，IP 電話清查可讓您只查看特定公司製造的電話，甚至只查看這些電話的特定版本。</span><span class="sxs-lookup"><span data-stu-id="0cca1-141">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="0cca1-142">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="0cca1-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="0cca1-143">在此情況下，登記會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="0cca1-143">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0cca1-144">下表列出您可以搭配 IP 電話清查報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="0cca1-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="0cca1-145">IP 電話清查報告篩選器</span><span class="sxs-lookup"><span data-stu-id="0cca1-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cca1-146">名稱</span><span class="sxs-lookup"><span data-stu-id="0cca1-146">Name</span></span></th>
<th><span data-ttu-id="0cca1-147">描述</span><span class="sxs-lookup"><span data-stu-id="0cca1-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-p109">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0cca1-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0cca1-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0cca1-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0cca1-p110">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="0cca1-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0cca1-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0cca1-154">7/7/2012</span></span></p>
<p><span data-ttu-id="0cca1-155">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="0cca1-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0cca1-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0cca1-156">7/3/2012</span></span></p>
<p><span data-ttu-id="0cca1-157">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="0cca1-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-p111">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0cca1-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0cca1-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0cca1-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0cca1-p112">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="0cca1-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0cca1-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0cca1-164">7/7/2012</span></span></p>
<p><span data-ttu-id="0cca1-165">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="0cca1-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0cca1-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0cca1-166">7/3/2012</span></span></p>
<p><span data-ttu-id="0cca1-167">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="0cca1-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-168"><strong>製造商</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-169">製造 IP 電話的公司名稱。</span><span class="sxs-lookup"><span data-stu-id="0cca1-169">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="0cca1-170">根據資料庫中目前的 IP 電話，此篩選器的值會自動填入。</span><span class="sxs-lookup"><span data-stu-id="0cca1-170">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-171"><strong>硬體版本</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-172">IP 電話的版本號碼;使用製造商和硬體版本篩選器，您可以唯一識別特定類型的電話。</span><span class="sxs-lookup"><span data-stu-id="0cca1-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="0cca1-173">根據資料庫中目前的 IP 電話，此篩選器的值會自動填入。</span><span class="sxs-lookup"><span data-stu-id="0cca1-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-174"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-175">IP 電話所使用之軟體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="0cca1-175">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="0cca1-176">根據目前資料庫中的 IP 電話，此篩選器的值會自動填入。</span><span class="sxs-lookup"><span data-stu-id="0cca1-176">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-177"><strong>MAC 位址</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-178">IP 電話上網路介面的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0cca1-178">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="0cca1-179">Media Access Control (MAC) 位址通常是在電話製造時，且硬接線到裝置硬體時進行指派。</span><span class="sxs-lookup"><span data-stu-id="0cca1-179">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="0cca1-180">若要搜尋與特定 MAC 位址相關的記錄，只要輸入該位址即可。</span><span class="sxs-lookup"><span data-stu-id="0cca1-180">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="0cca1-181">例如：</span><span class="sxs-lookup"><span data-stu-id="0cca1-181">For example:</span></span></p>
<p><span data-ttu-id="0cca1-182">00-08-16-16-48</span><span class="sxs-lookup"><span data-stu-id="0cca1-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="0cca1-183">您必須輸入完整的位址。</span><span class="sxs-lookup"><span data-stu-id="0cca1-183">You must enter the complete address.</span></span> <span data-ttu-id="0cca1-184">部分位址 (例如，00-08-5D) 不會傳回任何資料。</span><span class="sxs-lookup"><span data-stu-id="0cca1-184">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-185"><strong>天數之前的最後一個活動</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-186">選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="0cca1-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0cca1-187">一切</span><span class="sxs-lookup"><span data-stu-id="0cca1-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="0cca1-188">10 </span><span class="sxs-lookup"><span data-stu-id="0cca1-188">10</span></span></p></li>
<li><p><span data-ttu-id="0cca1-189">共</span><span class="sxs-lookup"><span data-stu-id="0cca1-189">20</span></span></p></li>
<li><p><span data-ttu-id="0cca1-190">大約</span><span class="sxs-lookup"><span data-stu-id="0cca1-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-191"><strong>前一天的登出時間</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-192">選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="0cca1-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0cca1-193">一切</span><span class="sxs-lookup"><span data-stu-id="0cca1-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="0cca1-194">10 </span><span class="sxs-lookup"><span data-stu-id="0cca1-194">10</span></span></p></li>
<li><p><span data-ttu-id="0cca1-195">共</span><span class="sxs-lookup"><span data-stu-id="0cca1-195">20</span></span></p></li>
<li><p><span data-ttu-id="0cca1-196">大約</span><span class="sxs-lookup"><span data-stu-id="0cca1-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-197"><strong>使用者 URI 字首</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-198">使用 IP 電話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0cca1-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0cca1-199">指標</span><span class="sxs-lookup"><span data-stu-id="0cca1-199">Metrics</span></span>

<span data-ttu-id="0cca1-200">下表列出 IP 電話清查報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="0cca1-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="0cca1-201">IP 電話清查報告計量</span><span class="sxs-lookup"><span data-stu-id="0cca1-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cca1-202">姓名</span><span class="sxs-lookup"><span data-stu-id="0cca1-202">Name</span></span></th>
<th><span data-ttu-id="0cca1-203">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="0cca1-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0cca1-204">描述</span><span class="sxs-lookup"><span data-stu-id="0cca1-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-205"><strong>製造商</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-206">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-207">製造 IP 電話的公司名稱。</span><span class="sxs-lookup"><span data-stu-id="0cca1-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-208"><strong>硬體版本</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-209">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-210">IP 電話的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="0cca1-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-211"><strong>MAC 位址</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-212">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-213">IP 電話上網路介面的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0cca1-213">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="0cca1-214">MAC 位址通常是在電話製造時所指派，而且會硬接線至裝置硬體。</span><span class="sxs-lookup"><span data-stu-id="0cca1-214">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-215"><strong>使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-216">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-217">使用 IP 電話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="0cca1-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-218"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-219">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-220">IP 電話所使用之軟體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="0cca1-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-221"><strong>上次登入時間</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-222">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-223">IP 電話上次登入 Lync Server 的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0cca1-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cca1-224"><strong>上次登出時間</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-225">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-226">IP 電話上次從 Lync Server 登出的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0cca1-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cca1-227"><strong>最後一個活動</strong></span><span class="sxs-lookup"><span data-stu-id="0cca1-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="0cca1-228">是</span><span class="sxs-lookup"><span data-stu-id="0cca1-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cca1-229">上次使用 IP 電話的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0cca1-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

