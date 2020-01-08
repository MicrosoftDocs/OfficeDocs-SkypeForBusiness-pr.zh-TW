---
title: Lync Server 2013：查看及分析監視伺服器報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="b19e7-102">在 Lync Server 2013 中查看及分析監視伺服器報告</span><span class="sxs-lookup"><span data-stu-id="b19e7-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b19e7-103">_**主題上次修改日期：** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="b19e7-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="b19e7-104">[監視伺服器] 報告提供數種不同的語音品質測量，以監控傳送給最終使用者的 QoE。</span><span class="sxs-lookup"><span data-stu-id="b19e7-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="b19e7-105">此外，監視伺服器還包含數個內建的報表，您的組織可以用來在組織的網路上觀看使用方式及媒體質量趨勢，並針對發生的媒體質量問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="b19e7-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="b19e7-106">讓監視伺服器報告對日常及每週操作感興趣的主要部分，就是查看並分析媒體質量報告，特別是：</span><span class="sxs-lookup"><span data-stu-id="b19e7-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="b19e7-107">QoE 摘要/趨勢報表</span><span class="sxs-lookup"><span data-stu-id="b19e7-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="b19e7-108">QoE 效能報告</span><span class="sxs-lookup"><span data-stu-id="b19e7-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="b19e7-109">從監控伺服器查看報表</span><span class="sxs-lookup"><span data-stu-id="b19e7-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="b19e7-110">從網頁瀏覽器，找出託管 SQL reporting services 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b19e7-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="b19e7-111">從瀏覽器畫面查看所需的報告。</span><span class="sxs-lookup"><span data-stu-id="b19e7-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="b19e7-112">可選選取 [匯出] 選項和 [所需的輸出格式]，匯出報表。</span><span class="sxs-lookup"><span data-stu-id="b19e7-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="b19e7-113">設定通話詳細資料錄製（CDR）</span><span class="sxs-lookup"><span data-stu-id="b19e7-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="b19e7-114">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等許可權），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b19e7-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b19e7-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b19e7-116">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="b19e7-117">在 [**通話詳細資料記錄**] 頁面上，按一下表格中的適當網站，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="b19e7-118">若要開啟清除，請選取 [**啟用監視伺服器的清除**]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="b19e7-119">在 **[保持通話詳細資料錄製的最大持續時間（天）** ] 中：選取應保留通話詳細資料錄製的最大天數。</span><span class="sxs-lookup"><span data-stu-id="b19e7-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="b19e7-120">若要在**最大持續時間（天）內保留錯誤報表資料：** 請選取要保留錯誤報表的最大天數。</span><span class="sxs-lookup"><span data-stu-id="b19e7-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="b19e7-121">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b19e7-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="b19e7-122">設定 QoE</span><span class="sxs-lookup"><span data-stu-id="b19e7-122">Configure QoE</span></span>

1.  <span data-ttu-id="b19e7-123">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="b19e7-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b19e7-124">如需詳細資訊，請參閱委派設定許可權。</span><span class="sxs-lookup"><span data-stu-id="b19e7-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="b19e7-125">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b19e7-126">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="b19e7-127">在 [**體驗品質資料**] 頁面上，從表格中按一下適當的網站，按一下 [**編輯**]，然後按一下 [**顯示詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="b19e7-128">若要開啟清除，請選取 [**啟用監視伺服器的清除**]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="b19e7-129">在 **[保持通話詳細資料記錄的最大持續時間（天）** ] 中：選取 QoE 資料應保留的最大天數。</span><span class="sxs-lookup"><span data-stu-id="b19e7-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="b19e7-130">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="b19e7-131">變更存檔原則</span><span class="sxs-lookup"><span data-stu-id="b19e7-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="b19e7-132">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b19e7-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b19e7-133">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b19e7-134">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="b19e7-135">按一下原則清單中的 [全域]\*\*\*\*，按一下 [編輯]\*\*\*\*，然後按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b19e7-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b19e7-136">在 [**編輯封存原則-全域**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b19e7-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="b19e7-137">若要啟用或停用部署的內部存檔，請選取或清除 [封存**內部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b19e7-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="b19e7-138">若要啟用或停用部署的外部存檔，請選取或清除 [封存**外部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b19e7-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="b19e7-139">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b19e7-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="b19e7-140">將存檔原則套用至使用者</span><span class="sxs-lookup"><span data-stu-id="b19e7-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="b19e7-141">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b19e7-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b19e7-142">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b19e7-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b19e7-143">在左導覽列中，按一下 [使用者]\*\*\*\*，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b19e7-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="b19e7-144">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b19e7-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b19e7-145">在 [**存檔原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的存檔使用者原則。</span><span class="sxs-lookup"><span data-stu-id="b19e7-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="b19e7-146">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b19e7-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b19e7-147">請參閱</span><span class="sxs-lookup"><span data-stu-id="b19e7-147">See Also</span></span>


[<span data-ttu-id="b19e7-148">在 Lync Server 2013 中使用監視報告</span><span class="sxs-lookup"><span data-stu-id="b19e7-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="b19e7-149">Lync Server 2013 中的伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="b19e7-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="b19e7-150">Lync Server 2013 中的媒體質量比較報告</span><span class="sxs-lookup"><span data-stu-id="b19e7-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

