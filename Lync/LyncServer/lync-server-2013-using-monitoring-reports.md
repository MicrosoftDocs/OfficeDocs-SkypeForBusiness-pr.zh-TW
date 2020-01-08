---
title: Lync Server 2013：使用監視報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7c1e70a47e3f3043215e1d16e1f01bfec4b677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="72408-102">在 Lync Server 2013 中使用監視報告</span><span class="sxs-lookup"><span data-stu-id="72408-102">Using Monitoring Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72408-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="72408-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="72408-104">Lync Server 2013 包含一組 Microsoft SQL Server Reporting Services 發佈的標準報告。</span><span class="sxs-lookup"><span data-stu-id="72408-104">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="72408-105">這些報表可透過網頁瀏覽器存取，提供使用方式、呼叫診斷資訊和媒體質量資訊，所有這些都是以呼叫詳細資料錄製（CDR）以及儲存在 CDR 和 QoE 資料庫的體驗品質（QoE）記錄為基礎。</span><span class="sxs-lookup"><span data-stu-id="72408-105">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="72408-106">若要使用這些報告，您必須在執行 SQL Server 實例的電腦上安裝 [監視報告]。</span><span class="sxs-lookup"><span data-stu-id="72408-106">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72408-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="72408-107">In This Section</span></span>

  - <span data-ttu-id="72408-108">[使用 Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   中的 [監視儀表板]，可讓系統管理員快速瞭解其系統健康情況與系統使用量。</span><span class="sxs-lookup"><span data-stu-id="72408-108">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="72408-109">[Lync server 2013](lync-server-2013-system-usage-reports.md)   中的系統使用量報告可根據 Lync Server 所收集的 CDR 資料，提供系統使用量資訊。</span><span class="sxs-lookup"><span data-stu-id="72408-109">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="72408-110">[在 Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   中呼叫診斷報告（每位使用者）可提供對點對點與會議會話失敗的每使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="72408-110">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="72408-111">[在 Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   中呼叫診斷報告，可提供失敗對等與會議會話的摘要資訊與診斷資料。</span><span class="sxs-lookup"><span data-stu-id="72408-111">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="72408-112">[Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   中的媒體質量診斷報告提供通話品質的相關資訊，以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="72408-112">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="72408-113">尋找記錄</span><span class="sxs-lookup"><span data-stu-id="72408-113">Locating Records</span></span>

<span data-ttu-id="72408-114">監視報告只會在任何時間顯示畫面上有限數量的記錄。</span><span class="sxs-lookup"><span data-stu-id="72408-114">Monitoring Reports only show a limited number of records on the screen at any one time.</span></span> <span data-ttu-id="72408-115">顯示在螢幕上的實際記錄數會依報表而有所不同。</span><span class="sxs-lookup"><span data-stu-id="72408-115">The actual number of records displayed on a screen varies depending on the report.</span></span> <span data-ttu-id="72408-116">若要查看目前未顯示在螢幕上的記錄，您可以使用 [標準前向] 和 [向後] 控制（可在每個報表的工具列上找到），讓您可以分頁流覽資料。</span><span class="sxs-lookup"><span data-stu-id="72408-116">To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data.</span></span> <span data-ttu-id="72408-117">您也可以快速跳至資料集的第一頁或最後一頁。</span><span class="sxs-lookup"><span data-stu-id="72408-117">You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="72408-118">除了使用向前和向後控制項之外，您也可以直接在 [**目前頁面**] 方塊中輸入頁碼，然後按 enter 鍵，跳至資料集中的任何頁面。</span><span class="sxs-lookup"><span data-stu-id="72408-118">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="72408-119">除了提供頁面流覽資料的功能之外，每個報告也包含尋找記錄的有限能力。</span><span class="sxs-lookup"><span data-stu-id="72408-119">In addition to providing the ability to page through the data, each report also includes the limited ability to find records.</span></span> <span data-ttu-id="72408-120">若要尋找以特定值為基礎的記錄，請在 [**尋找**] 方塊中輸入該值，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="72408-120">To find records based on a given value, type that value into the **Find** box, and then click **Find**.</span></span> <span data-ttu-id="72408-121">報告會開始搜尋資料，並停止在您在 [**尋找**] 方塊中輸入之值的第一個實例。</span><span class="sxs-lookup"><span data-stu-id="72408-121">The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box.</span></span> <span data-ttu-id="72408-122">若要尋找符合搜尋準則的下一筆記錄，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="72408-122">To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="72408-123">如所述，監視報告只提供最基本的搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="72408-123">As noted, the Monitoring Reports provide only the most basic search functions.</span></span> <span data-ttu-id="72408-124">例如，您無法指定應該在哪個欄位中找到值。</span><span class="sxs-lookup"><span data-stu-id="72408-124">For example, you cannot specify which field the value should be found in.</span></span> <span data-ttu-id="72408-125">[搜尋] 機制會自動在每一筆記錄的每個欄位中搜尋相符的值。</span><span class="sxs-lookup"><span data-stu-id="72408-125">The search mechanism automatically searches for matching values in every field in every record.</span></span> <span data-ttu-id="72408-126">您無法在搜尋中使用萬用字元，且所有搜尋都會尋找部分值。</span><span class="sxs-lookup"><span data-stu-id="72408-126">You cannot use wildcards in your searches, and all searches look for partial values.</span></span> <span data-ttu-id="72408-127">如此一來，如果您搜尋111，搜尋會傳回值111，以及在該欄位內任何位置都包含 value 3112 的值11100、811、111、611A5B 及任何其他欄位。</span><span class="sxs-lookup"><span data-stu-id="72408-127">That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="72408-128">每個報告都設定為顯示一組預設的記錄。</span><span class="sxs-lookup"><span data-stu-id="72408-128">Each report is configured to show a default set of records.</span></span> <span data-ttu-id="72408-129">例如，根據預設，[使用者註冊] 報告會顯示上周的使用者註冊活動。</span><span class="sxs-lookup"><span data-stu-id="72408-129">For example, by default the User Registration Report shows user registration activities for the past week.</span></span> <span data-ttu-id="72408-130">在某些情況下，這可能會導致不會傳回任何記錄的報表。</span><span class="sxs-lookup"><span data-stu-id="72408-130">In some cases, this might result in a report that returns no records.</span></span> <span data-ttu-id="72408-131">在這種情況下，這表示上周不會發生任何使用者註冊。</span><span class="sxs-lookup"><span data-stu-id="72408-131">In this case, it means that no user registrations have taken place in the past week.</span></span> <span data-ttu-id="72408-132">如果您看到「沒有結果符合報表篩選」的訊息，請嘗試變更篩選值（例如，將時段變更為 [上個月]，而非上周），然後重新執行查詢。</span><span class="sxs-lookup"><span data-stu-id="72408-132">If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query.</span></span> <span data-ttu-id="72408-133">如需詳細資訊，請參閱本主題稍後的「篩選資料」一節。</span><span class="sxs-lookup"><span data-stu-id="72408-133">For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="72408-134">篩選資料</span><span class="sxs-lookup"><span data-stu-id="72408-134">Filtering Data</span></span>

<span data-ttu-id="72408-135">有時候，您可能會想要只查看記錄的子集。</span><span class="sxs-lookup"><span data-stu-id="72408-135">There will likely be times when you want to look at only a subset of records.</span></span> <span data-ttu-id="72408-136">例如，只有點對點工作階段，而不是點對點工作階段與會議會話。</span><span class="sxs-lookup"><span data-stu-id="72408-136">For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="72408-137">同樣地，您也需要減少傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="72408-137">Likewise, there will be times when you need to reduce the number of records that are returned.</span></span> <span data-ttu-id="72408-138">根據預設，報告只能顯示資料集中的前1000筆記錄。</span><span class="sxs-lookup"><span data-stu-id="72408-138">By default, a report can only display the first 1,000 records in a data set.</span></span> <span data-ttu-id="72408-139">為了解決這些問題，大多數報表都包含許多篩選選項。</span><span class="sxs-lookup"><span data-stu-id="72408-139">To address these issues, most reports include a number of filtering options.</span></span> <span data-ttu-id="72408-140">例如，如果您只想要查看2011年1月1日到2011日的記錄，您可以在 [收件者] 方塊中輸入 [年1月 2011 1 日]，在 **[收\*\*\*\*件**者] 方塊中輸入1月 2011 15 日。</span><span class="sxs-lookup"><span data-stu-id="72408-140">For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box.</span></span> <span data-ttu-id="72408-141">如果您接著按一下 [**查看報表**]，則傳回的資料會限制在2011年1月1日到2011年1月15日之間發生的活動。</span><span class="sxs-lookup"><span data-stu-id="72408-141">If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="72408-142">您可使用的篩選依據您所查看的報表而有所不同。</span><span class="sxs-lookup"><span data-stu-id="72408-142">The filters available to you vary depending on the report that you are viewing.</span></span> <span data-ttu-id="72408-143">如需特定報告的詳細資訊，請參閱該報告的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="72408-143">For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="72408-144">匯出資料</span><span class="sxs-lookup"><span data-stu-id="72408-144">Exporting Data</span></span>

<span data-ttu-id="72408-145">[監視報告] 提供至少兩種不同的方式來匯出報表中包含的資料。</span><span class="sxs-lookup"><span data-stu-id="72408-145">The Monitoring Reports provide at least two different ways to export the data included in a report.</span></span> <span data-ttu-id="72408-146">您可以在每個報告頂端出現的工具列中，使用 [**匯出**] 選項。</span><span class="sxs-lookup"><span data-stu-id="72408-146">You can use the **Export** option in the toolbar that appears at the top of each report.</span></span> <span data-ttu-id="72408-147">若要使用此選項，請從 [**選取格式**] 下拉式清單中選取所要的匯出格式。</span><span class="sxs-lookup"><span data-stu-id="72408-147">To use this option, select the desired export format from the **Select a format** drop-down list.</span></span> <span data-ttu-id="72408-148">您可以使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="72408-148">The following formats are available to you:</span></span>

  - <span data-ttu-id="72408-149">含報表資料的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="72408-149">XML file with report data</span></span>

  - <span data-ttu-id="72408-150">CSV （逗號分隔）</span><span class="sxs-lookup"><span data-stu-id="72408-150">CSV (comma delimited)</span></span>

  - <span data-ttu-id="72408-151">Acrobat （PDF）檔案</span><span class="sxs-lookup"><span data-stu-id="72408-151">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="72408-152">MHTML （網頁檔案）</span><span class="sxs-lookup"><span data-stu-id="72408-152">MHTML (web archive)</span></span>

  - <span data-ttu-id="72408-153">Excel</span><span class="sxs-lookup"><span data-stu-id="72408-153">Excel</span></span>

  - <span data-ttu-id="72408-154">TIFF 檔案</span><span class="sxs-lookup"><span data-stu-id="72408-154">TIFF file</span></span>

  - <span data-ttu-id="72408-155">Word</span><span class="sxs-lookup"><span data-stu-id="72408-155">Word</span></span>

<span data-ttu-id="72408-156">選取格式之後，按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="72408-156">After selecting a format, click **Export**.</span></span> <span data-ttu-id="72408-157">當 [檔案**下載**] 對話方塊出現時，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="72408-157">When the **File Download** dialog box appears, click **Save**.</span></span> <span data-ttu-id="72408-158">在 [**另存**新檔] 對話方塊中，選取目的地資料夾，輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="72408-158">In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="72408-159">如果您已安裝 Microsoft OneNote，您也可以將報表資料複製到 OneNote。</span><span class="sxs-lookup"><span data-stu-id="72408-159">If you have Microsoft OneNote installed, you can also copy the report data to OneNote.</span></span> <span data-ttu-id="72408-160">若要這樣做，請以滑鼠右鍵按一下工具列上的 [**查看報表**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="72408-160">To do this, right-click the **View Report** button on the toolbar.</span></span> <span data-ttu-id="72408-161">在 [在**onenote 中選取位置**] 對話方塊中，選取 OneNote 中您要複製資料的區段，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="72408-161">In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

