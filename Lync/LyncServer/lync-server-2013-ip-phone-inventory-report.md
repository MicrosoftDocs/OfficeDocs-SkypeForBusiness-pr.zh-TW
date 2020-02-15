---
title: 'Lync Server 2013: IP 電話清查報告'
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
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="1f400-102">Lync Server 2013 中的 IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="1f400-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f400-103">_**主題上次修改日期：** 2012年-11-12_</span><span class="sxs-lookup"><span data-stu-id="1f400-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="1f400-104">IP 電話清查報告報告目前正在使用您組織中的 IP 電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1f400-104">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="1f400-105">IP 清查報告提供實際期間指定的報表期間內使用的 IP 電話的詳細的清單。</span><span class="sxs-lookup"><span data-stu-id="1f400-105">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="1f400-106">除此之外，這份報告可讓系統管理員知道仍在使用，應被取代; 是否有任何舊的、 過時的電話它也可以有貴組織中的電話，很少使用的事實警示系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1f400-106">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="1f400-107">提到的時間來購買新電話或轉散佈現有的電話時，該類型的資訊十分有用。</span><span class="sxs-lookup"><span data-stu-id="1f400-107">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="1f400-108">（例如，很少使用他/她昂貴的電話的使用者可能會要求來進行更常使用他/她電話的使用者交換電話。）</span><span class="sxs-lookup"><span data-stu-id="1f400-108">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="1f400-109">請注意，這份報告有一些限制對正在作為檔案，則為 true 的清查報告過濾。</span><span class="sxs-lookup"><span data-stu-id="1f400-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="1f400-110">第一，IP 電話報告只會列出所有登入 Lync Server 在指定的時間期間，其最後登入時間來排序的電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="1f400-111">如果電話沒有登入指定的時間期間然後它將不會列在清查報告。</span><span class="sxs-lookup"><span data-stu-id="1f400-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="1f400-112">包含之前的時間期間啟動，且已在指定的時間間隔期間仍登入的身分登入的電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="1f400-113">例如，假設您想要查看所有電話清查 2012 年 7 月。</span><span class="sxs-lookup"><span data-stu-id="1f400-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="1f400-114">假設以及數個電話登入 Lync Server 在 2012 年 6 月 30 日，且已截至年 7 月 1st 仍登入。</span><span class="sxs-lookup"><span data-stu-id="1f400-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="1f400-115">這些電話不會顯示在清查報告的年 7 月 1st。</span><span class="sxs-lookup"><span data-stu-id="1f400-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="1f400-116">務必也請注意，清查報告可能包含您的組織無法再使用的電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-116">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="1f400-117">例如，假設在 2012 年 7 月 1 日; 登入系統的 Fabrikam 電話的數目5 天後您的組織 got 排除所有這些 Fabrikam 電話，並取代較新的 Contoso 模型。</span><span class="sxs-lookup"><span data-stu-id="1f400-117">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="1f400-118">Fabrikam 電話上仍會顯示 「 存貨 」 報告只是因為他們登入系統的年 7 月份期間。</span><span class="sxs-lookup"><span data-stu-id="1f400-118">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="1f400-119">此外，IP 電話清查報告不會報告不同類型的電話摘要合計。</span><span class="sxs-lookup"><span data-stu-id="1f400-119">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="1f400-120">例如，假設您有 105 Polycom CX600 電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-120">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="1f400-121">報表不會告訴您，您有 105 的這些電話;相反地，您只會看到 Polycom Cx600 105 的個別項目。</span><span class="sxs-lookup"><span data-stu-id="1f400-121">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="1f400-122">若要知道有 Polycom Cx600 105 項目的唯一方法是手動計算每個這些項目。</span><span class="sxs-lookup"><span data-stu-id="1f400-122">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1f400-123">或者，匯出資料，並使用 Microsoft Excel 或 Windows PowerShell 來執行計算。</span><span class="sxs-lookup"><span data-stu-id="1f400-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="1f400-124">存取 IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="1f400-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="1f400-125">從監視報告首頁存取 IP 電話清查報告。</span><span class="sxs-lookup"><span data-stu-id="1f400-125">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="1f400-126">如果您按一下 [使用者 URI] 計量可以存取該使用者的使用者活動報告。</span><span class="sxs-lookup"><span data-stu-id="1f400-126">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="1f400-127">按一下 [上次活動計量的端對端電話將帶您前往端對端工作階段詳細資料報表;按一下該相同的會議計量，將帶您前往會議詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="1f400-127">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="1f400-128">IP 電話清查報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="1f400-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="1f400-129">如果您有興趣只有一種特定電話使用方式資訊 （例如，「 頻率使用者使用 Polycom CX600 電話？ 」） 您可以透過電話該特定類型的篩選直接從 IP 電話清查報告取得該資訊。</span><span class="sxs-lookup"><span data-stu-id="1f400-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="1f400-130">不過，如果您想要所有的電話摘要資訊 （多少人正在使用多少使用 LG Nortel IP8540 等 Polycom CX600） 則必須以匯出資料，並執行該類型的使用另一個應用程式 （例如 Windows PowerShell)分析。</span><span class="sxs-lookup"><span data-stu-id="1f400-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="1f400-131">例如，假設您將資料匯出成逗點分隔值檔案 (c:\\資料\\IP\_電話\_庫存\_Report.csv)。</span><span class="sxs-lookup"><span data-stu-id="1f400-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="1f400-132">在此情況下，您可以使用這兩個命令提供所有的電話摘要資料：</span><span class="sxs-lookup"><span data-stu-id="1f400-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="1f400-133">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="1f400-133">That will return data similar to this:</span></span>

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

<span data-ttu-id="1f400-134">同樣地，這兩個命令會告訴您哪些電話登入系統，但從未實際用於撥打電話 （上次活動計量值為空白，表示沒有任何上次活動）：</span><span class="sxs-lookup"><span data-stu-id="1f400-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="1f400-135">會傳回資料尚未使用每個電話如下：</span><span class="sxs-lookup"><span data-stu-id="1f400-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="1f400-136">有趣的另一種方式使用 IP 電話清查報告這是： 如果您有您可以找出使用者上次使用該電話只在 MAC 位址] 文字方塊中輸入該地址 IP 電話的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="1f400-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="1f400-137">IP 電話清查報告會再報告回 （除此之外） 上次登入與該電話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f400-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="1f400-138">或者，您可以輸入使用者 （在 [使用者 URI 字首] 方塊中） 的 SIP 位址，以找出所有使用過該使用者的電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1f400-139">篩選</span><span class="sxs-lookup"><span data-stu-id="1f400-139">Filters</span></span>

<span data-ttu-id="1f400-140">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="1f400-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="1f400-141">例如，IP 電話清查可讓您檢視僅限生產特定的公司或甚至是這些電話的特定版本的電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-141">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="1f400-142">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="1f400-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="1f400-143">在此情況下，註冊分組小時、 日、 週或月。</span><span class="sxs-lookup"><span data-stu-id="1f400-143">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="1f400-144">下表列出您可以使用 IP 電話清查報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="1f400-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="1f400-145">IP 電話清查報告篩選器</span><span class="sxs-lookup"><span data-stu-id="1f400-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f400-146">名稱</span><span class="sxs-lookup"><span data-stu-id="1f400-146">Name</span></span></th>
<th><span data-ttu-id="1f400-147">描述</span><span class="sxs-lookup"><span data-stu-id="1f400-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f400-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-p109">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1f400-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1f400-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f400-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f400-p110">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="1f400-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f400-154">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="1f400-154">7/7/2012</span></span></p>
<p><span data-ttu-id="1f400-155">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="1f400-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f400-156">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="1f400-156">7/3/2012</span></span></p>
<p><span data-ttu-id="1f400-157">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="1f400-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-p111">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1f400-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1f400-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f400-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f400-p112">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="1f400-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f400-164">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="1f400-164">7/7/2012</span></span></p>
<p><span data-ttu-id="1f400-165">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="1f400-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f400-166">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="1f400-166">7/3/2012</span></span></p>
<p><span data-ttu-id="1f400-167">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="1f400-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f400-168"><strong>製造商</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-169">生產該 IP 電話的公司名稱。</span><span class="sxs-lookup"><span data-stu-id="1f400-169">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="1f400-170">此篩選的值會自動填入您根據 IP 電話，而且目前在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="1f400-170">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-171"><strong>硬體版本</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-172">IP 電話; 的版本號碼製造商和硬體版本篩選器您可以使用唯一識別特定類型的電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="1f400-173">此篩選的值會自動填入您根據 IP 電話，而且目前在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="1f400-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f400-174"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-175">IP 電話所使用的軟體識別碼。</span><span class="sxs-lookup"><span data-stu-id="1f400-175">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="1f400-176">此篩選的值會自動填入您根據目前資料庫中的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-176">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-177"><strong>MAC 位址</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-178">IP 電話上的網路介面的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1f400-178">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="1f400-179">在電話生產，並且為硬體有線方式於裝置硬體的時間通常指派的媒體存取控制 (MAC) 位址。</span><span class="sxs-lookup"><span data-stu-id="1f400-179">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="1f400-180">若要搜尋記錄屬於特定的 MAC 位址只輸入該地址。</span><span class="sxs-lookup"><span data-stu-id="1f400-180">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="1f400-181">例如：</span><span class="sxs-lookup"><span data-stu-id="1f400-181">For example:</span></span></p>
<p><span data-ttu-id="1f400-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="1f400-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="1f400-183">您必須輸入完整的地址。</span><span class="sxs-lookup"><span data-stu-id="1f400-183">You must enter the complete address.</span></span> <span data-ttu-id="1f400-184">部分的地址 (例如 00-08-5 D) 不會傳回任何資料。</span><span class="sxs-lookup"><span data-stu-id="1f400-184">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f400-185"><strong>天前的最後活動</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-186">選取下列其中一個下列值：</span><span class="sxs-lookup"><span data-stu-id="1f400-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f400-187">[全部]</span><span class="sxs-lookup"><span data-stu-id="1f400-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="1f400-188">10 </span><span class="sxs-lookup"><span data-stu-id="1f400-188">10</span></span></p></li>
<li><p><span data-ttu-id="1f400-189">20</span><span class="sxs-lookup"><span data-stu-id="1f400-189">20</span></span></p></li>
<li><p><span data-ttu-id="1f400-190">30</span><span class="sxs-lookup"><span data-stu-id="1f400-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-191"><strong>天數前的最後登出時間</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-192">選取下列其中一個下列值：</span><span class="sxs-lookup"><span data-stu-id="1f400-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f400-193">[全部]</span><span class="sxs-lookup"><span data-stu-id="1f400-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="1f400-194">10 </span><span class="sxs-lookup"><span data-stu-id="1f400-194">10</span></span></p></li>
<li><p><span data-ttu-id="1f400-195">20</span><span class="sxs-lookup"><span data-stu-id="1f400-195">20</span></span></p></li>
<li><p><span data-ttu-id="1f400-196">30</span><span class="sxs-lookup"><span data-stu-id="1f400-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f400-197"><strong>使用者 URI 字首</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-198">使用 IP 電話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f400-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1f400-199">計量</span><span class="sxs-lookup"><span data-stu-id="1f400-199">Metrics</span></span>

<span data-ttu-id="1f400-200">下表列出 IP 電話清查報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="1f400-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="1f400-201">IP 電話清查報告計量</span><span class="sxs-lookup"><span data-stu-id="1f400-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f400-202">姓名</span><span class="sxs-lookup"><span data-stu-id="1f400-202">Name</span></span></th>
<th><span data-ttu-id="1f400-203">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="1f400-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f400-204">描述</span><span class="sxs-lookup"><span data-stu-id="1f400-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f400-205"><strong>製造商</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-206">是</span><span class="sxs-lookup"><span data-stu-id="1f400-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-207">生產該 IP 電話的公司名稱。</span><span class="sxs-lookup"><span data-stu-id="1f400-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-208"><strong>硬體版本</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-209">是</span><span class="sxs-lookup"><span data-stu-id="1f400-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-210">IP 電話的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="1f400-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f400-211"><strong>MAC 位址</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-212">是</span><span class="sxs-lookup"><span data-stu-id="1f400-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-213">IP 電話上的網路介面的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1f400-213">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="1f400-214">在電話生產，並且為硬體有線方式於裝置硬體的時間通常指派的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="1f400-214">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-215"><strong>使用者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-216">是</span><span class="sxs-lookup"><span data-stu-id="1f400-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-217">使用 IP 電話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="1f400-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f400-218"><strong>使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-219">是</span><span class="sxs-lookup"><span data-stu-id="1f400-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-220">IP 電話所使用的軟體識別碼。</span><span class="sxs-lookup"><span data-stu-id="1f400-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-221"><strong>上次登入時間</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-222">是</span><span class="sxs-lookup"><span data-stu-id="1f400-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-223">日期和時間 IP 電話上次登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="1f400-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f400-224"><strong>上次登出時間</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-225">是</span><span class="sxs-lookup"><span data-stu-id="1f400-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-226">日期和時間 IP 電話上次登出從 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="1f400-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f400-227"><strong>上次活動</strong></span><span class="sxs-lookup"><span data-stu-id="1f400-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="1f400-228">是</span><span class="sxs-lookup"><span data-stu-id="1f400-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f400-229">日期和時間上次使用 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="1f400-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

