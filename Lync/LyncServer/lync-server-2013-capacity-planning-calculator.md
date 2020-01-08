---
title: Lync Server 2013 容量規劃計算機
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 385127f1686c2a4fa5beaf33f02d2eec6ba19500
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="b7604-102">使用 Lync Server 2013 的容量規劃計算機</span><span class="sxs-lookup"><span data-stu-id="b7604-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7604-103">_**主題上次修改日期：** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="b7604-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="b7604-104">Microsoft® Lync™ Server 2013 容量規劃計算機可供下載<http://www.microsoft.com/en-us/download/details.aspx?id=36828>。</span><span class="sxs-lookup"><span data-stu-id="b7604-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="b7604-105">它是用來協助您根據貴組織所啟用的使用者和通訊形式來判斷伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="b7604-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="b7604-106">您可以輸入貴組織的設定檔，而計算機會提供建議，協助您規劃拓撲。</span><span class="sxs-lookup"><span data-stu-id="b7604-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="b7604-107">由計算機建立的建議僅供規劃之用。</span><span class="sxs-lookup"><span data-stu-id="b7604-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="b7604-108">需要實際的負載模擬，以確保 Lync Server 2013 具備適當的功能。</span><span class="sxs-lookup"><span data-stu-id="b7604-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="b7604-109">若要在模擬的負載下執行壓力測試，請使用[Lync Server 2013 應力和效能工具](http://go.microsoft.com/fwlink/?linkid=282724)。</span><span class="sxs-lookup"><span data-stu-id="b7604-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="b7604-110">確定您要為使用者啟用的使用者設定檔與形式之後，就可以使用計算機來規劃您所需的伺服器、記憶體和頻寬數目。</span><span class="sxs-lookup"><span data-stu-id="b7604-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="b7604-111">這個版本的計算機不會提供磁片輸入/輸出需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="b7604-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="b7604-112">此計算機會補充[Microsoft Lync server](http://go.microsoft.com/fwlink/?linkid=282725)和[microsoft lync server](lync-server-2013-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="b7604-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="b7604-113">在您查看指南並使用規劃工具建立建議的拓撲之後，請使用計算機。</span><span class="sxs-lookup"><span data-stu-id="b7604-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="b7604-114">如果您有有關特定使用者設定檔的準確、詳細資訊，您可以從計算機中取得最大的益處。</span><span class="sxs-lookup"><span data-stu-id="b7604-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="b7604-115">例如，語音啟用使用者的百分比、每個使用者每小時的平均通話數、通話持續時間，以及會議中併發使用者的百分比，可能會對伺服器需求產生巨大的差異。</span><span class="sxs-lookup"><span data-stu-id="b7604-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="b7604-116">計算機所建立之建議的精確度取決於您所提供資訊的準確性。</span><span class="sxs-lookup"><span data-stu-id="b7604-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="b7604-117">使用 [容量] 計算機</span><span class="sxs-lookup"><span data-stu-id="b7604-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="b7604-118">[計算機] 是 Microsoft Excel®試算表。</span><span class="sxs-lookup"><span data-stu-id="b7604-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="b7604-119">橙色彩色儲存格供您輸入。</span><span class="sxs-lookup"><span data-stu-id="b7604-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="b7604-120">預設值是在一個擁有十二個前端伺服器的池中輸入（80000使用者），但是您可以根據組織的需求變更這些值。</span><span class="sxs-lookup"><span data-stu-id="b7604-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="b7604-121">使用方式模型包含下列各節。</span><span class="sxs-lookup"><span data-stu-id="b7604-121">The usage model contains the following sections.</span></span> <span data-ttu-id="b7604-122">若要計算您的容量需求，請依照下列說明輸入資料：</span><span class="sxs-lookup"><span data-stu-id="b7604-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="b7604-123">**立即訊息和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="b7604-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="b7604-124">在 [使用者數量] 底下，輸入將同時登入的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="b7604-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="b7604-125">這個數位通常是已置備使用者總數的80%。</span><span class="sxs-lookup"><span data-stu-id="b7604-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="b7604-126">在大部分的情況下，會針對您併發的使用者啟用 IM 和目前狀態的100%。</span><span class="sxs-lookup"><span data-stu-id="b7604-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="b7604-127">預設值為80000。</span><span class="sxs-lookup"><span data-stu-id="b7604-127">The default is 80,000.</span></span>

  - <span data-ttu-id="b7604-128">連絡人清單中的連絡人平均數量會指出我們用來驗證您系統需求的連絡人數目。</span><span class="sxs-lookup"><span data-stu-id="b7604-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="b7604-129">這個數位不會改變。</span><span class="sxs-lookup"><span data-stu-id="b7604-129">This number is not changeable.</span></span>

<span data-ttu-id="b7604-130">**企業語音**</span><span class="sxs-lookup"><span data-stu-id="b7604-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="b7604-131">在 [企業語音啟用的使用者] 中，輸入已啟用企業語音的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="b7604-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="b7604-132">預設值為60%。</span><span class="sxs-lookup"><span data-stu-id="b7604-132">The default is 60%.</span></span>

  - <span data-ttu-id="b7604-133">在每個使用者每小時的平均通話數（峰值）中，輸入您預計平均使用者要在高峰期負載期間參與的通話次數。</span><span class="sxs-lookup"><span data-stu-id="b7604-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="b7604-134">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="b7604-134">The default is 4.</span></span>

  - <span data-ttu-id="b7604-135">在使用 [媒體旁路] 的呼叫百分比中，輸入使用者將繞過中繼伺服器的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="b7604-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="b7604-136">預設值為65%。</span><span class="sxs-lookup"><span data-stu-id="b7604-136">The default is 65%.</span></span>

  - <span data-ttu-id="b7604-137">在 UC PSTN 通話中所涉及的語音使用者百分比中，輸入貴組織通話的百分比，即「UC-PSTN 電話」。</span><span class="sxs-lookup"><span data-stu-id="b7604-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="b7604-138">預設值為60%</span><span class="sxs-lookup"><span data-stu-id="b7604-138">The default is 60%</span></span>

  - <span data-ttu-id="b7604-139">在 UC uc 通話中所涉及的語音使用者百分比會顯示已啟用之企業語音的使用者百分比，只適用于 UC UC 通話。</span><span class="sxs-lookup"><span data-stu-id="b7604-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="b7604-140">這個數位是根據您為啟用 UC PSTN 通話的語音使用者百分比所輸入的內容而計算。</span><span class="sxs-lookup"><span data-stu-id="b7604-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="b7604-141">**會議**</span><span class="sxs-lookup"><span data-stu-id="b7604-141">**Conferencing**</span></span>

  - <span data-ttu-id="b7604-142">在並行會議中的使用者百分比中，輸入將同時參與會議的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="b7604-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="b7604-143">預設值為5%。</span><span class="sxs-lookup"><span data-stu-id="b7604-143">The default is 5%.</span></span>

  - <span data-ttu-id="b7604-144">在只有「群組 IM」（無語音）的會議中，鍵入會議將只涉及立即訊息的會議百分比;也就是說，不包含音訊元件。</span><span class="sxs-lookup"><span data-stu-id="b7604-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="b7604-145">預設值為10%</span><span class="sxs-lookup"><span data-stu-id="b7604-145">The default is 10%</span></span>

  - <span data-ttu-id="b7604-146">使用電話撥入式會議的使用者百分比，輸入會議中將使用電話撥入式會議的併發參與者百分比。</span><span class="sxs-lookup"><span data-stu-id="b7604-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="b7604-147">預設值為15%。</span><span class="sxs-lookup"><span data-stu-id="b7604-147">The default is 15%.</span></span>

  - <span data-ttu-id="b7604-148">在使用語音的會議百分比中，輸入將包含音訊元件的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="b7604-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="b7604-149">如果20% 的語音會議也會包含一般影片，請選取 [包含影片（無多重視圖）] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b7604-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="b7604-150">如果20% 的會議也會包含多個觀賞影片，請選取 [包括多重視圖] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b7604-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="b7604-151">如果您的語音會議50% 也會包含應用程式共用，請選取 [包括應用程式共用] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b7604-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="b7604-152">如果20% 的語音會議包含資料上傳（例如 Microsoft PowerPoint®簡報），請選取 [包括 web 會議] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b7604-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="b7604-153">**行動性**</span><span class="sxs-lookup"><span data-stu-id="b7604-153">**Mobility**</span></span>

  - <span data-ttu-id="b7604-154">在啟用行動裝置的使用者百分比中，輸入可使用行動裝置連線至 Lync Server 的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="b7604-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="b7604-155">預設值為40%。</span><span class="sxs-lookup"><span data-stu-id="b7604-155">The default is 40%.</span></span>

<span data-ttu-id="b7604-156">輸入所有必要的資訊後，[容量] 計算機就會估計您的需求。</span><span class="sxs-lookup"><span data-stu-id="b7604-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="b7604-157">黃色的儲存格會根據 Lync Server 2013 效能實驗中執行的測試，顯示 CPU、記憶體和頻寬需求的計算值。</span><span class="sxs-lookup"><span data-stu-id="b7604-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="b7604-158">這些數位是作為指導原則提供的，並非每個單一變化都經過測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="b7604-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="b7604-159">會計算下列值：</span><span class="sxs-lookup"><span data-stu-id="b7604-159">The following values are calculated:</span></span>

  - <span data-ttu-id="b7604-160">前端 CPU： [CPU 使用量] 的百分比（如果整個負載是由與 Microsoft 測試中使用的伺服器相同的規格）所處理。</span><span class="sxs-lookup"><span data-stu-id="b7604-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="b7604-161">網路（Mbps）：頻寬需求，以每秒百萬位元（Mbps）為對應的工作負載。</span><span class="sxs-lookup"><span data-stu-id="b7604-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="b7604-162">GB 記憶體：以千百萬位元組（GB）為對應的工作負荷所需的記憶體。</span><span class="sxs-lookup"><span data-stu-id="b7604-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="b7604-163">綠色的儲存格會顯示您輸入之使用方式模型的建議。</span><span class="sxs-lookup"><span data-stu-id="b7604-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="b7604-164">前端伺服器總計伺服器數：所需的物理伺服器數量是以雙處理器的專用2013伺服器（含雙處理器，十六進位-核心）為基礎，且2260兆周期。</span><span class="sxs-lookup"><span data-stu-id="b7604-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="b7604-165">請注意，建議啟用超執行緒，且已證實可改善支援音訊/視頻之伺服器的效能。</span><span class="sxs-lookup"><span data-stu-id="b7604-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="b7604-166">Edge 伺服器：根據所有並行使用者透過邊緣伺服器進行通訊的30%，所需的邊緣伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="b7604-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="b7604-167">此百分比不能在計算機中變更。</span><span class="sxs-lookup"><span data-stu-id="b7604-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="b7604-168">封存/通話詳細資料記錄/體驗服務商店：如果您的組織已啟用，則封存或監視功能所需的存放區數。</span><span class="sxs-lookup"><span data-stu-id="b7604-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="b7604-169">需要後端資料庫伺服器（需要緩衝集區）：支援所選工作負荷所需的後端資料庫伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="b7604-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="b7604-170">此外，在總前端伺服器旁邊的列中，會提供更多關於您的伺服器和網路上的負載的詳細資訊，讓所有計劃的工作負載結合在一起。</span><span class="sxs-lookup"><span data-stu-id="b7604-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="b7604-171">平均 CPU 負載：每個前端伺服器的平均 CPU 使用量。</span><span class="sxs-lookup"><span data-stu-id="b7604-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="b7604-172">Network （Mbps）：支援您輸入之使用方式模型所需的頻寬配置。</span><span class="sxs-lookup"><span data-stu-id="b7604-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="b7604-173">GB：每個前端伺服器所需的記憶體，以 gb 為限。</span><span class="sxs-lookup"><span data-stu-id="b7604-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="b7604-174">調整您的處理器</span><span class="sxs-lookup"><span data-stu-id="b7604-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="b7604-175">試算表中的所有 CPU 使用量資料都假設每個伺服器都有雙處理器、十六進位與 2.26 GHz、至少 32 GB 的記憶體，以及至少有 72 GB 可用磁碟空間的8個或更多 10000 RPM 硬碟磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b7604-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="b7604-176">如果您的伺服器有不同的處理器，您可以調整這些資料來符合您的硬體。</span><span class="sxs-lookup"><span data-stu-id="b7604-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

