---
title: Lync Server 2013： 檢視及分析監控伺服器報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9970e4c440148cac2002088212a48283c86184eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="7b02d-102">檢視及分析 Lync Server 2013 中的監控伺服器報告</span><span class="sxs-lookup"><span data-stu-id="7b02d-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b02d-103">_**上次修改主題：** 2014年-05-19_</span><span class="sxs-lookup"><span data-stu-id="7b02d-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="7b02d-104">監控伺服器報告提供監視 QoE，即會傳遞至使用者的語音品質的數個不同的量值。</span><span class="sxs-lookup"><span data-stu-id="7b02d-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="7b02d-105">此外，監控伺服器包含幾個內建的報告，您的組織可觀看您的組織網路上的使用情況和媒體品質趨勢和引發的媒體品質問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="7b02d-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="7b02d-106">保持 Monitoring Server Reports 有趣每天與每週作業的主要部分是檢視，且分析媒體品質的報告，特別是：</span><span class="sxs-lookup"><span data-stu-id="7b02d-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="7b02d-107">QoE 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="7b02d-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="7b02d-108">QoE 效能報告</span><span class="sxs-lookup"><span data-stu-id="7b02d-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="7b02d-109">從監控伺服器檢視報告</span><span class="sxs-lookup"><span data-stu-id="7b02d-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="7b02d-110">從 web 瀏覽器中，找出您主控 SQL reporting services 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="7b02d-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="7b02d-111">檢視從瀏覽器] 畫面中所需的報表。</span><span class="sxs-lookup"><span data-stu-id="7b02d-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="7b02d-112">（選用）將報表匯出藉由選取 [匯出] 選項及所需的輸出格式。</span><span class="sxs-lookup"><span data-stu-id="7b02d-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="7b02d-113">設定詳細通話記錄 (CDR)</span><span class="sxs-lookup"><span data-stu-id="7b02d-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="7b02d-114">從使用者帳戶是 RTCUniversalServerAdmins 群組成員 （或具有相等權限），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入是在您部署了 Lync Server 2013 網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7b02d-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7b02d-115">開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="7b02d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7b02d-116">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="7b02d-117">在 [**詳細通話記錄**] 頁面上，按一下表格中的適當網站按一下 [**編輯**]，然後按一下 [**顯示詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="7b02d-118">若要開啟清除，請選取 [**啟用清除的監控伺服器**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="7b02d-119">在 [**保留通話詳細資料錄製最大持續期限 （天）：** 選取應該保留詳細通話最大天數。</span><span class="sxs-lookup"><span data-stu-id="7b02d-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="7b02d-120">在 [**將錯誤報告資料保留最大持續期限 （天）：** 選取錯誤報告應保留天數上限。</span><span class="sxs-lookup"><span data-stu-id="7b02d-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="7b02d-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="7b02d-122">需要設定 QoE</span><span class="sxs-lookup"><span data-stu-id="7b02d-122">Configure QoE</span></span>

1.  <span data-ttu-id="7b02d-123">以 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="7b02d-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7b02d-124">如需詳細資訊，請參閱＜Delegate Setup Permissions＞。</span><span class="sxs-lookup"><span data-stu-id="7b02d-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="7b02d-125">開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="7b02d-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7b02d-126">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="7b02d-127">在 [**經驗品質資料**] 頁面上，按一下表格中的適當網站按一下 [**編輯**]，然後按一下 [**顯示詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="7b02d-128">若要開啟清除，請選取 [**啟用清除的監控伺服器**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="7b02d-129">在 [**保留通話詳細資料錄製最大持續期限 （天）：** 選取應該保留 QoE 資料最大天數。</span><span class="sxs-lookup"><span data-stu-id="7b02d-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="7b02d-130">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="7b02d-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="7b02d-131">若要變更封存原則</span><span class="sxs-lookup"><span data-stu-id="7b02d-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="7b02d-132">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7b02d-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b02d-133">開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="7b02d-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7b02d-134">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="7b02d-135">按一下原則清單中的 **[全域]**，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7b02d-136">在 **[編輯封存原則 - 全域]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7b02d-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="7b02d-137">若要啟用或停用內部封存的部署，請選取或清除 [**封存內部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7b02d-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="7b02d-138">若要啟用或停用 [部署的外部封存，請選取或清除 [**封存外部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7b02d-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="7b02d-139">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="7b02d-140">封存原則套用至使用者</span><span class="sxs-lookup"><span data-stu-id="7b02d-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="7b02d-141">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7b02d-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b02d-142">開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="7b02d-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7b02d-143">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7b02d-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="7b02d-144">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7b02d-145">在 [**編輯 Lync Server 使用者**] [**封存原則**] 下，選取您想要套用的封存使用者原則。</span><span class="sxs-lookup"><span data-stu-id="7b02d-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="7b02d-146">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="7b02d-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7b02d-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b02d-147">See Also</span></span>


[<span data-ttu-id="7b02d-148">Lync Server 2013 中使用監控報告</span><span class="sxs-lookup"><span data-stu-id="7b02d-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="7b02d-149">Lync Server 2013 中的伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="7b02d-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="7b02d-150">Lync Server 2013 中的媒體品質比較報告</span><span class="sxs-lookup"><span data-stu-id="7b02d-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

