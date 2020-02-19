---
title: Lync Server 2013： 使用監控報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3911b5007c422a636b09a934a4f80e00c60db53f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="dd89a-102">Lync Server 2013 中使用監控報告</span><span class="sxs-lookup"><span data-stu-id="dd89a-102">Using Monitoring Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd89a-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="dd89a-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="dd89a-104">Lync Server 2013 包含一組標準發佈的 Microsoft SQL Server Reporting Service 的報告。</span><span class="sxs-lookup"><span data-stu-id="dd89a-104">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="dd89a-105">這些可透過網頁瀏覽器存取的報告，會根據詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料庫中儲存的 CDR 和 QoE 記錄，提供使用情況、通話診斷資訊況及媒體品質資訊。</span><span class="sxs-lookup"><span data-stu-id="dd89a-105">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="dd89a-106">才能使用這些報告，您必須執行 SQL Server 執行個體的電腦上安裝監控報告。</span><span class="sxs-lookup"><span data-stu-id="dd89a-106">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd89a-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="dd89a-107">In This Section</span></span>

  - <span data-ttu-id="dd89a-108">[在 Lync Server 2013 中使用監控儀表板](lync-server-2013-using-the-monitoring-dashboard.md)   提供系統管理員其系統運作情況與系統使用狀況的快速概觀。</span><span class="sxs-lookup"><span data-stu-id="dd89a-108">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="dd89a-109">[Lync Server 2013 中的系統使用量報告](lync-server-2013-system-usage-reports.md)   提供 Lync Server 所收集的 CDR 資料為基礎的系統使用狀況資訊。</span><span class="sxs-lookup"><span data-stu-id="dd89a-109">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="dd89a-110">[Lync Server 2013 中 call Diagnostic Reports (per user)](lync-server-2013-call-diagnostic-reports-per-user.md)   提供每位使用者失敗的對等和會議工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="dd89a-110">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="dd89a-111">[Lync Server 2013 中通話診斷報告](lync-server-2013-call-diagnostic-reports.md)   失敗的對等和會議工作階段提供摘要資訊與診斷資料。</span><span class="sxs-lookup"><span data-stu-id="dd89a-111">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="dd89a-112">[Lync Server 2013 中的媒體品質診斷報告](lync-server-2013-media-quality-diagnostic-reports.md)   提供通話品質的相關資訊以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="dd89a-112">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="dd89a-113">找出記錄</span><span class="sxs-lookup"><span data-stu-id="dd89a-113">Locating Records</span></span>

<span data-ttu-id="dd89a-p102">監控報告每次只會在螢幕上顯示一小部分的記錄。螢幕上實際顯示的記錄數量會依報告而異。若要檢視螢幕上未顯示的記錄，可使用標準的上一頁和下一頁控制項 (在每份報告的工具列上) 來翻閱資料。您也可以快速跳至資料集的第一頁或最後一頁。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="dd89a-118">除了使用上一頁和下一頁控制項外，只要在 **[目前頁面]** 方塊中鍵入頁碼再按 ENTER 鍵，就可跳至資料集的任何一頁。</span><span class="sxs-lookup"><span data-stu-id="dd89a-118">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="dd89a-p103">除了翻閱資料的功能外，每份報告也提供有限的記錄尋找功能。若要依指定的值來尋找記錄，請在 **[尋找]** 方塊中鍵入指定值，然後按一下 **[尋找]**。接著報告即會開始搜尋資料，並會停在符合 **[尋找]** 方塊輸入值的第一筆記錄上，若要尋找下一筆符合搜尋條件的記錄，請按 **[下一筆]**。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="dd89a-p104">如前所述，監控報告只提供最基本的搜尋功能。例如，您無法指定要在哪一個欄位內搜尋值。此搜尋機制會自動在所有記錄的所有欄位中搜尋符合的值。搜尋中不能使用萬用字元，且每筆搜尋都會找出部分符合的結果。也就是說，如果您搜尋 111，將不只會找到數值 111，也會找到 11100、811、3112、611A5B 以及任何其他含有數值 111 的欄位 (無論出現在欄位的任何地方)。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="dd89a-p105">每份報告會顯示的記錄都是預先設定好的。例如，使用者註冊報告預設會顯示過去一星期使用者的註冊活動。某些情況下，這可能會導致報告沒有傳回任何結果。以這個案例來說，就代表過去一星期內沒有任何使用者註冊活動發生。若您看見「沒有結果符合報告篩選」訊息，請嘗試變更篩選值 (例如，將時間範圍從過去一星期改成過去一個月) 再重新查詢。如需詳細資訊，請參閱本主題稍後的＜篩選資料＞一節。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="dd89a-134">篩選資料</span><span class="sxs-lookup"><span data-stu-id="dd89a-134">Filtering Data</span></span>

<span data-ttu-id="dd89a-p106">有些時候您可能只想查看某一組子集的資料。例如，只看對等工作階段，而排除對等工作階段和會議工作階段兩者的資料。同樣地，也有些時候您需要減少傳回記錄的筆數。依預設，每份報告只能顯示資料集中的首 1,000 筆記錄。為因應這些情況，多半的報告都含有一些篩選的選項。例如，如果您只想檢視 2011 年 1 月 1 日到 2011 年 1 月 15 日之間的記錄，您可在 **[從]** 方塊中輸入 2011 年 1 月 1 日，然後在 **[到]** 方塊中輸入 2011 年 1 月 15 日。接著只要按一下 **[檢視報告]**，便只會傳回 2011 年 1 月 1 日到 2011 年 1 月 15 日之間所發生的活動。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="dd89a-p107">可用的篩選器依您檢視的報告而有所不同。如需特定報告的詳細資訊，請參閱該報告的說明主題。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="dd89a-144">匯出資料</span><span class="sxs-lookup"><span data-stu-id="dd89a-144">Exporting Data</span></span>

<span data-ttu-id="dd89a-p108">監控報告提供了至少兩種匯出報告內資料的方式。您可使用工具列 (在報告的最上方) 中的 **[匯出]** 選項。若要使用這個選項，請在 **[選取格式]** 下拉式清單中選取想要的匯入格式。共有下列幾種格式可選：</span><span class="sxs-lookup"><span data-stu-id="dd89a-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="dd89a-149">XML 檔附加報告資料</span><span class="sxs-lookup"><span data-stu-id="dd89a-149">XML file with report data</span></span>

  - <span data-ttu-id="dd89a-150">CSV (逗點分隔)</span><span class="sxs-lookup"><span data-stu-id="dd89a-150">CSV (comma delimited)</span></span>

  - <span data-ttu-id="dd89a-151">Acrobat (PDF) 檔</span><span class="sxs-lookup"><span data-stu-id="dd89a-151">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="dd89a-152">MHTML (網頁封存)</span><span class="sxs-lookup"><span data-stu-id="dd89a-152">MHTML (web archive)</span></span>

  - <span data-ttu-id="dd89a-153">Excel</span><span class="sxs-lookup"><span data-stu-id="dd89a-153">Excel</span></span>

  - <span data-ttu-id="dd89a-154">TIFF 檔</span><span class="sxs-lookup"><span data-stu-id="dd89a-154">TIFF file</span></span>

  - <span data-ttu-id="dd89a-155">Word</span><span class="sxs-lookup"><span data-stu-id="dd89a-155">Word</span></span>

<span data-ttu-id="dd89a-p109">格式選好後，按一下 [匯出]\*\*\*\*。[檔案下載]\*\*\*\* 對話方塊出現時，按一下 [儲存]\*\*\*\*。在 [另存新檔]\*\*\*\* 對話方塊中，選取一個目的資料夾，輸入檔案名稱，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="dd89a-p110">若有安裝 Microsoft OneNote，您也可複製報告資料到 OneNote。方法是以滑鼠右鍵按一下工具列上的 [檢視報告]\*\*\*\* 按鈕。接著在 [在 OneNote 中選擇位置]\*\*\*\* 對話方塊中選擇您要複製哪些位置的資料到 OneNote，最後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dd89a-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

