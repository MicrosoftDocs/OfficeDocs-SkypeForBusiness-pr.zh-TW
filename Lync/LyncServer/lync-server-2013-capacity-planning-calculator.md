---
title: Lync Server 2013 容量規劃計算機
description: Lync Server 2013 容量規劃計算機。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f78019c98cf280f38249ac52cd063cede5319af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565139"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="3587b-103">使用 Lync Server 2013 的容量規劃計算機</span><span class="sxs-lookup"><span data-stu-id="3587b-103">Using the capacity planning calculator for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3587b-104">_**主題上次修改日期：** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="3587b-104">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="3587b-105">Microsoft® Lync™ Server 2013 容量規劃計算機可于下載 <https://www.microsoft.com/download/details.aspx?id=36828> 。</span><span class="sxs-lookup"><span data-stu-id="3587b-105">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="3587b-106">其設計目的是為了協助您根據組織中啟用的使用者數目和通訊形式來判斷伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="3587b-106">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="3587b-107">您可以輸入組織的設定檔，而計算機會提供建議，以協助您規劃拓撲。</span><span class="sxs-lookup"><span data-stu-id="3587b-107">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="3587b-108">計算機所建立的建議只用于規劃目的。</span><span class="sxs-lookup"><span data-stu-id="3587b-108">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="3587b-109">需要實際的負載模擬，以確保已適當布建 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3587b-109">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="3587b-110">若要在模擬負載下執行壓力測試，請使用 [Lync Server 2013 壓力和效能工具](https://go.microsoft.com/fwlink/?linkid=282724)。</span><span class="sxs-lookup"><span data-stu-id="3587b-110">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="3587b-111">在您決定要為使用者啟用的使用者設定檔和形式之後，就可以使用計算機來規劃所需的伺服器、記憶體及頻寬數目。</span><span class="sxs-lookup"><span data-stu-id="3587b-111">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="3587b-112">此版本的計算機不會提供磁片 I/O 需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="3587b-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="3587b-113">此計算機會對 [Microsoft Lync server](https://go.microsoft.com/fwlink/?linkid=282725) 和 [microsoft lync server](lync-server-2013-planning.md)進行補充。</span><span class="sxs-lookup"><span data-stu-id="3587b-113">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="3587b-114">在您複習指南並使用規劃工具建立建議的拓撲之後，使用計算機。</span><span class="sxs-lookup"><span data-stu-id="3587b-114">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="3587b-115">如果您有特定使用者設定檔的確切詳細資訊，您可以從計算機獲得最大益處。</span><span class="sxs-lookup"><span data-stu-id="3587b-115">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="3587b-116">例如，啟用語音功能的使用者數目、每位使用者每小時平均通話量、通話持續時間，以及會議中並行使用者的百分比，都可能會對伺服器的需求造成極大的影響。</span><span class="sxs-lookup"><span data-stu-id="3587b-116">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="3587b-117">計算機所建立之建議的準確性取決於您提供的資訊準確性。</span><span class="sxs-lookup"><span data-stu-id="3587b-117">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="3587b-118">使用容量計算機</span><span class="sxs-lookup"><span data-stu-id="3587b-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="3587b-119">計算機是 Microsoft Excel®試算表。</span><span class="sxs-lookup"><span data-stu-id="3587b-119">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="3587b-120">橙色-彩色儲存格供您輸入。</span><span class="sxs-lookup"><span data-stu-id="3587b-120">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="3587b-121">預設值是在具有十二部前端伺服器的一個集區中輸入 (80000 使用者) ，但是您可以根據組織的需求變更這些值。</span><span class="sxs-lookup"><span data-stu-id="3587b-121">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="3587b-122">使用模型包含下列章節。</span><span class="sxs-lookup"><span data-stu-id="3587b-122">The usage model contains the following sections.</span></span> <span data-ttu-id="3587b-123">若要計算您的容量需求，請輸入資料，如下所述：</span><span class="sxs-lookup"><span data-stu-id="3587b-123">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="3587b-124">**立即訊息與顯示狀態**</span><span class="sxs-lookup"><span data-stu-id="3587b-124">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="3587b-125">在 [使用者數目] 底下，輸入將同時登入的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="3587b-125">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="3587b-126">此數位通常是布建使用者總數的80%。</span><span class="sxs-lookup"><span data-stu-id="3587b-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="3587b-127">在大多數情況下，會為您的並行使用者啟用100% 的 IM 和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="3587b-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="3587b-128">預設值為80000。</span><span class="sxs-lookup"><span data-stu-id="3587b-128">The default is 80,000.</span></span>

  - <span data-ttu-id="3587b-129">連絡人清單中的連絡人數目平均會指出我們所用的連絡人數目，以驗證您的系統需求。</span><span class="sxs-lookup"><span data-stu-id="3587b-129">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="3587b-130">此數位不會改變。</span><span class="sxs-lookup"><span data-stu-id="3587b-130">This number is not changeable.</span></span>

<span data-ttu-id="3587b-131">**企業語音**</span><span class="sxs-lookup"><span data-stu-id="3587b-131">**Enterprise Voice**</span></span>

  - <span data-ttu-id="3587b-132">在 [已啟用企業語音的使用者] 中，輸入已啟用 Enterprise Voice 的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="3587b-132">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="3587b-133">預設值為60%。</span><span class="sxs-lookup"><span data-stu-id="3587b-133">The default is 60%.</span></span>

  - <span data-ttu-id="3587b-134">在 [每位使用者每小時平均通話數目] (峰值) 中，輸入您預期平均使用者在高峰時負載的期間內每小時所要加入的通話數目。</span><span class="sxs-lookup"><span data-stu-id="3587b-134">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="3587b-135">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="3587b-135">The default is 4.</span></span>

  - <span data-ttu-id="3587b-136">在使用媒體旁路的通話百分比中，輸入您的使用者所撥打的呼叫百分比，將會略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="3587b-136">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="3587b-137">預設值為65%。</span><span class="sxs-lookup"><span data-stu-id="3587b-137">The default is 65%.</span></span>

  - <span data-ttu-id="3587b-138">在 UC-PSTN 通話的語音使用者百分比中，輸入您組織通話的百分比 UC-PSTN 電話。</span><span class="sxs-lookup"><span data-stu-id="3587b-138">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="3587b-139">預設值為60%</span><span class="sxs-lookup"><span data-stu-id="3587b-139">The default is 60%</span></span>

  - <span data-ttu-id="3587b-140">在 UC-UC 通話的語音使用者百分比中，會顯示已啟用 Enterprise Voice 之使用者的百分比，只適用于 UC-UC 通話。</span><span class="sxs-lookup"><span data-stu-id="3587b-140">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="3587b-141">這個數位是根據您為 UC-PSTN 通話啟用之語音使用者百分比所輸入的專案而計算。</span><span class="sxs-lookup"><span data-stu-id="3587b-141">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="3587b-142">**會議**</span><span class="sxs-lookup"><span data-stu-id="3587b-142">**Conferencing**</span></span>

  - <span data-ttu-id="3587b-143">在 [同時會議的使用者百分比] 中，輸入將同時參與會議的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="3587b-143">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="3587b-144">預設值為5%。</span><span class="sxs-lookup"><span data-stu-id="3587b-144">The default is 5%.</span></span>

  - <span data-ttu-id="3587b-145">在 [僅限群組 IM 的會議百分比 (無語音) ] 中，輸入其會議只會涉及立即訊息的會議百分比;也就是說，不包含音訊元件。</span><span class="sxs-lookup"><span data-stu-id="3587b-145">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="3587b-146">預設值為10%</span><span class="sxs-lookup"><span data-stu-id="3587b-146">The default is 10%</span></span>

  - <span data-ttu-id="3587b-147">在使用電話撥入式會議的使用者百分比中，輸入要使用電話撥入式會議的會議中，同時參與者所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="3587b-147">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="3587b-148">預設值為15%。</span><span class="sxs-lookup"><span data-stu-id="3587b-148">The default is 15%.</span></span>

  - <span data-ttu-id="3587b-149">在 [使用語音的會議百分比] 中，輸入要包含音訊元件的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="3587b-149">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="3587b-150">如果20% 的語音會議也會包含一般影片，請選取 [包含影片 (沒有多重查看) ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3587b-150">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="3587b-151">如果20% 的會議也會包含多個 View 影片，請選取 [包含多重查看] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3587b-151">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="3587b-152">如果50% 的語音會議也會包含應用程式共用，請選取 [包括應用程式共用] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3587b-152">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="3587b-153">如果20% 的語音會議包含資料上傳，例如 Microsoft PowerPoint®簡報，請選取 [包含 web 會議] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3587b-153">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="3587b-154">**行動性**</span><span class="sxs-lookup"><span data-stu-id="3587b-154">**Mobility**</span></span>

  - <span data-ttu-id="3587b-155">在 [啟用行動的使用者百分比] 中，輸入使用行動裝置啟用以連線至 Lync Server 之使用者的百分比。</span><span class="sxs-lookup"><span data-stu-id="3587b-155">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="3587b-156">預設值為40%。</span><span class="sxs-lookup"><span data-stu-id="3587b-156">The default is 40%.</span></span>

<span data-ttu-id="3587b-157">當您輸入所有必要資訊之後，容量計算機會估計您的需求。</span><span class="sxs-lookup"><span data-stu-id="3587b-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="3587b-158">黃色儲存格會根據 Lync Server 2013 效能實驗室中所執行的測試，顯示 CPU、記憶體及頻寬需求的計算值。</span><span class="sxs-lookup"><span data-stu-id="3587b-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="3587b-159">這些數位是以指導方針提供，並非每個單一變化都會經過測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="3587b-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="3587b-160">計算下列值：</span><span class="sxs-lookup"><span data-stu-id="3587b-160">The following values are calculated:</span></span>

  - <span data-ttu-id="3587b-161">前端 CPU：如果整個負載都是由一個前端伺服器處理，而不是與 Microsoft 測試中所用伺服器的規格相同，則為 CPU 使用量的百分比。</span><span class="sxs-lookup"><span data-stu-id="3587b-161">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="3587b-162">網路（以 Mbps 為單位）：相對於工作負載 (Mbps) 的頻寬需求（以 mb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="3587b-162">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="3587b-163">記憶體單位為 GB：在對應工作量的 gb (GB) 中需要的記憶體。</span><span class="sxs-lookup"><span data-stu-id="3587b-163">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="3587b-164">綠色儲存格會顯示您輸入的使用模式建議。</span><span class="sxs-lookup"><span data-stu-id="3587b-164">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="3587b-165">前端伺服器總數：所需的物理伺服器數目是以執行 Lync Server 2013 的專用伺服器為基礎，具有雙處理器，hex 核心，含2260兆周期。</span><span class="sxs-lookup"><span data-stu-id="3587b-165">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="3587b-166">請注意，建議啟用超執行緒，並已驗證，以提升支援音訊/視頻之伺服器的效能。</span><span class="sxs-lookup"><span data-stu-id="3587b-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="3587b-167">Edge Server：所需的 Edge Server 數目，取決於所有同時使用者透過 Edge Server 進行通訊的使用者的30%。</span><span class="sxs-lookup"><span data-stu-id="3587b-167">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="3587b-168">計算機中無法變更此百分比。</span><span class="sxs-lookup"><span data-stu-id="3587b-168">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="3587b-169">封存/通話詳細資料記錄/經驗品質服務存放區：封存或監控功能所需的儲存區數目（如果在您的組織中已啟用）。</span><span class="sxs-lookup"><span data-stu-id="3587b-169">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="3587b-170">需要 (集區所需的後端資料庫伺服器) ：支援所選工作負載所需的後端資料庫伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="3587b-170">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="3587b-171">此外，在前端伺服器總數的最後一列中，會提供更多關於伺服器和網路上的負載的資訊，以結合所有計劃的工作負載。</span><span class="sxs-lookup"><span data-stu-id="3587b-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="3587b-172">平均 CPU 負載：每個前端伺服器的平均 CPU 使用量。</span><span class="sxs-lookup"><span data-stu-id="3587b-172">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="3587b-173">網路（以 Mbps 為單位）：支援您輸入的使用模式所需的頻寬配置。</span><span class="sxs-lookup"><span data-stu-id="3587b-173">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="3587b-174">記憶體單位為 GB：每一部前端伺服器所需的記憶體（gb）。</span><span class="sxs-lookup"><span data-stu-id="3587b-174">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="3587b-175">調整您的處理器</span><span class="sxs-lookup"><span data-stu-id="3587b-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="3587b-176">試算表中的所有 CPU 使用量圖假設每一部伺服器都有雙處理器、hex 核心和 2.26 GHz，至少 32 GB 的記憶體，以及8個或更多的 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="3587b-176">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="3587b-177">如果您的伺服器具有不同的處理器，您可以調整這些圖形，使其符合您的硬體。</span><span class="sxs-lookup"><span data-stu-id="3587b-177">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

