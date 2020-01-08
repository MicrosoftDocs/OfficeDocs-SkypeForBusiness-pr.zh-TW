---
title: Lync Server 2013：每週工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="6c93b-102">Lync Server 2013 中的每週工作</span><span class="sxs-lookup"><span data-stu-id="6c93b-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c93b-103">_**主題上次修改日期：** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="6c93b-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="6c93b-104">每週工作通常與收集及分析記錄和報告有關。</span><span class="sxs-lookup"><span data-stu-id="6c93b-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="6c93b-105">封存事件記錄</span><span class="sxs-lookup"><span data-stu-id="6c93b-105">Archive event logs</span></span>

<span data-ttu-id="6c93b-106">如果事件記錄未設定為視需要覆寫事件，則必須定期封存並刪除這些事件。</span><span class="sxs-lookup"><span data-stu-id="6c93b-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="6c93b-107">此動作對於安全記錄特別重要，在調查企圖安全破壞時可能需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="6c93b-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="6c93b-108">貴組織將必須定義記錄歸檔的原則與程式。</span><span class="sxs-lookup"><span data-stu-id="6c93b-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="6c93b-109">建立報表</span><span class="sxs-lookup"><span data-stu-id="6c93b-109">Create reports</span></span>

<span data-ttu-id="6c93b-110">建立狀態報表，以協助您進行容量規劃、SLA 審查，以及效能分析。</span><span class="sxs-lookup"><span data-stu-id="6c93b-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="6c93b-111">使用來自事件日誌和系統監視器的每日資料來建立磁片、記憶體和 CPU 使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="6c93b-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="6c93b-112">使用 System Center Operations Manager 來產生正常運作時間及可用性報告。</span><span class="sxs-lookup"><span data-stu-id="6c93b-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="6c93b-113">貴組織將必須定義狀態報表的原則與程式。</span><span class="sxs-lookup"><span data-stu-id="6c93b-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="6c93b-114">附隨報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-114">Incident reports</span></span>

<span data-ttu-id="6c93b-115">針對與 Lync Server 相關的組織附隨報告執行每週審核。</span><span class="sxs-lookup"><span data-stu-id="6c93b-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="6c93b-116">此審核應包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="6c93b-116">This audit should include the following:</span></span>

  - <span data-ttu-id="6c93b-117">最上層產生、已解決及待定的事件。</span><span class="sxs-lookup"><span data-stu-id="6c93b-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="6c93b-118">未解決之事件的解決方案。</span><span class="sxs-lookup"><span data-stu-id="6c93b-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="6c93b-119">更新報告以包含新的問題票證。</span><span class="sxs-lookup"><span data-stu-id="6c93b-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="6c93b-120">更新文件庫以取得疑難排解指南，並針對中斷進行文章 mortems。</span><span class="sxs-lookup"><span data-stu-id="6c93b-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="6c93b-121">因為您組織的事件追蹤系統是獨立于 Lync Server 的選擇，所以無法使用特定指示或指標。</span><span class="sxs-lookup"><span data-stu-id="6c93b-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="6c93b-122">請參閱貴組織所選系統的相關檔。</span><span class="sxs-lookup"><span data-stu-id="6c93b-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="6c93b-123">檢查 IIS 記錄和效能</span><span class="sxs-lookup"><span data-stu-id="6c93b-123">Check IIS logs and performance</span></span>

<span data-ttu-id="6c93b-124">針對網際網路資訊服務（IIS）記錄和效能執行每週檢查。</span><span class="sxs-lookup"><span data-stu-id="6c93b-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="6c93b-125">如需如何監視 IIS 記錄和效能的詳細資訊，請參閱[Windows Server 2003 Internet Information Services （IIS）事件記錄概覽](http://go.microsoft.com/fwlink/?linkid=36077)。</span><span class="sxs-lookup"><span data-stu-id="6c93b-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="6c93b-126">審查應包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="6c93b-126">The review should include the following:</span></span>

  - <span data-ttu-id="6c93b-127">[Web 服務快取計數器] 可監視 WWW 服務快取。</span><span class="sxs-lookup"><span data-stu-id="6c93b-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="6c93b-128">[Active Server Pages （Asp）] 計數器，可監視以 Asp 執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6c93b-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="6c93b-129">產生資料庫報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-129">Generate database reports</span></span>

<span data-ttu-id="6c93b-130">**若要在 SQL 資料庫上產生報告**</span><span class="sxs-lookup"><span data-stu-id="6c93b-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="6c93b-131">開啟 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6c93b-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="6c93b-132">在主控台樹中，展開 [林] 節點，展開 [**企業版池**]，然後按一下您要為其產生資料庫報告的池。</span><span class="sxs-lookup"><span data-stu-id="6c93b-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="6c93b-133">在 [詳細資料] 窗格中，按一下 [**資料庫**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6c93b-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="6c93b-134">在 [**資料庫**] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6c93b-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="6c93b-135">若要查看資料庫名稱，請展開 **[一般設定**]，然後查看資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="6c93b-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="6c93b-136">若要為該資源庫取得目前的使用者摘要統計資料 **，請展開**[**使用者摘要報告**]，按一下 [執行]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="6c93b-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="6c93b-137">若要針對池的單一使用者檢索目前的每個使用者資料，請展開 [**每使用者報告**]，輸入使用者的 SIP URI，**按一下 [** 執行]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="6c93b-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="6c93b-138">若要檢索該池子的目前會議摘要統計資料 **，請展開**[**會議摘要報告**]，按一下 [執行]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="6c93b-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="6c93b-139">檢查安全性和 Lync Server 更新</span><span class="sxs-lookup"><span data-stu-id="6c93b-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="6c93b-140">識別任何新的 service pack、熱修復程式或更新。</span><span class="sxs-lookup"><span data-stu-id="6c93b-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="6c93b-141">如有需要，請在測試實驗室中測試這些選項，然後使用變更控制程式來安排部署到生產伺服器。</span><span class="sxs-lookup"><span data-stu-id="6c93b-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="6c93b-142">此外，Lync Server 元件更新現可在 Windows update 中取得。</span><span class="sxs-lookup"><span data-stu-id="6c93b-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="6c93b-143">所有運行 lync Server 且適用更新的伺服器，都必須同時更新所有 Lync Server 元件更新。</span><span class="sxs-lookup"><span data-stu-id="6c93b-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="6c93b-144">執行 Lync Server 2013 最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="6c93b-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="6c93b-145">Lync Server 2013 最佳做法分析程式工具是一個診斷工具，可收集設定資訊並判斷是否已根據 Microsoft 最佳做法設定設定。</span><span class="sxs-lookup"><span data-stu-id="6c93b-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="6c93b-146">此工具的檔為[Lync Server 2013 最佳做法分析](lync-server-2013-lync-server-best-practices-analyzer.md)程式。</span><span class="sxs-lookup"><span data-stu-id="6c93b-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="6c93b-147">此工具會針對 Lync Server 的一組預先定義的規則，比較您的部署設定資料，並報告潛在問題。</span><span class="sxs-lookup"><span data-stu-id="6c93b-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="6c93b-148">針對報告的每個問題，該工具都會提供 Lync Server 環境中的目前設定，以及建議的設定。</span><span class="sxs-lookup"><span data-stu-id="6c93b-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="6c93b-149">使用正確的網路存取，此工具可以檢查您的 AD DS 和執行 Lync Server 2013 的伺服器，以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="6c93b-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="6c93b-150">主動執行狀況檢查，以驗證是否已根據建議的最佳做法設定設定</span><span class="sxs-lookup"><span data-stu-id="6c93b-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="6c93b-151">產生問題的清單，例如不理想的設定，或不支援或不建議的選項</span><span class="sxs-lookup"><span data-stu-id="6c93b-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="6c93b-152">判斷系統的一般狀況</span><span class="sxs-lookup"><span data-stu-id="6c93b-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="6c93b-153">協助解決特定問題</span><span class="sxs-lookup"><span data-stu-id="6c93b-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="6c93b-154">如果有可用的更新，系統會提示您下載更新</span><span class="sxs-lookup"><span data-stu-id="6c93b-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="6c93b-155">提供已報告問題的線上及本機檔，並加入疑難排解秘訣</span><span class="sxs-lookup"><span data-stu-id="6c93b-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="6c93b-156">產生可供日後查看的配置資訊</span><span class="sxs-lookup"><span data-stu-id="6c93b-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="6c93b-157">確定 RTCBPA 已安裝在所有 Lync Server 2013 伺服器上，並產生每週健康情況檢查報告。</span><span class="sxs-lookup"><span data-stu-id="6c93b-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="6c93b-158">如有需要，請注意結果並正確無誤。</span><span class="sxs-lookup"><span data-stu-id="6c93b-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="6c93b-159">審查 SLA 效能資料</span><span class="sxs-lookup"><span data-stu-id="6c93b-159">Review SLA performance figures</span></span>

<span data-ttu-id="6c93b-160">檢查上周的重要效能資料。</span><span class="sxs-lookup"><span data-stu-id="6c93b-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="6c93b-161">對照 SLA 的需求來審查效能。</span><span class="sxs-lookup"><span data-stu-id="6c93b-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="6c93b-162">找出尚未滿足目標的趨勢與專案。</span><span class="sxs-lookup"><span data-stu-id="6c93b-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="6c93b-163">審查 System Center Operations Manager 管理套件和經驗品質報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="6c93b-164">取得並查看 Lync Server 2013 管理套件及經驗報表品質報告。</span><span class="sxs-lookup"><span data-stu-id="6c93b-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="6c93b-165">產生及查看企業版池的資料庫報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="6c93b-166">**產生池報告**</span><span class="sxs-lookup"><span data-stu-id="6c93b-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="6c93b-167">開啟 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6c93b-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="6c93b-168">在主控台樹中，展開 [林] 節點，展開 [**企業版池**]，然後按一下您要為其產生資料庫報告的池。</span><span class="sxs-lookup"><span data-stu-id="6c93b-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="6c93b-169">在 [詳細資料] 窗格中，按一下 [**資料庫**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6c93b-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="6c93b-170">在 [**資料庫**] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6c93b-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="6c93b-171">若要查看資料庫名稱，請展開 **[一般設定**]，然後查看資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="6c93b-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="6c93b-172">若要為該資源庫取得目前的使用者摘要統計資料 **，請展開**[**使用者摘要報告**]，按一下 [執行]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="6c93b-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="6c93b-173">若要針對池的單一使用者檢索目前的每個使用者資料，請展開 [**每使用者報告**]，輸入使用者的 SIP URI，**按一下 [** 執行]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="6c93b-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="6c93b-174">若要檢索該池子的目前會議摘要統計資料 **，請展開**[**會議摘要報告**]，按一下 [執行]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="6c93b-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="6c93b-175">針對每個企業版池，管理員可以使用 [**資料庫**] 索引標籤來查看資料庫名稱，並從資料庫中檢索及查看報表。</span><span class="sxs-lookup"><span data-stu-id="6c93b-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="6c93b-176">資料庫報告和描述</span><span class="sxs-lookup"><span data-stu-id="6c93b-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c93b-177">頂部</span><span class="sxs-lookup"><span data-stu-id="6c93b-177">Section</span></span></th>
<th><span data-ttu-id="6c93b-178">描述</span><span class="sxs-lookup"><span data-stu-id="6c93b-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c93b-179">使用者摘要報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="6c93b-180">Dbanalyze/v/report：診斷 [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="6c93b-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="6c93b-181">此區段會顯示有關池中使用者的匯總資訊，例如已啟用的使用者數目、每個使用者的平均聯絡人數，以及特定功能的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="6c93b-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="6c93b-182">使用這些報表時，下列資訊可能會很有説明：</span><span class="sxs-lookup"><span data-stu-id="6c93b-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c93b-183">已啟用的使用者是使用 Active Directory 使用者和電腦管理單元啟用 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="6c93b-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="6c93b-184">[作用中的使用者] 是已登入或已註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="6c93b-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="6c93b-185">摘要報告也提供有關連絡人的一組統計資訊。</span><span class="sxs-lookup"><span data-stu-id="6c93b-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="6c93b-186">這些統計資料只對至少已登入一次且至少有一位連絡人的使用者群體有效。</span><span class="sxs-lookup"><span data-stu-id="6c93b-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="6c93b-187">因此，您通常不會看到最小值為0的連絡人。</span><span class="sxs-lookup"><span data-stu-id="6c93b-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="6c93b-188">由於這種行為，如果使用者沒有連絡人（但在使用者已註冊的情況下是作用中的使用者），您可能會&lt;看到&gt; ：針對某些統計資料欄位為空白。</span><span class="sxs-lookup"><span data-stu-id="6c93b-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c93b-189">每位使用者報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="6c93b-190">Dbanalyze/v/report： disk [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="6c93b-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="6c93b-191">與在使用者群體計算的摘要報表不同，這些是關於特定使用者的報表。</span><span class="sxs-lookup"><span data-stu-id="6c93b-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c93b-192">會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="6c93b-193">Dbanalyze/v/report：會議 [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="6c93b-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="6c93b-194">此區段會顯示有關該泳池之會議摘要統計資料的匯總資訊，例如使用中的會議數量及參與者總數。</span><span class="sxs-lookup"><span data-stu-id="6c93b-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="6c93b-195">運行頻寬利用率分析程式</span><span class="sxs-lookup"><span data-stu-id="6c93b-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="6c93b-196">[頻寬利用率分析] 是一種工具，可在商業網路中，透過廣域網路連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="6c93b-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="6c93b-197">這些報告可用來瞭解目前的頻寬使用量模式，並協助您進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="6c93b-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="6c93b-198">它也會根據指派給各種連結的頻寬容量來反覆運算。</span><span class="sxs-lookup"><span data-stu-id="6c93b-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="6c93b-199">此工具會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6c93b-199">This tool does the following:</span></span>

  - <span data-ttu-id="6c93b-200">針對網路上的音訊使用量產生特定報告</span><span class="sxs-lookup"><span data-stu-id="6c93b-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="6c93b-201">協助更有效的容量規劃，以及在指派給各種連結的頻寬容量上進行反覆運算</span><span class="sxs-lookup"><span data-stu-id="6c93b-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="6c93b-202">[頻寬利用率分析] 可產生頻寬容量與使用方式報告的圖形化圖形。</span><span class="sxs-lookup"><span data-stu-id="6c93b-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="6c93b-203">它們如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c93b-203">They are as follows:</span></span>

  - <span data-ttu-id="6c93b-204">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="6c93b-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="6c93b-205">依選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="6c93b-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="6c93b-206">使用超過連結容量的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="6c93b-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="6c93b-207">使用預配頻寬底下的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="6c93b-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="6c93b-208">依 WAN 連結所達到的 WAN 連結進行篩選（頻寬使用量大於 WAN 連結頻寬容量的90%）</span><span class="sxs-lookup"><span data-stu-id="6c93b-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="6c93b-209">依 WAN 連結類型進行篩選：網路網站連結、interregional 連結，以及網站內的連結</span><span class="sxs-lookup"><span data-stu-id="6c93b-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="6c93b-210">依網路區域篩選</span><span class="sxs-lookup"><span data-stu-id="6c93b-210">Filtered by network region</span></span>

<span data-ttu-id="6c93b-211">在[Lync Server 2013 資源套件工具檔](http://go.microsoft.com/fwlink/?linkid=623245)中提供此工具的檔。</span><span class="sxs-lookup"><span data-stu-id="6c93b-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c93b-212">請參閱</span><span class="sxs-lookup"><span data-stu-id="6c93b-212">See Also</span></span>


[<span data-ttu-id="6c93b-213">每週任務檢查清單</span><span class="sxs-lookup"><span data-stu-id="6c93b-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

