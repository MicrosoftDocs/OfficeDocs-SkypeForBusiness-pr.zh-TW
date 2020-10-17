---
title: Lync Server 2013：每週任務
description: Lync Server 2013：每週工作。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d818e1140141a470bb57a1471bb04931f505a6bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546139"
---
# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="3ac0d-103">Lync Server 2013 中的每週工作</span><span class="sxs-lookup"><span data-stu-id="3ac0d-103">Weekly tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ac0d-104">_**主題上次修改日期：** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="3ac0d-104">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="3ac0d-105">每週工作通常與收集和分析記錄檔及報告相關。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-105">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="3ac0d-106">封存事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="3ac0d-106">Archive event logs</span></span>

<span data-ttu-id="3ac0d-107">如果事件記錄未設定成視需要覆寫事件，則必須定期封存和刪除這些事件。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-107">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="3ac0d-108">此巨集指令對安全性記錄檔尤其重要，在調查企圖的安全性違規時，可能需要此動作。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-108">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="3ac0d-109">您的組織必須定義記錄檔封存的原則與程式。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-109">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="3ac0d-110">建立報表</span><span class="sxs-lookup"><span data-stu-id="3ac0d-110">Create reports</span></span>

<span data-ttu-id="3ac0d-111">建立狀態報表，以協助進行容量規劃、SLA 檢查和效能分析。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-111">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="3ac0d-112">使用事件記錄檔和系統監視器的 [每日資料]，建立磁片、記憶體及 CPU 使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-112">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="3ac0d-113">使用 System Center Operations Manager 來產生時間和可用性報告。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-113">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="3ac0d-114">您的組織將必須定義狀態報表的原則和程式。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-114">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="3ac0d-115">事件報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-115">Incident reports</span></span>

<span data-ttu-id="3ac0d-116">針對與 Lync Server 相關的組織附隨報告執行每週的審計。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-116">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="3ac0d-117">此項審計應包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-117">This audit should include the following:</span></span>

  - <span data-ttu-id="3ac0d-118">最上層產生、解決及擱置的事件。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-118">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="3ac0d-119">未解決事件的解決方案。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-119">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="3ac0d-120">更新報表以包含新的問題票。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-120">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="3ac0d-121">更新用於疑難排解指南的檔存放庫，並在中斷時發佈 mortems。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-121">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="3ac0d-122">因為您組織的事件追蹤系統是獨立于 Lync Server 的選擇，所以無法使用特定的指示或指標。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-122">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="3ac0d-123">請參閱您組織所選擇之系統的檔。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-123">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="3ac0d-124">檢查 IIS 記錄和效能</span><span class="sxs-lookup"><span data-stu-id="3ac0d-124">Check IIS logs and performance</span></span>

<span data-ttu-id="3ac0d-125">每週執行網際網路資訊服務的複查 (IIS) 記錄與效能。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-125">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="3ac0d-126">如需如何監視 IIS 記錄與效能的詳細資訊，請參閱 [Windows Server 2003 Internet Information Services (IIS) 事件記錄概述](https://go.microsoft.com/fwlink/?linkid=36077)。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-126">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="3ac0d-127">評審應包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-127">The review should include the following:</span></span>

  - <span data-ttu-id="3ac0d-128">用於監視 WWW 服務快取的 Web 服務快取計數器。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-128">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="3ac0d-129">Active Server Pages (Asp) 計數器，以監視以 Asp 形式執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-129">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="3ac0d-130">產生資料庫報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-130">Generate database reports</span></span>

<span data-ttu-id="3ac0d-131">**在 SQL 資料庫上產生報表**</span><span class="sxs-lookup"><span data-stu-id="3ac0d-131">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="3ac0d-132">開啟 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-132">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="3ac0d-133">在主控台樹中，依序展開 [樹系] 節點及 [ **企業版**集區]，然後按一下您要產生資料庫報告的集區。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-133">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="3ac0d-134">在詳細資料窗格中，按一下 [ **資料庫** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-134">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="3ac0d-135">在 [ **資料庫** ] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-135">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="3ac0d-136">若要查看資料庫的名稱，請展開 **[一般設定**]，然後查看資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-136">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="3ac0d-137">若要取得集區的目前使用者摘要統計資料，請展開 [ **使用者摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-137">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="3ac0d-138">若要針對集區的單一使用者取得目前的每一使用者資料，請展開 **Per-User 報告**]，輸入使用者的 SIP URI，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-138">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="3ac0d-139">若要取得集區的目前會議摘要統計資料，請展開 [ **會議摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-139">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="3ac0d-140">檢查安全性和 Lync Server 更新</span><span class="sxs-lookup"><span data-stu-id="3ac0d-140">Check for security and Lync Server updates</span></span>

<span data-ttu-id="3ac0d-141">識別任何新的 service pack、修復程式或更新。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-141">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="3ac0d-142">如有適當，請在測試實驗室中進行測試，然後使用變更控制程式安排部署至實際執行伺服器。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-142">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="3ac0d-143">此外，您現在可以使用「Windows 更新」中的 Lync Server 元件更新。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-143">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="3ac0d-144">所有執行更新之 Lync Server 的伺服器上，都必須同時更新所有的 Lync Server 元件更新。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-144">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="3ac0d-145">執行 Lync Server 2013 最佳作法分析程式</span><span class="sxs-lookup"><span data-stu-id="3ac0d-145">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="3ac0d-146">Lync Server 2013 最佳做法分析工具是一種診斷工具，可收集設定資訊，並決定是否要根據 Microsoft 最佳作法設定設定。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-146">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="3ac0d-147">此工具的檔是 [Lync Server 2013 最佳做法分析器](lync-server-2013-lync-server-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-147">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="3ac0d-148">該工具會比較您的部署的設定資料與 Lync Server 的一組預先定義的規則，並報告潛在的問題。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-148">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="3ac0d-149">針對每個報告的問題，此工具會在 Lync Server 環境中提供目前的設定，以及建議的設定。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-149">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="3ac0d-150">透過正確的網路存取，此工具可以檢查您的 AD DS 和執行 Lync Server 2013 的伺服器，以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-150">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="3ac0d-151">主動執行狀況檢查，確認設定是根據建議的最佳作法設定</span><span class="sxs-lookup"><span data-stu-id="3ac0d-151">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="3ac0d-152">產生問題的清單，例如設定最優的設定或不支援的選項或不建議的選項</span><span class="sxs-lookup"><span data-stu-id="3ac0d-152">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="3ac0d-153">判斷系統的一般健康情況</span><span class="sxs-lookup"><span data-stu-id="3ac0d-153">Judge the general health of a system</span></span>

  - <span data-ttu-id="3ac0d-154">協助疑難排解特定問題</span><span class="sxs-lookup"><span data-stu-id="3ac0d-154">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="3ac0d-155">提示您下載更新（若有的話）</span><span class="sxs-lookup"><span data-stu-id="3ac0d-155">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="3ac0d-156">提供有關報告問題的線上和本機檔，並包含疑難排解秘訣</span><span class="sxs-lookup"><span data-stu-id="3ac0d-156">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="3ac0d-157">產生可以捕獲以供日後檢查的設定資訊</span><span class="sxs-lookup"><span data-stu-id="3ac0d-157">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="3ac0d-158">確定所有 Lync Server 2013 伺服器上都安裝了 RTCBPA.msi，並產生每週的健全狀況檢查報告。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-158">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="3ac0d-159">請注意，如有必要，請注意結果和正確。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-159">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="3ac0d-160">查看 SLA 效能資料</span><span class="sxs-lookup"><span data-stu-id="3ac0d-160">Review SLA performance figures</span></span>

<span data-ttu-id="3ac0d-161">檢查前一周的重要效能資料。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-161">Check the key performance data for the previous week.</span></span> <span data-ttu-id="3ac0d-162">對照 SLA 的需求，檢查效能。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-162">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="3ac0d-163">找出未符合目標的趨勢及專案。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-163">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="3ac0d-164">查看 System Center Operations Manager 管理元件和經驗品質報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-164">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="3ac0d-165">取得及審閱 Lync Server 2013 管理元件和經驗品質報告。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-165">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="3ac0d-166">產生及查看企業集區的資料庫報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-166">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="3ac0d-167">**產生集區報告**</span><span class="sxs-lookup"><span data-stu-id="3ac0d-167">**To generate pool reports**</span></span>

1.  <span data-ttu-id="3ac0d-168">開啟 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-168">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="3ac0d-169">在主控台樹中，依序展開 [樹系] 節點及 [ **企業版**集區]，然後按一下您要產生資料庫報告的集區。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-169">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="3ac0d-170">在詳細資料窗格中，按一下 [ **資料庫** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-170">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="3ac0d-171">在 [ **資料庫** ] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-171">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="3ac0d-172">若要查看資料庫的名稱，請展開 **[一般設定**]，然後查看資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-172">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="3ac0d-173">若要取得集區的目前使用者摘要統計資料，請展開 [ **使用者摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-173">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="3ac0d-174">若要針對集區的單一使用者取得目前的每一使用者資料，請展開 **Per-User 報告**]，輸入使用者的 SIP URI，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-174">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="3ac0d-175">若要取得集區的目前會議摘要統計資料，請展開 [ **會議摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-175">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="3ac0d-176">系統管理員可以使用 [ **資料庫** ] 索引標籤來查看資料庫名稱，以及從資料庫中取得及查看報告。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-176">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="3ac0d-177">資料庫報告和描述</span><span class="sxs-lookup"><span data-stu-id="3ac0d-177">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ac0d-178">區段</span><span class="sxs-lookup"><span data-stu-id="3ac0d-178">Section</span></span></th>
<th><span data-ttu-id="3ac0d-179">描述</span><span class="sxs-lookup"><span data-stu-id="3ac0d-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ac0d-180">使用者摘要報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-180">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="3ac0d-181">Dbanalyze.exe/v/report：/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="3ac0d-181">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3ac0d-182">本節顯示集區中使用者的匯總資訊，例如啟用的使用者數目、每位使用者的平均連絡人數目，以及特定功能的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-182">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="3ac0d-183">使用這些報告時，下列資訊可能非常有用：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-183">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ac0d-184">已啟用的使用者是使用 [Active Directory 使用者及電腦] 嵌入式管理單元啟用 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-184">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="3ac0d-185">「作用中的使用者」是指已登入或註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-185">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="3ac0d-186">摘要報告也會提供一組有關連絡人的統計資訊。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-186">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="3ac0d-187">這些統計資料只對至少已登入一次，且至少有一個連絡人的使用者人數有效。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-187">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="3ac0d-188">因此，您通常不會看到最小值為0的連絡人數目。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-188">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="3ac0d-189">由於這種行為，如果使用者沒有任何連絡人 (但使用中，使用者已註冊) 時，您可能會看到 &lt; &gt; 一些統計資料欄位為空白。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-189">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ac0d-190">Per-User 報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-190">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="3ac0d-191">Dbanalyze.exe/v/report： disk [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="3ac0d-191">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3ac0d-192">不像是透過使用者人口計算的摘要報告，這些是有關特定使用者的報表。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-192">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ac0d-193">會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-193">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="3ac0d-194">Dbanalyze.exe/v/report：會議 [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="3ac0d-194">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3ac0d-195">本節顯示有關集區之會議摘要統計資料的匯總資訊，例如使用中會議數目及參與者總數。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-195">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="3ac0d-196">執行頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="3ac0d-196">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3ac0d-197">頻寬流量分析程式是一種工具，它會針對商業網路中 WAN 連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-197">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="3ac0d-198">這些報告可用於瞭解目前的頻寬消耗模式，以及協助您進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-198">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="3ac0d-199">它也會在指派給各種連結的頻寬容量上進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-199">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="3ac0d-200">此工具會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-200">This tool does the following:</span></span>

  - <span data-ttu-id="3ac0d-201">透過網路產生音訊使用方式的特定報告</span><span class="sxs-lookup"><span data-stu-id="3ac0d-201">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="3ac0d-202">協助在指派給各種連結的頻寬容量上進行更有效的容量規劃和反覆運算</span><span class="sxs-lookup"><span data-stu-id="3ac0d-202">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3ac0d-203">頻寬流量分析程式可以產生頻寬容量和使用方式報告的圖形化圖表。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-203">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="3ac0d-204">它們如下：</span><span class="sxs-lookup"><span data-stu-id="3ac0d-204">They are as follows:</span></span>

  - <span data-ttu-id="3ac0d-205">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="3ac0d-205">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="3ac0d-206">由選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="3ac0d-206">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="3ac0d-207">由超過連結容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="3ac0d-207">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="3ac0d-208">依照已布建頻寬的使用中的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="3ac0d-208">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="3ac0d-209">依 WAN 連結的頻寬使用量大於90% 的 wan 連結的頻寬使用量，依 WAN 連結篩選 () </span><span class="sxs-lookup"><span data-stu-id="3ac0d-209">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="3ac0d-210">依 WAN 連結類型篩選：網路網站連結、interregional 連結，以及網站內部的連結</span><span class="sxs-lookup"><span data-stu-id="3ac0d-210">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="3ac0d-211">依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="3ac0d-211">Filtered by network region</span></span>

<span data-ttu-id="3ac0d-212">在 [Lync Server 2013 資源套件工具檔](https://go.microsoft.com/fwlink/?linkid=623245)上提供此工具的檔。</span><span class="sxs-lookup"><span data-stu-id="3ac0d-212">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ac0d-213">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3ac0d-213">See Also</span></span>


[<span data-ttu-id="3ac0d-214">每週任務檢查清單</span><span class="sxs-lookup"><span data-stu-id="3ac0d-214">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

