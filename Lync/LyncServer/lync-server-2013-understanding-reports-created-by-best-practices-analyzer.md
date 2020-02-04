---
title: Lync Server 2013：瞭解由最佳做法分析工具所建立的報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2262c490d84ec6f93ff395a9c8ec38d81c82e7de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="c4ee1-102">瞭解 Lync Server 2013 中由最佳做法分析工具所建立的報告</span><span class="sxs-lookup"><span data-stu-id="c4ee1-102">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4ee1-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="c4ee1-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="c4ee1-104">最佳做法分析工具提供多個組織類型，以協助分析及問題的解決。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-104">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues.</span></span> <span data-ttu-id="c4ee1-105">最佳做法分析程式會找出錯誤、警告及其他資訊等問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-105">Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="c4ee1-106">有關</span><span class="sxs-lookup"><span data-stu-id="c4ee1-106">Reports</span></span>

<span data-ttu-id="c4ee1-107">您可以透過查看下列每個報告來存取掃描結果：</span><span class="sxs-lookup"><span data-stu-id="c4ee1-107">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="c4ee1-108">**清單報告**   清單報告是依特定準則來組織。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-108">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="c4ee1-109">您可以依類別、嚴重性或問題來排列結果。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-109">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="c4ee1-110">例如，如果您依班級組織結果，則會將與主管相關的問題包含在報告的 [控制器] 區段底下。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-110">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="c4ee1-111">您可以查看所有問題，或只是資訊性專案。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-111">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="c4ee1-112">您可以搜尋特定專案（例如 [記憶體]）的清單報表。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-112">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="c4ee1-113">您也可以列印報表或將其匯出。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-113">You can also print the report or export it.</span></span>

  - <span data-ttu-id="c4ee1-114">**樹狀報表**   樹狀報表是由用來執行掃描的規則，以及在執行掃描時指定的其他選項所組成。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-114">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="c4ee1-115">例如，與測試拓撲規則相關的問題會包含在報告的 [測試拓撲] 區段底下。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-115">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="c4ee1-116">您可以查看所有問題的詳細資料，或只查看問題的摘要。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-116">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="c4ee1-117">您可以搜尋樹狀報表中的特定專案，例如 [記憶體]。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-117">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="c4ee1-118">您也可以列印報表或將其匯出。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-118">You can also print the report or export it.</span></span>

  - <span data-ttu-id="c4ee1-119">\*\*\*\*    其他報表中的其他報表專案，包括掃描中所包含的執行時間記錄。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-119">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="c4ee1-120">您可以在其他報表中搜尋特定專案的專案，例如 [記憶體]。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-120">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="c4ee1-121">您也可以列印報表或將其匯出。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-121">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="c4ee1-122">存在</span><span class="sxs-lookup"><span data-stu-id="c4ee1-122">Issues</span></span>

<span data-ttu-id="c4ee1-123">最佳做法分析程式所產生的報告，會指出在您的環境中發現的特定問題，包括下列類型的問題：</span><span class="sxs-lookup"><span data-stu-id="c4ee1-123">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="c4ee1-124">**錯誤**   需要您在環境中變更的重要問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-124">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="c4ee1-125">例如，如果未安裝 Lync Server 2013 核心元件，則會記錄錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-125">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>
    
    <span data-ttu-id="c4ee1-126">在報表中，會以紅色 X 符號來標識類別為錯誤的問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-126">Issues that are classified as errors are identified in the report by a red X symbol.</span></span> <span data-ttu-id="c4ee1-127">錯誤會顯示在 [**清單報告**] 視圖的 [**所有問題**] 索引標籤上，以及 [**詳細視圖**] 索引標籤和 [**樹狀報表**] 視圖的 [**摘要視圖**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-127">Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view.</span></span> <span data-ttu-id="c4ee1-128">如果您不想在報表中看到特定錯誤，您可以指定不會針對單一實例或報表中該錯誤的所有實例顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-128">If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report.</span></span> <span data-ttu-id="c4ee1-129">接著，除非您變更設定並指定要在報表中顯示錯誤，否則會在 [**其他報表**] 視圖的 [**隱藏專案**] 索引標籤上顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-129">The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="c4ee1-130">\*\*\*\*    與最佳做法實現不一致的警告問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-130">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="c4ee1-131">這可能會表示您的環境需要變更，也可能不需要。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-131">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="c4ee1-132">這個問題可能是您不需要變更之特定設定的已知問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-132">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="c4ee1-133">例如，未在伺服器上啟動的服務會記錄為警告。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-133">For example, services that are not started on a server are logged as warnings.</span></span>
    
    <span data-ttu-id="c4ee1-134">在報告中，會以三角形黃色警告符號來標識分類為警告的問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-134">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol.</span></span> <span data-ttu-id="c4ee1-135">警告會顯示在 [**清單報告**] 視圖的 [**所有問題**] 索引標籤上，以及 [**詳細視圖**] 索引標籤和 [**樹狀報表**] 視圖的 [**摘要視圖**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-135">Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view.</span></span> <span data-ttu-id="c4ee1-136">如果您不想在報表中看到特定錯誤，您可以指定不會針對單一實例或報表中該錯誤的所有實例顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-136">If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report.</span></span> <span data-ttu-id="c4ee1-137">然後，除非您變更設定並指定要在報表中顯示警告，否則將會在 [**其他報表**] 視圖的 [**隱藏專案**] 索引標籤上顯示警告。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-137">The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="c4ee1-138">**資訊**   包括所有未分類為錯誤或警告的問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-138">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="c4ee1-139">例如，Active Directory 網域服務中的 Lync Server 2013 標準版 server 物件數會分類為資訊問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-139">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>
    
    <span data-ttu-id="c4ee1-140">資訊問題會顯示在 [**清單報告**] 視圖的 [**所有問題**] 索引標籤上，以及 [**樹狀報表**] 視圖的 [**詳細**資料] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-140">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="c4ee1-141">Lync Server 2013，最佳做法分析工具不會變更您的環境以解決問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-141">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="c4ee1-142">[掃描] 只會偵測到可能的問題，並提供報告，其中包含如何解決每個問題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-142">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="c4ee1-143">如果您按一下某個問題，則會針對特定問題顯示說明及一些選項。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-143">If you click an issue, an explanation and some options are displayed for specific issues.</span></span> <span data-ttu-id="c4ee1-144">接著，您可以執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="c4ee1-144">Then, you can do any of the following:</span></span>

  - <span data-ttu-id="c4ee1-145">尋找問題的詳細資訊，以及解決問題的方法。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-145">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="c4ee1-146">停止顯示報表中的問題：</span><span class="sxs-lookup"><span data-stu-id="c4ee1-146">Stop showing issues in reports:</span></span>
    
      - <span data-ttu-id="c4ee1-147">停止顯示所選實例的問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-147">Stop showing issues for the selected instance.</span></span>
    
      - <span data-ttu-id="c4ee1-148">停止顯示該問題所有實例的相關問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-148">Stop showing issues for all instances of that issue.</span></span>
    
    <span data-ttu-id="c4ee1-149">若要查看您已停止顯示在報表中的問題，請移至 [**其他報表**] 視圖的 [**隱藏的專案**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-149">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view.</span></span> <span data-ttu-id="c4ee1-150">您可以在這裡指定再次開始顯示報表中的問題。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-150">From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="c4ee1-151">如需解決特定問題的詳細資料，請參閱[在 Lync Server 2013 中分析及解決最佳做法分析程式所識別的問題](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ee1-151">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

