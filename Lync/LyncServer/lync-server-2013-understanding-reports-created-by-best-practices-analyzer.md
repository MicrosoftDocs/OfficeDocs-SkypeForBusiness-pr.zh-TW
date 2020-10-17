---
title: Lync Server 2013：瞭解最佳做法分析器所建立的報告
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
ms.openlocfilehash: 24699e685b58c718f6b67306c1eaa2d6974c87c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527720"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="8fc59-102">瞭解 Lync Server 2013 中的最佳做法分析程式所建立的報告</span><span class="sxs-lookup"><span data-stu-id="8fc59-102">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fc59-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="8fc59-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="8fc59-p101">Best Practices Analyzer 提供多種報告類型，有助於分析及解決問題。Best Practices Analyzer 會識別錯誤、警告及其他資訊等問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-p101">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues. Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="8fc59-106">報告</span><span class="sxs-lookup"><span data-stu-id="8fc59-106">Reports</span></span>

<span data-ttu-id="8fc59-107">您可以檢視下列每個報告來存取掃描結果：</span><span class="sxs-lookup"><span data-stu-id="8fc59-107">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="8fc59-108">**清單報告**    清單報表依特定準則進行組織。</span><span class="sxs-lookup"><span data-stu-id="8fc59-108">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="8fc59-109">您可以依類別、嚴重性或問題來排列結果。</span><span class="sxs-lookup"><span data-stu-id="8fc59-109">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="8fc59-110">例如，如果您依類別來組織結果，與 Director 相關的問題就會包含在報告的 Director 區段底下。</span><span class="sxs-lookup"><span data-stu-id="8fc59-110">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="8fc59-111">您可以檢視所有問題，或只檢視參考項目。</span><span class="sxs-lookup"><span data-stu-id="8fc59-111">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="8fc59-112">您可以在清單報告中搜尋特定項目，例如記憶體。</span><span class="sxs-lookup"><span data-stu-id="8fc59-112">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="8fc59-113">您也可以列印報告或將它匯出。</span><span class="sxs-lookup"><span data-stu-id="8fc59-113">You can also print the report or export it.</span></span>

  - <span data-ttu-id="8fc59-114">**樹報表**    樹狀報表是以執行掃描時所用的規則來組織，另一種是在執行掃描時指定的其他選項。</span><span class="sxs-lookup"><span data-stu-id="8fc59-114">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="8fc59-115">例如，與測試拓撲規則相關的問題會包含在報告的測試拓撲區段底下。</span><span class="sxs-lookup"><span data-stu-id="8fc59-115">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="8fc59-116">您可以檢視所有問題的詳細資訊，或只檢視問題的摘要。</span><span class="sxs-lookup"><span data-stu-id="8fc59-116">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="8fc59-117">您可以在樹狀報告中搜尋特定項目，例如記憶體。</span><span class="sxs-lookup"><span data-stu-id="8fc59-117">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="8fc59-118">您也可以列印報告或將它匯出。</span><span class="sxs-lookup"><span data-stu-id="8fc59-118">You can also print the report or export it.</span></span>

  - <span data-ttu-id="8fc59-119">**其他報告**    其他報告中的專案包含掃描中所包含之工作的執行時間記錄。</span><span class="sxs-lookup"><span data-stu-id="8fc59-119">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="8fc59-120">您可以在其他報告中搜尋特定項目，例如記憶體。</span><span class="sxs-lookup"><span data-stu-id="8fc59-120">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="8fc59-121">您也可以列印報告或將它匯出。</span><span class="sxs-lookup"><span data-stu-id="8fc59-121">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="8fc59-122">問題</span><span class="sxs-lookup"><span data-stu-id="8fc59-122">Issues</span></span>

<span data-ttu-id="8fc59-123">Best Practices Analyzer 所產生的報告會指出在掃描環境期間識別的特定問題，包括下列類型的問題：</span><span class="sxs-lookup"><span data-stu-id="8fc59-123">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="8fc59-124">**錯誤**    需要您在環境中進行變更的重大問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-124">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="8fc59-125">例如，如果未安裝 Lync Server 2013 核心元件，則會記錄錯誤。</span><span class="sxs-lookup"><span data-stu-id="8fc59-125">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>

    <span data-ttu-id="8fc59-p106">報告中會以紅色 X 符號來識別分類為錯誤的問題。錯誤會顯示在 [清單報告]\*\*\*\* 檢視的 [所有問題]\*\*\*\* 索引標籤上，以及 [樹狀報告]\*\*\*\* 檢視的 [詳細檢視]\*\*\*\* 索引標籤或 [摘要檢視]\*\*\*\* 索引標籤上。如果您不想在報告中看到特定錯誤，可以指定不要在報告中顯示該錯誤的單一執行個體或所有執行個體。該錯誤就只會顯示在 [其他報告]\*\*\*\* 檢視的 [隱藏項目]\*\*\*\* 索引標籤上，除非您變更設定，並指定在報告中顯示該錯誤。</span><span class="sxs-lookup"><span data-stu-id="8fc59-p106">Issues that are classified as errors are identified in the report by a red X symbol. Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="8fc59-130">**警告**    與最佳作法的實施不一致的問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-130">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="8fc59-131">這不一定表示需要在環境中進行變更。</span><span class="sxs-lookup"><span data-stu-id="8fc59-131">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="8fc59-132">此問題可能是不需要變更之特定設定的已知問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-132">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="8fc59-133">例如，未在伺服器上啟動的服務就會記錄為警告。</span><span class="sxs-lookup"><span data-stu-id="8fc59-133">For example, services that are not started on a server are logged as warnings.</span></span>

    <span data-ttu-id="8fc59-p108">報告中會以黃色三角形的警告符號來識別分類為警告的問題。警告會顯示在 [清單報告]\*\*\*\* 檢視的 [所有問題]\*\*\*\* 索引標籤上，以及 [樹狀報告]\*\*\*\* 檢視的 [詳細檢視]\*\*\*\* 索引標籤或 [摘要檢視]\*\*\*\* 索引標籤上。如果您不想在報告中看到特定錯誤，可以指定不要在報告中顯示該錯誤的單一執行個體或所有執行個體。該警告就只會顯示在 [其他報告]\*\*\*\* 檢視的 [隱藏項目]\*\*\*\* 索引標籤上，除非您變更設定，並指定在報告中顯示該警告。</span><span class="sxs-lookup"><span data-stu-id="8fc59-p108">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol. Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="8fc59-138">**資訊**    包括所有未分類為錯誤或警告的問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-138">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="8fc59-139">例如，Active Directory 網域服務中的 Lync Server 2013 Standard Edition server 物件數目會分類為資訊問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-139">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>

    <span data-ttu-id="8fc59-140">資訊問題會顯示在 [清單報告]\*\*\*\* 檢視的 [所有問題]\*\*\*\* 索引標籤上，以及 [樹狀報告]\*\*\*\* 檢視的 [詳細檢視] \*\*\*\* 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="8fc59-140">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="8fc59-141">Lync Server 2013，最佳做法分析器不會變更您的環境以解決問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-141">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="8fc59-142">掃描只會偵測潛在問題，並提供包含如何解決各問題的相關資訊報告。</span><span class="sxs-lookup"><span data-stu-id="8fc59-142">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="8fc59-p111">當您按一下問題，就會顯示特定問題的說明和某些選項。然後，您可以執行下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="8fc59-p111">If you click an issue, an explanation and some options are displayed for specific issues. Then, you can do any of the following:</span></span>

  - <span data-ttu-id="8fc59-145">尋找有關該問題以及如何解決的更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8fc59-145">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="8fc59-146">停止在報告中顯示問題：</span><span class="sxs-lookup"><span data-stu-id="8fc59-146">Stop showing issues in reports:</span></span>

      - <span data-ttu-id="8fc59-147">停止顯示選定執行個體的問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-147">Stop showing issues for the selected instance.</span></span>

      - <span data-ttu-id="8fc59-148">停止顯示該問題所有執行個體的問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-148">Stop showing issues for all instances of that issue.</span></span>

    <span data-ttu-id="8fc59-p112">若要顯示您已在報告中停止顯示的問題，請前往 [其他報告]\*\*\*\* 檢視的 [隱藏項目]\*\*\*\* 索引標籤。您可以從那裡指定在報告中重新開始顯示問題。</span><span class="sxs-lookup"><span data-stu-id="8fc59-p112">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view. From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="8fc59-151">如需解決特定問題的詳細資訊，請參閱 [分析和解決 Lync Server 2013 中的最佳做法分析程式所識別的問題](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="8fc59-151">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
