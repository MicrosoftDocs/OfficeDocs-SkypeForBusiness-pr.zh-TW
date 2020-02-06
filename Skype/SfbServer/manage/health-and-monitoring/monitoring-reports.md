---
title: 在商務用 Skype Server 中使用監視報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 摘要：瞭解在商務用 Skype Server 中監控報表的相關資訊。
ms.openlocfilehash: 1468a012501753a720807f1b1ec609ff187ffc1c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817802"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a><span data-ttu-id="add1a-103">在商務用 Skype Server 中使用監視報告</span><span class="sxs-lookup"><span data-stu-id="add1a-103">Using Monitoring Reports in Skype for Business Server</span></span> 
 
<span data-ttu-id="add1a-104">**摘要：** 瞭解如何在商務用 Skype Server 中監控報告。</span><span class="sxs-lookup"><span data-stu-id="add1a-104">**Summary:** Learn about Monitoring Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="add1a-105">商務用 Skype Server 包含一組由 Microsoft SQL Server Reporting Services 發佈的標準報告。</span><span class="sxs-lookup"><span data-stu-id="add1a-105">Skype for Business Server includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="add1a-106">這些報表可透過網頁瀏覽器存取，提供使用方式、呼叫診斷資訊和媒體質量資訊，所有這些都是以呼叫詳細資料錄製（CDR）以及儲存在 CDR 和 QoE 資料庫的體驗品質（QoE）記錄為基礎。</span><span class="sxs-lookup"><span data-stu-id="add1a-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>
  
<span data-ttu-id="add1a-107">若要使用這些報告，您必須在執行 SQL Server 實例的電腦上安裝 [監視報告]。</span><span class="sxs-lookup"><span data-stu-id="add1a-107">To use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="add1a-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="add1a-108">In This Section</span></span>

- <span data-ttu-id="add1a-109">[在商務用 Skype 伺服器中使用監視儀表板](monitoring-dashboard.md)為管理員提供系統健康情況與系統使用量的快速概覽。</span><span class="sxs-lookup"><span data-stu-id="add1a-109">[Using the Monitoring Dashboard in Skype for Business Server](monitoring-dashboard.md) Provides administrators with a quick overview of their system health and system usage.</span></span>
    
- <span data-ttu-id="add1a-110">[商務用 Skype Server 中的系統使用量報告](system-usage-reports.md)根據商務用 Skype Server 所收集的 CDR 資料，提供系統使用量資訊。</span><span class="sxs-lookup"><span data-stu-id="add1a-110">[System usage reports in Skype for Business Server](system-usage-reports.md) Provides system usage information based on CDR data collected by Skype for Business Server.</span></span>
    
- <span data-ttu-id="add1a-111">[在商務用 Skype Server 中呼叫診斷報告（每位使用者）](call-diagnostic-reports-per-user.md)提供針對點對點與會議會話失敗的每個使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="add1a-111">[Call Diagnostic Reports (per user) in Skype for Business Server](call-diagnostic-reports-per-user.md) Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="add1a-112">[在商務用 Skype Server 中呼叫診斷報告](call-diagnostic-reports.md)提供失敗的對等與會議會話的摘要資訊與診斷資料。</span><span class="sxs-lookup"><span data-stu-id="add1a-112">[Call Diagnostic Reports in Skype for Business Server](call-diagnostic-reports.md) Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="add1a-113">[商務用 Skype Server 中的媒體質量診斷報告](media-quality-diagnostic-reports.md)提供通話品質的相關資訊，以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="add1a-113">[Media Quality Diagnostic Reports in Skype for Business Server](media-quality-diagnostic-reports.md) Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>
    
## <a name="locating-records"></a><span data-ttu-id="add1a-114">尋找記錄</span><span class="sxs-lookup"><span data-stu-id="add1a-114">Locating Records</span></span>

<span data-ttu-id="add1a-115">監視報告只會在任何時間顯示畫面上有限數量的記錄。</span><span class="sxs-lookup"><span data-stu-id="add1a-115">Monitoring Reports only show a limited number of records on the screen at any one time.</span></span> <span data-ttu-id="add1a-116">顯示在螢幕上的實際記錄數會依報表而有所不同。</span><span class="sxs-lookup"><span data-stu-id="add1a-116">The actual number of records displayed on a screen varies depending on the report.</span></span> <span data-ttu-id="add1a-117">若要查看目前未顯示在螢幕上的記錄，您可以使用 [標準前向] 和 [向後] 控制（可在每個報表的工具列上找到），讓您可以分頁流覽資料。</span><span class="sxs-lookup"><span data-stu-id="add1a-117">To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report's toolbar) that enable you to page through the data.</span></span> <span data-ttu-id="add1a-118">您也可以快速跳至資料集的第一頁或最後一頁。</span><span class="sxs-lookup"><span data-stu-id="add1a-118">You can also quickly jump to the first page or the last page of the dataset.</span></span>
  
<span data-ttu-id="add1a-119">除了使用向前和向後控制項之外，您也可以直接在 [**目前頁面**] 方塊中輸入頁碼，然後按 enter 鍵，跳至資料集中的任何頁面。</span><span class="sxs-lookup"><span data-stu-id="add1a-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>
  
<span data-ttu-id="add1a-120">除了提供頁面流覽資料的功能之外，每個報告也包含尋找記錄的有限能力。</span><span class="sxs-lookup"><span data-stu-id="add1a-120">In addition to providing the ability to page through the data, each report also includes the limited ability to find records.</span></span> <span data-ttu-id="add1a-121">若要尋找以特定值為基礎的記錄，請在 [**尋找**] 方塊中輸入該值，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="add1a-121">To find records based on a given value, type that value into the **Find** box, and then click **Find**.</span></span> <span data-ttu-id="add1a-122">報告會開始搜尋資料，並停止在您在 [**尋找**] 方塊中輸入之值的第一個實例。</span><span class="sxs-lookup"><span data-stu-id="add1a-122">The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box.</span></span> <span data-ttu-id="add1a-123">若要尋找符合搜尋準則的下一筆記錄，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="add1a-123">To find the next record that meets the search criteria, click **Next**.</span></span>
  
<span data-ttu-id="add1a-124">如所述，監視報告只提供最基本的搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="add1a-124">As noted, the Monitoring Reports provide only the most basic search functions.</span></span> <span data-ttu-id="add1a-125">例如，您無法指定應該在哪個欄位中找到值。</span><span class="sxs-lookup"><span data-stu-id="add1a-125">For example, you cannot specify which field the value should be found in.</span></span> <span data-ttu-id="add1a-126">[搜尋] 機制會自動在每一筆記錄的每個欄位中搜尋相符的值。</span><span class="sxs-lookup"><span data-stu-id="add1a-126">The search mechanism automatically searches for matching values in every field in every record.</span></span> <span data-ttu-id="add1a-127">您無法在搜尋中使用萬用字元，且所有搜尋都會尋找部分值。</span><span class="sxs-lookup"><span data-stu-id="add1a-127">You cannot use wildcards in your searches, and all searches look for partial values.</span></span> <span data-ttu-id="add1a-128">如此一來，如果您搜尋111，搜尋會傳回值111，以及在該欄位內任何位置都包含 value 3112 的值11100、811、111、611A5B 及任何其他欄位。</span><span class="sxs-lookup"><span data-stu-id="add1a-128">That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>
  
<span data-ttu-id="add1a-129">每個報告都設定為顯示一組預設的記錄。</span><span class="sxs-lookup"><span data-stu-id="add1a-129">Each report is configured to show a default set of records.</span></span> <span data-ttu-id="add1a-130">例如，根據預設，[使用者註冊] 報告會顯示上周的使用者註冊活動。</span><span class="sxs-lookup"><span data-stu-id="add1a-130">For example, by default the User Registration Report shows user registration activities for the past week.</span></span> <span data-ttu-id="add1a-131">在某些情況下，這可能會導致不會傳回任何記錄的報表。</span><span class="sxs-lookup"><span data-stu-id="add1a-131">In some cases, this might result in a report that returns no records.</span></span> <span data-ttu-id="add1a-132">在這種情況下，這表示上周不會發生任何使用者註冊。</span><span class="sxs-lookup"><span data-stu-id="add1a-132">In this case, it means that no user registrations have taken place in the past week.</span></span> <span data-ttu-id="add1a-133">如果您看到「沒有結果符合報表篩選」的訊息，請嘗試變更篩選值（例如，將時段變更為 [上個月]，而非上周），然後重新執行查詢。</span><span class="sxs-lookup"><span data-stu-id="add1a-133">If you see the message "No results match the report filters," try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query.</span></span> <span data-ttu-id="add1a-134">如需詳細資訊，請參閱本主題稍後的「篩選資料」一節。</span><span class="sxs-lookup"><span data-stu-id="add1a-134">For details, see the "Filtering Data" section later in this topic.</span></span>
  
## <a name="filtering-data"></a><span data-ttu-id="add1a-135">篩選資料</span><span class="sxs-lookup"><span data-stu-id="add1a-135">Filtering Data</span></span>

<span data-ttu-id="add1a-136">有時候，您可能會想要只查看記錄的子集。</span><span class="sxs-lookup"><span data-stu-id="add1a-136">There will likely be times when you want to look at only a subset of records.</span></span> <span data-ttu-id="add1a-137">例如，只有點對點工作階段，而不是點對點工作階段與會議會話。</span><span class="sxs-lookup"><span data-stu-id="add1a-137">For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="add1a-138">同樣地，您也需要減少傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="add1a-138">Likewise, there will be times when you need to reduce the number of records that are returned.</span></span> <span data-ttu-id="add1a-139">根據預設，報告只能顯示資料集中的前1000筆記錄。</span><span class="sxs-lookup"><span data-stu-id="add1a-139">By default, a report can only display the first 1,000 records in a data set.</span></span> <span data-ttu-id="add1a-140">為了解決這些問題，大多數報表都包含許多篩選選項。</span><span class="sxs-lookup"><span data-stu-id="add1a-140">To address these issues, most reports include a number of filtering options.</span></span> <span data-ttu-id="add1a-141">例如，如果您只想要查看2011年1月1日到2011日的記錄，您可以在 [收件者] 方塊中輸入 [年1月 2011 1 日]，在 **[收\*\*\*\*件**者] 方塊中輸入1月 2011 15 日。</span><span class="sxs-lookup"><span data-stu-id="add1a-141">For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box.</span></span> <span data-ttu-id="add1a-142">如果您接著按一下 [**查看報表**]，則傳回的資料會限制在2011年1月1日到2011年1月15日之間發生的活動。</span><span class="sxs-lookup"><span data-stu-id="add1a-142">If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>
  
<span data-ttu-id="add1a-143">您可使用的篩選依據您所查看的報表而有所不同。</span><span class="sxs-lookup"><span data-stu-id="add1a-143">The filters available to you vary depending on the report that you are viewing.</span></span> <span data-ttu-id="add1a-144">如需特定報告的詳細資訊，請參閱該報告的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="add1a-144">For details about a specific report, see the help topic for that report.</span></span>
  
## <a name="exporting-data"></a><span data-ttu-id="add1a-145">匯出資料</span><span class="sxs-lookup"><span data-stu-id="add1a-145">Exporting Data</span></span>

<span data-ttu-id="add1a-146">[監視報告] 提供至少兩種不同的方式來匯出報表中包含的資料。</span><span class="sxs-lookup"><span data-stu-id="add1a-146">The Monitoring Reports provide at least two different ways to export the data included in a report.</span></span> <span data-ttu-id="add1a-147">您可以在每個報告頂端出現的工具列中，使用 [**匯出**] 選項。</span><span class="sxs-lookup"><span data-stu-id="add1a-147">You can use the **Export** option in the toolbar that appears at the top of each report.</span></span> <span data-ttu-id="add1a-148">若要使用此選項，請從 [**選取格式**] 下拉式清單中選取所要的匯出格式。</span><span class="sxs-lookup"><span data-stu-id="add1a-148">To use this option, select the desired export format from the **Select a format** drop-down list.</span></span> <span data-ttu-id="add1a-149">您可以使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="add1a-149">The following formats are available to you:</span></span>
  
- <span data-ttu-id="add1a-150">含報表資料的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="add1a-150">XML file with report data</span></span>
    
- <span data-ttu-id="add1a-151">CSV （逗號分隔）</span><span class="sxs-lookup"><span data-stu-id="add1a-151">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="add1a-152">Acrobat （PDF）檔案</span><span class="sxs-lookup"><span data-stu-id="add1a-152">Acrobat (PDF) file</span></span>
    
- <span data-ttu-id="add1a-153">MHTML （網頁檔案）</span><span class="sxs-lookup"><span data-stu-id="add1a-153">MHTML (web archive)</span></span>
    
- <span data-ttu-id="add1a-154">Excel</span><span class="sxs-lookup"><span data-stu-id="add1a-154">Excel</span></span>
    
- <span data-ttu-id="add1a-155">TIFF 檔案</span><span class="sxs-lookup"><span data-stu-id="add1a-155">TIFF file</span></span>
    
- <span data-ttu-id="add1a-156">Word</span><span class="sxs-lookup"><span data-stu-id="add1a-156">Word</span></span>
    
<span data-ttu-id="add1a-157">選取格式之後，按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="add1a-157">After selecting a format, click **Export**.</span></span> <span data-ttu-id="add1a-158">當 [檔案**下載**] 對話方塊出現時，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="add1a-158">When the **File Download** dialog box appears, click **Save**.</span></span> <span data-ttu-id="add1a-159">在 [**另存**新檔] 對話方塊中，選取目的地資料夾，輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="add1a-159">In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>
  
<span data-ttu-id="add1a-160">如果您已安裝 Microsoft OneNote，您也可以將報表資料複製到 OneNote。</span><span class="sxs-lookup"><span data-stu-id="add1a-160">If you have Microsoft OneNote installed, you can also copy the report data to OneNote.</span></span> <span data-ttu-id="add1a-161">若要這樣做，請以滑鼠右鍵按一下工具列上的 [**查看報表**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="add1a-161">To do this, right-click the **View Report** button on the toolbar.</span></span> <span data-ttu-id="add1a-162">在 [在**onenote 中選取位置**] 對話方塊中，選取 OneNote 中您要複製資料的區段，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="add1a-162">In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>
  

