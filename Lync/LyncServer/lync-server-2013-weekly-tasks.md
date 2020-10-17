---
title: Lync Server 2013：每週任務
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
ms.openlocfilehash: d8177cf0a647ec5155a32a91c6e764e9c13e1dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518220"
---
# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="62b10-102">Lync Server 2013 中的每週工作</span><span class="sxs-lookup"><span data-stu-id="62b10-102">Weekly tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62b10-103">_**主題上次修改日期：** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="62b10-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="62b10-104">每週工作通常與收集和分析記錄檔及報告相關。</span><span class="sxs-lookup"><span data-stu-id="62b10-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="62b10-105">封存事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="62b10-105">Archive event logs</span></span>

<span data-ttu-id="62b10-106">如果事件記錄未設定成視需要覆寫事件，則必須定期封存和刪除這些事件。</span><span class="sxs-lookup"><span data-stu-id="62b10-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="62b10-107">此巨集指令對安全性記錄檔尤其重要，在調查企圖的安全性違規時，可能需要此動作。</span><span class="sxs-lookup"><span data-stu-id="62b10-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="62b10-108">您的組織必須定義記錄檔封存的原則與程式。</span><span class="sxs-lookup"><span data-stu-id="62b10-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="62b10-109">建立報表</span><span class="sxs-lookup"><span data-stu-id="62b10-109">Create reports</span></span>

<span data-ttu-id="62b10-110">建立狀態報表，以協助進行容量規劃、SLA 檢查和效能分析。</span><span class="sxs-lookup"><span data-stu-id="62b10-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="62b10-111">使用事件記錄檔和系統監視器的 [每日資料]，建立磁片、記憶體及 CPU 使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="62b10-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="62b10-112">使用 System Center Operations Manager 來產生時間和可用性報告。</span><span class="sxs-lookup"><span data-stu-id="62b10-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="62b10-113">您的組織將必須定義狀態報表的原則和程式。</span><span class="sxs-lookup"><span data-stu-id="62b10-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="62b10-114">事件報告</span><span class="sxs-lookup"><span data-stu-id="62b10-114">Incident reports</span></span>

<span data-ttu-id="62b10-115">針對與 Lync Server 相關的組織附隨報告執行每週的審計。</span><span class="sxs-lookup"><span data-stu-id="62b10-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="62b10-116">此項審計應包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="62b10-116">This audit should include the following:</span></span>

  - <span data-ttu-id="62b10-117">最上層產生、解決及擱置的事件。</span><span class="sxs-lookup"><span data-stu-id="62b10-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="62b10-118">未解決事件的解決方案。</span><span class="sxs-lookup"><span data-stu-id="62b10-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="62b10-119">更新報表以包含新的問題票。</span><span class="sxs-lookup"><span data-stu-id="62b10-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="62b10-120">更新用於疑難排解指南的檔存放庫，並在中斷時發佈 mortems。</span><span class="sxs-lookup"><span data-stu-id="62b10-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="62b10-121">因為您組織的事件追蹤系統是獨立于 Lync Server 的選擇，所以無法使用特定的指示或指標。</span><span class="sxs-lookup"><span data-stu-id="62b10-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="62b10-122">請參閱您組織所選擇之系統的檔。</span><span class="sxs-lookup"><span data-stu-id="62b10-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="62b10-123">檢查 IIS 記錄和效能</span><span class="sxs-lookup"><span data-stu-id="62b10-123">Check IIS logs and performance</span></span>

<span data-ttu-id="62b10-124">每週執行網際網路資訊服務的複查 (IIS) 記錄與效能。</span><span class="sxs-lookup"><span data-stu-id="62b10-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="62b10-125">如需如何監視 IIS 記錄與效能的詳細資訊，請參閱 [Windows Server 2003 Internet Information Services (IIS) 事件記錄概述](https://go.microsoft.com/fwlink/?linkid=36077)。</span><span class="sxs-lookup"><span data-stu-id="62b10-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="62b10-126">評審應包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="62b10-126">The review should include the following:</span></span>

  - <span data-ttu-id="62b10-127">用於監視 WWW 服務快取的 Web 服務快取計數器。</span><span class="sxs-lookup"><span data-stu-id="62b10-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="62b10-128">Active Server Pages (Asp) 計數器，以監視以 Asp 形式執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="62b10-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="62b10-129">產生資料庫報告</span><span class="sxs-lookup"><span data-stu-id="62b10-129">Generate database reports</span></span>

<span data-ttu-id="62b10-130">**在 SQL 資料庫上產生報表**</span><span class="sxs-lookup"><span data-stu-id="62b10-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="62b10-131">開啟 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="62b10-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="62b10-132">在主控台樹中，依序展開 [樹系] 節點及 [ **企業版**集區]，然後按一下您要產生資料庫報告的集區。</span><span class="sxs-lookup"><span data-stu-id="62b10-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="62b10-133">在詳細資料窗格中，按一下 [ **資料庫** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="62b10-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="62b10-134">在 [ **資料庫** ] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="62b10-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="62b10-135">若要查看資料庫的名稱，請展開 **[一般設定**]，然後查看資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="62b10-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="62b10-136">若要取得集區的目前使用者摘要統計資料，請展開 [ **使用者摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="62b10-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="62b10-137">若要針對集區的單一使用者取得目前的每一使用者資料，請展開 **Per-User 報告**]，輸入使用者的 SIP URI，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="62b10-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="62b10-138">若要取得集區的目前會議摘要統計資料，請展開 [ **會議摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="62b10-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="62b10-139">檢查安全性和 Lync Server 更新</span><span class="sxs-lookup"><span data-stu-id="62b10-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="62b10-140">識別任何新的 service pack、修復程式或更新。</span><span class="sxs-lookup"><span data-stu-id="62b10-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="62b10-141">如有適當，請在測試實驗室中進行測試，然後使用變更控制程式安排部署至實際執行伺服器。</span><span class="sxs-lookup"><span data-stu-id="62b10-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="62b10-142">此外，您現在可以使用「Windows 更新」中的 Lync Server 元件更新。</span><span class="sxs-lookup"><span data-stu-id="62b10-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="62b10-143">所有執行更新之 Lync Server 的伺服器上，都必須同時更新所有的 Lync Server 元件更新。</span><span class="sxs-lookup"><span data-stu-id="62b10-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="62b10-144">執行 Lync Server 2013 最佳作法分析程式</span><span class="sxs-lookup"><span data-stu-id="62b10-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="62b10-145">Lync Server 2013 最佳做法分析工具是一種診斷工具，可收集設定資訊，並決定是否要根據 Microsoft 最佳作法設定設定。</span><span class="sxs-lookup"><span data-stu-id="62b10-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="62b10-146">此工具的檔是 [Lync Server 2013 最佳做法分析器](lync-server-2013-lync-server-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="62b10-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="62b10-147">該工具會比較您的部署的設定資料與 Lync Server 的一組預先定義的規則，並報告潛在的問題。</span><span class="sxs-lookup"><span data-stu-id="62b10-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="62b10-148">針對每個報告的問題，此工具會在 Lync Server 環境中提供目前的設定，以及建議的設定。</span><span class="sxs-lookup"><span data-stu-id="62b10-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="62b10-149">透過正確的網路存取，此工具可以檢查您的 AD DS 和執行 Lync Server 2013 的伺服器，以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="62b10-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="62b10-150">主動執行狀況檢查，確認設定是根據建議的最佳作法設定</span><span class="sxs-lookup"><span data-stu-id="62b10-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="62b10-151">產生問題的清單，例如設定最優的設定或不支援的選項或不建議的選項</span><span class="sxs-lookup"><span data-stu-id="62b10-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="62b10-152">判斷系統的一般健康情況</span><span class="sxs-lookup"><span data-stu-id="62b10-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="62b10-153">協助疑難排解特定問題</span><span class="sxs-lookup"><span data-stu-id="62b10-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="62b10-154">提示您下載更新（若有的話）</span><span class="sxs-lookup"><span data-stu-id="62b10-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="62b10-155">提供有關報告問題的線上和本機檔，並包含疑難排解秘訣</span><span class="sxs-lookup"><span data-stu-id="62b10-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="62b10-156">產生可以捕獲以供日後檢查的設定資訊</span><span class="sxs-lookup"><span data-stu-id="62b10-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="62b10-157">確定所有 Lync Server 2013 伺服器上都安裝了 RTCBPA.msi，並產生每週的健全狀況檢查報告。</span><span class="sxs-lookup"><span data-stu-id="62b10-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="62b10-158">請注意，如有必要，請注意結果和正確。</span><span class="sxs-lookup"><span data-stu-id="62b10-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="62b10-159">查看 SLA 效能資料</span><span class="sxs-lookup"><span data-stu-id="62b10-159">Review SLA performance figures</span></span>

<span data-ttu-id="62b10-160">檢查前一周的重要效能資料。</span><span class="sxs-lookup"><span data-stu-id="62b10-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="62b10-161">對照 SLA 的需求，檢查效能。</span><span class="sxs-lookup"><span data-stu-id="62b10-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="62b10-162">找出未符合目標的趨勢及專案。</span><span class="sxs-lookup"><span data-stu-id="62b10-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="62b10-163">查看 System Center Operations Manager 管理元件和經驗品質報告</span><span class="sxs-lookup"><span data-stu-id="62b10-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="62b10-164">取得及審閱 Lync Server 2013 管理元件和經驗品質報告。</span><span class="sxs-lookup"><span data-stu-id="62b10-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="62b10-165">產生及查看企業集區的資料庫報告</span><span class="sxs-lookup"><span data-stu-id="62b10-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="62b10-166">**產生集區報告**</span><span class="sxs-lookup"><span data-stu-id="62b10-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="62b10-167">開啟 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="62b10-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="62b10-168">在主控台樹中，依序展開 [樹系] 節點及 [ **企業版**集區]，然後按一下您要產生資料庫報告的集區。</span><span class="sxs-lookup"><span data-stu-id="62b10-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="62b10-169">在詳細資料窗格中，按一下 [ **資料庫** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="62b10-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="62b10-170">在 [ **資料庫** ] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="62b10-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="62b10-171">若要查看資料庫的名稱，請展開 **[一般設定**]，然後查看資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="62b10-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="62b10-172">若要取得集區的目前使用者摘要統計資料，請展開 [ **使用者摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="62b10-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="62b10-173">若要針對集區的單一使用者取得目前的每一使用者資料，請展開 **Per-User 報告**]，輸入使用者的 SIP URI，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="62b10-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="62b10-174">若要取得集區的目前會議摘要統計資料，請展開 [ **會議摘要報告**]，按一下 [ **前往**]，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="62b10-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="62b10-175">系統管理員可以使用 [ **資料庫** ] 索引標籤來查看資料庫名稱，以及從資料庫中取得及查看報告。</span><span class="sxs-lookup"><span data-stu-id="62b10-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="62b10-176">資料庫報告和描述</span><span class="sxs-lookup"><span data-stu-id="62b10-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62b10-177">區段</span><span class="sxs-lookup"><span data-stu-id="62b10-177">Section</span></span></th>
<th><span data-ttu-id="62b10-178">描述</span><span class="sxs-lookup"><span data-stu-id="62b10-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62b10-179">使用者摘要報告</span><span class="sxs-lookup"><span data-stu-id="62b10-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="62b10-180">Dbanalyze.exe/v/report：/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="62b10-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="62b10-181">本節顯示集區中使用者的匯總資訊，例如啟用的使用者數目、每位使用者的平均連絡人數目，以及特定功能的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="62b10-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="62b10-182">使用這些報告時，下列資訊可能非常有用：</span><span class="sxs-lookup"><span data-stu-id="62b10-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="62b10-183">已啟用的使用者是使用 [Active Directory 使用者及電腦] 嵌入式管理單元啟用 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="62b10-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="62b10-184">「作用中的使用者」是指已登入或註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="62b10-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="62b10-185">摘要報告也會提供一組有關連絡人的統計資訊。</span><span class="sxs-lookup"><span data-stu-id="62b10-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="62b10-186">這些統計資料只對至少已登入一次，且至少有一個連絡人的使用者人數有效。</span><span class="sxs-lookup"><span data-stu-id="62b10-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="62b10-187">因此，您通常不會看到最小值為0的連絡人數目。</span><span class="sxs-lookup"><span data-stu-id="62b10-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="62b10-188">由於這種行為，如果使用者沒有任何連絡人 (但使用中，使用者已註冊) 時，您可能會看到 &lt; &gt; 一些統計資料欄位為空白。</span><span class="sxs-lookup"><span data-stu-id="62b10-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62b10-189">Per-User 報告</span><span class="sxs-lookup"><span data-stu-id="62b10-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="62b10-190">Dbanalyze.exe/v/report： disk [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="62b10-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="62b10-191">不像是透過使用者人口計算的摘要報告，這些是有關特定使用者的報表。</span><span class="sxs-lookup"><span data-stu-id="62b10-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62b10-192">會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="62b10-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="62b10-193">Dbanalyze.exe/v/report：會議 [/sqlserver： value]</span><span class="sxs-lookup"><span data-stu-id="62b10-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="62b10-194">本節顯示有關集區之會議摘要統計資料的匯總資訊，例如使用中會議數目及參與者總數。</span><span class="sxs-lookup"><span data-stu-id="62b10-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="62b10-195">執行頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="62b10-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="62b10-196">頻寬流量分析程式是一種工具，它會針對商業網路中 WAN 連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="62b10-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="62b10-197">這些報告可用於瞭解目前的頻寬消耗模式，以及協助您進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="62b10-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="62b10-198">它也會在指派給各種連結的頻寬容量上進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="62b10-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="62b10-199">此工具會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="62b10-199">This tool does the following:</span></span>

  - <span data-ttu-id="62b10-200">透過網路產生音訊使用方式的特定報告</span><span class="sxs-lookup"><span data-stu-id="62b10-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="62b10-201">協助在指派給各種連結的頻寬容量上進行更有效的容量規劃和反覆運算</span><span class="sxs-lookup"><span data-stu-id="62b10-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="62b10-202">頻寬流量分析程式可以產生頻寬容量和使用方式報告的圖形化圖表。</span><span class="sxs-lookup"><span data-stu-id="62b10-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="62b10-203">它們如下：</span><span class="sxs-lookup"><span data-stu-id="62b10-203">They are as follows:</span></span>

  - <span data-ttu-id="62b10-204">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="62b10-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="62b10-205">由選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="62b10-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="62b10-206">由超過連結容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="62b10-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="62b10-207">依照已布建頻寬的使用中的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="62b10-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="62b10-208">依 WAN 連結的頻寬使用量大於90% 的 wan 連結的頻寬使用量，依 WAN 連結篩選 () </span><span class="sxs-lookup"><span data-stu-id="62b10-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="62b10-209">依 WAN 連結類型篩選：網路網站連結、interregional 連結，以及網站內部的連結</span><span class="sxs-lookup"><span data-stu-id="62b10-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="62b10-210">依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="62b10-210">Filtered by network region</span></span>

<span data-ttu-id="62b10-211">在 [Lync Server 2013 資源套件工具檔](https://go.microsoft.com/fwlink/?linkid=623245)上提供此工具的檔。</span><span class="sxs-lookup"><span data-stu-id="62b10-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62b10-212">另請參閱</span><span class="sxs-lookup"><span data-stu-id="62b10-212">See Also</span></span>


[<span data-ttu-id="62b10-213">每週任務檢查清單</span><span class="sxs-lookup"><span data-stu-id="62b10-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

