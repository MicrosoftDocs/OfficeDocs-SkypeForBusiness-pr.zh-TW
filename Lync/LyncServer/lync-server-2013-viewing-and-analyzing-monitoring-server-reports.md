---
title: Lync Server 2013：查看和分析監控伺服器報告
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
ms.openlocfilehash: 7416b54e7b1ddb5bfc41c07502802c7c120a93ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523570"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="b4564-102">在 Lync Server 2013 中查看及分析監控伺服器報告</span><span class="sxs-lookup"><span data-stu-id="b4564-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4564-103">_**主題上次修改日期：** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="b4564-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="b4564-104">監控伺服器報告提供數種不同的語音品質度量，以監視傳遞給使用者的 QoE。</span><span class="sxs-lookup"><span data-stu-id="b4564-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="b4564-105">此外，監控伺服器也包含數個內建報告，您的組織可以用來監視組織網路的流量和媒體質量趨勢，並疑難排解所引發的媒體質量問題。</span><span class="sxs-lookup"><span data-stu-id="b4564-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="b4564-106">使監控伺服器報告成為每日和每週作業的主要工作是查看和分析媒體質量報告，具體如下：</span><span class="sxs-lookup"><span data-stu-id="b4564-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="b4564-107">QoE 摘要/趨勢報表</span><span class="sxs-lookup"><span data-stu-id="b4564-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="b4564-108">QoE 效能報告</span><span class="sxs-lookup"><span data-stu-id="b4564-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="b4564-109">從監控伺服器查看報告</span><span class="sxs-lookup"><span data-stu-id="b4564-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="b4564-110">從網頁瀏覽器中，找出主控 SQL reporting services 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b4564-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="b4564-111">從瀏覽器畫面查看必要的報表。</span><span class="sxs-lookup"><span data-stu-id="b4564-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="b4564-112"> (選用) 請選取 [匯出] 選項及必要的輸出格式，以匯出報告。</span><span class="sxs-lookup"><span data-stu-id="b4564-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="b4564-113">設定 (CDR) 的詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="b4564-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="b4564-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或具有對等許可權) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b4564-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b4564-115">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b4564-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b4564-116">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="b4564-117">在 [ **詳細通話記錄** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="b4564-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="b4564-118">若要開啟清除，請選取 [ **啟用監視伺服器的清除**]。</span><span class="sxs-lookup"><span data-stu-id="b4564-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="b4564-119">在 [ **保留詳細通話記錄 (天數) ：** ] 中，選取應該保留詳細通話記錄的最大天數。</span><span class="sxs-lookup"><span data-stu-id="b4564-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="b4564-120">在 [ **將錯誤報表的最大持續時間 (天數]) 中：** 選取應該保留錯誤報表的最大天數。</span><span class="sxs-lookup"><span data-stu-id="b4564-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="b4564-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="b4564-122">設定 QoE</span><span class="sxs-lookup"><span data-stu-id="b4564-122">Configure QoE</span></span>

1.  <span data-ttu-id="b4564-123">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="b4564-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b4564-124">如需詳細資訊，請參閱＜Delegate Setup Permissions＞。</span><span class="sxs-lookup"><span data-stu-id="b4564-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="b4564-125">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b4564-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b4564-126">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="b4564-127">在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="b4564-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="b4564-128">若要開啟清除，請選取 [ **啟用監視伺服器的清除**]。</span><span class="sxs-lookup"><span data-stu-id="b4564-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="b4564-129">在 [ **保留詳細通話記錄的最大持續時間 (天數) ：** ] 中，選取應該保留 QoE 資料的最大天數。</span><span class="sxs-lookup"><span data-stu-id="b4564-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="b4564-130">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="b4564-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="b4564-131">變更封存原則</span><span class="sxs-lookup"><span data-stu-id="b4564-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="b4564-132">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b4564-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b4564-133">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b4564-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b4564-134">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="b4564-135">按一下原則清單中的 **[全域]**，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b4564-136">在 **[編輯封存原則 - 全域]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b4564-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="b4564-137">若要啟用或停用部署的內部封存，請選取或清除 [封存 **內部通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b4564-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="b4564-138">若要啟用或停用部署的外部封存，請選取或清除 [封存 **外部通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b4564-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="b4564-139">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="b4564-140">將封存原則套用至使用者</span><span class="sxs-lookup"><span data-stu-id="b4564-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="b4564-141">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b4564-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b4564-142">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b4564-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b4564-143">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b4564-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="b4564-144">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b4564-145">在 [封存**原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的封存使用者原則。</span><span class="sxs-lookup"><span data-stu-id="b4564-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="b4564-146">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b4564-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4564-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b4564-147">See Also</span></span>


[<span data-ttu-id="b4564-148">在 Lync Server 2013 中使用監控報告</span><span class="sxs-lookup"><span data-stu-id="b4564-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="b4564-149">Lync Server 2013 中的伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="b4564-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="b4564-150">Lync Server 2013 中的媒體質量比較報告</span><span class="sxs-lookup"><span data-stu-id="b4564-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

