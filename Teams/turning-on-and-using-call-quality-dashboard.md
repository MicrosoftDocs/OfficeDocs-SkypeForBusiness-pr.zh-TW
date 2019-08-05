---
title: 開啟並使用通話品質儀表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: '瞭解如何開啟並使用商務用 Skype Online 的通話品質儀表板, 並取得通話品質的摘要報告。 '
ms.openlocfilehash: a4fc0875e9c9672a53f6399aac344285b070855a
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183708"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="b7234-103">開啟並使用 Microsoft 團隊及商務用 Skype Online 的通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="b7234-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="b7234-104">瞭解如何設定您的 Office 365 組織, 以使用通話品質儀表板來監控通話品質。</span><span class="sxs-lookup"><span data-stu-id="b7234-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="b7234-105">Microsoft 團隊和商務用 Skype Online 的通話品質儀表板 (CQD) 可讓您深入瞭解使用 Microsoft 團隊和商務用 Skype 服務所進行的通話品質。</span><span class="sxs-lookup"><span data-stu-id="b7234-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="b7234-106">本主題描述開始收集資料所需完成的步驟。</span><span class="sxs-lookup"><span data-stu-id="b7234-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="b7234-107">最新變更與更新</span><span class="sxs-lookup"><span data-stu-id="b7234-107">Latest changes and updates</span></span>

<span data-ttu-id="b7234-108">最近的 CQD 變更如下所示:</span><span class="sxs-lookup"><span data-stu-id="b7234-108">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="b7234-109">包括 Microsoft 團隊資料 (除了商務用 Skype Online 資料之外)。</span><span class="sxs-lookup"><span data-stu-id="b7234-109">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="b7234-110">摘要報告包含 [產品] 篩選器, 可供您選取 [所有資料]、[Microsoft 團隊資料] 或 [商務用 Skype Online] 資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-110">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="b7234-111">已更新視頻與 VBSS 資料流程品質分類邏輯。</span><span class="sxs-lookup"><span data-stu-id="b7234-111">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="b7234-112">請參閱[通話品質儀表板中的資料流程分類](stream-classification-in-call-quality-dashboard.md), 以取得最新的分類器定義。</span><span class="sxs-lookup"><span data-stu-id="b7234-112">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="b7234-113">請參閱這篇文章, 以取得[通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)的清單。</span><span class="sxs-lookup"><span data-stu-id="b7234-113">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7234-114">您可以按一下 [**好消息**] 中的連結, 找到有關儀表板更新和變更的資訊!</span><span class="sxs-lookup"><span data-stu-id="b7234-114">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="b7234-115">顯示在儀表板上的橫幅。</span><span class="sxs-lookup"><span data-stu-id="b7234-115">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="b7234-116">啟動 Microsoft 通話品質儀表板 (CQD) 摘要報告</span><span class="sxs-lookup"><span data-stu-id="b7234-116">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="b7234-117">在您開始使用 CQD 之前, 您必須針對您的 Office 365 組織啟用它。</span><span class="sxs-lookup"><span data-stu-id="b7234-117">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>

<span data-ttu-id="b7234-118">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="b7234-118">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
 
1. <span data-ttu-id="b7234-119">使用 Microsoft 團隊服務系統管理員帳戶登入您的 Office 365 組織, 然後選取 [系統**管理**] 磚以開啟系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b7234-119">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="b7234-120">在左窗格中的 [系統**管理中心**] 底下, 選取 [ **microsoft 團隊**] 以開啟 microsoft 團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b7234-120">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
    
3. <span data-ttu-id="b7234-121">在 Microsoft [團隊管理中心] 中, 選取左窗格中的 [**通話品質儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="b7234-121">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
    
  
4. <span data-ttu-id="b7234-122">在開啟的頁面上, 使用您的全域系統管理員帳戶或 Microsoft 團隊服務系統管理員帳戶登入, 然後在出現提示時提供該帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="b7234-122">On the page that opens, sign in with your Global Administrator account or Microsoft Teams Service Admin account, and then provide the credentials for the account when prompted.</span></span>
    
     ![顯示 [認證提示] 的螢幕擷取畫面](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="b7234-124">登入後, CQD 就會開始收集及處理資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-124">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="b7234-125">可能需要幾個小時的時間來處理足夠的資料, 才能在報表中顯示有意義的結果。</span><span class="sxs-lookup"><span data-stu-id="b7234-125">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 

<span data-ttu-id="b7234-126">![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="b7234-126">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="b7234-127">使用系統管理員帳戶登入您的 Office 365 組織, 然後選取 [系統**管理**] 磚以開啟系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b7234-127">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="b7234-128">在左窗格中的 [系統**管理中心**] 底下, 選取 [**商務用 skype** ] 以開啟商務用 skype 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b7234-128">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="b7234-129">在商務用 Skype 系統管理中心中, 選取左窗格中的 [**工具**], 然後選取 [**商務用 Skype Online 通話品質儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="b7234-129">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![螢幕擷取畫面顯示選取通話品質儀表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="b7234-131">在開啟的頁面上, 使用您的全域系統管理員帳戶登入, 然後在出現提示時提供該帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="b7234-131">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![顯示 [認證提示] 的螢幕擷取畫面](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="b7234-133">登入後, CQD 就會開始收集及處理資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-133">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="b7234-134">Microsoft 團隊和商務用 Skype Online 的通話品質儀表板功能</span><span class="sxs-lookup"><span data-stu-id="b7234-134">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span> 
<span data-ttu-id="b7234-135"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="b7234-135"></span></span>

<span data-ttu-id="b7234-136">CQD 摘要報告提供規劃詳細報告之功能的子集。</span><span class="sxs-lookup"><span data-stu-id="b7234-136">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="b7234-137">這兩種版本之間的差異摘要如下:</span><span class="sxs-lookup"><span data-stu-id="b7234-137">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="b7234-138">**功能**</span><span class="sxs-lookup"><span data-stu-id="b7234-138">**Feature**</span></span>|<span data-ttu-id="b7234-139">**摘要報告**</span><span class="sxs-lookup"><span data-stu-id="b7234-139">**Summary Reports**</span></span>|<span data-ttu-id="b7234-140">**詳細報告**</span><span class="sxs-lookup"><span data-stu-id="b7234-140">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7234-141">應用程式共用躍點數</span><span class="sxs-lookup"><span data-stu-id="b7234-141">Application sharing metric</span></span>  <br/> |<span data-ttu-id="b7234-142">不</span><span class="sxs-lookup"><span data-stu-id="b7234-142">No</span></span>  <br/> |<span data-ttu-id="b7234-143">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-143">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-144">客戶建立資訊支援</span><span class="sxs-lookup"><span data-stu-id="b7234-144">Customer building information support</span></span>  <br/> |<span data-ttu-id="b7234-145">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-145">Yes</span></span>  <br/> |<span data-ttu-id="b7234-146">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-146">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-147">用戶端點資訊支援</span><span class="sxs-lookup"><span data-stu-id="b7234-147">Customer endpoint information support</span></span>  <br/> |<span data-ttu-id="b7234-148">僅限 cqd.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b7234-148">Only in cqd.teams.microsoft.com</span></span>  <br/> |<span data-ttu-id="b7234-149">僅限 cqd.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b7234-149">Only in cqd.teams.microsoft.com</span></span>  <br/> |
|<span data-ttu-id="b7234-150">向下切入分析支援</span><span class="sxs-lookup"><span data-stu-id="b7234-150">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="b7234-151">不</span><span class="sxs-lookup"><span data-stu-id="b7234-151">No</span></span>  <br/> |<span data-ttu-id="b7234-152">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-152">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-153">媒體可靠性度量單位</span><span class="sxs-lookup"><span data-stu-id="b7234-153">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="b7234-154">不</span><span class="sxs-lookup"><span data-stu-id="b7234-154">No</span></span>  <br/> |<span data-ttu-id="b7234-155">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-155">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-156">外框報告</span><span class="sxs-lookup"><span data-stu-id="b7234-156">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="b7234-157">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-157">Yes</span></span>  <br/> |<span data-ttu-id="b7234-158">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-158">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-159">[總覽] 報表</span><span class="sxs-lookup"><span data-stu-id="b7234-159">Overview reports</span></span>  <br/> |<span data-ttu-id="b7234-160">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-160">Yes</span></span>  <br/> |<span data-ttu-id="b7234-161">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-161">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-162">每個使用者的報表集</span><span class="sxs-lookup"><span data-stu-id="b7234-162">Per-user report set</span></span>  <br/> |<span data-ttu-id="b7234-163">不</span><span class="sxs-lookup"><span data-stu-id="b7234-163">No</span></span>  <br/> |<span data-ttu-id="b7234-164">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-164">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-165">報表集自訂 (新增、刪除、修改報告)</span><span class="sxs-lookup"><span data-stu-id="b7234-165">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="b7234-166">不</span><span class="sxs-lookup"><span data-stu-id="b7234-166">No</span></span>  <br/> |<span data-ttu-id="b7234-167">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-167">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-168">以影片為基礎的畫面共用規格</span><span class="sxs-lookup"><span data-stu-id="b7234-168">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="b7234-169">不</span><span class="sxs-lookup"><span data-stu-id="b7234-169">No</span></span>  <br/> |<span data-ttu-id="b7234-170">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-170">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-171">影片度量單位</span><span class="sxs-lookup"><span data-stu-id="b7234-171">Video metrics</span></span>  <br/> |<span data-ttu-id="b7234-172">不</span><span class="sxs-lookup"><span data-stu-id="b7234-172">No</span></span>  <br/> |<span data-ttu-id="b7234-173">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-173">Yes</span></span>  <br/> |
|<span data-ttu-id="b7234-174">可用的資料量</span><span class="sxs-lookup"><span data-stu-id="b7234-174">Amount of data available</span></span>  <br/> |<span data-ttu-id="b7234-175">過去6個月</span><span class="sxs-lookup"><span data-stu-id="b7234-175">Last 6 months</span></span>  <br/> |<span data-ttu-id="b7234-176">過去6個月</span><span class="sxs-lookup"><span data-stu-id="b7234-176">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="b7234-177">Microsoft 團隊資料</span><span class="sxs-lookup"><span data-stu-id="b7234-177">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="b7234-178">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-178">Yes</span></span>  <br/> |<span data-ttu-id="b7234-179">是的</span><span class="sxs-lookup"><span data-stu-id="b7234-179">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="b7234-180">外框報告</span><span class="sxs-lookup"><span data-stu-id="b7234-180">Out-of-the-box reports</span></span>

<span data-ttu-id="b7234-181">這兩個版本的 CQD 都提供全新的體驗, 讓您可以呼叫品質指標, 而不需要建立任何新的報表。</span><span class="sxs-lookup"><span data-stu-id="b7234-181">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="b7234-182">在後端處理完資料之後, 您就可以開始在報表中查看通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-182">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="b7234-183">[總覽] 報表</span><span class="sxs-lookup"><span data-stu-id="b7234-183">Overview reports</span></span>

<span data-ttu-id="b7234-184">這兩個版本的 CQD 都提供了整體通話品質資訊的高層進入點, 但資訊在摘要報告中呈現的方式與詳細報告的方式不同。</span><span class="sxs-lookup"><span data-stu-id="b7234-184">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="b7234-185">[摘要報告] 提供簡化的索引標籤式頁面報表檢視, 可讓使用者快速流覽並瞭解整體通話品質狀態與趨勢。</span><span class="sxs-lookup"><span data-stu-id="b7234-185">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="b7234-186">四個索引標籤包括:</span><span class="sxs-lookup"><span data-stu-id="b7234-186">The four tabs include:</span></span>
  
- <span data-ttu-id="b7234-187">**整體通話品質**-提供所有資料流程的相關資訊, 這些資料流程是伺服器用戶端資料流程與用戶端資料流程的匯總, 以及獨立的伺服器用戶端和用戶端資料流程, 其形式為每月和每日趨勢。</span><span class="sxs-lookup"><span data-stu-id="b7234-187">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="b7234-188">**伺服器-用戶端**-針對伺服器與用戶端端點之間的資料流程提供其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-188">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="b7234-189">**用戶端-用戶端**-針對兩個用戶端端點之間的資料流程提供其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-189">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="b7234-190">**語音品質 SLA** -提供包含在商務用 Skype Online 語音品質 SLA 中之通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b7234-190">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="b7234-191">[整體通話品質] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b7234-191">Overall Call Quality tab</span></span>

<span data-ttu-id="b7234-192">使用此索引標籤上的資料, 透過查看串流數量及較差的百分比來評估通話品質狀態與趨勢。</span><span class="sxs-lookup"><span data-stu-id="b7234-192">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="b7234-193">右上角的圖例會顯示哪些色彩和視覺元素代表這些度量單位。</span><span class="sxs-lookup"><span data-stu-id="b7234-193">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![顯示 [通話品質] 索引標籤的螢幕擷取畫面](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="b7234-195">串流分為三個群組: [完好]、[差] 和 [未分類]。</span><span class="sxs-lookup"><span data-stu-id="b7234-195">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="b7234-196">此外, 也會計算出*較差的%* 值, 可讓您將資料流程分類為不*佳*至總分類資料流程計數的比例。</span><span class="sxs-lookup"><span data-stu-id="b7234-196">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="b7234-197">由於*差% = 無法正確的資料流程/(資料流程 + 良好資料流程) \* 100* , 這會讓目前狀態與多個未*分類*資料流程產生不受影響的*差%* 。</span><span class="sxs-lookup"><span data-stu-id="b7234-197">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="b7234-198">針對用來將串流分類為不良或良好的用途, 請參閱[通話品質儀表板中的資料流程分類](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="b7234-198">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="b7234-199">使用左邊的刻度來測量串流計數值。</span><span class="sxs-lookup"><span data-stu-id="b7234-199">Use the scale on the left to measure the stream count values.</span></span>
  
![顯示串流計數值的螢幕擷取畫面](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="b7234-201">使用右側的刻度來測量較差的% 值。</span><span class="sxs-lookup"><span data-stu-id="b7234-201">Use the scale on the right to measure the Poor % values.</span></span>
  
![螢幕擷取畫面顯示較差的% 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="b7234-203">您也可以將滑鼠游標停留在列上方, 以取得實際數值。</span><span class="sxs-lookup"><span data-stu-id="b7234-203">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7234-204">下列範例是來自非常小的範例資料集, 且這些值對於實際部署而言並不切合實際。</span><span class="sxs-lookup"><span data-stu-id="b7234-204">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![顯示使用滑鼠存取資料的螢幕擷取畫面](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="b7234-206">整個資料流量是判斷計算出不佳百分比的相關程度的重要因素。</span><span class="sxs-lookup"><span data-stu-id="b7234-206">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="b7234-207">總體資料流程的數量越小, 報告的低百分比值就越不可靠。</span><span class="sxs-lookup"><span data-stu-id="b7234-207">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="b7234-208">[伺服器-用戶端] 索引標籤和用戶端用戶端索引標籤</span><span class="sxs-lookup"><span data-stu-id="b7234-208">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="b7234-209">這兩個索引標籤提供在其端點對端點案例中所發生之資料流程的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-209">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="b7234-210">這兩個索引標籤都有四個可折迭的區段, 代表媒體資料流程流動的四種案例。</span><span class="sxs-lookup"><span data-stu-id="b7234-210">Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="b7234-211">有線內</span><span class="sxs-lookup"><span data-stu-id="b7234-211">Wired Inside</span></span>
    
- <span data-ttu-id="b7234-212">外有線</span><span class="sxs-lookup"><span data-stu-id="b7234-212">Wired Outside</span></span>
    
- <span data-ttu-id="b7234-213">內部 Wifi</span><span class="sxs-lookup"><span data-stu-id="b7234-213">Wifi Inside</span></span>
    
- <span data-ttu-id="b7234-214">Wifi 外</span><span class="sxs-lookup"><span data-stu-id="b7234-214">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="b7234-215">內部測試</span><span class="sxs-lookup"><span data-stu-id="b7234-215">Inside Test</span></span>

<span data-ttu-id="b7234-216">在處理期間, CQD 後端會使用建築物資訊 (如果有的話) 將串流分類為*內部*或*外部*。</span><span class="sxs-lookup"><span data-stu-id="b7234-216">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="b7234-217">每個串流的端點都會與子網位址產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b7234-217">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="b7234-218">如果子網位於已上傳的建築物資訊中標示為 InsideCorp 的子網清單中, 則會被視為*內部*。</span><span class="sxs-lookup"><span data-stu-id="b7234-218">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="b7234-219">如果建築物資訊尚未上傳, 則在測試中將永遠會將資料流程分類為*外部*。</span><span class="sxs-lookup"><span data-stu-id="b7234-219">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="b7234-220">請注意, 在伺服器用戶端案例的內部測試中, 只會考慮用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="b7234-220">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="b7234-221">因為伺服器永遠都不是從使用者的角度來看, 所以在測試中並不考慮。</span><span class="sxs-lookup"><span data-stu-id="b7234-221">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="b7234-222">有線與 wifi</span><span class="sxs-lookup"><span data-stu-id="b7234-222">Wired vs. wifi</span></span>

<span data-ttu-id="b7234-223">如名稱所指出, 這是依據用戶端連線類型的分類準則。</span><span class="sxs-lookup"><span data-stu-id="b7234-223">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="b7234-224">同樣地, 伺服器總是是有線的, 而且不會包含在計算中。</span><span class="sxs-lookup"><span data-stu-id="b7234-224">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7234-225">如果有一個資料流程, 如果兩個端點中有一個連接至 Wifi 網路, 則會在 CQD 中分類為 Wifi。</span><span class="sxs-lookup"><span data-stu-id="b7234-225">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="b7234-226">選取要在報表中查看的產品資料</span><span class="sxs-lookup"><span data-stu-id="b7234-226">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="b7234-227">您可以在 [摘要] 和 [位置] 增強式報表中, 使用 [**產品篩選**] 下拉式清單來顯示所有產品資料、只顯示 Microsoft 團隊資料, 或只顯示商務用 Skype Online 資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-227">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![顯示 [產品] 篩選控制項選項的螢幕擷取畫面](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="b7234-229">在 [詳細報告] 中, 您可以使用 [**成為團隊**維度] 來篩選資料至 Microsoft 團隊或商務用 Skype Online 資料 (請見定義報表)。</span><span class="sxs-lookup"><span data-stu-id="b7234-229">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="b7234-230">上傳租使用者資料資訊</span><span class="sxs-lookup"><span data-stu-id="b7234-230">Upload Tenant Data information</span></span>
<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="b7234-231">CQD 摘要報告儀表板包含**租使用者資料上傳**頁面, 方法是從右上角的 [設定] 功能表中選取 [**租使用者資料上傳**]。</span><span class="sxs-lookup"><span data-stu-id="b7234-231">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="b7234-232">此頁面可供系統管理員上傳自己的資訊, 例如 IP 位址和地理資訊的對應、對應每個無線 AP 及其 MAC 位址、將端點對應到端點產生/模型/類型等。</span><span class="sxs-lookup"><span data-stu-id="b7234-232">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, mapping of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![顯示 [通話品質] 儀表板的螢幕擷取畫面](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="b7234-234">在 [**租使用者資料上傳**] 頁面上, 使用下拉式功能表, 選擇要上傳的資料檔案類型。</span><span class="sxs-lookup"><span data-stu-id="b7234-234">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="b7234-235">[檔案] 資料類型代表檔案的內容 (例如, "建築物" 代表 IP 位址與建築物以及其他地理位置資訊, "端點" 代表將端點名稱對應到端點 [建立/模型/類型 ...]。資訊)。</span><span class="sxs-lookup"><span data-stu-id="b7234-235">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type…information).</span></span> <span data-ttu-id="b7234-236">我們目前支援上傳「大樓」和 "Endpoint" 資料類型 for cqd (在預覽階段中, 尚未正式提供), cqd.lync.com 只支援上傳「組建」資料類型。</span><span class="sxs-lookup"><span data-stu-id="b7234-236">Currently we support upload “Building” and “Endpoint” data types for cqd.teams.microsoft.com(in preview stage and not officially available yet), cqd.lync.com only supports upload "Building" data type.</span></span> <span data-ttu-id="b7234-237">後續版本中將會新增更多的資料類型。</span><span class="sxs-lookup"><span data-stu-id="b7234-237">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="b7234-238">選取 [檔案] 資料類型之後, 按一下 **[流覽]** 以選擇資料檔案。</span><span class="sxs-lookup"><span data-stu-id="b7234-238">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="b7234-239">資料檔案必須是. tsv (以 Tab 分隔的值) 檔案或 .csv (逗號分隔值) 檔案。</span><span class="sxs-lookup"><span data-stu-id="b7234-239">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="b7234-240">如果使用 .csv 檔案, 任何包含逗號的欄位都必須以引號括住, 或移除逗號。</span><span class="sxs-lookup"><span data-stu-id="b7234-240">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="b7234-241">例如, 如果您的建築物名稱是 NY、NY, 請在 .csv 檔案中輸入 "NY, NY"。</span><span class="sxs-lookup"><span data-stu-id="b7234-241">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="b7234-242">資料檔的大小必須不超過不可50MB。</span><span class="sxs-lookup"><span data-stu-id="b7234-242">The data file must be no larger than 50MB in size.</span></span>

   - <span data-ttu-id="b7234-243">上傳到 cqd.teams.microsoft.com 的檔案已展開1000000的列限制, 以加速查詢效能。</span><span class="sxs-lookup"><span data-stu-id="b7234-243">File uploaded to cqd.teams.microsoft.com has expanded row limit of 1,000,000 to speed up query performance.</span></span> <span data-ttu-id="b7234-244">我們也可能會在 cqd.lync.com 上強加該限制。</span><span class="sxs-lookup"><span data-stu-id="b7234-244">We may impose that limit on cqd.lync.com as well.</span></span>
    
   - <span data-ttu-id="b7234-245">針對每個資料檔案, 檔案中的每一欄都必須符合預先定義的資料類型, 本主題稍後將討論。</span><span class="sxs-lookup"><span data-stu-id="b7234-245">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="b7234-246">選取資料檔之後, 請指定**開始日期**, 也可以**指定結束日期**。</span><span class="sxs-lookup"><span data-stu-id="b7234-246">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="b7234-247">選取 [**開始日期**] 後, 選取 **[上傳**], 將檔案上傳到 CQD 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7234-247">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="b7234-248">檔案上傳之前, 先進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b7234-248">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="b7234-249">驗證之後, 就會儲存在 Azure blob 中。</span><span class="sxs-lookup"><span data-stu-id="b7234-249">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="b7234-250">如果驗證失敗, 或檔案無法儲存在 Azure blob 中, 則會顯示一則錯誤訊息, 要求對檔案進行修正。</span><span class="sxs-lookup"><span data-stu-id="b7234-250">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="b7234-251">下列影像顯示當資料檔案中的欄數不正確時, 會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="b7234-251">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![顯示上傳驗證錯誤的螢幕擷取畫面](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="b7234-253">如果驗證期間沒有發生任何錯誤, 檔案上傳就會成功。</span><span class="sxs-lookup"><span data-stu-id="b7234-253">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="b7234-254">接著, 您可以在 [我的上**傳**] 資料表中看到上傳的資料檔, 該檔案會在該頁面的底部顯示目前租使用者的所有已上傳檔案的完整清單。</span><span class="sxs-lookup"><span data-stu-id="b7234-254">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="b7234-255">每個記錄會顯示一個上傳的租使用者資料檔, 其中包含檔案類型、上次更新時間、時間段、描述、移除圖示及下載圖示。</span><span class="sxs-lookup"><span data-stu-id="b7234-255">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="b7234-256">若要移除檔案, 請選取表格中的 [回收站] 圖示。</span><span class="sxs-lookup"><span data-stu-id="b7234-256">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="b7234-257">若要下載檔案, 請選取表格 [**下載**] 欄中的 [下載] 圖示。</span><span class="sxs-lookup"><span data-stu-id="b7234-257">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![顯示 [我的上傳] 資料表的螢幕擷取畫面](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="b7234-259">租使用者資料檔案格式與結構</span><span class="sxs-lookup"><span data-stu-id="b7234-259">Tenant data file format and structure</span></span>
<span data-ttu-id="b7234-260"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="b7234-260"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="b7234-261">建立資料檔案</span><span class="sxs-lookup"><span data-stu-id="b7234-261">Building data file</span></span>
<span data-ttu-id="b7234-262">CQD 會先從展開 Network + NetworkRange 欄, 然後將子網欄加入至通話記錄的第一個子網/第二個子網欄, 以顯示建築物/城市/國家/地區, 以建立資料檔案</span><span class="sxs-lookup"><span data-stu-id="b7234-262">CQD uses Building data file by first derive Subnet column from expanding Network+NetworkRange column, then joining Subnet column to the call record’s First Subnet/Second Subnet column to show Building/City/Country/Region…</span></span> <span data-ttu-id="b7234-263">錯誤資訊.</span><span class="sxs-lookup"><span data-stu-id="b7234-263">information.</span></span> <span data-ttu-id="b7234-264">您上傳的資料檔案格式必須符合下列規則, 才能在上傳前通過驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="b7234-264">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="b7234-265">檔案必須是一個 tsv 檔案, 也就是說, 在每個資料列中, 欄會以一個索引標籤分隔, 或是以逗號分隔每個資料行的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="b7234-265">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="b7234-266">資料檔案的內容不會包含表格標題。</span><span class="sxs-lookup"><span data-stu-id="b7234-266">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="b7234-267">這表示資料檔案的第一行應該是真實資料, 而不是像是「網路」等的標頭。</span><span class="sxs-lookup"><span data-stu-id="b7234-267">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="b7234-268">針對每個資料行, 資料類型只能是 String、Number 或 Bool。</span><span class="sxs-lookup"><span data-stu-id="b7234-268">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="b7234-269">如果是 Number, 則該值必須是一個數值;如果是 Bool, 則該值必須是0或1。</span><span class="sxs-lookup"><span data-stu-id="b7234-269">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="b7234-270">針對每個資料行, 如果資料類型是 string, 則資料可以是空白 (但必須以適當的分隔符號 (亦即定位字元或逗號) 分隔。</span><span class="sxs-lookup"><span data-stu-id="b7234-270">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="b7234-271">這只會將該欄位指派為空白字串值。</span><span class="sxs-lookup"><span data-stu-id="b7234-271">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="b7234-272">每個資料列都必須有14個數據行, 每一欄都必須具有下列資料類型, 且欄必須按照下表所列的順序排列:</span><span class="sxs-lookup"><span data-stu-id="b7234-272">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="b7234-273">**欄名稱**</span><span class="sxs-lookup"><span data-stu-id="b7234-273">**Column Name**</span></span>|<span data-ttu-id="b7234-274">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="b7234-274">**Data type**</span></span>|<span data-ttu-id="b7234-275">**範例**</span><span class="sxs-lookup"><span data-stu-id="b7234-275">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7234-276">局域網</span><span class="sxs-lookup"><span data-stu-id="b7234-276">Network</span></span>  <br/> |<span data-ttu-id="b7234-277">String</span><span class="sxs-lookup"><span data-stu-id="b7234-277">String</span></span>  <br/> |<span data-ttu-id="b7234-278">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="b7234-278">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="b7234-279">NetworkName</span><span class="sxs-lookup"><span data-stu-id="b7234-279">NetworkName</span></span>  <br/> |<span data-ttu-id="b7234-280">String</span><span class="sxs-lookup"><span data-stu-id="b7234-280">String</span></span>  <br/> |<span data-ttu-id="b7234-281">美國/西雅圖/西雅圖-海-1</span><span class="sxs-lookup"><span data-stu-id="b7234-281">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="b7234-282">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="b7234-282">NetworkRange</span></span>  <br/> |<span data-ttu-id="b7234-283">電話</span><span class="sxs-lookup"><span data-stu-id="b7234-283">Number</span></span>  <br/> |<span data-ttu-id="b7234-284">26</span><span class="sxs-lookup"><span data-stu-id="b7234-284">26</span></span>  <br/> |
|<span data-ttu-id="b7234-285">BuildingName</span><span class="sxs-lookup"><span data-stu-id="b7234-285">BuildingName</span></span>  <br/> |<span data-ttu-id="b7234-286">String</span><span class="sxs-lookup"><span data-stu-id="b7234-286">String</span></span>  <br/> |<span data-ttu-id="b7234-287">北京-海-1</span><span class="sxs-lookup"><span data-stu-id="b7234-287">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="b7234-288">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="b7234-288">OwnershipType</span></span>  <br/> |<span data-ttu-id="b7234-289">String</span><span class="sxs-lookup"><span data-stu-id="b7234-289">String</span></span>  <br/> |<span data-ttu-id="b7234-290">尚未</span><span class="sxs-lookup"><span data-stu-id="b7234-290">Contoso</span></span>  <br/> |
|<span data-ttu-id="b7234-291">BuildingType</span><span class="sxs-lookup"><span data-stu-id="b7234-291">BuildingType</span></span>  <br/> |<span data-ttu-id="b7234-292">String</span><span class="sxs-lookup"><span data-stu-id="b7234-292">String</span></span>  <br/> |<span data-ttu-id="b7234-293">終止</span><span class="sxs-lookup"><span data-stu-id="b7234-293">IT Termination</span></span>  <br/> |
|<span data-ttu-id="b7234-294">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="b7234-294">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="b7234-295">String</span><span class="sxs-lookup"><span data-stu-id="b7234-295">String</span></span>  <br/> |<span data-ttu-id="b7234-296">工程學</span><span class="sxs-lookup"><span data-stu-id="b7234-296">Engineering</span></span>  <br/> |
|<span data-ttu-id="b7234-297">座</span><span class="sxs-lookup"><span data-stu-id="b7234-297">City</span></span>  <br/> |<span data-ttu-id="b7234-298">String</span><span class="sxs-lookup"><span data-stu-id="b7234-298">String</span></span>  <br/> |<span data-ttu-id="b7234-299">西雅圖</span><span class="sxs-lookup"><span data-stu-id="b7234-299">Seattle</span></span>  <br/> |
|<span data-ttu-id="b7234-300">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="b7234-300">ZipCode</span></span>  <br/> |<span data-ttu-id="b7234-301">String</span><span class="sxs-lookup"><span data-stu-id="b7234-301">String</span></span>  <br/> |<span data-ttu-id="b7234-302">98001</span><span class="sxs-lookup"><span data-stu-id="b7234-302">98001</span></span>  <br/> |
|<span data-ttu-id="b7234-303">國家</span><span class="sxs-lookup"><span data-stu-id="b7234-303">Country</span></span>  <br/> |<span data-ttu-id="b7234-304">String</span><span class="sxs-lookup"><span data-stu-id="b7234-304">String</span></span>  <br/> |<span data-ttu-id="b7234-305">一下</span><span class="sxs-lookup"><span data-stu-id="b7234-305">US</span></span>  <br/> |
|<span data-ttu-id="b7234-306">市</span><span class="sxs-lookup"><span data-stu-id="b7234-306">State</span></span>  <br/> |<span data-ttu-id="b7234-307">String</span><span class="sxs-lookup"><span data-stu-id="b7234-307">String</span></span>  <br/> |<span data-ttu-id="b7234-308">華盛頓</span><span class="sxs-lookup"><span data-stu-id="b7234-308">WA</span></span>  <br/> |
|<span data-ttu-id="b7234-309">國家</span><span class="sxs-lookup"><span data-stu-id="b7234-309">Region</span></span>  <br/> |<span data-ttu-id="b7234-310">String</span><span class="sxs-lookup"><span data-stu-id="b7234-310">String</span></span>  <br/> |<span data-ttu-id="b7234-311">MSUS</span><span class="sxs-lookup"><span data-stu-id="b7234-311">MSUS</span></span>  <br/> |
|<span data-ttu-id="b7234-312">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="b7234-312">InsideCorp</span></span>  <br/> |<span data-ttu-id="b7234-313">Bool</span><span class="sxs-lookup"><span data-stu-id="b7234-313">Bool</span></span>  <br/> |<span data-ttu-id="b7234-314">sr-1</span><span class="sxs-lookup"><span data-stu-id="b7234-314">1</span></span>  <br/> |
|<span data-ttu-id="b7234-315">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="b7234-315">ExpressRoute</span></span>  <br/> |<span data-ttu-id="b7234-316">Bool</span><span class="sxs-lookup"><span data-stu-id="b7234-316">Bool</span></span>  <br/> |<span data-ttu-id="b7234-317">0</span><span class="sxs-lookup"><span data-stu-id="b7234-317">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="b7234-318">網路範圍可用來代表 supernet (多個子網與單一路由前置詞的組合)。</span><span class="sxs-lookup"><span data-stu-id="b7234-318">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="b7234-319">所有新的建築物上傳都會被檢查, 以取得任何重迭的範圍。</span><span class="sxs-lookup"><span data-stu-id="b7234-319">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="b7234-320">如果您先前上傳的是組建檔案, 您應該下載目前的檔案, 然後重新上傳以找出任何重疊, 並修正問題, 然後再重新上傳。</span><span class="sxs-lookup"><span data-stu-id="b7234-320">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="b7234-321">先前上傳的檔案中的任何交疊, 可能會導致無法正確地將子網對應至報表中的建築物。</span><span class="sxs-lookup"><span data-stu-id="b7234-321">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="b7234-322">某些 VPN 實現不會精確地報告子網資訊。</span><span class="sxs-lookup"><span data-stu-id="b7234-322">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="b7234-323">建議將 VPN 子網新增至組建檔案, 而不是子網的一個專案時, 會針對 VPN 子網中的每個位址, 為個別的32位網路新增個別專案。</span><span class="sxs-lookup"><span data-stu-id="b7234-323">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="b7234-324">每個資料列都可以有相同的建築物中繼資料。</span><span class="sxs-lookup"><span data-stu-id="b7234-324">Each row can have the same building metadata.</span></span> <span data-ttu-id="b7234-325">例如, 172.16.18.0/24 不只一列, 您應該有256列, 每個位址都有一個資料列, 其中每個位址都在 172.16.18.0/32 和 172.16.18.255/32 之間 (含)。</span><span class="sxs-lookup"><span data-stu-id="b7234-325">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 

### <a name="endpoint-data-file"></a><span data-ttu-id="b7234-326">端點資料檔案</span><span class="sxs-lookup"><span data-stu-id="b7234-326">Endpoint data file</span></span>
<span data-ttu-id="b7234-327">CQD 會使用端點資料檔案, 方法是將其點字聯接至通話記錄的第一個用戶端端點名稱/第二個用戶端端點名稱欄, 以顯示端點產生/模型/類型資訊。</span><span class="sxs-lookup"><span data-stu-id="b7234-327">CQD uses Endpoint data file by joining its EndpointName column to the call record’s First Client Endpoint Name/Second Client Endpoint Name column to show Endpoint Make/Model/Type information.</span></span> <span data-ttu-id="b7234-328">您上傳的資料檔案格式必須符合下列規則, 才能在上傳前通過驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="b7234-328">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>

- <span data-ttu-id="b7234-329">檔案必須是一個 tsv 檔案, 也就是說, 在每個資料列中, 欄會以一個索引標籤分隔, 或是以逗號分隔每個資料行的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="b7234-329">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>

- <span data-ttu-id="b7234-330">資料檔案的內容不會包含表格標題。</span><span class="sxs-lookup"><span data-stu-id="b7234-330">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="b7234-331">這表示資料檔的第一行應該是實際資料, 而不是像是「終結點」等的標頭。</span><span class="sxs-lookup"><span data-stu-id="b7234-331">That means the first line of the data file should be real data, not headers like "EndpointName," etc.</span></span>

- <span data-ttu-id="b7234-332">針對每個資料行, 資料類型只能是字串, 且不應超過64個字元 (最大允許長度)。</span><span class="sxs-lookup"><span data-stu-id="b7234-332">For each column, the data type can only be String and it should have no more than 64 chars, which is maximum allowed length.</span></span>

- <span data-ttu-id="b7234-333">針對每一欄, 資料都可以是空白的 (但必須以適當的分隔符號 (亦即定位字元或逗號) 分隔。</span><span class="sxs-lookup"><span data-stu-id="b7234-333">For each column, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="b7234-334">這只會將該欄位指派為空白字串值。</span><span class="sxs-lookup"><span data-stu-id="b7234-334">This just assigns that field an empty string value.</span></span>

- <span data-ttu-id="b7234-335">每個資料列都必須有7欄, 且欄必須按照下表所列的順序排列。</span><span class="sxs-lookup"><span data-stu-id="b7234-335">There must be 7 columns for each row and the columns must be in the order listed in the following table.</span></span>

- <span data-ttu-id="b7234-336">終結點必須是唯一的, 否則上傳會因為重複的資料列而失敗, 因為這會造成不正確的聯接。</span><span class="sxs-lookup"><span data-stu-id="b7234-336">EndpointName must be unique otherwise upload will fail due to duplicate row as it will cause incorrect joining.</span></span>

-  <span data-ttu-id="b7234-337">EndpointLabel1、EndpointLabel2、EndpointLable3 是使用者可自訂的標籤, 它們可以是空白字串或使用者喜歡的值, 例如「IT 部門指派2018膝上型電腦」、「資產標籤5678」 .。。等.</span><span class="sxs-lookup"><span data-stu-id="b7234-337">EndpointLabel1, EndpointLabel2, EndpointLable3 are user customizable labels, they can be empty strings or value users prefer such as “IT Department designated 2018 Laptop”, “Asset Tag 5678” …etc.</span></span>

|<span data-ttu-id="b7234-338">**欄名稱**</span><span class="sxs-lookup"><span data-stu-id="b7234-338">**Column Name**</span></span>|<span data-ttu-id="b7234-339">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="b7234-339">**Data type**</span></span>|<span data-ttu-id="b7234-340">**範例**</span><span class="sxs-lookup"><span data-stu-id="b7234-340">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7234-341">點</span><span class="sxs-lookup"><span data-stu-id="b7234-341">EndpointName</span></span>  <br/> |<span data-ttu-id="b7234-342">String</span><span class="sxs-lookup"><span data-stu-id="b7234-342">String</span></span>  <br/> |<span data-ttu-id="b7234-343">1409W3534</span><span class="sxs-lookup"><span data-stu-id="b7234-343">1409W3534</span></span>  <br/> |
|<span data-ttu-id="b7234-344">EndpointMake</span><span class="sxs-lookup"><span data-stu-id="b7234-344">EndpointMake</span></span>  <br/> |<span data-ttu-id="b7234-345">String</span><span class="sxs-lookup"><span data-stu-id="b7234-345">String</span></span>  <br/> |<span data-ttu-id="b7234-346">Fabrikam Inc。</span><span class="sxs-lookup"><span data-stu-id="b7234-346">Fabrikam Inc</span></span>  <br/> |
|<span data-ttu-id="b7234-347">EndpointModel</span><span class="sxs-lookup"><span data-stu-id="b7234-347">EndpointModel</span></span>  <br/> |<span data-ttu-id="b7234-348">String</span><span class="sxs-lookup"><span data-stu-id="b7234-348">String</span></span>  <br/> |<span data-ttu-id="b7234-349">Fabrikam 模型123</span><span class="sxs-lookup"><span data-stu-id="b7234-349">Fabrikam Model 123</span></span>  <br/> |
|<span data-ttu-id="b7234-350">EndpointType</span><span class="sxs-lookup"><span data-stu-id="b7234-350">EndpointType</span></span>   <br/> |<span data-ttu-id="b7234-351">String</span><span class="sxs-lookup"><span data-stu-id="b7234-351">String</span></span>  <br/> |<span data-ttu-id="b7234-352">筆記本</span><span class="sxs-lookup"><span data-stu-id="b7234-352">Laptop</span></span>  <br/> |
|<span data-ttu-id="b7234-353">EndpointLabel1</span><span class="sxs-lookup"><span data-stu-id="b7234-353">EndpointLabel1</span></span>  <br/> |<span data-ttu-id="b7234-354">String</span><span class="sxs-lookup"><span data-stu-id="b7234-354">String</span></span>  <br/> |<span data-ttu-id="b7234-355">指派2018膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="b7234-355">IT designated 2018 Laptop</span></span>  <br/> |
|<span data-ttu-id="b7234-356">EndpointLabel2</span><span class="sxs-lookup"><span data-stu-id="b7234-356">EndpointLabel2</span></span>  <br/> |<span data-ttu-id="b7234-357">String</span><span class="sxs-lookup"><span data-stu-id="b7234-357">String</span></span>  <br/> |<span data-ttu-id="b7234-358">資產標記5678</span><span class="sxs-lookup"><span data-stu-id="b7234-358">Asset Tag 5678</span></span>  <br/> |
|<span data-ttu-id="b7234-359">EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="b7234-359">EndpointLabel3</span></span>  <br/> |<span data-ttu-id="b7234-360">String</span><span class="sxs-lookup"><span data-stu-id="b7234-360">String</span></span>  <br/> |<span data-ttu-id="b7234-361">購買2018</span><span class="sxs-lookup"><span data-stu-id="b7234-361">Purchase 2018</span></span>   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="b7234-362">選取 [詳細報告] 中的媒體類型</span><span class="sxs-lookup"><span data-stu-id="b7234-362">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="b7234-363">詳細報告支援針對音訊、影片、應用程式共用及影片式螢幕共用媒體類型, 查看品質與媒體的可靠性。</span><span class="sxs-lookup"><span data-stu-id="b7234-363">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="b7234-364">單一媒體類型專用的維度、量值及篩選, 具有 "音訊"、"影片"、"AppSharing" 或 "VBSS" 做為前置詞。</span><span class="sxs-lookup"><span data-stu-id="b7234-364">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![螢幕擷取畫面顯示 [通話品質儀表板] 尺寸。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="b7234-366">如果您想要針對單一媒體類型查看維度與量值, 可能需要新的媒體類型維度和篩選器。</span><span class="sxs-lookup"><span data-stu-id="b7234-366">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="b7234-367">例如, 若要讓報表顯示不同媒體類型的總會話計數, 請包含 [媒體類型] 維度。</span><span class="sxs-lookup"><span data-stu-id="b7234-367">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![螢幕擷取畫面顯示 [通話品質儀表板總串流數]。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="b7234-369">相關主題</span><span class="sxs-lookup"><span data-stu-id="b7234-369">Related topics</span></span>
[<span data-ttu-id="b7234-370">設定商務用 Skype 通話分析</span><span class="sxs-lookup"><span data-stu-id="b7234-370">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="b7234-371">使用呼叫分析來排查不佳的通話品質問題</span><span class="sxs-lookup"><span data-stu-id="b7234-371">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

<span data-ttu-id="b7234-372">[[通話分析] 和 [通話品質儀表板]](difference-between-call-analytics-and-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="b7234-372">[Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)</span></span>

  
 
