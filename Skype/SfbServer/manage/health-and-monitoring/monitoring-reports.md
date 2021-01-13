---
title: 在商務用 Skype Server 中使用監控報告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 摘要：瞭解如何在商務用 Skype Server 中監控報告。
ms.openlocfilehash: 32e16d02f458ca36fb18b52790966c68a354503e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827763"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a><span data-ttu-id="4e134-103">在商務用 Skype Server 中使用監控報告</span><span class="sxs-lookup"><span data-stu-id="4e134-103">Using Monitoring Reports in Skype for Business Server</span></span> 
 
<span data-ttu-id="4e134-104">**摘要：** 深入瞭解商務用 Skype Server 中的監控報告。</span><span class="sxs-lookup"><span data-stu-id="4e134-104">**Summary:** Learn about Monitoring Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="4e134-105">商務用 Skype 伺服器包含一組 Microsoft SQL Server Reporting Service 所發佈的標準報告。</span><span class="sxs-lookup"><span data-stu-id="4e134-105">Skype for Business Server includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="4e134-106">這些可透過網頁瀏覽器存取的報告，會根據詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料庫中儲存的 CDR 和 QoE 記錄，提供使用情況、通話診斷資訊況及媒體品質資訊。</span><span class="sxs-lookup"><span data-stu-id="4e134-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>
  
<span data-ttu-id="4e134-107">若要使用這些報告，您必須在執行 SQL Server 實例的電腦上安裝監控報告。</span><span class="sxs-lookup"><span data-stu-id="4e134-107">To use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="4e134-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4e134-108">In This Section</span></span>

- <span data-ttu-id="4e134-109">[在商務用 Skype Server 中使用監控儀表板](monitoring-dashboard.md) 為系統管理員提供系統健康情況和系統使用狀況的快速綜述。</span><span class="sxs-lookup"><span data-stu-id="4e134-109">[Using the Monitoring Dashboard in Skype for Business Server](monitoring-dashboard.md) Provides administrators with a quick overview of their system health and system usage.</span></span>
    
- <span data-ttu-id="4e134-110">[商務用 Skype Server 中的系統使用狀況報告](system-usage-reports.md) 提供以商務用 Skype Server 所收集的 CDR 資料為基礎的系統使用狀況資訊。</span><span class="sxs-lookup"><span data-stu-id="4e134-110">[System usage reports in Skype for Business Server](system-usage-reports.md) Provides system usage information based on CDR data collected by Skype for Business Server.</span></span>
    
- <span data-ttu-id="4e134-111">[在商務用 Skype Server 中 (每位使用者) 的通話診斷報告](call-diagnostic-reports-per-user.md) 提供失敗的對等和會議會話的每一使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4e134-111">[Call Diagnostic Reports (per user) in Skype for Business Server](call-diagnostic-reports-per-user.md) Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="4e134-112">[在商務用 Skype Server 中通話診斷報告](call-diagnostic-reports.md) 提供失敗的對等和會議會話的摘要資訊和診斷資料。</span><span class="sxs-lookup"><span data-stu-id="4e134-112">[Call Diagnostic Reports in Skype for Business Server](call-diagnostic-reports.md) Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="4e134-113">[商務用 Skype Server 中的媒體質量診斷報告](media-quality-diagnostic-reports.md) 提供通話品質的相關資訊，以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="4e134-113">[Media Quality Diagnostic Reports in Skype for Business Server](media-quality-diagnostic-reports.md) Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>
    
## <a name="locating-records"></a><span data-ttu-id="4e134-114">找出記錄</span><span class="sxs-lookup"><span data-stu-id="4e134-114">Locating Records</span></span>

<span data-ttu-id="4e134-115">監控報告每次只會在螢幕上顯示一小部分的記錄。</span><span class="sxs-lookup"><span data-stu-id="4e134-115">Monitoring Reports only show a limited number of records on the screen at any one time.</span></span> <span data-ttu-id="4e134-116">螢幕上實際顯示的記錄數量會依報告而異。</span><span class="sxs-lookup"><span data-stu-id="4e134-116">The actual number of records displayed on a screen varies depending on the report.</span></span> <span data-ttu-id="4e134-117">若要查看目前未顯示在螢幕上的記錄，您可以使用每個報告的) 工具列上的標準向前及向後控制 (，讓您能夠逐頁查看資料。</span><span class="sxs-lookup"><span data-stu-id="4e134-117">To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report's toolbar) that enable you to page through the data.</span></span> <span data-ttu-id="4e134-118">您也可以快速跳至資料集的第一頁或最後一頁。</span><span class="sxs-lookup"><span data-stu-id="4e134-118">You can also quickly jump to the first page or the last page of the dataset.</span></span>
  
<span data-ttu-id="4e134-119">除了使用上一頁和下一頁控制項外，只要在 **[目前頁面]** 方塊中鍵入頁碼再按 ENTER 鍵，就可跳至資料集的任何一頁。</span><span class="sxs-lookup"><span data-stu-id="4e134-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>
  
<span data-ttu-id="4e134-p103">除了翻閱資料的功能外，每份報告也提供有限的記錄尋找功能。若要依指定的值來尋找記錄，請在 **[尋找]** 方塊中鍵入指定值，然後按一下 **[尋找]**。接著報告即會開始搜尋資料，並會停在符合 **[尋找]** 方塊輸入值的第一筆記錄上，若要尋找下一筆符合搜尋條件的記錄，請按 **[下一筆]**。</span><span class="sxs-lookup"><span data-stu-id="4e134-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>
  
<span data-ttu-id="4e134-p104">如前所述，監控報告只提供最基本的搜尋功能。例如，您無法指定要在哪一個欄位內搜尋值。此搜尋機制會自動在所有記錄的所有欄位中搜尋符合的值。搜尋中不能使用萬用字元，且每筆搜尋都會找出部分符合的結果。也就是說，如果您搜尋 111，將不只會找到數值 111，也會找到 11100、811、3112、611A5B 以及任何其他含有數值 111 的欄位 (無論出現在欄位的任何地方)。</span><span class="sxs-lookup"><span data-stu-id="4e134-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>
  
<span data-ttu-id="4e134-129">每份報告會顯示的記錄都是預先設定好的。</span><span class="sxs-lookup"><span data-stu-id="4e134-129">Each report is configured to show a default set of records.</span></span> <span data-ttu-id="4e134-130">例如，使用者註冊報告預設會顯示過去一星期使用者的註冊活動。</span><span class="sxs-lookup"><span data-stu-id="4e134-130">For example, by default the User Registration Report shows user registration activities for the past week.</span></span> <span data-ttu-id="4e134-131">某些情況下，這可能會導致報告沒有傳回任何結果。</span><span class="sxs-lookup"><span data-stu-id="4e134-131">In some cases, this might result in a report that returns no records.</span></span> <span data-ttu-id="4e134-132">以這個案例來說，就代表過去一星期內沒有任何使用者註冊活動發生。</span><span class="sxs-lookup"><span data-stu-id="4e134-132">In this case, it means that no user registrations have taken place in the past week.</span></span> <span data-ttu-id="4e134-133">如果您看到「沒有結果符合報表篩選」的訊息，請嘗試變更篩選值 (例如，將時段變更為過去的月份，而不是過去一周) 然後重新執行查詢。</span><span class="sxs-lookup"><span data-stu-id="4e134-133">If you see the message "No results match the report filters," try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query.</span></span> <span data-ttu-id="4e134-134">如需詳細資訊，請參閱本主題稍後的＜篩選資料＞一節。</span><span class="sxs-lookup"><span data-stu-id="4e134-134">For details, see the "Filtering Data" section later in this topic.</span></span>
  
## <a name="filtering-data"></a><span data-ttu-id="4e134-135">篩選資料</span><span class="sxs-lookup"><span data-stu-id="4e134-135">Filtering Data</span></span>

<span data-ttu-id="4e134-p106">有些時候您可能只想查看某一組子集的資料。例如，只看對等工作階段，而排除對等工作階段和會議工作階段兩者的資料。同樣地，也有些時候您需要減少傳回記錄的筆數。依預設，每份報告只能顯示資料集中的首 1,000 筆記錄。為因應這些情況，多半的報告都含有一些篩選的選項。例如，如果您只想檢視 2011 年 1 月 1 日到 2011 年 1 月 15 日之間的記錄，您可在 **[從]** 方塊中輸入 2011 年 1 月 1 日，然後在 **[到]** 方塊中輸入 2011 年 1 月 15 日。接著只要按一下 **[檢視報告]**，便只會傳回 2011 年 1 月 1 日到 2011 年 1 月 15 日之間所發生的活動。</span><span class="sxs-lookup"><span data-stu-id="4e134-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>
  
<span data-ttu-id="4e134-p107">可用的篩選器依您檢視的報告而有所不同。如需特定報告的詳細資訊，請參閱該報告的說明主題。</span><span class="sxs-lookup"><span data-stu-id="4e134-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>
  
## <a name="exporting-data"></a><span data-ttu-id="4e134-145">匯出資料</span><span class="sxs-lookup"><span data-stu-id="4e134-145">Exporting Data</span></span>

<span data-ttu-id="4e134-p108">監控報告提供了至少兩種匯出報告內資料的方式。您可使用工具列 (在報告的最上方) 中的 **[匯出]** 選項。若要使用這個選項，請在 **[選取格式]** 下拉式清單中選取想要的匯入格式。共有下列幾種格式可選：</span><span class="sxs-lookup"><span data-stu-id="4e134-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>
  
- <span data-ttu-id="4e134-150">XML 檔附加報告資料</span><span class="sxs-lookup"><span data-stu-id="4e134-150">XML file with report data</span></span>
    
- <span data-ttu-id="4e134-151">CSV (逗點分隔)</span><span class="sxs-lookup"><span data-stu-id="4e134-151">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="4e134-152">Acrobat (PDF) 檔</span><span class="sxs-lookup"><span data-stu-id="4e134-152">Acrobat (PDF) file</span></span>
    
- <span data-ttu-id="4e134-153">MHTML (網頁封存)</span><span class="sxs-lookup"><span data-stu-id="4e134-153">MHTML (web archive)</span></span>
    
- <span data-ttu-id="4e134-154">Excel</span><span class="sxs-lookup"><span data-stu-id="4e134-154">Excel</span></span>
    
- <span data-ttu-id="4e134-155">TIFF 檔</span><span class="sxs-lookup"><span data-stu-id="4e134-155">TIFF file</span></span>
    
- <span data-ttu-id="4e134-156">Word</span><span class="sxs-lookup"><span data-stu-id="4e134-156">Word</span></span>
    
<span data-ttu-id="4e134-p109">格式選好後，按一下 [匯出]。[檔案下載] 對話方塊出現時，按一下 [儲存]。在 [另存新檔] 對話方塊中，選取一個目的資料夾，輸入檔案名稱，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4e134-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>
  
<span data-ttu-id="4e134-p110">若有安裝 Microsoft OneNote，您也可複製報告資料到 OneNote。方法是以滑鼠右鍵按一下工具列上的 [檢視報告] 按鈕。接著在 [在 OneNote 中選擇位置] 對話方塊中選擇您要複製哪些位置的資料到 OneNote，最後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="4e134-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>
  

